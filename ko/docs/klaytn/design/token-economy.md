# 토큰 이코노미 <a id="token-economy"></a>

## 개요 <a id="overview"></a>

Klaytn의 토큰 이코노미는 생태계 운영, 성장 전략, 전략적 투자에 동력을 제공할 수 있도록 지속적인 펀딩이 가능한 구조로 설계되었습니다. 많은 퍼블릭 블록체인 프로젝트는 네트워크 유지의 기술적 측면에만 초점을 맞춰서 노드 운영자(채굴자 또는 블록 생산자)에게만 인센티브를 주는 토큰 이코노미를 가지고 있습니다. 그러나, 이러한 디자인은 네트워크의 성장에 기여하거나 장기 성장 가능성에 투자하는 다른 참여자들에게 인센티브를 제공하지 못합니다. 하지만, 클레이튼의 토큰 이코노미는 광범위한 참여자들이 더 다양한 형태의 기여에 대해 보상을 받을 수 있도록 설계되었습니다. 블록체인 노드를 유지하는 것 외에도 전략적으로 투자를 받은 프로젝트들과 그들의 미래 성장 전략에 지속해서 자원을 공급할 수 있는 펀딩 구조가 내장되어있습니다. For detailed information on Klaytn token economy, please refer to [Token Economy & Governance Paper](https://www.klaytn.com/Klaytn_Token_Economics_and_Governance_Paper_V1.01.pdf).

## 펀딩 구조(Funding Structure)<a id="funding-structure"></a>

Klaytn의 펀딩 구조는 Klaytn 네트워크의 블록 생성과 함께 지속적으로 운영됩니다. 모든 신규 블록에서 새로 발행된 KLAY와 블록\(총칭 "블록 보상" \)에 사용된 트랜잭션 수수료 합계는 사전 결정된 비율에 따라 다음 세 개의 대상 계정에 집계 및 배포됩니다.

* Klaytn 거버넌스 카운슬 보상: 34%
* 기여증명 \(PoC\) : 54 %
* Klaytn 개선 준비금 \(KIR\) : 12 %

Klaytn 메인넷 출시 시점에는 블록당 9.6 KLAY가 발행됩니다. 따라서, 매년 약 3억개의 KLAY가 발행될 것으로 예상할 수 있습니다. 이는 처음에 발행된 100억 KLAY 대비 연간 3 %의 인플레이션이 일어나는 것과 같습니다(연간 인플레이션율은 Klaytn Governance Process를 통해 변경 될 수 있습니다). 트랜잭션 수수료는 OPcode당 부과되며, 트랜잭션 수수료 표에 따라 책정됩니다. 트랜잭션 수수료 표에 대해서 더 많은 정보가 필요하면 [트랜잭션 수수료](transaction-fees.md)를 참고해주세요.

## Klaytn 거버넌스 카운슬 보상 <a id="klaytn-governance-council-reward"></a>

Klaytn 거버넌스 카운슬은 코어 셀 운영자\(CCOs\) 들의 그룹입니다. 카운슬 구성원은 코어 셀 \(CCs\)을 유지해야 할 책임이 있으며, 이 카운슬은 Klaytn 생태계에서 기본 인프라 제공을 담당하는 필수 기관이됩니다. 카운슬 멤버가 되려면 Klaytn Governance Process에서 자격 검토를 받아야하며 최소 5백만 KLAY를 스테이크해야합니다. Klaytn 거버넌스 카운슬 보상은 카운슬 멤버들이 Klaytn 생태계의 안정적인 기반이 될 수 있도록 인센티브를 제공하는 구조입니다.

### Klaytn 거버넌스 카운슬 보상 메커니즘 <a id="klaytn-governance-council-reward-mechanism"></a>

모든 블록마다 무작위로 선정된 카운슬 멤버로 이루어진 위원회가 구성됩니다. 각 위원회는 한 멤버가 제안자(Proposer) 역할을 할당받습니다. 다른 모든 위원회 위원은 검증자(Validator)의 역할을 맡습니다. 블록이 성공적으로 생성되어 Klaytn 블록체인에 추가되면, 해당 블록의 제안자에게는 블록 보상의 100%가 제공됩니다. 카운슬 멤버가 제안자로 선정될 확률은 회원이 스테이크한 KLAY의 양에 비례합니다. 즉, 더 많은 KLAY를 스테이크 할수록 멤버가 제안자로 선정되어 블록보상을 받을 가능성이 커집니다.

요구사항인 최소 500만 KLAY 스테이킹이 충족되는 한 Klaytn 거버넌스 카운슬 멤버는 자신의 KLAY를 자유롭게 스테이크하거나 언스테이크(unstake) 할 수 있습니다. 스테이킹 정보는 86,400블록마다 업데이트되며, 새로 스테이크 된 KLAY는 스테이킹이 완료된 후 두 번의 업데이트 주기 이후에 효력이 생깁니다. 스테이크 된 KLAY를 인출하는 일은 악의적인 멤버가 즉시 빠져나가지 못하도록 일주일 정도 지연됩니다.

많이 투자한 소규모 그룹의 카운슬 멤버들이 Klaytn 거버넌스 카운슬 보상을 독점하는 것을 막기 위해 지니 계수(Gini coefficient)가 이용되어 스테이크 된 Klay의 유효 수량을 조정할 수 있습니다. 적용 공식은 다음과 같습니다.

* _조정된 스테이킹 양(Adjusted staking amount) = \(카운슬 멤버의 스테이킹 양\)^\(1/1+G\)_

### 잘못된 행동을 하는 카운슬 멤버에 대한 처벌 <a id="penalty-for-misbehaving-council-members"></a>

카운슬 멤버는 아래와 같은 잘못된 행동을 하면 처벌의 대상이 될 수 있습니다. 앞으로 Klaytn Governance Process를 통해 더 많은 페널티 규칙이 수립되고 수정될 수 있습니다.

Safety Failure를 일으키는 경우:

* 제안자로 선택된 카운슬 멤버는 같은 height에 두 개 이상의 블록을 만들 수 없습니다.
* 제안자로 선정된 카운슬 멤버는 의도적으로 특정 트랜잭션을 제외할 수 없습니다.

Liveness Failure를 일으키는 경우:

* 제안자로 선택된 카운슬 멤버는 유효한 블록을 생성해야 합니다.
* 검증자로 선정된 카운슬 멤버는 제안자가 제안한 블록을 검증해야합니다.

## 기여증명(Proof of Contribution)<a id="proof-of-contribution"></a>

Klaytn의 토큰 이코노미는 경제 활동에 자발적으로 참여하여 가치를 창출하고 시장에서 가치를 교환하는 경제 주체들에 의해 지탱됩니다. 이런 활동들이 모여 자산이 순환하는 경제를 구축하고, 전체 생태계의 경제적인 성장을 이끕니다. Klaytn은 기여도를 평가하고 기여증명 \(PoC\)이라는 투명한 평가 메커니즘을 통해 참여자들을 보상함으로써 이코노미 참여자들에게 인센티브를 제공하고 자극합니다.

기여증명은 의미 있는 기여를 하는 Klaytn 토큰 이코노미의 모든 참가자를 보상하기 위해 디자인되었습니다. 그러나, 현재 PoC는 주로 두 가지 경제 주체에 초점을 두고 있습니다. 하나는 서비스 제공 업체 \(사용자에게 블록체인 응용 프로그램 서비스를 제공하는)이고, 또 다른 하나는 사용자\(서비스 제공 업체의 서비스를 사용하는 소비자\)입니다.

### 서비스 제공자(Service Providers)<a id="service-providers"></a>

블록체인 기술이 대중화되려면 대규모 블록체인 애플리케이션 또는 Killer BApp이 구현되고 널리 활용되는 것이 중요합니다. 그러면 일상생활 속에서 그런 앱들을 통해 가치를 발견하고 즐기는 사용자층이 두터워질 것입니다. 서비스 제공자는 공급측의 주체로서 Klaytn 이코노미에서 핵심적인 역할을 합니다. 서비스 제공자는 사용자를 만족시키는 서비스를 공급할 뿐만 아니라 새로운 사용자 확보 채널 및 사용자 참여의 앵커 역할도 합니다. 서비스 제공자들의 기여를 알기 때문에, Klaytn은 서비스 제공자들이 쉽게 Klaytn 플랫폼으로 유입되고 생태계가 성장함에 따라 지속적인 지원을 받을 수 있도록 인센티브를 제공하는 PoC를 디자인했습니다.

### 사용자(End-Users)<a id="end-users"></a>

수요와 공급 사이의 불균형이 확대되면 경제가 지속 가능하지 않습니다. 따라서, 사용자는 Klaytn 토큰 이코노미 내에서 중요한 위치를 차지합니다. 사용자는 주요한 수요 주체로서 경제적 성장을 이끄는 근본적인 원동력입니다. 사용자는 서비스를 신중하게 선택하고, 사용하며, 리뷰를 공유함으로써 귀중한 시장 신호(Market signal)를 만듭니다. Klaytn은 사용자의 가치를 인식하여, PoC가 Klaytn 생태계 성장에 기여하는 바에 따라 사용자에게 보상하는 인센티브 메커니즘이 될 수 있도록 검토하고 있습니다.

## PoC 파일럿 테스트 운영 계획 <a id="proof-of-contribution-operation-plan"></a>

Klaytn은 파일럿 테스트를 통해 PoC 정책을 보다 고도화 시켜 나감으로써, 보다 많은 Klaytn 네트워크 참가자들이 PoC의 혜택을 누릴 수 있게 하고자 합니다. 1차 PoC 파일럿 테스트 Klaytn 네트워크 초기에 시행 됨에 따라, Klaytn 생태계에 대한 영향을 최소화하기 위해 소규모로 진행될 예정입니다. 아래에 언급된 사항들은 파일럿 테스트 결과에 따라 지속 수정될 것입니다.

### 개요 <a id="overview"></a>

1차 PoC 파일럿 테스트는 아래와 같이 진행될 예정입니다.

| Phase 1      |                                                                                                              |
|:------------ |:------------------------------------------------------------------------------------------------------------ |
| **대상**       | 1차 PoC 파일럿 테스트 신청 및 내부 심사를 통과한 서비스 제공자                                                                       |
| **기간**       | 2020.09 ~ 2020.11                                                                                            |
| **기본 요구 사항** | 다음 조건을 충족한 서비스 제공자: \(1\) Cypress 온보딩 완료, \(2\) 고객이 직접 스마트 컨트랙트와 상호작용할 수 있는 기능 지원, \(3\) 규제 준수         |
| **자원**       | 최대 600,000 KLAY가 서비스 제공자들에게 배포될 예정입니다.                                                                       |
| **보상 지급 일정** | 서비스 제공자는 기여도 평가 라운드가 끝난 이후에 보상을 지급 받습니다. 기여도 평가 라운드는 격주로 시작되며, 서비스 제공자의 보상량은 2주 동안 수집된 블록체인 데이터를 기반으로 산정됩니다. |
| **자격박탈**     | 기여도 측정 관련 데이터 조작과 같은 부정 행위를 저지른 서비스 제공자는 영구적으로 PoC 참여 자격이 박탈됩니다.                                             |

### 인센티브 프로그램 <a id="incentive-programs"></a>

본 파일럿 테스트에서, 서비스 제공자는 기여도 평가 라운드 마다 기여도가 측정되며, 이를 기반으로 보상을 분배받습니다. 서비스 제공자에 대한 ‘기여도 측정 지표’ 및 ‘보상 분배 방식’은 아래와 같습니다.

#### 1. 기여도 측정 지표

서비스 제공자에 대한 기여도 측정을 위해, 서비스 스마트컨트랙트에 대한 트랜잭션을 기반으로 아래의 4가지 지표 데이터가 수집될 예정입니다.
* 신규 유저 수: 해당 라운드 기간 동안 서비스 스마트 컨트랙트에 트랜잭션을 1개 이상 보낸 신규 고유 계정 수 입니다.
* 재방문 유저 수: 해당 라운드 기간 동안 서비스 스마트 컨트랙트에 트랜잭션을 1개 이상 보낸 재방문 고유 계정 수 입니다.
* 트랜잭션 발생 수: 해당 라운드 기간 동안 서비스 스마트컨트랙트를 호출하는 트랜잭션 수 입니다.
* KLAY 사용 규모: 해당 라운드 기간 동안 서비스 스마트 컨트랙트로 전송되는 KLAY 전체 수량 입니다.

#### 2. 보상 분배 방식

서비스 제공자는 한 라운드 기간 동안 수집된 데이터를 기반으로, 아래와 같이 3단계에 거쳐 보상을 분배받습니다.

1. 1단계 - 최소 기준 통과 및 기여도 산정: 최소 기준(eg. 신규 유저 100명 이상 유입) 을 통과한 서비스 제공자에 한 하여 기여도 측정 및 보상 지급이 이뤄집니다. 기여도는 위에서 언급한 4가지 지표 값 및 각 지표별 가중치를 기반으로 측정됩니다.

2. 2단계 - 라운드 별 총 보상량 산정: 라운드 별 총 보상량은 총 유저(신규/기존) 유입 수를 기반으로 측정됩니다. 이때, 라운드에 대한 총 보상량에는 상한선이 존재함에 따라 PoC 보상 풀 고갈에 대한 우려는 없습니다.

3. 3단계 - 기여율 및 기여도 순위 기반 보상 분배: 앞서 산정된 서비스 제공자의 기여도를 기반으로 서비스 제공자별 기여율 및 기여도 순위가 산정됩니다. 서비스 제공자는 최종적으로 기여율 및 기여도 순위에 따라 보상을 배분받습니다.

본 보상 분배 방식은 서비스 제공자가 유저 유치 및 서비스 개발에 힘쓸 수록 보다 많은 보상을 받을 수 있도록 디자인되었습니다.

## Klaytn 개선 준비금(Klaytn Improvement Reserve)<a id="klaytn-improvement-reserve"></a>

기술은 지속해서 향상되고, 사용자의 요구는 시간이 지나면서 변화합니다. 그러므로 플랫폼은 발생하는 모든 새로운 상황에 신속하게 대처할 수 있는 능력을 갖추어야 합니다. 이러한 변화에 대응하기 위해서 서비스뿐 아니라 Klaytn의 생태계를 유지하기 위해 다양한 활동에 노력을 들여야 합니다. Klaytn 개선 준비금(Klaytn Improvement Reserve) 은 그러한 노력의 일환으로서, 지속적으로 변화하는 환경속에서 Klaytn 생태계의 발전 및 확장을 위하여 진행되는 프로그램입니다. 플랫폼에 기여할 다양한 의견들을 수렴하고 이 중 주요한 기여를 할 제안들을 수용하고 지원함으로써, Klaytn 생태계는 지속적으로 확장 및 발전할 것입니다.

Klaytn 생태계에 필요한 주요 카테고리는 다음과 같이 분류할 수 있습니다.



| 카테고리                            | 상세 카테고리                                                                                                                            |
|:------------------------------- |:---------------------------------------------------------------------------------------------------------------------------------- |
| **Development**                 | <ul><li>IDE & Editors</li><li>Oracle</li><li>Contract Library</li>                           |
| **Infrastructure**              | <ul><li>Local Testnet</li><li>Decentralized File System</li><li>Multi-VM</li>                           |
| **Test, Debugging, Deployment** | <ul><li>Testing & Deployment Tools</li><li>Security & Audit Tools</li>                                                     |
| **Monitoring & Analytics**      | <ul><li>Monitoring</li><li>Analytics</li>                                                     |
| **Education & Activity**        | <ul><li>Documentation</li><li>Educational Materials</li><li>Community Building</li><li>Open Source Activity(Including Bug Bounty)</li> |
| **Research**                    | <ul><li>Security, Scalability, Cryptography, etc.</li></ul>                                                                                                         |


KIR 제안은 Klaytn 생태계의 모든 참여자가 작성할 수 있습니다. KIR 지출 제안은 KIR 심사 절차에 따라 처리됩니다.   제안이 통과되면, 프로젝트의 진행 수준에 맞추어, 사전에 설정된 KLAY 가 지급됩니다. 프로젝트에 따라 지원되는 KLAY 총량 및 지급시기 등이 달라집니다.

자세한 사항은 KIR Forum(https://kir.klaytn.com/) 을 참고하세요.