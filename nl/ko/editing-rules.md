---

copyright:
  years: 2017,2018
lastupdated: "2018-01-22"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 하드웨어 방화벽(전용) 구성

처음으로 방화벽을 VLAN에 추가하는 경우 모든 트래픽이 방화벽을 통과할 수 있도록 규칙 세트가 초기에 실시됩니다. 방화벽을 구성하는 작업은 다른 소스의 트래픽은 거부하는 반면 특정 인터넷 주소의 IP 주소/포트에 대한 액세스는 허용하도록 규칙 세트를 작성하는 것만큼 간단합니다. 

## 규칙 편집

방화벽 규칙을 편집하려면 다음을 수행하십시오.

1. 브라우저에서 [고객 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){: new_window}을 열고 계정에 로그인하십시오.
2. 고객 포털 탐색에서 **네트워크 > IP 관리 > VLAN**을 선택하십시오. 각 행은 인프라에 있는 VLAN을 표시합니다. 관리하려는 VLAN과 연관된 Firewall-vlanXXXX.networklayer.com 링크를 클릭하여 **디바이스 세부사항** 페이지로 이동하십시오. "상태"가 방화벽이 "규칙을 모두 처리 중"임을 나타내는지 확인하십시오. 사용자는 구현된 규칙이 환경에 의도하지 않은 영향을 미치는 경우 "규칙 무시"를 클릭하여 규칙을 무시하도록 선택할 수 있습니다.
3. 규칙 업데이트를 시작하려면 **규칙** 탭을 클릭하십시오. 페이지에 IPv4 및 IPv6 주소에 영향을 미치는 현재 규칙이 포함된 섹션이 표시됩니다. 규칙이 구현되지 않은 경우 희미해진 플레이스홀더가 표시됩니다. 해당되는 행을 클릭하여 개별 규칙을 편집하십시오. 이 규칙 목록이 '작업 중인 구성'으로 알려져 있습니다. '작업 중인 구성'은 작성 중이지만 아직 방화벽에 적용되지 않은 규칙 세트입니다. 사용자는 규칙 세트가 완료될 때까지 규칙을 편집, 추가 및 삭제할 수 있습니다. 규칙은 처리되는 순서대로 표시되며 번호가 낮은 규칙이 번호가 높은 규칙보다 우선권을 갖습니다(규칙 1이 패킷을 통과하도록 허용되면 규칙 2 이후는 패킷에서 무시함).
4. 편집할 규칙을 클릭하거나 추가 규칙을 추가하려면 테이블의 맨 아래 있는 더하기 기호를 클릭하십시오. 빼기 아이콘을 클릭하면 규칙이 삭제됩니다. 규칙을 입력하면 자동으로 유효성이 검증됩니다. 

    필드는 다음과 같습니다.

    **주문:** 규칙의 주문 번호입니다. 제공된 화살표를 사용하여 규칙을 목록에서 위 또는 아래로 이동할 수 있으며 맨 위부터 맨 아래로 적용됩니다.

    **조치:** 이 규칙과 일치하는 트래픽을 '허용' 또는 '거부'합니다.

    **소스:** '임의', 특정 IP 주소, 특정 서브넷의 네트워크 주소 중 하나일 수 있습니다.

    **CIDR:** 선택한 소스에 대한 표준 CIDR 표기법을 나타냅니다. 예를 들어, "24"는 256개 IP에 대한 규칙을 구현하는 반면, "32"는 단일 IP에 대한 규칙을 구현합니다.

    **대상:** '임의', 특정 IP 주소, 특정 서브넷의 네트워크 주소 중 하나일 수 있습니다.

    **CIDR:** 선택한 대상에 대한 표준 CIDR 표기법을 나타냅니다.

    **포트 범위:** 이러한 두 개 필드는 규칙을 적용하는 포트의 범위를 나타냅니다(1 - 65535 사이).

    **프로토콜:** 규칙을 적용하는 프로토콜을 선택합니다(TCP/GRE/ICMP/UDP/PPTP/AH/ESP).

    **참고:** 이 규칙에 대한 참고사항을 입력하는 필드입니다.
    
5. '작업 중인 구성'이 완료되면 **규칙 업데이트** 단추를 눌러서 방화벽에 '작업 중인 구성'을 적용하십시오. 규칙은 2분 안에 적용됩니다. 

## 공통 포트

| 프로토콜| 포트    |
| :-----: | :-----: |
| FTP | 21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| HTTP | 80 |
| POP3 | 110 |
| IMAP | 143 |
| HTTPS | 443 |
| MSSQL | 1433 |
| MySQL | 3306 |
| 원격 데스크탑  | 3389 |
| PostgreSQL | 5432 |
| VNC 웹  | 5800 |
| VNC 클라이언트 | 5900 |
| Urchin | 9999 또는 10000 ||