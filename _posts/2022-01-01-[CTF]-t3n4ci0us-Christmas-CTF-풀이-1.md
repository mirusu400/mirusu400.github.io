---
title: t3n4ci0us Christmas CTF 풀이-1
author:
  name: mirusu400
  link: https://github.com/mirusu400
date: 2022-01-01 15:10:00 +0800
categories: [CTF]
tags: [CTF]
render_with_liquid: false
---


# ANNOUNCEMENT Writeup

## Sanity Check

![](/img/2022-01-01/2021-12-25-14-00-10.png)

![](/img/2022-01-01/2021-12-25-14-00-27.png)

> Christmas{WelC0m3_T0_Chr1sT_MaS_CTF}

## Discord

![](/img/2022-01-01/2021-12-25-14-02-09.png)

![](/img/2022-01-01/2021-12-25-14-02-26.png)

> Christmas{maKe_Su6e_t0_6eAd_Th3_Ru1es!!}


## gift from santa

![](/img/2022-01-01/2021-12-25-15-16-27.png)

![](/img/2022-01-01/2021-12-25-15-17-15.png)

FindinFiles 를 통해 Flag를 쉽게 찾을수 있다.

> Christmas{Congratulations_You_got_a_flag_}


## Feedback

![](/img/2022-01-01/2021-12-25-22-26-25.png)


![](/img/2022-01-01/2021-12-25-22-26-51.png)

네이버 폼을 다 채우면 플래그가 나온다.

> Christmas{Merry_Chrsitmas}


# FORENSIC writeup

## santa home?

![](/img/2022-01-01/2021-12-25-13-53-01.png)

왠지 모르게 각 문자열 들 간의 간격이 일정한 거 같아서 적당히 게싱해 소스코드를 짯다.

규칙은
1. 대문자는 대문자로, 소문자는 소문자로 출력
2. 특수문자는 그대로 출력


```python
payload = "Mlpswrweq{Rijv0_JMbilcma!!}"
# answer1 = "Christmas{Hell0_FOrensic!!}"
start = 10
for j in payload:
    if j in "{}_0":
        print(j, end="")
        continue
    print(chr(ord(j) - start), end="")
    start -= 6
    if start < -4:
        start = 10
```

![](/img/2022-01-01/2021-12-25-13-53-53.png)

실제론 답이 이렇게 나왔는데 제출하니 틀려서 게싱으로 이빨나간 문자들 몇개 수정해서 제출했더니 맞았다.

> Christmas{Hell0_FOrensic!!}


## Corrupted

![](/img/2022-01-01/2021-12-25-18-52-08.png)


![](/img/2022-01-01/2021-12-25-18-51-54.png)

딱봐도 PNG파일인데 헤더가 손상되어있다.
파일시그니처 `89 50 4E 47 0D 0A 1A 0A`를 `0x00` 영역부터 채워주고 다시 켠다.

![](/img/2022-01-01/2021-12-25-18-52-32.png)

플래그 획득!

> Christmas{itisflag}



# WEB Writeup

## injured rudolph

![](/img/2022-01-01/2021-12-25-15-18-29.png)

사이트가 맨처음에 None 뜨는걸봐서 딱봐도 Python+Flask 라고 생각했다.

![](/img/2022-01-01/2021-12-25-15-19-00.png)

Page Source에 Request 방법 적시됨을 확인. SSTI 시도.

```
https://christmas-web1.herokuapp.com/?santa={{config.items()}}
```

![](/img/2022-01-01/2021-12-25-15-19-41.png)

간단히 플래그가 나왔다.

> Christmas{Rudolfu_G0_H0spital}

## Rabbit Hole

![](/img/2022-01-01/2021-12-25-17-20-01.png)


![](/img/2022-01-01/2021-12-25-17-20-31.png)

사이트를 들어가보니 이런식으로 Go [하위주소] 로 나타나있어서 쭉쭉 따라가는 문제인듯 하다.
requests로 자동화 프로그램을 짰다.

```python
import requests
start = "https://rabbit.t3n4ci0us-noah.repl.co/"
while True:
    r = requests.get(start)
    
    result = r.text.split("<h1>")[1].split("</h1>")[0].split(" ")[1]
    start = "https://rabbit.t3n4ci0us-noah.repl.co/" + result
    print(f"Go {start}")
```

![](/img/2022-01-01/2021-12-25-17-21-13.png)

![](/img/2022-01-01/2021-12-25-17-21-35.png)

> Christmas{What_1sS_1t!!}

