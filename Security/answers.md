# 정보보안 문제 답안

1. 기밀성, 무결성, 가용성
    자산이 인가(authorization)된 당사자에 의해서만 접근하는 것을 보장하는 것
    자산이 인가된 당사자에 의해서, 인가된 방법으로만 변경 가능한 것
    자산이 적절한 시간에 인가된 당사자에게 접근 가능해야하는 것
    
      
    
2. 128,192, 256 비트 / 10, 12, 14회전

      

3. land 공격, 수신되는 패킷 중 출발지 주소(또는 포트)와 목적지 주소(또는 포트)가 동일한 패킷들을 차단함으로써 이 공격을 피할 수 있다.

      

4. smurf는 여러 호스트가 공격 대상에게 많은 양의 ICMP Echo Request를 보내게 하여 공격 대상을 마비시키는 공격이다.
    증폭 네트워크로 사용되는 것을 막기 위해 다른 네트워크로부터 자신의 네트워크로 들어오는 Directed Broadcast 패킷을 허용하지 않도록 라우터 설정을 통하여 대응
    ping of death는 규정 크기 이상의 커다란 ICMP 패킷을 통해 공격하는 방법
    방화벽등의 장치에서 ping 명령을 전송하는 ICMP 프로토콜을 차단하여 대응

      

5. MAC
    주체와 객체의 보안 등급을 비교하여 접근 권한을 부여하는 접근통제이다. (규칙기반 접근통제)
    보안 관리자가 취급 인가를 허용한 개체만 접근할 수 있도록 강제적으로 통제한다. (중앙 집중형 보안관리)  
    DAC
    주체가 속해있는 그룹의 신원에 근거하여 객체에 대한 접근을 제한하는 방법이다. (신분기반 접근통제)
    객체의 소유자가 접근 여부를 결정한다. (분산형 보안관리)
    하나의 주체마다 객체에 대한 접근 권한을 부여해야 한다.
    리눅스, 윈도우, 유닉스 등 대부분의 운영시스템은 DAC에 기반한다. (ACL)  
    RBAC
    주체와 객체 사이에 역할을 두어 역할에 따라 접근통제한다. (역할은 사용자의 집합과 권한 집합의 매개체)
    강제적 접근제어와 임의적 접근제어의 대안으로 사용된다.  
