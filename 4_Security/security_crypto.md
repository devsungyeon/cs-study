# 정보보안/암호학



### 블록암호

* AES
  * 128/192,256 비트 블록, 키
  * 10, 12, 14 라운드로 구성, 비 페이스텔 구조
* IDEA
  * 64비트 블록, 128비트 키
  * PGP의 암호 알고리즘으로 채택

---

### 블록암호 모드

* ECB모드
  * 평문을 동일한 블럭으로 나눠서 같은 방식으로 암호화
  * 패턴이 나타나기 때문에 안정성이 떨어진다.
* CBC모드
  * IV를 사용하고 앞의 블럭과 XOR 한 뒤 암호화
  * 오류전이 발생
* CFB모드
  * IV를 사용하고 앞의 블럭을 암호화 한 뒤 XOR
  * 오류전이 발생
* OFB모드
  * IV에 대한 연속적으로 암호화, 이를 평문블럭과 XOR
* CTR 모드
  * 카운터를 암호화, 이를 평문블럭과 XOR

---

### 공개키 암호화

#### 디피-헬먼

> 최초의 공개키 암호화 알고리즘으로 1976년에 Diffie와 Hellman에 의해 개발

* 소수 p가 충분히 클 때 주어진 두 개의 공개 값들 g<sup>a</sup> mod p와 g<sup>b</sup> mod p를 가지고 공유된 비밀키 g<sup>ab</sup> mod p를 계산하는 것이 불가능하다고 가정한 **이산대수 문제**를 기반으로 함

* 키 교환을 하는 대상과 비밀 정보를 공유할 수 있지만, 상대방에 대한 인증은 보장되지 않아 중간자 공격(MITM)이 가능
* IPSEC에서 IKE(Inter Key Exchange)의 기본 키 교환 알고리즘으로 채택

#### DSA

> 1991년 NIST에서는 DSS에 DSA를 사용하도록 제안 (DSS : 전자서명표준, DSA : 알고리즘)

* **이산대수 문제** Y = g<sup>x</sup> mod p 에서 Y, g, p을 공개하더라도 x를 계산하기 어렵다는 가정

#### Elgamal

> 1984년 스탠퍼드 대학의 테하르 엘가말(Tehar ElGamal)이 제안한 알고리즘

* **이산대수 문제**를 기반으로 함
* 난수 k를 이용하므로 매 암호화 시 다른 암호문을 얻어 RSA에 비해 더 안전함
* 암호문의 길이가 평문 길이의 두배가 되는 단점 존재

#### RSA

* **소인수분해**의 어려움을 기반으로 하며 키 사이즈는 2048bit 권장
* 기밀성과 부인방지 기능 제공

#### Rabin

* RSA 알고리즘의 변형, 마찬가지로 **소인수분해**의 어려움을 기반
* RSA는 e,d라는 지수를 사용하지만, Rabin은 e,d가 2로 고정되어 있어 RSA보다 암호화 연산이 빠름

#### ECC

* **타원곡선상에서 이산대수의 어려움**을 기반으로한 공개키 암호 알고리즘
* 기존 공개키 암호화보다 짧은 키의 길이로 동일한 안전성을 제공 (RSA 1024bit = ECC 160bit)
* 무선 환경과 같이 전송량과 계산량이 상대적으로 열악한 환경에 적합
* 이론적으로 복잡하여 실제 구현이 어려움

___

### 해시

* 특성
  * 1역상 저항성
    * 역상 저항성은 해시 값이 주어졌을 때, 그 해시 값을 생성하는 입력값을 알아내기가 불가능하다는 특성
    * 주어진 해시 값이 H가 있다면 그 해시 값을 생성하는 H=Hash(M)의 M을 계산하기가 어려워야 한다.
  * 제2 역상저항성(약한 충돌 회피성)
    * 어떤 입력 값과 동일한 해시 값(결과 값)을 가지는 다른 입력 값을 찾을 수 없어야 한다는 특성
    * 어떤 입력값 M1 에 대해 M1≠M2이며, Hash(M1)=Hash(M2) 인 M2를 찾을 수 없어야 함
  * 충돌 저항성(강한 충돌 회피성)
    * 해시 값 (결과 값)이 이 같은 입력 값 두 개를 찾을 수 없다는 특성
    * 동일 해시값을 생성하는 M1, M2를 찾기 어려워야 한다.

---


