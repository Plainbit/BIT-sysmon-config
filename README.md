# BIT-sysmon-config
이는 Microsoft Sysinternals Sysmon의 Configure 파일이다.

실제 사이버 공격 사례를 분석해 공격자의 행위에 대한 전략을 표준화한 MITRE ATT&CK 프레임워크는 공격자의 행위를 식별할 수 있는 프레임워크로 발전해 국내에서도 사이버 위협을 탐지하고 대응하기 위해 많이 활용되고 있다. 다만, 대부분의 전술이 APT 공격에 조금 더 초점이 맞춰져 있어 국내를 타겟으로 한 공격을 탐지하고 대응하는데 한계가 있다.

최근 수준 높은 공격자들은 공격 탐지를 회피하기 위해 자신이 수행한 공격을 파일리스 공격이나 공격 도구 등을 완전 삭제해 철저하게 은닉하고 있다. 랜섬웨어와 같이 표면적으로 드러나는 공격이면 기업에서도 사고를 빠르게 인지할 수 있지만 로그 설정이 미흡한 인프라를 공격자가 침투해 해킹 경유지 등으로 활용하는 경우 로그 부재로 사고에 대한 원인과 영향을 규명하기에 한계가 있다.

따라서, 다년간 침해사고 분석과 대응 경험에 대한 노하우를 살려 국내에서 발생하는 다양한 사이버 위협을 탐지하기 위한 BIT-sysmon-config를 작성하였다.

BIT-sysmon-config는 DFIR 관점으로 접근해 사이버 위협을 탐지 및 분석할 때 분석가가 유용한 정보를 확인할 수 있도록 아래와 같은 관점으로 작성되었다.
1. 다양한 사이버 위협 시나리오를 포함해 더 넓은 이벤트 범위 탐지 가능
2. 국내에 맞는 환경을 접목시켜 더 명확하고 상세하게 위협 탐지 가능
3. DFIR을 지원하기 위해 설계되어, 분석가가 사고를 신속하게 분석하고 대응할 수 있도록 유용한 정보 제공
4. 다년간 경험한 침해사고에서 파악된 주요 공격자 행위를 반영해 현실적인 사이버 위협에 대응할 수 있도록 개선
5. 설정을 최적화해 네트워크와 동작되는 시스템 성능에 부담을 주지 않으면서 효과적으로 사이버 위협 탐지

***참고***: Configure File을 시스템에 적용하기 전 충분한 테스트 기간을 거치고 시스템과 용도에 따라 추가적으로 수정해야한다.


# Usage
## Install
아래 명령어를 통해 Sysmon 설치와 동시에 Configure를 적용할 수 있다.(관리자 권한으로 실행)

```sysmon.exe -accepteula -i BIT-sysmon-config.xml```

## Configure Update
아래 명령어를 통해 기존 Sysmon에 적용된 Configure를 변경할 수 있다.(관리자 권한으로 실행)

```sysmon -c BIT-sysmon-config.xml```

## Uninstall
아래 명령어를 통해 시스템에 설치된 Sysmon을 삭제할 수 있다.(관리자 권한으로 실행)

```sysmon.exe -u```


# 참고 사항
Sysmon에 대한 추가적인 내용을 알고싶다면, 아래 링크를 참고바란다.
1. Sysmon 활용 가이드: 개념 및 설치 방법 <https://blog.plainbit.co.kr/sysmon_concepts_installations/>
2. Sysmon 활용 가이드: 이벤트 구성 항목 <https://blog.plainbit.co.kr/configuring_sysmon_events/>
3. Sysmon 활용 가이드: Configure File 구성과 작성 방법 <https://blog.plainbit.co.kr/sysmon_configure_file/>
