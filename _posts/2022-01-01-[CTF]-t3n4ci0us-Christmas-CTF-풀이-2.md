---
title: t3n4ci0us Christmas CTF 풀이-2
author:
  name: mirusu400
  link: https://github.com/mirusu400
date: 2022-01-01 16:10:00 +0800
categories: [CTF]
tags: [CTF]
render_with_liquid: false
---

# CRYPTO Writeup

## PassW0rd

![](/img/2022-01-01/2021-12-25-14-02-58.png)

```
Vm0wd2QyUXlVWGxXYTFwUFZsZFNjRlZ0TVZOWFJsbDNXa2M1VjJKR2JETlhhMUpUVmpGYWMySkVUbGhoTVVwVVZqQmFTMlJIVmtsaVJtaG9UV3N3ZUZadGNFZFRNbEpJVm10c2FWSnRhRzlVVmxaM1ZsWmFkR05GZEZSTlZUVkpWbTEwYTJGV1NYZFhiRkpYWWxob2VsUlVSbXRXTVhCRlZXeFNUbUY2UlRGV2EyUXdZekpHUjFOdVRtcFNiV2hvVm1wT1UyRkdWWGhYYlVacVlrWmFlVnBGV2xOVWJGcFZWbXhzVjFaNlFYaFdSRVpyVTBaT2NscEhjRlJTVlhCWlZrWldZV1F4VWtkWGJHUllZbFZhY1ZSV1pEQk9iR3hXVjJ4T1ZXSkdjREZWVjNCWFZqRkplbUZHYUZkaGExcG9WVEJhVDJOdFJrZFhiV3hUWVROQ2RsWnRNWGRVTVZWNVVtdGthVk5GV2xSWmJHaFRWMFpTVjFkdFJteFdia0pIVmpJeE1GWlhTbFpYVkVwWFlsaENhRlpxU2tabFZsSlpZVVphYUdFeGNHaFhiRnBoVkRKT2MyTkZhR3BTYXpWeldXeG9iMWRHV25STlNHUnNVbXhXTTFSc2FFOWhiRXBYVjJ4U1dtSkhhRlJaTVZwVFZqRmtkVnBGTlZOaWEwcElWbXBLTkdFeVJrZFhiazVxVTBoQ1lWUlZXbUZrYkZweFVtdDBVMkpIVWpCWlZWcDNWakZLVjJOSE9WaGhNVnBvVmtSS1QyUkdUbkphUmxKcFZqTm9WVlpHWTNoaU1sSnpWMjVTVGxkSFVsWlVWM1J6VGxaV2RHUkhkRmhTTUhCNVZqSjRVMWR0U2tkWGJXaFhUVVp3VkZacVJuZFNNVkowWlVkc1UwMHhSalpXYlRFMFZURlplRmRZWkU1WFJYQnhWV3hrTkdGR1ZYZGhSVTVUVW14c00xWXlNVWRWTWtwR1RsUkNXbFpXY0ROV2FrWkxWakpPU0U5V1pGZFNWWEJ2Vm10U1MxUXlVa2RVYmtwaFVteEtjRlpxVG05V2JGcFlaVVprYTAxWFVraFdNalZUVkd4YVIxTnRPVlZXYkhCWVZHdGFXbVZYVWtoa1JtUnBWbGhDU2xkV1ZtOVVNVnAwVTJ4c1ZWZEhhRmhVVlZwM1pXeHJlV1ZIZEd0V2JrSkpXbFZrYzFVeVNuSlRhM1JYWVRGd2FGWnFTa1psVmtweVdrWm9hV0V6UW5oV1Z6QXhVVEZaZUZkdVVrNVdlbXh5V1d0YWQyVkdWblJOVldSV1RXdHdTVlpYY0VkV01ERjFZVVJPV2xaWFVrZGFWV1JQVWpKR1IyRkhiRk5pU0VKMlZqRmFVMU14VVhoWFdHaHFVbGQ0Vmxsc1ZtRldSbEpZVGxjNWEySkdjRWhXVjNSUFZrVXhjbUpFVWxkTlYyaDZXV3RhU21Wc1ZuVlViSEJwVW01Q2IxWlhjRWRWTVZwMFVtdG9VRlp0VWs5WlZFWmFUVlphYzFwRVVsWk5WbXcxVld4b2MxWnNXa1pUYkdoWFlXczFkbGxWV21GalZrcHpXa1pvVjJKclNrbFdWbVEwV1ZaWmVGTnJXbE5XUlZVNQ==
```

뒤에 == 를 봐서 딱봐도 Base64로 암호화됨을 알수있다.
플래그가 나올때까지 계속 디코딩 해주면 끝.
```python
import base64
payload = "(길이상 생략)"

# Base64 decode
payload = payload.encode()
while True:
    try:
        payload = base64.b64decode(payload)
    except:
        break
    print(payload)
```
![](/img/2022-01-01/2021-12-25-14-05-35.png)

> Christmas{PAs3_w0rD_1s_SanTA_VeRY_Go0D_Fr1Ends}

## Cal1 Santa

![](/img/2022-01-01/2021-12-25-14-06-02.png)

```
43 68 72 69 73 74 6d 61 73 7b 53 61 6e 54 61 5f 50 31 65 61 32 65 5f 50 31 63 6b 5f 75 50 5f 74 68 33 5f 70 48 6f 6e 33 7d
```

![](/img/2022-01-01/2021-12-25-14-06-27.png)

Hex to String

> Christmas{SanTa_P1ea2e_P1ck_uP_th3_pHon3}

## What are you doing?

![](/img/2022-01-01/2021-12-25-14-06-52.png)

```
01000011 01101000 01110010 01101001 01110011 01110100 01101101 01100001 01110011 01111011 01010111 01101000 01100001 01010100 01011111 01100001 01110010 00110011 01011111 01111001 00110000 01110101 01011111 01100100 01101111 00110001 01101110 01100111 01011111 00111111 01111101 
```

![](/img/2022-01-01/2021-12-25-14-07-21.png)

Binary to String

> Christmas{WhaT_ar3_y0u_do1ng_?}



## Cl0th3s

![](/img/2022-01-01/2021-12-25-13-46-23.png)

```
cipher txt : V}g|faxtfnB#Ta2&JBgz[rJb$a]Jl%`gJVy%a}&f*h

Key : 010101
```

![](/img/2022-01-01/2021-12-25-13-47-51.png)

단일 Key로 된 XOR 암호화

> Christmas{W6At'3_WroNg_w1tH_y0ur_Cl0th3s?}


## santa village

![](/img/2022-01-01/2021-12-25-14-08-28.png)

딱 봐도 인코딩된 URL

![](/img/2022-01-01/2021-12-25-14-08-54.png)

Decode 반복했더니 유튜브 URL이 나온다

![](/img/2022-01-01/2021-12-25-14-09-35.png)

20초 부근에 플래그가 뜬다
(정확한 플래그는 기억이 안납니다 ㅠㅠ)

> Christmas{66° 33' 07"}


## Di3c0uNt3

![](/img/2022-01-01/2021-12-25-14-10-26.png)

```
MzAgMzEgMzAgMzEgMzAgMzAgMzAgMzEgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzEgMzAgMjAgMzAgMzEgMzEgMzAgMzEgMzAgMzAgMzAgMjAgMzAgMzEgMzEgMzEgMzEgMzAgMzAgMzEgMjAgMzAgMzEgMzEgMzAgMzAgMzAgMzAgMzEgMjAgMzAgMzEgMzAgMzEgMzEgMzAgMzAgMzAgMjAgMzAgMzEgMzAgMzAgMzEgMzEgMzEgMzAgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzAgMzAgMjAgMzAgMzEgMzEgMzAgMzAgMzAgMzEgMzAgMjAgMzAgMzEgMzAgMzEgMzAgMzEgMzEgMzEgMjAgMzAgMzEgMzAgMzAgMzAgMzEgMzEgMzAgMjAgMzAgMzEgMzEgMzEgMzEgMzAgMzEgMzAgMjAgMzAgMzEgMzEgMzAgMzAgMzEgMzAgMzEgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzAgMzAgMjAgMzAgMzEgMzAgMzEgMzAgMzAgMzEgMzAgMjAgMzAgMzEgMzEgMzEgMzAgMzAgMzAgMzAgMjAgMzAgMzEgMzAgMzAgMzEgMzEgMzAgMzEgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzEgMzAgMjAgMzAgMzEgMzAgMzAgMzEgMzEgMzAgMzEgMjAgMzAgMzEgMzEgMzEgMzAgMzEgMzEgMzEgMjAgMzAgMzEgMzEgMzAgMzAgMzEgMzAgMzAgMjAgMzAgMzEgMzAgMzEgMzAgMzEgMzAgMzEgMjAgMzAgMzAgMzEgMzEgMzAgMzEgMzAgMzEgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzAgMzAgMjAgMzAgMzEgMzAgMzAgMzEgMzEgMzAgMzEgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzAgMzEgMjAgMzAgMzAgMzEgMzEgMzEgMzAgMzAgMzEgMjAgMzAgMzEgMzAgMzAgMzAgMzAgMzEgMzAgMjAgMzAgMzEgMzEgMzAgMzAgMzAgMzEgMzEgMjAgMzAgMzEgMzEgMzAgMzEgMzAgMzEgMzAgMjAgMzAgMzEgMzAgMzAgMzEgMzEgMzEgMzAgMjAgMzAgMzEgMzEgMzAgMzAgMzEgMzEgMzAgMjAgMzAgMzEgMzAgMzEgMzAgMzAgMzAgMzEgMjAgMzAgMzEgMzAgMzEgMzAgMzEgMzEgMzEgMjAgMzAgMzEgMzEgMzEgMzEgMzAgMzAgMzAgMjAgMzAgMzEgMzAgMzEgMzEgMzAgMzAgMzAgMjAgMzAgMzEgMzAgMzEgMzEgMzAgMzAgMzEgMjAgMzAgMzEgMzAgMzEgMzEgMzAgMzAgMzAgMjAgMzAgMzEgMzEgMzAgMzEgMzAgMzEgMzEgMjAgMzAgMzEgMzEgMzEgMzEgMzAgMzEgMzAgMjAgMzAgMzEgMzAgMzEgMzEgMzAgMzAgMzAgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzAgMzAgMjAgMzAgMzEgMzEgMzAgMzAgMzAgMzEgMzEgMjAgMzAgMzEgMzEgMzEgMzAgMzEgMzEgMzEgMjAgMzAgMzEgMzEgMzAgMzAgMzAgMzEgMzAgMjAgMzAgMzAgMzEgMzEgMzAgMzAgMzEgMzAgMjAgMzAgMzEgMzAgMzEgMzAgMzAgMzEgMzAgMjAgMzAgMzAgMzEgMzEgMzEgMzAgMzAgMzE=
```

![](/img/2022-01-01/2021-12-25-14-11-32.png)

Base64 Decode -> Hex to str -> Binary to str -> Base64 Decode 하면 플래그 획득

> Christmas{Di3c0uNt3_Ar3_AlWay3_G0od}


## l1cense_plate

![](/img/2022-01-01/2021-12-25-14-12-16.png)

```
Xsirhgnzh{o1XvmHV_k1ZGv_ZAN9590}
```

`Christmas{` 형식인데 ri하고 ir이 바뀐것을 확인, 치환 암호임을 확인했다.
적당히 DB짜서 굴리고 게싱해서 솔브


```python
payload = "Xsirhgnzh{o1XvmHV_k1ZGv_ZAN9590}"
# answer1 = "Christmas{l1CenSE_p1ATe_AZM9590}"
solver = [
    ["x", "c"], ["s", "h"], ["i", 'r'], ['h', 's'], ['g', 't'],
    ['m', 'n'], ['z', 'a'], ['o', 'l'], ['v', 'e'], ['k', 'p']
]

def solve(char):
    char1 = char.lower()
    if ord(char1) >= 0x61 and ord(char1) <= 0x7A:
        for item in solver:
            if item[0] == char1:
                return item[1]
            elif item[1] == char1:
                return item[0]
    else:
        return char
    return "?"

for j in payload:
    print(solve(j), end="")
```

![](/img/2022-01-01/2021-12-25-14-15-14.png)

대소문자는 원본 payload 보고 맞췄다.

> Christmas{l1CenSE_p1ATe_AZM9590}

## G1FT
![](/img/2022-01-01/2021-12-25-16-05-58.png)

마찬가지로 `Christmas{` 플래그 시작 부분과 비교했을 때 두 차이의 절대값이 47임을 확인하고 소스코드를 짯다.
```python
payload = "r9C:DE>2DL`EVa0E9b0q6bE04wC`DE>pD08`uE02}50`EVDN"
answers = "Christmas{"
solver = []
for i in range(len(answers)):
    solver.append([answers[i], payload[i]])

for i in range(len(solver)):
    print(abs(ord(solver[i][0]) - ord(solver[i][1])))

for j in payload:
    out = 0
    if j == "L": out = "{"
    elif j == "N": out = "}"
    elif ord(j)+47 >= ord('A') and ord(j)+47 <= ord('z'): out = (chr(ord(j)+47))
    else: out = (chr(ord(j)-47))
    print(out, end="")
```
![](/img/2022-01-01/2021-12-25-16-06-40.png)

> Christmas{1t'2_th3_Be3t_cHr1stmAs_g1Ft_aNd_1t's}

## Pa3sp0rt

![](/img/2022-01-01/2021-12-25-15-48-28.png)

[RsaCtfTool](https://github.com/Ganapati/RsaCtfTool) 을 이용해 풀었다.

```
python3 RsaCtfTool.py -n 15418152892607352670726779453104492159030823601102923034887223619599420214365854362547222415232578972321402313365345456611125976119576376028173874636648164525025217815074934755005703994343699279425620518986613084415826219659636762426998085583889268036141848389564061029937847824954259914625563761807325252396800215568344747654733200871951437148543964901558483985352632105578535797462422615402989941799788668870511295281937619419517694470516639111334457574519662593713149139190698436341088773892709083650646454760846045979331703637002946149686156399404797375920722741630669366715487262832057855782192888781534106494517 -e 65537 -p 130783778303010010110492164476991939047910854853219547762631527862056465880703917794384668821885058841319228346234324546822304903987646138003862070025543937556271789218692909468449392252066173363930460229624215836261330682144434384055842615553160051062905455668080350239746220766182392285792704472339032205921 -q 117890407301778506217222406532644946292179579868701560342212789813915501759366350648868156661193294566367426411876005862929164989446500938803139548797759131121293649415291291733630361453936793791636335108652914819173491912852021621501665214411605719598187288970046947402626143768707326215929062138383216366677 --uncipher 13273391952920458943509137299532401854555882021411009525396691663790028388846905869392714575571518621211649914662336276814433688977793743560828354429096970890300677056418379588286085644837633867547577880701020602837610285710580403578750977516628605086982281716390227362113966035625031885787496545390380593064916717354451104714050829234006269097298606441993548442155185029550949631530259100552019161736827582814987904654795312867454180251044607521429139311956183748509908447898279202145113702058720629181148772279091956696873618983350918352419053598549791029235941380073809329257421142692819812828055098954344378802676
```


![](/img/2022-01-01/2021-12-25-15-48-47.png)

> Christmas{D1d_y0u_f1nD_y0ur_Pa3sp0rt?}


## Ripped Pieces

![](/img/2022-01-01/2021-12-25-17-23-24.png)

Passport 문제와 비슷했지만 이번엔 Base64로 암호화 되어있었다.
복호화를 하고 RsaCtfTool 을 돌렸다.

```
python3 RsaCtfTool.py -e 23 -p 126863417777880944077073657022563073741153701628371623876838535713988050984071779167353165495756198127631595107921337764425055960974957981779220838612644011426570917378116874784915561284722749253042579989043260019288501118789748376495820092775186850169899276785715350500071151074802954933003331973870591938659 -q 174703590431654017161614884278142153611688164283619254706795281737693165233852575854328809687338165524430657514746464716290253556608276847507210761458204445634172752685323727680003618829976432932334663780561976892795585766278855100437521357398583196962332908521793728947028881877625700589893345594199922838179 --uncipher 15337995067927154271326877909442865328414639563582230190106358523851336011142632482200522471577715318935164661474094734002899821181293563798974852048459631556081946856569342965892601396168051896620984763836924331385222727595111390036076502736279300437231206848184476528239547963040380203471360828595227632029834173432648717248908400197405380553202424835141489753368000367147959725752403111832090010745838844981812968338139094763767045301943399320464758101949992301892565955501324053532148456240888941827215201839923925820655945579517230627706787471044513191653029074041712367021735274234836650178258481059601792049062
```

![](/img/2022-01-01/2021-12-25-17-24-29.png)

> Christmas{1t'3_t0Rn_whAt_sHoUld_1_d0?}


## SanTa_Vil1Ain

![](/img/2022-01-01/2021-12-25-19-42-05.png)

![](/img/2022-01-01/2021-12-25-19-42-18.png)

주어진 텍스트는 탭과 스페이스바, 개행문자로 이루어진 텍스트다.

* 스페이스바 -> 0 치환
* 탭 문자 -> 1 치환

![](/img/2022-01-01/2021-12-25-19-43-34.png)

이런식으로 되는데 한줄에 1글자, 10글자 12글자 이므로 앞의 4글자 제거하고 읽어보면

![](/img/2022-01-01/2021-12-25-19-44-16.png)

플래그가 나온다.

> Christmas{sAnTai3_a_VillA1n?}


## Th3 Th1EvEs

![](/img/2022-01-01/2021-12-25-19-46-04.png)

주어진 텍스트는 [S스페이스바], [T탭], [L개행문자] 로 되어있다

* S스페이스바 -> 0 치환
* T탭 -> 1 치환
* L글자 -> 제거

![](/img/2022-01-01/2021-12-25-19-47-06.png)

이런식으로 되는데 한줄에 1글자, 10글자 12글자 이므로 앞의 4글자 제거하고 읽어보면

![](/img/2022-01-01/2021-12-25-19-47-32.png)

플래그가 나온다.

> Chrismtas{whY_ar3_y0u_3teAliNg_Th1ngS_1ik3_th1s?}


# 05 MISC Writeup

## r3al_GiFT

![](/img/2022-01-01/2021-12-25-13-42-49.png)

png 파일 같지만 실제로는 그냥 raw파일이다.

![](/img/2022-01-01/2021-12-25-13-43-33.png)

Hex viewer로 열면 끝.

> Chrsitmas{It_1S_ReaL_g1FT?_0r_Fak3_GifT?}

## r3al SanTa

![](/img/2022-01-01/2021-12-25-13-44-02.png)

![](/img/2022-01-01/2021-12-25-13-44-32.png)

이미지를 Hex viewer로 보면 맨 하단에 의심스러운게 있다.

![](/img/2022-01-01/2021-12-25-13-45-00.png)

문자열을 다시 Hex로 변환하면 끝.

> Christmas{Wh0's_Th3_r3al_SanTa?}


## Wak3 UP
![](/img/2022-01-01/2021-12-25-09-57-11.png)

![](/img/2022-01-01/2021-12-25-09-56-49.png)

웹이 있고 안에 console.log로 엄청난 양의 flag를 찍어내는 것이 있다.

![](/img/2022-01-01/2021-12-25-09-57-36.png)

실제론 동일한 flag를 반복해서 찍어내길래 (한 플래그개 몇백개씩 출력됐다)
하나하나씩 다 찍어보며 다른건 일괄적으로 제거함으로써 남은 플래그를 찾았다.

> Christmas{m1SC_0r_html}


## Addr3ss b00k

![](/img/2022-01-01/2021-12-25-13-50-24.png)

![](/img/2022-01-01/2021-12-25-13-50-12.png)

Hex 에디터로 까니 적당한 곳에 플래그가 있다.

> Christmas{whErE's_th3_Addr3ss_b00k?}

## Santa's whereabouts

![](/img/2022-01-01/2021-12-25-13-51-21.png)

![](/img/2022-01-01/2021-12-25-13-51-51.png)

웹사이트 소스코드 js파일에 플래그가 있다.

> Christmas{djtjdhkjsanswpsmscdmadlwl}


## De1iv3Ry sTar7ed

![](/img/2022-01-01/2021-12-25-13-41-36.png)

SECRET 파일은 실제로는 까보면 Png 파일이다.

![](/img/2022-01-01/2021-12-25-13-37-58.png)

포토샵으로 열고 적당히 페인트통 검은색을 부어보면 QR코드가 나온다

![](/img/2022-01-01/2021-12-25-13-38-59.png)

QR코드 리더로 읽으면 끝

> Christmas{iT's_t1m3_t0_g1v3_0ut_Pr3s3nts}

## Christmas Site

![](/img/2022-01-01/2021-12-25-15-38-15.png)

그냥 지문 그대로 따라하면 되고, 정답인 사이트는
> https://santatracker.google.com/intl/ko/
였다.

> Christmas{https://santatracker.google.com/intl/ko/}

## CulpRit is Santa

![](/img/2022-01-01/2021-12-25-17-22-07.png)

해당 주소는 Github 에서 제공하는 주소이므로, 원본 레포를 찾을 수 있다.

https://github.com/CYB3R-Syno/cyb3r-syno.github.io

커밋 히스토리를 찾으니 플래그가 있었다.

![](/img/2022-01-01/2021-12-25-17-22-51.png)

> Christmas{Th3_cUlpRit_1s_Santa}

## Santa Ma1l

![](/img/2022-01-01/2021-12-25-17-26-06.png)

https://api.protonmail.ch/pks/lookup?op=index&search=
여기서 메일 룩업을 할수있다.

https://api.protonmail.ch/pks/lookup?op=index&search=Yenjamin@protonmail.com

![](/img/2022-01-01/2021-12-25-17-27-16.png)

![](/img/2022-01-01/2021-12-25-17-27-32.png)

> Christmas{2021_11_14}

## Who is Santa? + rudolph math 1

![](/img/2022-01-01/2021-12-25-18-55-12.png)

```
1. 산타 == 부모님 == Parents
2. (9*8) % 2 == 2
```

> Christmas{Parents+2}

## Who is Santa? + rudolph math 2

![](/img/2022-01-01/2021-12-25-20-17-16.png)

```
1. 산타 == 산타
2-1. 11 * 11 = (1+1) * (1+1) = 2 * 2 = 4
2-2. 22 * 22 = (2+2) * (2+2) = 4 * 4 = 16
2-3. 33 * 33 = (3+3) * (3+3) = 6 * 6 = 36
```

> Christmas{santa+36}


# 06 PWNABLE Writeup

## Covid-19_VaCc1ne

![](/img/2022-01-01/2021-12-25-13-57-20.png)

```python
from pwn import *

nc = remote('34.125.134.97', 3344)
print(nc.recvline())
```

![](/img/2022-01-01/2021-12-25-13-58-35.png)

> Christmas{covid_19_Vaccine_1s_AstraZeneca}