**Volume 22. Hills Robotics Engineering Standards**

# Chapter 01. HRS-001 Electrical Architecture

## 01.01. Scope and Purpose

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

이 표준의 적용 범위(scope)는 힐스 로보틱스 엔지니어링 표준(Hills Robotics Engineering Standards)에 따라 개발되는 로봇 제품을 위한 공통 전기·전자 아키텍처(electrical and electronic architecture) 프레임워크를 확립하는 것이다. 전력 분배(power distribution), 전기 인터페이스(electrical interfaces), 컴퓨팅 노드(computing nodes), 센서(sensors), 액추에이터(actuators), 통신 네트워크(communication networks), 안전 회로(safety circuits), 접지(grounding), 보호(protection), 진단(diagnostics), 서비스 인터페이스(service interfaces)를 제품 수명주기(product lifecycle) 전체에 걸쳐 설계하기 위한 시스템 수준의 원칙을 정의한다.

HRS_001의 목적(purpose)은 세부 제품 및 서브시스템 표준(subsystem standards)을 도출할 수 있는 안정적인 아키텍처 기반(architectural foundation)을 제공하는 것이다. 모든 회로 구현 방법을 규정하는 대신, 서로 다른 로봇 플랫폼 간의 일관성(consistency), 상호운용성(interoperability), 추적성(traceability), 안전성(safety), 유지보수성(maintainability)을 확보하기 위해 필요한 경계(boundaries), 책임(responsibilities), 인터페이스(interfaces), 엔지니어링 규칙(engineering rules)을 정의한다.

이 표준은 초기 개념 개발(early concept development)부터 상세 설계(detailed design), 시제품 제작(prototype construction), 검증(verification), 양산 승인(production release), 현장 운용(field operation), 유지보수(maintenance), 통제된 변경(controlled modification)에 이르는 전기 아키텍처 활동에 적용된다. 개별 전선 굵기(wire gauge), 커넥터(connector), 퓨즈(fuse), 통신 프로토콜(communication protocol), 교정 절차(calibration procedure) 또는 부품 수준 구현 세부사항이 확정되기 전에 엔지니어링 의사결정을 지원하는 것을 목적으로 한다.

전기 아키텍처(electrical architecture)는 로봇을 독립적으로 설계된 전자 장치들의 집합이 아니라 하나의 통합 전기 시스템(integrated electrical system)으로 취급해야 한다. 따라서 에너지원(energy sources), 전력 변환 단계(power conversion stages), 분배 장치(distribution units), 제어기(controllers), 센서(sensors), 액추에이터(actuators), 네트워크 장비(network equipment), 안전 장치(safety devices), 외부 인터페이스(external interfaces)를 함께 고려해야 한다. 상세 구현 이전에 이들의 전기적 종속 관계(electrical dependencies)와 고장 상호작용(failure interactions)을 아키텍처 수준에서 식별해야 한다.

HRS_001은 전압 레일(voltage rails), 이중화(redundancy), 하네스 설계(harness design), 커넥터 선정(connector selection), 퓨즈 보호(fuse protection), 접지(grounding), 통신(communication), 교정(calibration), 안전(safety)을 다루는 후속 표준에 상위 아키텍처 맥락(parent architectural context)을 제공한다. 자율이동로봇(AMR), 매니퓰레이터(manipulator), 실외 차량(outdoor vehicle), 화물 무인항공기(cargo UAV), 사족보행 로봇(quadruped), 휴머노이드(humanoid)를 위한 제품별 표준은 각 운용 환경과 시스템 특성에 적합한 요구사항을 추가하면서 이러한 공통 원칙을 적용해야 한다.

이 표준은 모든 제품에 동일한 하드웨어 구성을 강제하지 않으면서 여러 로봇 제품군(robot families) 사이에서 재사용(reuse)을 촉진하도록 설계되었다. 소형 실내 자율이동로봇(indoor AMR), 실외 자율주행 차량(outdoor autonomous vehicle), 모바일 매니퓰레이터(mobile manipulator), 사족보행 로봇(quadruped), 휴머노이드(humanoid)는 서로 다른 전압 수준, 액추에이터 용량, 센서 구성 및 컴퓨팅 자원을 요구할 수 있다. 그러나 아키텍처 분해(decomposition)와 인터페이스 정의(interface definition)에는 공통된 엔지니어링 논리를 적용해야 한다.

전기 아키텍처는 에너지 생성 또는 저장(energy generation or storage), 1차 전력 분배(primary distribution), 2차 전력 변환(secondary conversion), 컴퓨팅 부하(computational loads), 센싱 부하(sensing loads), 액추에이터 부하(actuator loads), 안전 관련 회로(safety-related circuits), 보조 장비(auxiliary equipment) 사이의 명확한 경계를 정의해야 한다. 이러한 경계는 이해하기 쉬운 시스템 수준 아키텍처를 유지하면서 전류 요구량(current demand), 고장 전파(fault propagation), 절연 및 격리(isolation), 기동 동작(startup behavior), 종료 동작(shutdown behavior), 성능 저하 운전(degraded operation)을 독립적으로 분석할 수 있도록 해야 한다.

특히 고전력 도메인(high-power domain)과 저전력 도메인(low-power domain)의 분리에 주의를 기울여야 한다. 모터 드라이브(motor drives), 구동 시스템(traction systems), 고전류 액추에이터(high-current actuators), 충전 장비(charging equipment) 및 기타 대전력 소비 장치는 민감한 전자장치에 영향을 주는 전압 교란(voltage disturbances), 전도성 노이즈(conducted noise), 열 스트레스(thermal stress), 고장 에너지(fault energy)를 발생시킬 수 있다. 따라서 적절한 도메인 분리(domain separation), 보호(protection), 접지(grounding), 필터링(filtering), 통제된 상호연결(controlled interconnection)을 아키텍처 단계에서 확립해야 한다.

이 표준은 통신 아키텍처(communication architecture)가 전기 아키텍처의 일부라는 원칙도 확립한다. CAN, 이더넷(Ethernet), 산업용 네트워크(industrial networks), ROS 2 인터페이스(ROS 2 interfaces), 직렬 통신(serial communication), 무선 링크(wireless links) 및 기타 데이터 경로(data paths)는 물리적인 전원, 접지, 차폐(shielding), 커넥터, 타이밍(timing), 네트워크 토폴로지(network topology)에 의존한다. 따라서 이러한 요구사항은 독립된 소프트웨어 인터페이스로 설계하기보다 전기 패키징(electrical packaging) 및 시스템 아키텍처와 조정되어야 한다.

안전 관련 전기 기능(safety-related electrical functions)은 기본 아키텍처에 영향을 줄 수 있을 만큼 초기 단계에서 식별되어야 한다. 비상 정지(emergency stopping), 전원 차단(power isolation), 액추에이터 비활성화(actuator disablement), 안전 센싱(safety sensing), 안전 통신(safety communication), 워치독 기능(watchdog functions), 이중화 제어 경로(redundant control paths), 고장 격리(fault containment)는 전용 회로나 독립적인 자원을 요구할 수 있다. 이러한 요구사항을 기능 아키텍처(functional architecture)와 전력 분배 구조가 이미 확정된 이후에 추가해서는 안 된다.

아키텍처는 결정론적이고 진단 가능한 기동(deterministic and diagnosable startup), 정상 운전(normal operation), 성능 저하 운전(degraded operation), 비상 대응(emergency response), 제어된 종료(controlled shutdown), 충전(charging), 유지보수(maintenance), 복구(recovery)를 지원해야 한다. 의도하지 않은 전원 인가(unintended energization), 제어되지 않은 액추에이터 작동(uncontrolled actuator activation), 불명확한 제어기 상태(ambiguous controller states), 안전하지 않은 복구 동작(unsafe recovery behavior)을 의도적으로 설계된 아키텍처 메커니즘을 통해 방지하거나 감지할 수 있도록 전기적 상태와 상태 전이(state transitions)를 정의해야 한다.

신뢰성(reliability)과 가용성(availability) 요구사항은 제품의 의도된 임무(intended product mission)에 따라 아키텍처 결정으로 변환되어야 한다. 단일 부품의 손실이 허용할 수 없는 시스템 결과를 발생시키는 경우 이중화 전원(redundant supplies), 이중 통신 경로(duplicated communication paths), 백업 컴퓨팅 자원(backup computing resources), 독립 안전 채널(independent safety channels), 고장 허용 센싱(fault-tolerant sensing)이 필요할 수 있다. 이중화는 통제되지 않은 하드웨어 복제가 아니라 문서화된 요구사항(documented requirements)에 근거하여 도입해야 한다.

아키텍처는 효과적인 진단(diagnostics)과 정비성(serviceability)도 지원해야 한다. 주요 전력 분기(power branches), 제어기, 통신 세그먼트(communication segments), 센서, 액추에이터, 안전 장치는 시스템 상태를 파악하고 고장을 격리하기에 충분한 관측 가능성(observability)을 제공해야 한다. 현장 고장 진단(field troubleshooting)이 침습적인 분해나 문서화되지 않은 측정에 의존하지 않도록 진단 인터페이스(diagnostic interfaces), 측정 지점(measurement points), 로그(logs), 고장 코드(fault codes), 서비스 절차(service procedures)를 아키텍처 정의 단계에서 고려해야 한다.

구성 관리(configuration management) 역시 이 표준의 목적에 포함된다. 전기 아키텍처 변경은 여러 엔지니어링 영역으로 파급될 수 있기 때문이다. 전압 레일, 커넥터, 퓨즈 정격(fuse ratings), 네트워크 토폴로지, 제어기 할당(controller allocation), 센서 인터페이스 또는 접지 전략(grounding strategy)의 변경은 하드웨어, 하네스, 펌웨어(firmware), 소프트웨어, 제조, 교정, 시험 및 서비스 문서에 영향을 줄 수 있다. 따라서 아키텍처 변경은 추적 가능해야 하며 통제된 엔지니어링 검토(controlled engineering review)의 대상이 되어야 한다.

HRS_001의 준수(compliance)는 상세 계산(detailed calculations), 부품 적격성 평가(component qualification), 안전 분석(safety analysis), 전자파 적합성 검증(EMC verification), 환경 검증(environmental validation) 또는 제품별 인증(product-specific certification) 활동을 대체하지 않는다. 대신 이러한 활동을 일관된 방식으로 수행할 수 있는 프레임워크를 확립한다. 상세 요구사항은 승인된 시스템 아키텍처와의 추적성을 유지하면서 관련 HRS 표준과 제품 엔지니어링 사양(product engineering specifications)에 할당되어야 한다.

궁극적인 목표는 전체 제품 수명주기에 걸쳐 서로 다른 엔지니어링 팀이 이해하고, 검토하고, 구현하고, 시험하고, 제조하고, 유지보수하며 확장할 수 있는 전기 아키텍처를 구축하는 것이다. HRS_001은 상세 구현 이전에 공통 아키텍처 원칙(common architectural principles)을 확립함으로써 제품 복잡성이 증가하더라도 전력(power), 통신(communication), 안전(safety), 센싱(sensing), 액추에이션(actuation), 컴퓨팅(computing) 시스템의 일관성을 유지할 수 있는 확장 가능한 로보틱스 플랫폼(scalable robotics platforms)의 기반을 제공한다.

## 01.02. Architecture Requirements

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

전기 아키텍처(electrical architecture)는 주 에너지원(primary energy source)에서 모든 전기 부하(electrical load), 제어 노드(control node), 센서(sensor), 액추에이터(actuator), 통신 인터페이스(communication interface), 안전 기능(safety function)에 이르는 명확한 시스템 계층 구조(system hierarchy)를 정의해야 한다. 각 요소에는 아키텍처 책임자(architectural owner), 기능적 목적(functional purpose), 전원 공급원(power source), 인터페이스 경계(interface boundary), 고장 관계(failure relationship)가 식별되어야 하며, 이를 통해 전체 로봇을 독립된 조립체들의 집합이 아니라 하나의 통합 전기·전자 시스템(integrated electrical and electronic system)으로 분석할 수 있어야 한다.

모든 제품 아키텍처(product architecture)는 전력 도메인(power domains), 전압 레일(voltage rails), 전력 분배 경로(distribution paths), 변환 단계(conversion stages), 제어기(controllers), 통신 네트워크(communication networks), 안전 회로(safety circuits), 센서(sensors), 액추에이터(actuators), 접지 경계(grounding boundaries), 외부 인터페이스(external interfaces)를 나타내는 승인된 시스템 수준 전기 아키텍처 다이어그램(system-level electrical architecture diagram)을 유지해야 한다. 이 다이어그램은 상세 회로도(schematics), 하네스 도면(harness drawings), 인터페이스 사양(interface specifications), 소프트웨어 구성(software configuration), 자재 명세서(bills of materials), 공식 배포된 제품 문서(released product documentation)와 일관성을 유지해야 한다.

전력 아키텍처(power architecture)는 전압 수준(voltage level), 전류 요구량(current demand), 기능 중요도(functional criticality), 전기적 노이즈 특성(electrical noise characteristics), 고장 결과(fault consequences)에 따라 명확하게 정의된 도메인으로 구성되어야 한다. 주 배터리(primary battery) 또는 외부 전원(external power)은 하위 부하로 공급되기 전에 통제된 보호(protection) 및 분배(distribution) 단계를 거쳐야 한다. DC/DC 컨버터(DC/DC converter)와 인버터(inverter) 등의 변환 단계에는 입력 범위(input range), 출력 요구사항(output requirements), 보호 동작(protection behavior), 기동 특성(startup characteristics), 종료 종속성(shutdown dependencies)이 정의되어야 한다.

전압 레일(voltage rails)은 불필요한 컨버터 종류, 커넥터 다양성, 예비 부품 복잡성 및 통합 오류를 줄이기 위해 가능한 범위에서 표준화되어야 한다. 각 레일에는 공칭 전압(nominal voltage), 허용 운전 범위(permitted operating range), 최대 예상 부하(maximum expected load), 과도 상태 요구사항(transient requirements), 보호 방식(protection method), 접지 기준(grounding reference), 지원 장비(supported equipment)가 정의되어야 한다. 승인된 기존 레일이 전기적 및 기능적 요구사항을 만족할 수 있는 경우 단순히 특정 부분의 편의를 위해 새로운 전압 레일을 추가해서는 안 된다.

전기 부하(electrical loads)는 기능과 중요도(criticality)에 따라 분류되어야 한다. 컴퓨팅 플랫폼(computing platforms), 인지 센서(perception sensors), 통신 장치(communication devices), 안전 제어기(safety controllers), 모터 드라이브(motor drives), 액추에이터(actuators), 조명(lighting), 보조 장비(auxiliary equipment), 서비스 부하(service loads)는 적절한 전력 분기(power branches)에 할당되어야 한다. 아키텍처 검토에서는 하나의 분기에서 발생한 고장, 과부하(overload), 단락(short circuit), 불안정한 부하가 제어, 인지, 통신 또는 안전 종료(safe shutdown)에 필요한 장비를 의도치 않게 비활성화할 가능성이 있는지 평가해야 한다.

고전류 및 노이즈 발생 부하(high-current and noise-generating loads)는 필요한 경우 민감한 저전압 전자장치(sensitive low-voltage electronics)와 아키텍처적으로 분리되어야 한다. 구동 모터(traction motors), 서보 드라이브(servo drives), 펌프(pumps), 압축기(compressors), 충전기(chargers), 인버터(inverters), 스위칭 전력 변환기(switching power converters)는 전도 및 방사성 노이즈(conducted and radiated disturbances)를 발생시킬 수 있다. 따라서 이들의 전력 경로(power paths), 귀환 경로(return paths), 스위칭 인터페이스(switching interfaces), 접지, 차폐(shielding), 필터링(filtering), 물리적 배선 경로(physical routing)는 센서, 통신 및 컴퓨팅 아키텍처와 조정되어야 한다.

보호 장치(protection devices)는 보호 대상인 도체(conductors), 부하(loads), 에너지원(energy sources), 고장 조건(fault conditions)에 따라 위치와 정격이 결정되어야 한다. 퓨즈(fuses), 회로 차단기(circuit breakers), 릴레이(relays), 접촉기(contactors), 전자식 스위치(electronic switches), 전력 분배 장치(power distribution units)는 공칭 운전 전류만을 기준으로 선정해서는 안 된다. 돌입 전류(inrush current), 과도 부하(transient loading), 전선 허용 용량(wire capacity), 단락 에너지(short-circuit energy), 차단 능력(interruption capability), 열 조건(thermal conditions), 고장 격리(fault isolation), 보호 협조(protection coordination)를 아키텍처 수준에서 고려해야 한다.

아키텍처는 해당되는 경우 보관(storage), 운송(transportation), 충전(charging), 대기(standby), 초기화(initialization), 정상 운전(normal operation), 성능 저하 운전(degraded operation), 비상 정지(emergency stopping), 정비(service), 종료(shutdown)를 위한 통제된 전원 상태(controlled power states)를 정의해야 한다. 전원 시퀀싱(power sequencing)은 제어되지 않은 액추에이터 작동과 정의되지 않은 제어기 상태를 방지해야 한다. 기동 또는 종료 순서가 시스템 동작에 영향을 주는 경우 컴퓨팅 노드, 센서, 통신 장치, 모터 드라이브, 안전 제어기 사이의 종속 관계(dependencies)를 문서화해야 한다.

통신 네트워크(communication networks)는 대역폭(bandwidth), 지연시간(latency), 결정성(determinism), 안전 관련성(safety relevance), 환경 강건성(environmental robustness), 진단 요구사항(diagnostic requirements), 서브시스템 호환성(subsystem compatibility)에 따라 할당되어야 한다. CAN, 이더넷(Ethernet), 산업용 네트워크(industrial networks), 직렬 링크(serial links), ROS 2 인터페이스(ROS 2 interfaces), 무선 통신(wireless communication)은 상호 조정된 아키텍처 구성 요소로 취급해야 한다. 네트워크 분할(network segmentation)과 게이트웨이 기능(gateway functions)은 불필요한 결합을 방지하면서 기능 도메인 사이에 필요한 정보가 전달될 수 있도록 해야 한다.

안전 관련 기능(safety-related functions)은 제품에 정의된 고장 가정(fault assumptions) 조건에서도 유효하게 유지되어야 한다. 비상 정지 회로(emergency-stop circuits), 액추에이터 활성화 경로(actuator enable paths), 안전 제어기(safety controllers), 안전 센서(safety sensors), 전원 격리 장치(power isolation devices), 워치독(watchdogs), 독립 종료 메커니즘(independent shutdown mechanisms)은 일반 애플리케이션 소프트웨어(ordinary application software)가 요구되는 안전 상태(safe state)를 달성하기 위한 유일한 수단이 되지 않도록 할당되어야 한다. 안전 종속성(safety dependencies)은 시스템 아키텍처에서 명확하게 확인할 수 있어야 하며 제품 안전 요구사항까지 추적 가능해야 한다.

이중화(redundancy)가 요구되는 경우 이중화된 요소들은 의도된 고장 허용 능력(fault tolerance)을 제공할 수 있도록 충분히 독립적이어야 한다. 동일한 비보호 전력 분기(unprotected power branch), 통신 스위치(communication switch), 커넥터(connector), 접지 고장 지점(grounding failure point) 또는 소프트웨어 종속성(software dependency)에 연결된 두 개의 장치는 효과적인 이중화로 인정되지 않을 수 있다. 따라서 이중화 전원, 제어기, 통신 경로, 센서, 안전 채널 또는 컴퓨팅 자원을 정의할 때 공통 원인 고장(common-cause failures)을 평가해야 한다.

접지(grounding)와 전자파 적합성(electromagnetic compatibility, EMC)은 EMC 시험 단계에서만 수정하는 항목이 아니라 아키텍처 속성(architectural properties)으로 정의되어야 한다. 섀시 기준(chassis references), 신호 기준(signal references), 전력 귀환(power returns), 차폐 종단 개념(shield termination concepts), 고전류 귀환 경로(high-current return paths), 절연 경계(isolation boundaries)는 하네스 배선 경로가 확정되기 전에 설정되어야 한다. 아키텍처는 통제되지 않은 접지 루프(ground loops)를 최소화하고 고에너지 스위칭 전류(high-energy switching currents)가 민감한 전자장치와 부적절한 귀환 경로를 공유하지 않도록 해야 한다.

서브시스템 사이의 인터페이스(interfaces)는 명시적으로 관리되어야 한다. 각 전기 인터페이스는 전원 핀(power pins), 신호 핀(signal pins), 통신 프로토콜(communication protocol), 접지 기준(grounding reference), 차폐 요구사항(shielding requirements), 커넥터 제품군(connector family), 전류 용량(current capability), 전압 허용 범위(voltage tolerance), 기동 동작(startup behavior), 진단 동작(diagnostic behavior), 필요한 경우 안전 분리 상태(safe disconnected state)를 정의해야 한다. 인터페이스 정의는 서로 독립적으로 개발된 모듈을 엔지니어링 팀 사이의 문서화되지 않은 가정에 의존하지 않고 통합할 수 있도록 해야 한다.

아키텍처는 적절한 교체 가능 장치(replaceable-unit) 또는 서브시스템 수준에서 고장을 식별할 수 있도록 충분한 진단 관측성(diagnostic observability)을 제공해야 한다. 주요 전압 레일, 보호 상태(protection states), 통신 링크(communication links), 제어기 상태(controller health), 센서 가용성(sensor availability), 액추에이터 고장(actuator faults), 온도 상태(temperature conditions), 안전 상태(safety states)는 진단 또는 서비스 측정을 통해 관측할 수 있어야 한다. 진단 기능은 현장 고장이 발생한 이후에 추가하는 것이 아니라 아키텍처에 처음부터 포함하여 설계해야 한다.

정비성(serviceability)은 전기적 분할(electrical partitioning)과 물리적 인터페이스 결정에 영향을 주어야 한다. 교체, 교정(calibration), 검사(inspection), 고장 진단(troubleshooting)이 예상되는 부품은 관련 없는 안전 중요 회로나 고전류 회로를 불필요하게 건드리지 않고 접근할 수 있어야 한다. 커넥터, 서비스 차단 장치(service disconnects), 측정 지점(measurement points), 라벨(labels), 하네스 분기(harness branches), 교체 가능 모듈(replaceable modules)은 통제된 유지보수를 지원하면서 잘못된 재연결 또는 구성 오류의 가능성을 줄여야 한다.

전기 아키텍처는 제품 수명주기 전체에 걸쳐 구성 식별(configuration identification)과 통제된 발전(controlled evolution)을 지원해야 한다. 하드웨어 개정(hardware revisions), 전압 변경, 네트워크 변경, 제어기 교체, 센서 추가, 커넥터 변경, 보호 설계 변경은 시스템 수준에서 영향을 평가해야 한다. 전력 용량, 통신 부하, 안전 동작, EMC 성능, 진단, 제조 또는 서비스 절차에 영향을 줄 수 있는 아키텍처 변경은 독립된 변경 사항으로 간주해서는 안 된다.

아키텍처 검증(architecture verification)은 제품 출시 전에 요구사항과 실제 구현 사이의 일관성을 확인해야 한다. 검토 과정에서는 전력 예산(power budgets), 전압 강하 가정(voltage-drop assumptions), 보호 협조, 네트워크 용량(network capacity), 기동 및 종료 동작, 접지 전략(grounding strategy), 이중화, 안전 경로(safety paths), 열 부하(thermal loading), 진단 범위(diagnostic coverage), 인터페이스 호환성(interface compatibility)을 평가해야 한다. 승인된 아키텍처 요구사항에서 벗어나는 사항은 문서화되고 기술적으로 정당화되며 검토된 후 구성 관리(configuration control)에 반영되어야 한다.

이러한 요구사항은 하네스(harnesses), 커넥터(connectors), 보호(protection), 접지(grounding), 통신(communication), 교정(calibration), 안전(safety), 제품별 로봇 아키텍처(product-specific robot architectures)를 다루는 후속 HRS 표준을 위한 공통 전기 아키텍처 기준선(common electrical architecture baseline)을 형성한다. 자율이동로봇(AMR), 매니퓰레이터(manipulator), 실외 차량(outdoor vehicles), 화물 무인항공기(cargo UAVs), 사족보행 로봇(quadrupeds), 휴머노이드(humanoids)는 추가적인 제약조건을 도입할 수 있지만, 승인된 엔지니어링 예외(engineering deviation)가 별도로 정의되지 않는 한 상세 전기 설계는 이 공통 아키텍처 프레임워크(common architecture framework)까지 추적 가능해야 한다.

## 01.03. Voltage Rail Standard

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

전압 레일 표준(voltage rail standard)은 로봇 제품 전반에서 사용되는 승인된 전원 공급 도메인(electrical supply domains)을 정의하고 각 도메인에 부하를 할당하기 위한 일관된 방법을 확립한다. 전압 레일(voltage rails)은 에너지 수준(energy level), 부하 특성(load characteristics), 변환 효율(conversion efficiency), 안전 요구사항(safety requirements), 부품 호환성(component compatibility), 시스템 아키텍처(system architecture)를 기준으로 선정해야 한다. 불필요한 전압 종류는 컨버터, 커넥터, 예비 부품, 검증 작업 및 통합 위험을 증가시키므로 최소화해야 한다.

각 전압 레일에는 공칭 전압(nominal voltage), 정상 운전 범위(normal operating range), 과도 상태 범위(transient range), 최대 연속 전류(maximum continuous current), 허용 피크 전류(allowable peak current), 보호 방식(protection method), 접지 기준(grounding reference), 전원 컨버터(source converter), 대상 부하 범주(intended load category)가 문서화되어야 한다. 또한 전기 아키텍처는 기동, 종료, 충전, 비상 정지, 저전압, 과전압, 과부하, 단락 및 주 에너지원 상실 시 각 레일의 예상 동작을 식별해야 한다.

주 전력 레일(primary power rail)은 일반적으로 배터리 시스템(battery system), 외부 직류 전원(external DC source) 또는 해당 로봇 플랫폼에 적합한 다른 통제된 에너지원(controlled energy source)에서 공급되어야 한다. 배터리 전압은 충전 상태(state of charge), 부하, 온도 및 화학계(chemistry)에 따라 크게 변할 수 있으므로 주 레일에 직접 연결되는 장비는 규정된 전체 운전 범위를 견딜 수 있어야 한다. 장비와 배터리의 공칭 전압이 동일해 보인다는 이유만으로 직접 연결이 가능하다고 가정해서는 안 된다.

48 V급 레일(48 V class rail)은 구동 드라이브(traction drives), 고출력 액추에이터(high-power actuators), 대형 서보 시스템(large servo systems), 펌프(pumps), 압축기(compressors) 및 상당한 전력이 필요한 기타 부하에 가능한 경우 적용하는 것이 바람직하다. 높은 배전 전압(distribution voltage)은 동일한 전력에서 전류를 감소시켜 도체 질량과 전압 강하를 줄일 수 있다. 정확한 허용 범위는 선택된 배터리, 구동 시스템, 충전 아키텍처, 보호 장치 및 제품별 안전 요구사항에 따라 정의해야 한다.

24 V급 레일(24 V class rail)은 24 V 호환성이 실질적인 통합 이점을 제공하는 산업용 제어 장비와 중간 출력 장치에 사용해야 한다. 대표적인 적용 대상으로 산업용 센서, 릴레이, 접촉기(contactors), 프로그래머블 제어기(programmable controllers), 입출력 모듈(I/O modules), 브레이크, 밸브, 보조 액추에이터 및 일부 통신 장비가 포함될 수 있다. 아키텍처는 동일한 전원을 공유하는 24 V 산업용 부하와 민감한 전자 부하 사이에서 통제되지 않은 상호작용이 발생하지 않도록 해야 한다.

12 V급 레일(12 V class rail)은 이 전압 등급으로 설계된 센서, 카메라, 통신 장치, 조명, 자동차 기반 장비(automotive-derived equipment) 및 보조 전자장치에 할당할 수 있다. 설계자는 12 V 제품으로 표시된 모든 장치가 동일한 전압 범위를 지원한다고 가정하지 말고 실제 장치의 허용 범위를 확인해야 한다. 레일 한계를 정의할 때 기동 돌입 전류(startup surge), 케이블 전압 강하, 과도 교란(transient disturbances), 역극성 노출(reverse polarity exposure), 컨버터 전압 조정(converter regulation)을 고려해야 한다.

5 V와 3.3 V 같은 저전압 레일(lower-voltage rails)은 주로 컴퓨팅 로직(computing logic), 임베디드 전자장치(embedded electronics), 인터페이스 회로(interface circuits), 저전력 센서 및 보드 수준 기능(board-level functions)에 사용한다. 이러한 레일은 일반적으로 높은 전류 상태로 긴 하네스를 통해 배전하기보다 부하 내부 또는 부하 가까이에서 생성해야 한다. 저전압 배전은 도체 저항, 커넥터 접촉 저항, 과도 부하 변화, 접지 전위차(grounding offsets), 전자기 간섭(electromagnetic interference)에 특히 민감하다.

전압 변환(voltage conversion)은 주 에너지원에서 낮은 전압 도메인 방향으로 통제된 계층 구조(controlled hierarchy)를 따라야 한다. 다단 변환(cascaded conversion)은 추가되는 각 컨버터가 효율 손실, 열 부하, 기동 종속성, 고장 모드 및 부품 복잡성을 증가시키므로 가능한 경우 최소화해야 한다. 다단 변환이 필요한 경우 아키텍처는 상위 및 하위 전원 사이의 종속성을 문서화하고 컨버터 시퀀싱(converter sequencing)이 의도하지 않은 전기 상태를 생성하지 않는지 확인해야 한다.

모든 레일에는 연속 부하(continuous load), 피크 부하(peak load), 기동 부하(startup load), 과도 부하(transient load)를 각각 고려한 적절한 전력 예산(power budget)이 포함되어야 한다. 장비의 공칭 정격을 단순히 합산하는 것만으로는 아키텍처 승인에 충분하지 않다. 모터 제어기, 컴퓨터, GPU, 라이다(LiDAR), 카메라, 통신 장치, 히터, 팬, 펌프 및 기타 부하는 동시에 피크 전력을 요구하거나 상당한 돌입 특성(inrush behavior)을 나타낼 수 있으므로 이를 시스템 수준 전력 분석에 반영해야 한다.

예측된 전력 요구량과 사용 가능한 레일 용량 사이에는 설계 여유(design margin)를 포함해야 한다. 필요한 여유는 부하 불확실성(load uncertainty), 제품 성숙도(product maturity), 환경 조건, 컨버터 특성 및 향후 확장 계획에 따라 달라질 수 있다. 미래 장비를 위해 확보한 용량은 문서화되지 않은 과대 설계에 숨기지 말고 명확하게 식별해야 한다. 아키텍처 검토에서는 실제로 사용 가능한 엔지니어링 여유(engineering margin)와 열 또는 보호 제한으로 인해 사용할 수 없는 용량을 구분해야 한다.

전압 강하(voltage drop)는 전원에서 전기 부하까지 관련 전류 조건에서 평가해야 한다. 분석에는 하네스 도체 저항(harness conductor resistance), 커넥터 접촉 저항(connector contact resistance), 퓨즈 및 릴레이 저항, 전력 분배 장치(PDU) 경로, 스위치, 접촉기, 서비스 차단 장치(service disconnects) 및 기타 직렬 구성 요소를 포함해야 한다. 부하에서 사용 가능한 전압은 전원 단자에서뿐만 아니라 정상 운전과 규정된 피크 조건에서도 장비의 운전 범위 내에 유지되어야 한다.

보호(protection)는 각 전압 레일과 그 하위 분기(downstream branches)에 맞추어 협조되어야 한다. 보호 장치는 연결된 장비뿐만 아니라 도체와 전기 경로도 보호해야 한다. 따라서 퓨즈 또는 회로 차단기의 정격은 전선 허용 용량(wire capacity), 연속 부하, 돌입 전류, 단락 전류(short-circuit current), 주변 온도, 차단 능력(interruption capability), 상위·하위 보호 선택성(upstream-downstream selectivity)을 고려해야 한다. 하위 분기에서 발생한 고장은 관련 없는 중요 기능까지 불필요하게 정지시키지 않고 격리되어야 한다.

공통 전원 고장이 허용할 수 없는 시스템 상태를 초래할 수 있는 경우 중요 부하(critical loads)와 비중요 부하(noncritical loads)를 분리하는 것이 바람직하다. 안전 제어기, 비상 정지 감시, 제동 기능, 필수 통신, 위치 추정 센서(localization sensors) 또는 안전 상태 도달에 필요한 컴퓨팅 자원은 전용 또는 독립적으로 보호되는 레일이 필요할 수 있다. 필요한 독립성은 하네스 배선 편의성이 아니라 안전 및 가용성 분석(safety and availability analysis)을 기준으로 결정해야 한다.

고전력 레일(high-power rails)과 민감한 전자장치 레일(sensitive electronic rails)은 전도성 노이즈(conducted noise), 스위칭 교란(switching disturbances), 접지 전위차 및 고장 전파를 제어하기 위해 분리해야 한다. 모터 드라이브와 인버터는 공칭 전압이 허용 범위에 있더라도 센서와 컴퓨터를 교란하는 급격한 전류 변화를 발생시킬 수 있다. 따라서 컨버터 배치, 귀환 전류 경로(return-current paths), 필터링, 접지, 차폐, 케이블 배선 및 물리적 분리를 전압 레일 아키텍처의 일부로 함께 조정해야 한다.

접지 기준 요구사항(ground reference requirements)은 모든 레일에 대해 명시적으로 정의해야 한다. 시스템 요구사항에 따라 레일은 공통 전력 귀환(common power return), 섀시 기준 귀환(chassis-referenced return), 절연 귀환(isolated return) 또는 다른 승인된 접지 구성을 사용할 수 있다. 기준 도메인(reference domains) 사이의 연결은 의도적으로 설계되고 문서화되어야 한다. 통제되지 않은 다중 연결은 접지 루프(ground loops)를 생성할 수 있으며, 부적절한 절연은 필요한 고장 전류 경로를 차단하거나 통신 기준 문제를 발생시킬 수 있다.

기동 및 종료 시퀀싱(startup and shutdown sequencing)은 각 레일이 다른 레일에 대해 언제 활성화되고 비활성화되는지를 정의해야 한다. 액추에이터 전원이 활성화되기 전에 제어기가 초기화되어야 할 수 있고, 자율 운전 시작 전에 센서가 안정화되어야 할 수 있으며, 통신 장비는 제어된 종료 과정에서 계속 동작해야 할 수 있다. 비상 정지 동작은 즉시 차단해야 하는 레일과 안전, 진단 또는 복구를 위해 계속 활성화해야 하는 레일을 별도로 정의해야 한다.

레일 상태(rail status)는 진단, 안전 또는 정비에 중요한 경우 관측 가능해야 한다. 전압, 전류, 컨버터 상태, 퓨즈 상태, 접촉기 상태, 저전압, 과전압, 과부하 및 온도 정보는 시스템 중요도에 따라 감시하는 것이 바람직하다. 가능한 경우 진단 소프트웨어(diagnostic software)는 전력 레일 상실과 개별 하위 장치의 고장을 구분할 수 있어야 하며, 이를 통해 고장 진단 과정에서 불필요한 부품 교체를 줄일 수 있다.

커넥터, 전선 식별(wire identification), 도면 및 서비스 문서는 제품 전체에서 전압 도메인의 식별성을 유지해야 한다. 서로 다른 전압 등급은 통제된 핀 할당(pin allocation), 커넥터 선정, 라벨링(labeling), 하네스 문서 및 인터페이스 정의를 통해 구별할 수 있어야 한다. 특히 잘못된 연결이 전자장치를 손상시키거나 위험한 상태를 만들 수 있는 경우 정비 인력이 전선 위치나 장비 외형만으로 전압을 추정하도록 해서는 안 된다.

새로운 전압 레일의 도입 또는 기존 레일의 변경은 아키텍처 수준 변경(architecture-level change)으로 취급해야 한다. 엔지니어링 검토에서는 전력 용량, 변환 효율, 보호, 배선, 커넥터, 접지, 전자파 적합성(EMC), 열 거동(thermal behavior), 진단, 안전, 제조, 정비성 및 기존 모듈과의 호환성을 평가해야 한다. 승인된 변경 사항은 아키텍처 다이어그램, 회로도, 하네스 도면, 인터페이스 사양 및 자재 명세서(bills of materials)에 일관되게 반영되어야 한다.

이 전압 레일 표준은 HRS 체계에 정의된 자율이동로봇(AMR), 매니퓰레이터(manipulator), 실외 차량(outdoor vehicles), 화물 무인항공기(cargo UAVs), 사족보행 로봇(quadrupeds), 휴머노이드(humanoids) 및 미래 로봇 플랫폼을 위한 공통 전력 도메인 기반(common power-domain foundation)을 제공한다. 제품별 표준은 기술적으로 필요한 경우 추가 전압 또는 더 높은 전압 도메인을 정의할 수 있지만, 모든 예외는 통제된 배전(controlled distribution), 정의된 운전 한계(defined operating limits), 보호 협조(protection coordination), 진단 가능성(diagnosability), 추적성(traceability), 안전한 시스템 통합(safe system integration)의 원칙을 유지해야 한다.

## 01.04. Redundancy Requirements

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

단일 전기 또는 전자 요소의 상실, 성능 저하 또는 오작동으로 인해 로봇이 허용 가능한 운전 상태 또는 안전 상태에 도달하거나 이를 유지할 수 없는 경우 이중화(redundancy)를 적용해야 한다. 이중화는 모든 부품에 일률적으로 적용되는 요구사항이 아니다. 이중화의 적용 여부는 기능 중요도(functional criticality), 위험 분석(hazard analysis), 가용성 목표(availability targets), 임무 요구사항(mission requirements), 복구 능력(recovery capability), 단일 고장(single-point failure)의 결과를 기준으로 결정해야 한다.

이중화 아키텍처(redundancy architecture)는 안전 관련 이중화(safety-related redundancy)와 가용성 중심 이중화(availability-oriented redundancy)를 구분해야 한다. 안전 이중화는 고장이 허용할 수 없는 위험 상태를 발생시키는 것을 방지하기 위한 것이며, 가용성 이중화는 고장 발생 후에도 시스템이 임무의 일부 또는 전부를 계속 수행할 수 있도록 한다. 따라서 고장 후 요구되는 동작은 안전 종료(safe shutdown), 제어된 성능 저하(controlled degradation), 고장 후 운전 유지(fail-operational operation) 또는 승인된 다른 시스템 대응으로 정의해야 한다.

이중화 아키텍처는 의도된 고장 허용 능력(fault tolerance)을 달성할 수 있도록 채널 사이에 충분한 독립성(independence)을 제공해야 한다. 동일한 비보호 전원, 퓨즈, 커넥터, 통신 스위치, 접지 경로, 클록 소스(clock source), 소프트웨어 프로세스 또는 환경 조건에 두 개의 동일한 부품이 의존한다면 단순히 부품을 두 개 설치한 것만으로는 효과적인 이중화를 제공할 수 없다. 공유 종속성(shared dependencies)은 명시적으로 식별하고 잠재적인 공통 고장 지점(common failure points)으로 평가해야 한다.

제어, 통신, 인지(perception), 제동, 안전 감시 또는 제어된 종료를 유지하기 위해 필요한 전기 기능에는 전원 이중화(power redundancy)를 고려해야 한다. 독립 전원 채널(independent power channels)이 요구되는 경우 각 채널은 적절한 전원 용량, 변환, 분배, 배선, 보호 및 감시 기능을 포함해야 한다. 공통 상위 구성 요소(common upstream component)가 존재하는 경우 해당 구성 요소의 고장이 시스템 안전 분석(system safety analysis)을 통해 허용 가능하다고 입증되지 않는 한 의도된 이중화를 무효화해서는 안 된다.

이중화 전원 공급 장치(redundant power supplies)는 고장 후 요구되는 운전 상태(post-failure operating state)에 따라 용량을 결정해야 한다. 비상 정지만을 지원하는 보조 전원(secondary supply)은 자율 운전을 계속 유지해야 하는 전원과 서로 다른 용량 요구사항을 가질 수 있다. 하나의 고장 난 전원이 정상 채널을 의도치 않게 비활성화하거나 과부하시키지 않도록 부하 분담(load sharing), 자동 절체(automatic transfer), 절연(isolation), 역전류 보호(reverse-current protection), 기동 시퀀싱(startup sequencing), 고장 감지(fault detection)를 정의해야 한다.

단일 네트워크 경로의 상실이 허용할 수 없는 시스템 상태를 초래하는 경우 통신 이중화(communication redundancy)를 적용해야 한다. 이중화 CAN 채널, 이더넷(Ethernet) 경로, 스위치, 게이트웨이 또는 기타 통신 링크는 필요한 경우 물리적 및 논리적으로 분리되어야 한다. 두 개의 통신 채널이 동일한 커넥터, 케이블 번들(cable bundle), 스위치, 게이트웨이 또는 전원을 통과하는 경우 해당 아키텍처를 이중화 구조로 인정하기 전에 공통 원인 고장(common-cause failure)을 평가해야 한다.

제어기 이중화(controller redundancy)는 복제된 제어기(duplicated controllers), 감독 제어기(supervisory controllers), 안전 제어기(safety controllers), 분산 제어(distributed control) 또는 기타 승인된 아키텍처를 사용할 수 있다. 설계에서는 정상 운전 중 어느 제어기가 제어 권한(control authority)을 가지는지, 불일치를 어떻게 감지하는지, 제어권을 어떻게 전환하는지, 두 채널이 서로 충돌하는 결과를 생성할 경우 어떻게 대응하는지를 정의해야 한다. 이중화 제어기는 초기화, 고장, 복구 또는 통신 상실 과정에서 액추에이터에 통제되지 않은 동시 명령을 발생시켜서는 안 된다.

센서 이중화(sensor redundancy)는 단순한 센서 수량의 중복이 아니라 의도된 시스템 상태를 유지하는 데 필요한 정보를 기준으로 설계해야 한다. 동일한 시야(field of view), 장착 구조, 전원, 환경 취약성(environmental susceptibility), 처리 알고리즘을 공유하는 동일 센서 두 개는 같은 고장 메커니즘에 동시에 영향을 받을 수 있다. 공통 모드 고장(common-mode failure)이 중요한 경우 센싱 원리(sensing principle), 위치, 처리 경로 또는 진단 방법의 다양성(diversity)을 고려하는 것이 바람직하다.

액추에이터 이중화(actuator redundancy)는 기계 아키텍처(mechanical architecture)와 요구되는 안전 동작에 따라 평가해야 한다. 일부 로봇은 액추에이터 토크를 제거함으로써 안전을 확보할 수 있지만, 다른 로봇은 고장 이후에도 제어된 제동(controlled braking), 유지력(holding force), 조향 제어 능력(steering authority) 또는 지속적인 자세 안정화가 필요할 수 있다. 따라서 모터 드라이브, 브레이크, 조향 시스템, 관절 액추에이터 및 활성화 회로(enable circuits)의 전기적 이중화 요구사항은 로봇에 요구되는 물리적 대응으로부터 도출해야 한다.

독립 채널을 요구하는 안전 기능은 일반 제어 소프트웨어가 의도된 보호 동작을 무력화할 수 없도록 설계해야 한다. 비상 정지 회로(emergency-stop circuits), 안전 제어기, 액추에이터 활성화 경로(actuator enable paths), 접촉기(contactors), 브레이크, 워치독(watchdogs), 안전 센서에는 독립적인 전기 경로가 필요할 수 있다. 안전 관련 이중화는 필요한 경우 주 컴퓨팅 플랫폼, 애플리케이션 소프트웨어, 주 통신 네트워크 또는 비안전 전력 도메인(non-safety power domain)의 고장 중에도 유효하게 유지되어야 한다.

이중화 채널에는 고장 감지(fault detection)와 채널 상태 감시(channel health monitoring) 메커니즘이 포함되어야 한다. 전압 상태, 통신 가용성, 제어기 하트비트(controller heartbeat), 센서 타당성(sensor plausibility), 액추에이터 피드백, 보호 상태 및 기타 관련 지표는 시스템 중요도에 따라 감시하는 것이 바람직하다. 감지되지 않은 상태로 고장 날 수 있는 이중화 요소는 시스템이 가정된 고장 허용 능력을 상실한 상태로 운전될 수 있으므로 잠재 고장(latent-fault) 문제로 취급해야 한다.

독립 채널이 서로의 동작을 검증해야 하는 경우 상호 감시(cross-monitoring)를 사용해야 한다. 감시 메커니즘은 이중화 채널 사이에 과도한 결합을 발생시키지 않으면서 불일치를 감지할 수 있어야 한다. 한 채널이 다른 채널을 감시하는 경우 감시 채널의 고장이 정상 채널을 잘못 비활성화하거나 위험한 고장을 은폐할 가능성이 있는지 고려해야 한다. 진단 독립성(diagnostic independence)은 기능적 독립성(functional independence)과 함께 평가해야 한다.

공통 원인 고장 분석(common-cause failure analysis)은 전기적, 기계적, 환경적, 소프트웨어적, 제조 및 설치상의 종속성을 고려해야 한다. 동일한 하네스 구간을 통과하는 이중화 채널은 마모, 열, 수분 침투(water ingress) 또는 기계적 충격으로 동시에 손상될 수 있다. 마찬가지로 동일한 장치는 펌웨어 결함이나 전자기 간섭(electromagnetic interference)에 대한 동일한 취약성을 공유할 수 있다. 요구되는 무결성(integrity)에 따라 필요한 경우 물리적 분리(physical separation) 또는 기술적 다양성(technological diversity)을 적용해야 한다.

고장 격리 경계(fault containment boundaries)는 하나의 이중화 채널에서 발생한 고장이 다른 채널로 전파되는 것을 방지해야 한다. 단락, 과전압, 역전류, 접지 고장, 통신 버스 고장, 열적 이상(thermal events), 잘못된 제어 출력 등을 고려해야 한다. 전기 아키텍처에 적합한 개별 보호(separate protection), 독립 컨버터(independent converters), 갈바닉 절연(galvanic isolation), 통신 분할(communication segmentation), 통제된 게이트웨이(controlled gateways) 또는 기타 메커니즘을 통해 적절한 격리를 제공할 수 있다.

시스템은 이중화가 상실되었을 때의 동작을 결정론적으로 정의해야 한다. 제품 요구사항에 따라 로봇은 제한된 시간 동안 정상 운전을 지속하거나, 성능 저하 운전(degraded operation)으로 전환하거나, 속도를 낮추거나, 움직임을 제한하거나, 특정 기능을 비활성화하거나, 지정된 위치로 복귀하거나, 운영자 개입을 요청하거나, 제어된 정지(controlled stop)를 수행할 수 있다. 남아 있는 채널이 정상으로 보인다는 이유만으로 이중화 상실 이후 운전을 계속해서는 안 되며, 이러한 운전은 명시적으로 승인되어야 한다.

고장 난 이중화 채널의 복구 및 재통합(reintegration)은 통제되어야 한다. 수리되거나 재시작되었거나 일시적으로 사용할 수 없었던 채널은 상태, 구성(configuration), 통신 상태, 동기화(synchronization), 진단 상태가 확인되기 전까지 자동으로 제어 권한을 다시 획득해서는 안 된다. 자동 재통합이 허용되는 경우 전환 조건과 로직은 액추에이터 명령, 네트워크 소유권(network ownership), 전력 부하 또는 안전 상태가 갑작스럽게 변경되지 않도록 해야 한다.

이중화 요구사항에는 유지보수와 진단에 대한 고려가 포함되어야 한다. 대기 상태의 백업 채널(standby backup channels)은 장기간 시험되지 않은 상태로 남아 있을 수 있기 때문이다. 내장 시험(built-in tests), 주기적 점검(periodic checks), 기동 진단(startup diagnostics), 검증 시험(proof tests) 또는 계획된 유지보수를 통해 대기 자원이 정상적으로 기능하는지 확인해야 한다. 진단 범위(diagnostic coverage)와 시험 주기는 특히 다중 고장이 안전 관련 아키텍처를 무력화할 수 있는 경우 잠재 고장의 발생 가능성과 결과를 반영해야 한다.

검증(verification)은 정의된 단일 고장 및 적용 가능한 다중 고장 조건에서 요구되는 각 이중화 기능이 계속 유효함을 입증해야 한다. 시험에는 필요에 따라 전원 채널, 통신 링크, 제어기, 센서, 액추에이터, 보호 장치 및 감시 기능의 상실을 포함해야 한다. 고장 주입(fault injection), 인터페이스 분리(interface disconnection), 통신 상실 모사, 저전압 및 통제된 부품 고장을 사용하여 고장 감지, 격리, 상태 전환 및 복구 동작을 검증할 수 있다.

이중화 아키텍처에 영향을 미치는 모든 변경은 시스템 수준 변경(system-level change)으로 취급해야 한다. 전력 컨버터, 네트워크 스위치, 커넥터, 제어기, 센서, 하네스 경로, 접지 구성, 펌웨어 구성 요소 또는 진단 메커니즘의 변경은 이전에 존재하지 않았던 공통 종속성(common dependency)을 발생시킬 수 있다. 따라서 변경 검토에서는 독립성, 고장 격리, 진단 범위, 성능 저하 동작, 기존 이중화 요구사항 준수 여부를 다시 평가해야 한다.

이러한 이중화 요구사항은 HRS 체계 내의 자율이동로봇(AMR), 매니퓰레이터(manipulator), 실외 차량(outdoor vehicles), 화물 무인항공기(cargo UAVs), 사족보행 로봇(quadrupeds), 휴머노이드(humanoids) 및 기타 로봇 플랫폼을 위한 공통 프레임워크를 제공한다. 제품별 표준은 임무 및 안전 요구에 따라 필요한 이중화 수준을 결정해야 하며, 동시에 독립성(independence), 고장 감지(fault detection), 고장 격리(fault containment), 결정론적 성능 저하(deterministic degradation), 통제된 복구(controlled recovery), 검증(verification), 추적성(traceability)의 원칙을 유지해야 한다.

## 01.05. Change Control

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

변경 관리(change control)는 제품 수명주기(product lifecycle) 전체에 걸쳐 전기 아키텍처(electrical architecture)의 변경 사항이 통제된 방식으로 평가, 승인, 문서화, 구현 및 검증되도록 해야 한다. 변경 사항이 전력 분배(power distribution), 인터페이스, 통신, 안전, 진단, 제조, 교정(calibration), 소프트웨어 구성(software configuration), 서비스 절차 또는 출시된 제품과의 호환성에 영향을 줄 수 있는 경우 이를 단순한 국부적 엔지니어링 작업(local engineering action)으로 취급해서는 안 된다.

관리 기준선(controlled baseline)에는 승인된 전기 아키텍처, 회로도(schematics), 하네스 도면(harness drawings), 인터페이스 사양(interface specifications), 커넥터 정의(connector definitions), 전압 레일(voltage rails), 보호 설정(protection settings), 통신 토폴로지(communication topology), 접지 전략(grounding strategy), 자재 명세서(bills of materials), 교정 정보(calibration information), 관련 소프트웨어 또는 펌웨어 구성(firmware configurations)이 포함되어야 한다. 출시된 각 기준선에는 식별 가능한 개정 번호(revision)가 있어야 하며, 이를 통해 시제품, 시험 장비, 양산 로봇 또는 현장 운용 장비의 정확한 구성을 재구성할 수 있어야 한다.

변경 요청(change request)은 제안된 변경 사항, 변경 사유, 영향을 받는 제품 또는 서브시스템, 예상되는 기술적 이점 또는 해결하려는 문제를 명확하게 설명해야 한다. 변경 요청에는 설계 개선(design improvement), 부품 단종(component obsolescence), 공급업체 대체(supplier substitution), 현장 고장(field failure), 안전 문제(safety concern), 제조 문제(manufacturing issue), 원가 절감(cost reduction), 규제 요구사항(regulatory requirement), 성능 개선(performance improvement) 또는 기타 문서화된 엔지니어링 필요사항 중 어떤 사유로 변경이 발생했는지를 식별하는 것이 바람직하다.

변경 사항은 변경되는 부품의 물리적 크기나 비용만을 기준으로 하지 않고 잠재적인 시스템 영향(system impact)에 따라 분류해야 한다. 작은 커넥터, 퓨즈, 센서, 컨버터, 저항, 네트워크 장치 또는 소프트웨어 파라미터의 교체도 중대한 아키텍처 영향을 발생시킬 수 있다. 변경 분류에서는 안전, 기능, 인터페이스 호환성(interface compatibility), 전기 부하(electrical loading), 전자파 적합성(EMC), 신뢰성, 제조, 정비성(serviceability), 기존 운용 제품군(installed base)에 대한 영향을 고려해야 한다.

아키텍처와 관련된 모든 변경을 승인하기 전에 엔지니어링 영향 분석(engineering impact analysis)을 완료해야 한다. 분석에서는 해당되는 경우 영향을 받는 전압 레일, 전류 요구량, 전력 예산(power budgets), 보호 협조(protection coordination), 전압 강하(voltage drop), 접지, 열 부하(thermal loading), 통신 대역폭, 타이밍, 진단, 기동 및 종료 동작, 안전 기능, 이중화(redundancy), 기계적 패키징(mechanical packaging), 하네스 배선 경로, 커넥터, 교정, 소프트웨어 및 검증 요구사항을 식별해야 한다.

전압 레일 또는 전력 분배 변경은 전원 용량(source capacity), 컨버터 정격(converter rating), 도체 허용 용량(conductor capacity), 커넥터 전류 용량, 퓨즈 협조(fuse coordination), 돌입 전류(inrush current), 과도 상태 동작(transient behavior), 열 성능(thermal performance), 하위 장치 호환성(downstream compatibility)을 검토해야 한다. 공칭 부하에서 허용 가능한 것으로 보이는 변경이라도 피크, 기동, 고장 및 성능 저하 운전 조건과 필요한 엔지니어링 여유(engineering margin)를 함께 고려하기 전에는 승인해서는 안 된다.

이중화에 영향을 미치는 변경은 독립성(independence)과 공통 원인 고장(common-cause failures)을 검토해야 한다. 전원 공급 장치, 제어기, 스위치, 커넥터, 센서, 하네스 경로 또는 접지 구성의 변경으로 이전에는 독립적이었던 채널 사이에 공유 종속성(shared dependency)이 발생할 수 있다. 검토에서는 고장 감지(fault detection), 고장 격리(fault containment), 성능 저하 운전(degraded operation), 안전 상태 전환(safe-state transition), 복구 동작 및 진단 범위(diagnostic coverage)가 승인된 이중화 개념과 일관성을 유지하는지 확인해야 한다.

통신 변경은 물리적 아키텍처와 논리적 아키텍처를 모두 평가해야 한다. CAN, 이더넷(Ethernet), 직렬 링크(serial links), 게이트웨이, 스위치, 무선 인터페이스, ROS 2 통신, 주소 지정(addressing), 메시지 정의(message definitions), 네트워크 부하(network loading) 또는 타이밍의 변경은 여러 서브시스템에 동시에 영향을 줄 수 있다. 기존 노드 및 진단 도구와의 호환성을 검증해야 하며, 통신 인터페이스 변경 사항은 해당 관리 대상 인터페이스 문서(controlled interface documentation)에 반영해야 한다.

안전 관련 변경(safety-related changes)은 잠재적인 위험 영향(hazard impact)에 적합한 수준의 검토를 받아야 한다. 비상 정지 기능(emergency-stop functions), 안전 제어기(safety controllers), 액추에이터 활성화 회로(actuator enable circuits), 브레이크, 접촉기(contactors), 안전 센서, 워치독(watchdogs), 절연 장치(isolation devices) 또는 안전 통신(safety communication)과 관련된 변경은 적용되는 안전 요구사항까지 추적 가능해야 한다. 기존 위험 분석(hazard analyses)과 검증 증거(verification evidence)를 검토하여 계속 유효한지 또는 개정이 필요한지를 판단해야 한다.

대체 부품이 유사한 공칭 사양을 가지고 있다는 이유만으로 부품 대체(component substitution)를 승인해서는 안 된다. 운전 범위, 과도 상태 허용 능력(transient tolerance), 커넥터 인터페이스, 핀 할당(pin assignment), 열적 거동, EMC 특성, 기동 동작, 펌웨어, 통신 타이밍, 진단, 환경 등급(environmental rating), 수명 및 고장 모드(failure modes)의 차이를 평가해야 한다. 형상(form), 장착 적합성(fit), 공칭 기능(nominal function)의 일치만으로는 완전한 전기적 또는 시스템 호환성을 입증할 수 없다.

공급업체 주도 변경(supplier-driven changes)도 내부에서 시작된 변경과 동일한 엔지니어링 관리(engineering control)를 적용해야 한다. 제조사 부품 개정(manufacturer part revisions), 공정 변경(process changes), 재료 대체(material substitutions), 펌웨어 업데이트, 단종 통보(end-of-life notifications), 대체 공급원 제안(alternate-source proposals)은 공급업체가 동일한 상용 부품 번호를 유지하는 경우에도 제품 동작을 변경할 수 있다. 따라서 중요 부품에는 시스템 영향에 적합한 변경 통보(notification), 적격성 평가(qualification), 승인 요구사항을 정의하는 것이 바람직하다.

시제품, 실험, 고장 진단 또는 현장 조사를 위해 사용하는 임시 변경(temporary modifications)은 공식 출시된 양산 변경과 별도로 식별해야 한다. 임시 배선, 바이패스(bypasses), 대체 부품, 변경된 퓨즈 정격, 진단 어댑터(diagnostic adapters) 또는 소프트웨어 오버라이드(software overrides)가 비공식적인 반복 적용을 통해 양산 설계로 이전되어서는 안 된다. 임시 변경의 목적, 적용 기간, 대상 장비, 위험 및 원상 복구 조건을 문서화해야 하며, 임시 예외는 종료하거나 공식적으로 승인된 변경으로 전환해야 한다.

승인된 모든 변경에는 명확한 적용 범위(implementation applicability)가 정의되어야 한다. 변경 기록에는 신규 설계에만 적용되는지, 향후 생산 장비에 적용되는지, 특정 일련번호(serial number) 이후 장비에 적용되는지, 일부 시제품, 서비스 교체품 또는 기존 운용 제품 전체에 적용되는지를 명시해야 한다. 개조(retrofit)가 필요한 경우 대상 제품군, 개조 방법, 필요한 부품, 소프트웨어 호환성, 검증 절차 및 완료 기록을 관리해야 한다.

여러 하드웨어 또는 소프트웨어 개정 버전이 동시에 존재할 수 있는 경우 구성 호환성(configuration compatibility)을 평가해야 한다. 조직은 어떤 제어기, 센서, 하네스, 전력 분배 장치(PDU), 펌웨어, 소프트웨어, 교정 데이터 및 통신 버전의 조합이 함께 운용될 수 있는지를 결정해야 한다. 개별적으로는 기술적으로 유효한 부품들이 조합되었을 때 유효하지 않은 시스템 구성이 만들어지는 것을 방지하기 위해 필요한 경우 호환성 매트릭스(compatibility matrices) 또는 이에 상응하는 구성 규칙(configuration rules)을 유지하는 것이 바람직하다.

문서 업데이트(documentation updates)는 구현 이후 별도로 수행하는 작업이 아니라 변경 자체의 일부가 되어야 한다. 아키텍처 다이어그램, 회로도, 하네스 도면, 커넥터 표(connector tables), 인터페이스 관리 문서(interface control documents), 자재 명세서, 소프트웨어 구성 기록, 교정 데이터, 시험 절차, 제조 지침, 서비스 매뉴얼 및 진단 정보는 해당되는 경우 개정되어야 하며, 변경된 구성이 완전히 출시된 것으로 간주되기 전에 이러한 문서 개정이 완료되어야 한다.

검증 요구사항(verification requirements)은 영향 분석 결과에 따라 결정해야 한다. 변경 사항에 따라 검사(inspection), 전기 측정(electrical measurement), 기능 시험(functional testing), 통신 시험, 고장 주입(fault injection), EMC 시험, 환경 시험(environmental testing), 안전 검증(safety validation), 회귀 시험(regression testing) 또는 현장 평가(field evaluation)가 필요할 수 있다. 검증은 변경된 기능이 정상적으로 동작하는 것뿐만 아니라 변경의 영향을 받는 기존 승인 기능도 계속 요구사항을 만족한다는 것을 입증해야 한다.

회귀 시험(regression testing)은 간접적으로 영향을 받을 수 있는 인터페이스와 기능에 중점을 두어야 한다. 새로운 컨버터는 EMC 특성을 변경할 수 있고, 커넥터 변경은 전압 강하에 영향을 줄 수 있으며, 펌웨어 업데이트는 기동 타이밍을 변경할 수 있고, 센서 교체는 네트워크 부하 또는 교정에 영향을 줄 수 있다. 따라서 검증 계획은 변경 요청에 명시된 부품이나 기능만 시험하는 것이 아니라 합리적으로 예상 가능한 2차 영향(secondary effects)까지 다루어야 한다.

변경 승인 권한(change approval authority)은 변경의 중요도에 따라 결정해야 한다. 아키텍처 또는 안전에 영향을 주지 않는 경미한 변경은 간소화된 승인 절차를 따를 수 있지만, 안전, 주 전원(primary power), 이중화, 통신 아키텍처, 중요 인터페이스 또는 출시되어 현장에서 운용 중인 장비에 영향을 미치는 변경은 다분야 검토(multidisciplinary review)가 필요하다. 식별된 영향에 따라 전기, 기계, 소프트웨어, 안전, 제조, 품질, 시험 및 서비스 관련 조직이 검토에 참여하는 것이 바람직하다.

추적성(traceability)은 최초 문제 또는 요구사항을 변경 요청, 엔지니어링 분석, 승인 결정, 수정된 설계 산출물(design artifacts), 검증 증거, 출시 기록(release record), 영향을 받는 제품 구성까지 연결해야 한다. 이러한 추적성을 통해 향후 엔지니어는 무엇이 변경되었는지뿐만 아니라 왜 변경되었는지, 어떤 대안이 검토되었는지, 어떤 위험이 식별되었는지, 최종 엔지니어링 결정을 뒷받침한 증거가 무엇이었는지를 확인할 수 있어야 한다.

구현 이후 중요한 변경 사항에 대해서는 예상하지 못한 현장, 생산 또는 서비스 영향을 검토하는 것이 바람직하다. 초기 생산 결과, 진단 로그(diagnostic logs), 고장 보고서(failure reports), 제조 피드백 및 서비스 정보는 분석 단계에서 식별되지 않은 상호작용을 드러낼 수 있다. 새로운 증거를 통해 기존 가정이 잘못된 것으로 확인된 경우 문서화되지 않은 시정 조치에 의존하지 말고 기존 변경 건을 다시 검토하거나 새로운 통제된 변경(controlled change)을 시작해야 한다.

HRS 변경 관리 프로세스(HRS change-control process)는 엔지니어링 표준 체계에 정의된 자율이동로봇(AMR), 매니퓰레이터(manipulator), 실외 차량(outdoor vehicles), 화물 무인항공기(cargo UAVs), 사족보행 로봇(quadrupeds), 휴머노이드(humanoids) 및 기타 로봇 플랫폼 전반에 적용되어야 한다. 그 목적은 제품의 발전을 허용하면서 아키텍처 무결성(architectural integrity)을 보존하고, 모든 중요한 변경이 기술적으로 정당화되고, 구성 관리(configuration-controlled)되며, 검증 가능하고, 추적 가능하며, 해당 시스템의 안전 및 수명주기 요구사항과 호환되도록 하는 것이다.
