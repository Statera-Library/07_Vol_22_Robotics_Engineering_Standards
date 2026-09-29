**Volume 22. Hills Robotics Engineering Standards**


# Chapter 11. HRS-011 Outdoor Vehicle

##  

## 11.01. Outdoor EE Architecture

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

The outdoor vehicle electrical and electronic architecture shall define a modular, fault-aware platform capable of supporting autonomous operation under weather, vibration, temperature, contamination, and communication conditions that are substantially more demanding than those of indoor AMRs. The architecture shall integrate propulsion, steering, braking, sensing, computation, communication, power distribution, diagnostics, and safety functions while maintaining clear electrical and functional boundaries between subsystems.

The architecture shall be organized into functional domains that include the traction and drive-by-wire domain, autonomous computing domain, perception domain, localization domain, safety domain, communication domain, and electrical power domain. Interfaces between these domains shall be explicitly defined so that changes to sensors, computing platforms, batteries, or actuators can be implemented without unnecessary redesign of the complete vehicle electrical system.

A controlled DC power architecture shall distribute battery energy to propulsion equipment, steering and braking actuators, computing units, sensors, communication devices, and auxiliary loads. High-current propulsion branches shall be electrically separated from noise-sensitive electronics wherever practical. Protected low-voltage rails shall be provided through appropriately rated DC/DC converters, fuses, circuit breakers, contactors, or electronic protection devices according to load criticality and expected fault current.

The main battery interface shall include isolation, overcurrent protection, controlled connection and disconnection, emergency shutdown capability, and battery-management communication. Power distribution shall prevent a failure in a noncritical auxiliary load from disabling steering, braking, safety sensing, or the supervisory controller. Voltage drop, transient behavior, inrush current, regenerative energy, grounding paths, thermal loading, and connector current capability shall be evaluated for both nominal and worst-case operating conditions.

Drive-by-wire functions shall provide controlled electrical interfaces to propulsion, steering, and braking systems. Commands originating from autonomous software shall pass through defined control interfaces rather than directly manipulating power-stage hardware. Each critical actuator interface shall support command validation, state feedback, diagnostic information, timeout supervision, and transition to a predefined safe behavior when communication, power, sensor feedback, or controller integrity is lost.

Autonomous computing shall be separated logically from deterministic vehicle control. High-performance computers or AI accelerators may execute perception, localization, planning, mapping, and intelligent decision functions, while dedicated controllers shall maintain time-critical vehicle control and safety supervision. A failure, reboot, overload, or software update of the autonomous computer shall therefore not create uncontrolled propulsion, steering, or braking behavior.

The perception architecture shall accommodate outdoor sensors such as cameras, depth cameras, 2D or 3D LiDAR, radar, ultrasonic sensors, and application-specific inspection devices. Sensor power branches shall be individually protected or grouped according to functional dependency. Interfaces shall consider bandwidth, synchronization, environmental sealing, cable length, electromagnetic compatibility, mounting location, serviceability, and the ability to isolate a defective sensor without unnecessarily disabling other perception functions.

Outdoor localization shall support GNSS and, where required, RTK correction together with IMU, wheel odometry, steering feedback, and perception-based localization. GNSS antennas and receivers shall be installed with appropriate power integrity, grounding, shielding, and electromagnetic separation from switching converters, motors, high-current cables, radios, and other interference sources. Localization data shall include validity and quality information so that degraded positioning can be detected before it affects autonomous motion.

Communication networks shall be selected according to determinism, bandwidth, diagnostic needs, environmental robustness, and safety relevance. CAN or CAN FD may support distributed controllers and vehicle-level signals, while Ethernet may support high-bandwidth sensors, computing systems, diagnostics, and data logging. ROS 2 or equivalent software middleware may operate above the physical network, but software communication shall not replace the electrical safeguards required for critical vehicle control.

Time synchronization shall be treated as an architectural function when multiple cameras, LiDARs, IMUs, GNSS receivers, radar sensors, and computing nodes contribute to perception or localization. GNSS-derived timing, PTP, hardware triggering, or equivalent mechanisms shall be selected according to required accuracy. Timestamp origin, clock ownership, synchronization loss detection, and degraded operation shall be defined so recorded and real-time sensor information remains temporally consistent.

The safety architecture shall remain independent enough to supervise autonomous functions even when the primary computing path becomes unavailable. Emergency-stop circuits, safety controllers, safety sensors, brake interfaces, propulsion inhibit functions, and relevant contactors shall form a defined safety chain. Activation of an emergency condition shall place the vehicle into a controlled safe state without relying solely on the operating system, ROS 2 software, AI model, or central autonomous computer.

Environmental design shall address rain, water spray, dust, mud, condensation, solar heating, low temperature, vibration, shock, corrosion, and repeated mechanical loading. Electrical enclosures, connectors, harness transitions, antennas, sensor interfaces, and service points shall use protection levels appropriate to their mounting zones. Drainage, sealing, cable glands, strain relief, connector orientation, and prevention of water accumulation shall be considered as part of the electrical architecture rather than as packaging details alone.

Grounding and EMC design shall establish controlled return paths for propulsion electronics, computing equipment, sensors, communication interfaces, and chassis bonding. High-current motor and inverter paths shall be routed to minimize coupling into GNSS, IMU, camera, LiDAR, Ethernet, and other sensitive circuits. Shield termination, chassis bonding, filtering, cable separation, common-mode control, and grounding topology shall be defined consistently across the vehicle and verified during integration.

The architecture shall support diagnostics at component, network, power-domain, and vehicle levels. Controllers shall report relevant faults, communication status, supply voltage, temperature, actuator state, and sensor validity where available. Diagnostic information shall be timestamped and correlated with vehicle operating states so intermittent outdoor failures can be reconstructed from logs. Service interfaces shall allow technicians to identify faults without unnecessary disassembly or uncontrolled bypassing of protection functions.

Availability requirements shall distinguish between faults that require immediate stopping and faults that permit degraded operation. Loss of a nonessential camera, communication link, auxiliary sensor, or inspection payload may allow restricted operation when supported by the safety concept, whereas loss of braking authority, critical steering feedback, safety supervision, or required localization integrity shall initiate an appropriate safe-state response. Degradation rules shall be explicitly assigned rather than inferred by application software.

The electrical architecture shall support product scalability from basic outdoor AMRs to inspection, patrol, agriculture, mining, port, or other autonomous vehicle variants. Optional sensors, communication modules, payload interfaces, computing tiers, and auxiliary power outputs should therefore use standardized interfaces whenever practical. Expansion capacity shall be considered for PDU channels, network ports, compute power, communication bandwidth, connector positions, and thermal capability without compromising existing safety margins.

Harnesses and connectors shall be selected for outdoor mechanical and environmental exposure and shall support manufacturing, inspection, replacement, and field maintenance. High-current, communication, sensor, antenna, and safety circuits shall be identified through controlled drawings and interface definitions. Connector keying, locking, polarization, environmental rating, current derating, shielding, bend radius, abrasion protection, and routing near moving mechanisms shall be addressed during architecture release.

The released outdoor E/E architecture shall be controlled through system diagrams, power budgets, network definitions, interface-control information, protection assignments, grounding requirements, safety dependencies, and approved component configurations. Any change affecting voltage rails, safety paths, network topology, actuator interfaces, sensor timing, grounding, protection devices, or power capacity shall undergo engineering review so that local modifications do not introduce unintended vehicle-level hazards.

Verification shall demonstrate correct operation during startup, normal driving, autonomous operation, charging, shutdown, emergency stopping, communication loss, sensor degradation, controller reset, undervoltage, and representative electrical faults. Testing shall also confirm power integrity, network behavior, diagnostic coverage, environmental robustness, EMC performance, and safe-state transitions. Results shall remain traceable to architecture requirements and the approved hardware and software configuration.

The final architecture shall provide a common engineering foundation connecting the outdoor vehicle requirements with the broader Hills Robotics standards for electrical architecture, harness design, connector selection, fuse protection, grounding, communication, calibration, and safety. The objective is not merely to interconnect vehicle components, but to establish a repeatable E/E platform in which autonomy, power, sensing, communication, diagnostics, and safety remain controlled throughout development, production, field operation, and future product evolution.

옥외 차량 전기·전자 아키텍처(Outdoor Vehicle Electrical and Electronic Architecture)는 실내 자율이동로봇(Indoor AMR)보다 훨씬 가혹한 기상, 진동, 온도, 오염 및 통신 조건에서도 자율 운행(Autonomous Operation)을 지원할 수 있는 모듈형(Modular) 및 고장 인지형(Fault-Aware) 플랫폼으로 정의되어야 한다. 이 아키텍처는 추진(Propulsion), 조향(Steering), 제동(Braking), 센싱(Sensing), 컴퓨팅(Computing), 통신(Communication), 전력 분배(Power Distribution), 진단(Diagnostics) 및 안전(Safety) 기능을 통합하는 동시에 각 서브시스템(Subsystem) 사이의 명확한 전기적·기능적 경계를 유지해야 한다.

아키텍처는 구동 및 드라이브 바이 와이어(Drive-by-Wire) 도메인, 자율 컴퓨팅(Autonomous Computing) 도메인, 인지(Perception) 도메인, 위치 추정(Localization) 도메인, 안전(Safety) 도메인, 통신(Communication) 도메인 및 전력(Electrical Power) 도메인을 포함하는 기능 영역으로 구성되어야 한다. 이러한 도메인 간 인터페이스(Interface)는 명확하게 정의되어 센서, 컴퓨팅 플랫폼, 배터리 또는 액추에이터(Actuator)의 변경 시 전체 차량 전기 시스템을 불필요하게 재설계하지 않도록 해야 한다.

제어된 직류 전력 아키텍처(DC Power Architecture)는 배터리 에너지를 추진 장치, 조향 및 제동 액추에이터, 컴퓨팅 장치, 센서, 통신 장치 및 보조 부하(Auxiliary Load)에 분배해야 한다. 고전류 추진 회로는 가능한 경우 노이즈에 민감한 전자장치와 전기적으로 분리해야 한다. 보호된 저전압 레일(Low-Voltage Rail)은 부하의 중요도와 예상 고장 전류에 따라 적절한 정격의 DC/DC 컨버터(DC/DC Converter), 퓨즈(Fuse), 회로 차단기(Circuit Breaker), 접촉기(Contactor) 또는 전자식 보호 장치를 통해 공급되어야 한다.

주 배터리 인터페이스(Main Battery Interface)는 절연(Isolation), 과전류 보호(Overcurrent Protection), 제어된 연결 및 차단, 비상 차단(Emergency Shutdown) 기능과 배터리 관리 통신(Battery-Management Communication)을 포함해야 한다. 전력 분배 시스템은 비핵심 보조 부하의 고장이 조향, 제동, 안전 센싱 또는 감독 제어기(Supervisory Controller)를 비활성화하지 않도록 설계해야 한다. 전압 강하, 과도 상태(Transient Behavior), 돌입 전류(Inrush Current), 회생 에너지(Regenerative Energy), 접지 경로, 열 부하 및 커넥터 전류 용량은 정상 조건과 최악 조건 모두에서 평가되어야 한다.

드라이브 바이 와이어(Drive-by-Wire) 기능은 추진, 조향 및 제동 시스템에 대한 제어된 전기 인터페이스를 제공해야 한다. 자율주행 소프트웨어(Autonomous Software)에서 발생하는 명령은 전력단 하드웨어(Power-Stage Hardware)를 직접 제어하는 대신 정의된 제어 인터페이스를 통과해야 한다. 각 핵심 액추에이터 인터페이스는 명령 검증(Command Validation), 상태 피드백(State Feedback), 진단 정보, 타임아웃 감시(Timeout Supervision)를 지원하고 통신, 전원, 센서 피드백 또는 제어기 무결성(Controller Integrity)이 상실될 경우 사전에 정의된 안전 동작(Safe Behavior)으로 전환되어야 한다.

자율 컴퓨팅(Autonomous Computing)은 결정론적 차량 제어(Deterministic Vehicle Control)와 논리적으로 분리되어야 한다. 고성능 컴퓨터 또는 인공지능 가속기(AI Accelerator)는 인지, 위치 추정, 경로 계획(Planning), 지도 생성(Mapping) 및 지능형 의사결정 기능을 수행할 수 있으며, 전용 제어기는 시간 임계 차량 제어(Time-Critical Vehicle Control)와 안전 감시를 유지해야 한다. 따라서 자율 컴퓨터의 고장, 재부팅, 과부하 또는 소프트웨어 업데이트가 제어되지 않은 추진, 조향 또는 제동 동작을 발생시켜서는 안 된다.

인지 아키텍처(Perception Architecture)는 카메라(Camera), 깊이 카메라(Depth Camera), 2차원 또는 3차원 라이다(2D/3D LiDAR), 레이더(Radar), 초음파 센서(Ultrasonic Sensor) 및 용도별 검사 장치(Application-Specific Inspection Device)와 같은 옥외 센서를 수용해야 한다. 센서 전원 회로는 개별적으로 보호하거나 기능적 의존성에 따라 그룹화해야 한다. 인터페이스는 대역폭(Bandwidth), 동기화(Synchronization), 환경 밀봉(Environmental Sealing), 케이블 길이, 전자기 적합성(EMC), 장착 위치, 정비성(Serviceability) 및 다른 인지 기능을 불필요하게 비활성화하지 않고 고장 센서를 격리할 수 있는 능력을 고려해야 한다.

옥외 위치 추정(Localization)은 위성항법시스템(GNSS)과 필요한 경우 실시간 이동측위 보정(RTK Correction)을 관성측정장치(IMU), 휠 오도메트리(Wheel Odometry), 조향 피드백 및 인지 기반 위치 추정(Perception-Based Localization)과 함께 지원해야 한다. GNSS 안테나와 수신기는 스위칭 컨버터, 모터, 고전류 케이블, 무선 장치 및 기타 간섭원으로부터 적절한 전력 무결성(Power Integrity), 접지, 차폐 및 전자기적 분리를 확보하도록 설치해야 한다. 위치 추정 데이터에는 유효성 및 품질 정보를 포함하여 성능 저하가 자율 이동에 영향을 미치기 전에 감지될 수 있도록 해야 한다.

통신 네트워크(Communication Network)는 결정성(Determinism), 대역폭, 진단 요구사항, 환경적 견고성 및 안전 중요도에 따라 선택해야 한다. CAN 또는 CAN FD는 분산 제어기 및 차량 수준 신호를 지원할 수 있으며, 이더넷(Ethernet)은 고대역폭 센서, 컴퓨팅 시스템, 진단 및 데이터 로깅(Data Logging)을 지원할 수 있다. ROS 2 또는 이에 상응하는 소프트웨어 미들웨어(Software Middleware)는 물리 네트워크 상위에서 동작할 수 있지만, 소프트웨어 통신이 핵심 차량 제어에 필요한 전기적 안전장치를 대체해서는 안 된다.

시간 동기화(Time Synchronization)는 다수의 카메라, 라이다, IMU, GNSS 수신기, 레이더 센서 및 컴퓨팅 노드가 인지 또는 위치 추정에 참여하는 경우 아키텍처 수준의 기능으로 다루어야 한다. GNSS 기반 타이밍(GNSS-Derived Timing), 정밀 시간 프로토콜(PTP), 하드웨어 트리거링(Hardware Triggering) 또는 이에 상응하는 메커니즘은 요구 정확도에 따라 선택해야 한다. 기록 데이터와 실시간 센서 정보의 시간적 일관성을 유지하도록 타임스탬프 발생원(Timestamp Origin), 기준 클록(Clock Ownership), 동기화 상실 감지 및 성능 저하 시 동작을 정의해야 한다.

안전 아키텍처(Safety Architecture)는 주 컴퓨팅 경로가 사용 불가능해지는 경우에도 자율 기능을 감시할 수 있을 정도로 독립성을 유지해야 한다. 비상정지 회로(Emergency-Stop Circuit), 안전 제어기(Safety Controller), 안전 센서(Safety Sensor), 제동 인터페이스, 추진 억제 기능(Propulsion Inhibit Function) 및 관련 접촉기는 명확하게 정의된 안전 체인(Safety Chain)을 구성해야 한다. 비상 조건이 활성화되면 운영체제, ROS 2 소프트웨어, AI 모델 또는 중앙 자율 컴퓨터에만 의존하지 않고 차량을 제어된 안전 상태(Safe State)로 전환해야 한다.

환경 설계(Environmental Design)는 비, 물 분사, 먼지, 진흙, 결로, 태양열, 저온, 진동, 충격, 부식 및 반복적인 기계적 하중을 고려해야 한다. 전기 인클로저(Electrical Enclosure), 커넥터, 하네스 전이부(Harness Transition), 안테나, 센서 인터페이스 및 정비 지점은 각각의 장착 영역에 적합한 보호 수준을 적용해야 한다. 배수, 밀봉, 케이블 글랜드(Cable Gland), 스트레인 릴리프(Strain Relief), 커넥터 방향 및 물 고임 방지는 단순한 패키징 세부사항이 아니라 전기 아키텍처의 일부로 고려되어야 한다.

접지 및 전자기 적합성 설계(Grounding and EMC Design)는 추진 전자장치, 컴퓨팅 장비, 센서, 통신 인터페이스 및 차체 본딩(Chassis Bonding)에 대해 제어된 귀환 경로(Return Path)를 확립해야 한다. 고전류 모터 및 인버터 경로는 GNSS, IMU, 카메라, 라이다, 이더넷 및 기타 민감한 회로에 대한 결합(Coupling)을 최소화하도록 배선해야 한다. 차폐 종단(Shield Termination), 차체 본딩, 필터링(Filtering), 케이블 분리, 공통 모드 제어(Common-Mode Control) 및 접지 토폴로지(Grounding Topology)는 차량 전체에 걸쳐 일관되게 정의하고 통합 단계에서 검증해야 한다.

아키텍처는 구성요소, 네트워크, 전력 도메인 및 차량 수준의 진단(Diagnostics)을 지원해야 한다. 제어기는 가능한 경우 관련 고장, 통신 상태, 공급 전압, 온도, 액추에이터 상태 및 센서 유효성을 보고해야 한다. 간헐적으로 발생하는 옥외 고장을 로그(Log)로부터 재구성할 수 있도록 진단 정보에는 타임스탬프를 부여하고 차량 운행 상태와 연계해야 한다. 정비 인터페이스(Service Interface)는 기술자가 불필요한 분해나 보호 기능의 통제되지 않은 우회 없이 고장을 식별할 수 있도록 해야 한다.

가용성 요구사항(Availability Requirements)은 즉시 정지가 필요한 고장과 성능 저하 운행(Degraded Operation)이 가능한 고장을 구분해야 한다. 안전 개념(Safety Concept)이 이를 허용하는 경우 비필수 카메라, 통신 링크, 보조 센서 또는 검사 페이로드(Inspection Payload)의 손실에도 제한된 운행이 가능할 수 있다. 반면 제동 권한(Braking Authority), 핵심 조향 피드백, 안전 감시 또는 필수 위치 추정 무결성(Localization Integrity)의 상실은 적절한 안전 상태 대응을 시작해야 한다. 성능 저하 규칙은 응용 소프트웨어가 임의로 판단하도록 두지 않고 명시적으로 정의해야 한다.

전기 아키텍처는 기본 옥외 자율이동로봇(Outdoor AMR)부터 검사(Inspection), 순찰(Patrol), 농업(Agriculture), 광산(Mining), 항만(Port) 또는 기타 자율주행 차량 변형까지 제품 확장성(Product Scalability)을 지원해야 한다. 따라서 선택형 센서, 통신 모듈, 페이로드 인터페이스, 컴퓨팅 등급(Computing Tier) 및 보조 전원 출력은 가능한 경우 표준화된 인터페이스를 사용해야 한다. 기존 안전 여유도를 손상시키지 않으면서 전력분배장치(PDU) 채널, 네트워크 포트, 컴퓨팅 전력, 통신 대역폭, 커넥터 위치 및 열 용량의 확장성을 고려해야 한다.

와이어 하네스(Wire Harness)와 커넥터는 옥외의 기계적·환경적 노출 조건에 적합하도록 선정하고 제조, 검사, 교체 및 현장 유지보수를 지원해야 한다. 고전류, 통신, 센서, 안테나 및 안전 회로는 관리되는 도면과 인터페이스 정의를 통해 식별되어야 한다. 커넥터 키잉(Keying), 잠금(Locking), 극성(Polarization), 환경 등급, 전류 디레이팅(Current Derating), 차폐, 굽힘 반경(Bend Radius), 마모 방지 및 가동 기구 주변의 배선은 아키텍처 승인 과정에서 고려되어야 한다.

승인된 옥외 전기·전자 아키텍처(Outdoor E/E Architecture)는 시스템 다이어그램(System Diagram), 전력 예산(Power Budget), 네트워크 정의, 인터페이스 제어 정보(Interface-Control Information), 보호 할당(Protection Assignment), 접지 요구사항, 안전 의존성 및 승인된 구성요소 설정을 통해 관리되어야 한다. 전압 레일, 안전 경로, 네트워크 토폴로지, 액추에이터 인터페이스, 센서 타이밍, 접지, 보호 장치 또는 전력 용량에 영향을 미치는 모든 변경은 국부적 수정으로 인해 의도하지 않은 차량 수준의 위험이 발생하지 않도록 엔지니어링 검토(Engineering Review)를 거쳐야 한다.

검증(Verification)은 시동, 정상 주행, 자율 운행, 충전, 종료, 비상정지, 통신 상실, 센서 성능 저하, 제어기 재설정, 저전압 및 대표적인 전기적 고장 조건에서 올바른 동작을 입증해야 한다. 시험에서는 전력 무결성, 네트워크 동작, 진단 범위(Diagnostic Coverage), 환경적 견고성, 전자기 적합성 성능 및 안전 상태 전환도 확인해야 한다. 시험 결과는 아키텍처 요구사항과 승인된 하드웨어 및 소프트웨어 구성에 대해 추적성(Traceability)을 유지해야 한다.

최종 아키텍처는 옥외 차량 요구사항을 전기 아키텍처, 하네스 설계, 커넥터 선정, 퓨즈 보호, 접지, 통신, 캘리브레이션(Calibration) 및 안전에 관한 Hills Robotics의 상위 엔지니어링 표준과 연결하는 공통 엔지니어링 기반(Common Engineering Foundation)을 제공해야 한다. 목적은 단순히 차량 구성요소를 연결하는 것이 아니라 자율성, 전력, 센싱, 통신, 진단 및 안전이 개발, 생산, 현장 운용 및 향후 제품 진화 전 과정에서 일관되게 관리되는 반복 가능한 전기·전자 플랫폼(Repeatable E/E Platform)을 확립하는 것이다.

##  

## 11.02. GNSS/RTK Standard

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

The GNSS RTK system shall provide the primary absolute positioning reference for outdoor autonomous vehicles requiring lane-level or centimeter-class localization. It shall be engineered as part of the vehicle localization architecture rather than treated as an independent navigation accessory. The system shall integrate GNSS receivers, antennas, RTK correction sources, inertial sensing, vehicle odometry, communication interfaces, time synchronization, diagnostics, and autonomous computing.

The GNSS receiver shall support multiple satellite constellations whenever practical, including GPS, Galileo, GLONASS, BeiDou, or regionally applicable navigation systems. Multi-constellation and multi-frequency reception should be used to improve satellite availability, convergence, ambiguity resolution, and resistance to multipath effects. Receiver selection shall consider positioning accuracy, update rate, correction protocol support, environmental rating, initialization behavior, timing capability, and diagnostic accessibility.

RTK operation shall use carrier-phase measurements together with correction information from an approved reference source to achieve high-precision positioning. The architecture may use a local base station, network RTK service, continuously operating reference station network, or another validated correction infrastructure. The selected method shall define correction availability, communication latency, geographic coverage, service dependency, expected convergence time, and behavior when correction data becomes unavailable.

The positioning solution shall explicitly report its operating state rather than providing coordinates without quality information. At minimum, the autonomous system shall distinguish between RTK fixed, RTK float, differential or corrected positioning, standalone GNSS, and invalid or unavailable positioning states when supported by the receiver. Position quality shall be evaluated using receiver status, estimated accuracy, satellite geometry, correction age, satellite availability, and other integrity indicators.

RTK fixed status alone shall not automatically be interpreted as permission for autonomous motion. The vehicle localization function shall verify that horizontal and vertical accuracy, correction age, solution stability, timestamp validity, and other project-defined quality criteria remain within acceptable limits. Sudden coordinate jumps, unrealistic velocity changes, inconsistent heading, or disagreement with independent localization sources shall be detected before the GNSS solution is used for safety-relevant vehicle control.

GNSS antennas shall be installed at locations providing the widest practical view of the sky while minimizing obstruction from vehicle structures, payloads, sensor towers, equipment enclosures, and moving mechanisms. The antenna shall be mechanically rigid so its position relative to the vehicle coordinate frame remains stable. Antenna installation shall also consider water accumulation, vibration, impact exposure, cable strain, service accessibility, and replacement repeatability.

The antenna installation shall minimize electromagnetic interference from motors, inverters, DC/DC converters, switching power supplies, high-current harnesses, computing equipment, radios, and other noise sources. Antenna cables shall use suitable impedance, shielding, connectors, routing, and bend radius. Cable length and insertion loss shall remain within receiver and antenna specifications, and unnecessary adapters or unqualified extensions shall be avoided because they can degrade received signal quality.

The GNSS antenna reference point shall be calibrated relative to the defined vehicle coordinate system. Lever-arm offsets between the antenna, IMU, vehicle reference point, wheelbase reference, and other localization sensors shall be measured and recorded in controlled configuration data. Mechanical modifications that change antenna or sensor positions shall trigger verification or recalibration according to the applicable calibration standard.

Vehicles requiring reliable heading at low speed or while stationary should use a validated heading source such as dual-antenna GNSS, inertial heading, steering and odometry fusion, or another appropriate method. When dual GNSS antennas are used, antenna separation, baseline orientation, structural rigidity, cable characteristics, and installation tolerances shall be controlled. Heading validity and accuracy shall be monitored independently from position validity whenever supported.

GNSS data shall be fused with an inertial measurement unit, wheel odometry, steering information, LiDAR localization, visual localization, or other available sources when required by the vehicle operating environment. Sensor fusion shall provide continuity through short GNSS interruptions and improve dynamic state estimation, but it shall not conceal persistent GNSS degradation. Each source shall retain validity information so the localization system can identify which measurements remain trustworthy.

The GNSS/RTK interface to the vehicle shall use an approved communication method appropriate to the receiver and system architecture, such as Ethernet, CAN, serial communication, or another controlled interface. Message definitions shall specify coordinate format, position, velocity, heading, accuracy estimates, fix state, correction status, timestamps, and diagnostic information. Units, axis conventions, sign conventions, coordinate frames, and update rates shall be documented consistently across software and hardware interfaces.

RTK correction communication may use cellular networks, Wi-Fi, radio links, Ethernet, or other validated communication channels according to the deployment environment. Network-based corrections shall define authentication, endpoint configuration, reconnect behavior, data usage, communication timeout, and correction-age limits. Loss of the external communication link shall be distinguishable from GNSS receiver failure so diagnostics and degraded-operation logic can identify the actual cause.

Time synchronization shall be incorporated whenever GNSS information is fused with cameras, LiDAR, radar, IMU, wheel encoders, or other time-sensitive measurements. GNSS time, PPS, PTP, hardware timestamps, or equivalent mechanisms may be used according to required accuracy. The architecture shall define the master time reference, timestamp generation point, transport delay assumptions, clock synchronization status, and response to synchronization loss.

The system shall define degraded operating modes for environments where satellite visibility or correction reception cannot be guaranteed. Examples include operation near tall buildings, trees, retaining walls, tunnels, bridges, industrial structures, containers, or covered facilities. The localization architecture shall detect degraded GNSS performance and transition to an approved fallback strategy, restricted operating mode, controlled stop, or other project-defined safe response.

Multipath and non-line-of-sight reception shall be considered during route design and validation because centimeter-class receiver specifications do not guarantee centimeter-class vehicle localization in every outdoor environment. Field testing shall evaluate representative open-sky and obstructed conditions along the intended operating area. Repeated localization errors at specific locations shall be documented and addressed through sensor fusion, route constraints, infrastructure changes, or operational rules.

The electrical supply to GNSS receivers, antennas, correction modems, and related localization equipment shall meet defined voltage, transient, grounding, and noise requirements. Sensitive GNSS circuits should be separated from high-current switching paths wherever practical. Power interruptions, brownouts, receiver resets, antenna faults, communication failures, and restoration behavior shall be considered so temporary electrical disturbances do not create an undetected invalid localization state.

Diagnostics shall monitor receiver communication, antenna status where available, satellite count, fix state, correction reception, correction age, estimated accuracy, heading validity, synchronization status, and relevant hardware faults. Diagnostic records shall include timestamps and vehicle operating context to support field troubleshooting. Persistent or recurring GNSS degradation shall be identifiable from logs without requiring direct access to the receiver during the original event.

Configuration parameters affecting positioning performance shall be controlled as engineering data. These include receiver firmware, constellation and frequency settings, correction source configuration, communication parameters, antenna type, antenna offsets, coordinate reference system, datum, geoid settings where applicable, update rate, filtering parameters, and localization thresholds. Unauthorized or undocumented changes to these parameters shall not be permitted on released production configurations.

Verification shall include static accuracy, dynamic accuracy, repeatability, initialization time, RTK convergence, correction interruption, communication recovery, GNSS outage, multipath exposure, antenna disconnection, power cycling, timestamp integrity, and transition between positioning states. Testing shall be performed under representative vehicle motion and environmental conditions, and results shall demonstrate that reported quality indicators correctly represent the usable positioning performance.

Acceptance criteria shall be defined according to the vehicle application rather than relying only on receiver data-sheet accuracy. Required positioning accuracy, heading accuracy, update frequency, maximum correction age, convergence time, outage tolerance, and recovery behavior shall be traceable to autonomous driving and safety requirements. Validation shall confirm not only nominal centimeter-class performance but also reliable detection of conditions in which that performance cannot be maintained.

The released GNSS RTK configuration shall provide a repeatable localization reference across manufacturing, commissioning, maintenance, and field replacement. Receiver, antenna, mounting geometry, calibration data, firmware, correction service, communication configuration, and validation records shall remain configuration-controlled. The objective is to ensure that outdoor autonomous vehicles receive accurate, time-consistent, diagnosable, and integrity-aware positioning information throughout the operational lifecycle.

GNSS RTK 시스템은 차선 수준(Lane-Level) 또는 센티미터급(Centimeter-Class) 위치 추정이 필요한 옥외 자율주행 차량(Outdoor Autonomous Vehicle)에 주요 절대 위치 기준(Primary Absolute Positioning Reference)을 제공해야 한다. 이 시스템은 독립적인 내비게이션 보조장치가 아니라 차량 위치 추정 아키텍처(Vehicle Localization Architecture)의 일부로 설계되어야 한다. 시스템은 GNSS 수신기, 안테나, RTK 보정원(RTK Correction Source), 관성 센싱(Inertial Sensing), 차량 오도메트리(Vehicle Odometry), 통신 인터페이스, 시간 동기화(Time Synchronization), 진단(Diagnostics) 및 자율 컴퓨팅(Autonomous Computing)을 통합해야 한다.

GNSS 수신기는 가능한 경우 GPS, Galileo, GLONASS, BeiDou 또는 해당 지역에서 사용할 수 있는 위성항법시스템을 포함한 다중 위성군(Multiple Satellite Constellations)을 지원해야 한다. 다중 위성군 및 다중 주파수(Multi-Frequency) 수신은 위성 가용성, 수렴성(Convergence), 모호정수 결정(Ambiguity Resolution) 및 다중경로(Multipath) 영향에 대한 내성을 향상하기 위해 사용해야 한다. 수신기 선정 시 위치 정확도, 갱신 주기(Update Rate), 보정 프로토콜 지원, 환경 등급, 초기화 특성, 타이밍 기능 및 진단 접근성을 고려해야 한다.

RTK 운용은 고정밀 위치 추정을 달성하기 위해 승인된 기준원(Reference Source)의 보정 정보와 함께 반송파 위상 측정(Carrier-Phase Measurement)을 사용해야 한다. 아키텍처는 로컬 기준국(Local Base Station), 네트워크 RTK 서비스(Network RTK Service), 상시 운영 기준국 네트워크(Continuously Operating Reference Station Network) 또는 검증된 다른 보정 인프라를 사용할 수 있다. 선택된 방식에 대해 보정 가용성, 통신 지연, 지리적 범위, 서비스 의존성, 예상 수렴 시간 및 보정 데이터 사용 불가 시 동작을 정의해야 한다.

위치 추정 솔루션(Positioning Solution)은 품질 정보 없이 좌표만 제공하지 않고 현재 운용 상태를 명시적으로 보고해야 한다. 최소한 자율 시스템은 수신기가 지원하는 경우 RTK 고정(RTK Fixed), RTK 유동(RTK Float), 차분 또는 보정 위치 추정(Differential or Corrected Positioning), 단독 GNSS(Standalone GNSS), 그리고 무효 또는 사용 불가능 위치 상태를 구분해야 한다. 위치 품질은 수신기 상태, 추정 정확도, 위성 기하구조(Satellite Geometry), 보정 데이터 경과 시간(Correction Age), 위성 가용성 및 기타 무결성 지표(Integrity Indicator)를 사용하여 평가해야 한다.

RTK 고정 상태(RTK Fixed Status)만으로 자율 이동을 자동 허용해서는 안 된다. 차량 위치 추정 기능은 수평 및 수직 정확도, 보정 데이터 경과 시간, 솔루션 안정성(Solution Stability), 타임스탬프 유효성 및 기타 프로젝트에서 정의한 품질 기준이 허용 범위 내에 유지되는지 검증해야 한다. 갑작스러운 좌표 점프, 비현실적인 속도 변화, 일관되지 않은 헤딩(Heading) 또는 독립적인 위치 추정원과의 불일치는 GNSS 솔루션이 안전 관련 차량 제어에 사용되기 전에 감지되어야 한다.

GNSS 안테나는 차량 구조물, 페이로드(Payload), 센서 타워, 장비 인클로저(Equipment Enclosure) 및 가동 기구에 의한 차폐를 최소화하면서 가능한 한 넓은 상공 시야(Sky View)를 확보할 수 있는 위치에 설치해야 한다. 안테나는 차량 좌표계(Vehicle Coordinate Frame)에 대한 위치가 안정적으로 유지되도록 기계적으로 견고하게 고정해야 한다. 또한 안테나 설치 시 물 고임, 진동, 충격 노출, 케이블 변형, 정비 접근성 및 교체 시 위치 재현성을 고려해야 한다.

안테나 설치는 모터, 인버터(Inverter), DC/DC 컨버터(DC/DC Converter), 스위칭 전원공급장치(Switching Power Supply), 고전류 하네스, 컴퓨팅 장비, 무선 장치 및 기타 노이즈원으로부터 발생하는 전자기 간섭(Electromagnetic Interference)을 최소화해야 한다. 안테나 케이블에는 적절한 임피던스(Impedance), 차폐(Shielding), 커넥터, 배선 경로 및 굽힘 반경(Bend Radius)을 적용해야 한다. 케이블 길이와 삽입 손실(Insertion Loss)은 수신기 및 안테나 사양 범위 내에 있어야 하며, 수신 신호 품질을 저하시킬 수 있는 불필요한 어댑터나 검증되지 않은 연장 케이블은 사용하지 않아야 한다.

GNSS 안테나 기준점(Antenna Reference Point)은 정의된 차량 좌표계에 대해 캘리브레이션(Calibration)되어야 한다. 안테나, 관성측정장치(IMU), 차량 기준점(Vehicle Reference Point), 휠베이스 기준점(Wheelbase Reference) 및 기타 위치 추정 센서 사이의 레버 암 오프셋(Lever-Arm Offset)은 측정하여 관리되는 구성 데이터(Configuration Data)에 기록해야 한다. 안테나 또는 센서 위치를 변경하는 기계적 수정이 발생하면 해당 캘리브레이션 표준에 따라 검증 또는 재캘리브레이션(Recalibration)을 수행해야 한다.

저속 또는 정지 상태에서도 신뢰성 높은 헤딩이 필요한 차량은 듀얼 안테나 GNSS(Dual-Antenna GNSS), 관성 헤딩(Inertial Heading), 조향 및 오도메트리 융합(Steering and Odometry Fusion) 또는 기타 적절하고 검증된 헤딩원을 사용해야 한다. 듀얼 GNSS 안테나를 사용하는 경우 안테나 간격, 베이스라인 방향(Baseline Orientation), 구조적 강성, 케이블 특성 및 설치 공차를 관리해야 한다. 지원되는 경우 헤딩 유효성과 정확도는 위치 유효성과 독립적으로 감시해야 한다.

GNSS 데이터는 차량 운용 환경에 따라 필요한 경우 관성측정장치(IMU), 휠 오도메트리(Wheel Odometry), 조향 정보, 라이다 위치 추정(LiDAR Localization), 비전 기반 위치 추정(Visual Localization) 또는 기타 가용 정보원과 융합해야 한다. 센서 융합(Sensor Fusion)은 짧은 GNSS 단절 구간에서 연속성을 제공하고 동적 상태 추정(Dynamic State Estimation)을 향상해야 하지만, 지속적인 GNSS 성능 저하를 은폐해서는 안 된다. 위치 추정 시스템이 신뢰 가능한 측정값을 식별할 수 있도록 각 정보원은 유효성 정보를 유지해야 한다.

차량에 대한 GNSS/RTK 인터페이스는 수신기 및 시스템 아키텍처에 적합한 승인된 통신 방식인 이더넷(Ethernet), CAN, 직렬 통신(Serial Communication) 또는 기타 관리되는 인터페이스를 사용해야 한다. 메시지 정의에는 좌표 형식, 위치, 속도, 헤딩, 정확도 추정값, 픽스 상태(Fix State), 보정 상태, 타임스탬프 및 진단 정보를 규정해야 한다. 단위, 축 규약(Axis Convention), 부호 규약(Sign Convention), 좌표계 및 갱신 주기는 소프트웨어와 하드웨어 인터페이스 전체에서 일관되게 문서화해야 한다.

RTK 보정 통신(RTK Correction Communication)은 배치 환경에 따라 셀룰러 네트워크(Cellular Network), Wi-Fi, 무선 링크(Radio Link), 이더넷 또는 기타 검증된 통신 채널을 사용할 수 있다. 네트워크 기반 보정(Network-Based Correction)은 인증(Authentication), 엔드포인트 설정(Endpoint Configuration), 재연결 동작, 데이터 사용량, 통신 타임아웃 및 보정 데이터 경과 시간 제한을 정의해야 한다. 진단 및 성능 저하 운용 로직이 실제 원인을 식별할 수 있도록 외부 통신 링크 상실과 GNSS 수신기 고장을 구분할 수 있어야 한다.

GNSS 정보가 카메라, 라이다, 레이더, IMU, 휠 인코더(Wheel Encoder) 또는 기타 시간 민감형 측정값과 융합되는 경우 시간 동기화(Time Synchronization)를 적용해야 한다. 요구 정확도에 따라 GNSS 시간(GNSS Time), 초당 펄스(PPS), 정밀 시간 프로토콜(PTP), 하드웨어 타임스탬프(Hardware Timestamp) 또는 이에 상응하는 메커니즘을 사용할 수 있다. 아키텍처는 마스터 시간 기준(Master Time Reference), 타임스탬프 생성 지점, 전송 지연 가정, 클록 동기화 상태 및 동기화 상실 시 대응을 정의해야 한다.

시스템은 위성 가시성 또는 보정 정보 수신을 보장할 수 없는 환경에 대해 성능 저하 운용 모드(Degraded Operating Mode)를 정의해야 한다. 이러한 환경에는 고층 건물, 나무, 옹벽, 터널, 교량, 산업 구조물, 컨테이너 또는 지붕이 있는 시설 주변의 운용이 포함된다. 위치 추정 아키텍처는 GNSS 성능 저하를 감지하고 승인된 대체 전략(Fallback Strategy), 제한 운행 모드(Restricted Operating Mode), 제어 정지(Controlled Stop) 또는 프로젝트에서 정의한 기타 안전 대응으로 전환해야 한다.

다중경로(Multipath) 및 비가시선 수신(Non-Line-of-Sight Reception)은 센티미터급 수신기 사양이 모든 옥외 환경에서 센티미터급 차량 위치 추정을 보장하지 않으므로 경로 설계 및 검증 과정에서 고려해야 한다. 현장 시험(Field Testing)은 목표 운용 구역에서 대표적인 개방된 상공(Open-Sky) 조건과 차폐 조건을 평가해야 한다. 특정 위치에서 반복되는 위치 추정 오차는 문서화하고 센서 융합, 경로 제한(Route Constraint), 인프라 변경 또는 운용 규칙을 통해 대응해야 한다.

GNSS 수신기, 안테나, 보정 모뎀(Correction Modem) 및 관련 위치 추정 장비에 공급되는 전원은 정의된 전압, 과도 상태(Transient), 접지 및 노이즈 요구사항을 충족해야 한다. 민감한 GNSS 회로는 가능한 경우 고전류 스위칭 경로와 분리해야 한다. 일시적인 전기적 교란으로 인해 감지되지 않은 무효 위치 상태가 발생하지 않도록 전원 중단, 브라운아웃(Brownout), 수신기 재설정, 안테나 고장, 통신 장애 및 복구 동작을 고려해야 한다.

진단(Diagnostics)은 수신기 통신, 가능한 경우 안테나 상태, 위성 수, 픽스 상태, 보정 데이터 수신, 보정 데이터 경과 시간, 추정 정확도, 헤딩 유효성, 동기화 상태 및 관련 하드웨어 고장을 감시해야 한다. 진단 기록에는 현장 고장 분석을 지원할 수 있도록 타임스탬프와 차량 운행 상황을 포함해야 한다. 지속적이거나 반복적인 GNSS 성능 저하는 해당 이벤트 발생 당시 수신기에 직접 접근하지 않더라도 로그(Log)를 통해 식별할 수 있어야 한다.

위치 추정 성능에 영향을 미치는 구성 파라미터(Configuration Parameter)는 엔지니어링 데이터로 관리해야 한다. 여기에는 수신기 펌웨어, 위성군 및 주파수 설정, 보정원 설정, 통신 파라미터, 안테나 종류, 안테나 오프셋, 좌표 기준계(Coordinate Reference System), 측지 기준(Datum), 필요한 경우 지오이드(Geoid) 설정, 갱신 주기, 필터링 파라미터 및 위치 추정 임계값(Localization Threshold)이 포함된다. 승인된 양산 구성에서 이러한 파라미터를 승인 없이 또는 문서화하지 않고 변경해서는 안 된다.

검증(Verification)은 정적 정확도(Static Accuracy), 동적 정확도(Dynamic Accuracy), 반복성(Repeatability), 초기화 시간, RTK 수렴, 보정 중단, 통신 복구, GNSS 단절, 다중경로 노출, 안테나 분리, 전원 재인가(Power Cycling), 타임스탬프 무결성 및 위치 추정 상태 간 전환을 포함해야 한다. 시험은 대표적인 차량 운동 및 환경 조건에서 수행되어야 하며, 보고되는 품질 지표가 실제 사용 가능한 위치 추정 성능을 올바르게 나타낸다는 것을 입증해야 한다.

합격 기준(Acceptance Criteria)은 수신기 데이터시트의 정확도에만 의존하지 않고 차량 적용 분야에 따라 정의해야 한다. 요구 위치 정확도, 헤딩 정확도, 갱신 주파수, 최대 보정 데이터 경과 시간, 수렴 시간, 단절 허용 시간 및 복구 동작은 자율주행 및 안전 요구사항에 대한 추적성(Traceability)을 확보해야 한다. 검증은 정상적인 센티미터급 성능뿐만 아니라 해당 성능을 유지할 수 없는 조건을 신뢰성 있게 감지할 수 있음을 확인해야 한다.

승인된 GNSS RTK 구성은 제조, 시운전(Commissioning), 유지보수 및 현장 교체 전 과정에서 반복 가능한 위치 추정 기준(Repeatable Localization Reference)을 제공해야 한다. 수신기, 안테나, 장착 형상, 캘리브레이션 데이터, 펌웨어, 보정 서비스, 통신 설정 및 검증 기록은 구성 관리(Configuration Control)되어야 한다. 최종 목적은 옥외 자율주행 차량이 전체 운용 수명주기 동안 정확하고 시간적으로 일관되며 진단 가능하고 무결성을 인지하는(Integrity-Aware) 위치 정보를 확보하도록 하는 것이다.

##  

## 11.03. DBW Design Rule

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

The drive-by-wire system shall provide the controlled electrical and electronic interface between autonomous driving functions and the vehicle propulsion, steering, and braking mechanisms. DBW architecture shall separate high-level autonomy commands from direct actuator power control so that perception, localization, planning, or AI software cannot directly energize propulsion or manipulate safety-critical actuators without validation by the vehicle control layer.

The DBW architecture shall include propulsion-by-wire, steering-by-wire, and braking-by-wire functions appropriate to the vehicle configuration. Each function shall define command inputs, actuator outputs, position or state feedback, communication interfaces, power supplies, diagnostic signals, and safe-state behavior. Functional boundaries shall remain sufficiently modular to permit replacement or upgrade of individual actuators without redesigning the entire autonomous control architecture.

A dedicated vehicle control unit shall mediate commands between the autonomous computing system and DBW actuators. High-level commands such as target velocity, acceleration, steering angle, curvature, or stopping request shall be checked against vehicle limits before conversion into actuator commands. The controller shall reject malformed, stale, conflicting, physically impossible, or out-of-range commands rather than transmitting them directly to the propulsion, steering, or braking hardware.

Propulsion control shall provide deterministic management of motor torque, rotational speed, vehicle velocity, direction, acceleration, deceleration, and regenerative behavior where applicable. Command limits shall consider motor and inverter ratings, battery capability, vehicle mass, payload, slope, traction conditions, and thermal limits. Unexpected propulsion shall be prevented through enable logic, command plausibility checking, communication supervision, and independent propulsion-inhibit mechanisms.

Steering control shall translate commanded vehicle motion into a controlled steering actuator request while continuously monitoring actual steering position. The system shall define steering-angle limits, steering-rate limits, center position, mechanical boundaries, actuator current or torque limits, and feedback plausibility. Steering commands exceeding allowed dynamic or mechanical limits shall be constrained or rejected before they can produce unstable or mechanically damaging motion.

Braking control shall provide predictable deceleration and stopping under autonomous, manual, degraded, and emergency conditions. Service braking and emergency or parking brake functions shall be coordinated according to the vehicle design while maintaining appropriate independence. The braking system shall not depend exclusively on regenerative braking because regenerative capability may decrease or disappear due to battery state, inverter faults, low speed, traction conditions, or electrical power loss.

Command and feedback paths shall be treated separately. A commanded steering angle, wheel torque, brake request, or velocity shall not be assumed to have been executed merely because the command was transmitted successfully. Actual actuator position, velocity, torque, pressure, current, brake state, or other available feedback shall be monitored to confirm response. Persistent disagreement between command and feedback shall generate a diagnostic fault and initiate the defined degraded or safe-state response.

DBW communication shall use a controlled network interface such as CAN, CAN FD, Automotive Ethernet, or another validated deterministic transport suitable for the application. Messages shall define signal scaling, units, ranges, update periods, timeout limits, counters, status fields, and diagnostic information. Safety-relevant commands should include mechanisms such as alive counters, sequence monitoring, checksums, CRC protection, or equivalent integrity measures where supported by the system design.

Communication timeout behavior shall be explicitly defined for every motion-critical interface. Loss of a valid command stream shall not cause the actuator to indefinitely maintain the last propulsion or steering request. The receiving controller shall detect stale information within the specified timeout and transition toward an approved degraded or safe state. Timeout thresholds shall consider control frequency, network latency, vehicle dynamics, stopping distance, and actuator response time.

DBW state management shall distinguish initialization, standby, manual control, autonomous-ready, autonomous-active, degraded, emergency, fault, and shutdown conditions as required by the vehicle. Transitions between states shall occur only when defined prerequisites are satisfied. Autonomous motion shall require valid safety status, acceptable localization, healthy DBW communication, available braking, valid actuator feedback, and all other project-specific motion-enabling conditions.

The system shall use explicit enable and inhibit logic to prevent unintended motion during booting, software restart, maintenance, charging, calibration, communication recovery, or controller replacement. Propulsion enable shall require deliberate fulfillment of defined conditions rather than merely the absence of a fault. Safety circuits shall retain the authority to inhibit propulsion or request braking regardless of the state of the autonomous computing software.

Emergency-stop operation shall override normal autonomous motion commands through a defined safety path. Activation of an E-Stop shall remove or inhibit propulsion and command the appropriate stopping mechanism according to the vehicle safety architecture. Recovery from an emergency stop shall require controlled reset conditions and shall not automatically resume the previous motion command when the E-Stop device is released.

Power architecture for DBW components shall maintain sufficient independence between propulsion, steering, braking, vehicle control, and safety supervision according to their criticality. A failure of an auxiliary sensor, payload, high-performance computer, or noncritical power branch shall not unnecessarily disable the electrical functions required to stop the vehicle safely. Voltage monitoring, undervoltage detection, overcurrent protection, grounding, and transient protection shall be provided where required.

Steering and braking availability following partial electrical failure shall be considered during architecture design. Where the vehicle risk assessment requires continued control after a single fault, redundant power feeds, backup energy, redundant sensing, independent control paths, mechanical fallback, or other appropriate measures shall be evaluated. Redundancy shall be introduced according to safety requirements rather than duplicated without analysis, because common-cause failures can defeat nominally redundant channels.

Manual and autonomous control interfaces shall have explicitly defined authority. If a vehicle supports manual driving, remote control, service control, or teleoperation, the priority and transition rules between these modes and autonomous control shall be documented. Simultaneous controllers shall not issue uncontrolled competing actuator commands. Transfer of control shall include command neutralization, state confirmation, and appropriate operator or system acknowledgement where required.

Vehicle dynamics constraints shall be incorporated into DBW command validation. Maximum velocity, acceleration, deceleration, steering angle, steering rate, lateral acceleration, curvature, and other applicable limits shall be configured according to vehicle geometry and operating conditions. Different limits may be applied for payload, terrain, slope, weather, localization quality, restricted areas, or degraded states, provided that the active limit set is controlled and diagnosable.

DBW diagnostics shall continuously monitor controller communication, actuator feedback, supply voltage, temperature, motor or actuator current, sensor plausibility, command tracking, internal controller faults, and safety-related status where available. Diagnostic events shall contain sufficient timestamps and operating context to reconstruct abnormal vehicle behavior. Fault codes and status definitions shall be controlled so that engineering, production, and service tools interpret DBW failures consistently.

Calibration parameters affecting vehicle motion shall be configuration-controlled. These may include steering center and ratio, actuator direction, wheel diameter, wheelbase, velocity conversion factors, brake response characteristics, torque limits, acceleration limits, dead bands, command offsets, and control gains. Changes to these values shall require defined authorization and verification because incorrect calibration can produce hazardous motion even when all hardware components are functioning normally.

The DBW system shall support deterministic startup and shutdown sequences. At power-up, actuator outputs shall remain inhibited until communication, feedback, configuration, safety status, and controller initialization have been verified. During shutdown, propulsion shall be reduced or disabled in a controlled manner, vehicle motion shall cease, required braking or parking functions shall be established, and stored faults or operational data shall be preserved as required.

Verification shall include normal command tracking, acceleration and deceleration, steering response, braking performance, communication interruption, stale commands, corrupted messages, actuator feedback loss, sensor disagreement, controller reset, power interruption, undervoltage, emergency stop, mode transition, and recovery from faults. Tests shall confirm both correct execution of valid commands and correct rejection or containment of invalid commands under representative vehicle operating conditions.

Fault-injection testing shall demonstrate that individual failures do not produce uncontrolled vehicle motion. Representative faults should include communication loss, frozen commands, implausible feedback, actuator saturation, power loss, controller reboot, disconnected sensors, steering faults, propulsion faults, and braking faults according to the architecture. The resulting vehicle response shall be compared with the defined degraded-state and safe-state requirements and recorded for traceability.

The released DBW configuration shall maintain controlled definitions for controllers, actuators, network messages, electrical interfaces, software versions, calibration parameters, safety limits, diagnostics, and validation results. Changes affecting steering, propulsion, braking, command authority, communication timing, or safe-state behavior shall undergo engineering review and regression testing. The objective is a predictable and fault-aware vehicle control interface that enables autonomous operation without surrendering motion authority directly to high-level software.

드라이브 바이 와이어 시스템(Drive-by-Wire System)은 자율주행 기능(Autonomous Driving Function)과 차량의 추진(Propulsion), 조향(Steering) 및 제동(Braking) 메커니즘 사이에 제어된 전기·전자 인터페이스를 제공해야 한다. DBW 아키텍처(DBW Architecture)는 상위 수준 자율주행 명령을 직접적인 액추에이터 전력 제어(Actuator Power Control)와 분리하여, 인지(Perception), 위치 추정(Localization), 경로 계획(Planning) 또는 AI 소프트웨어가 차량 제어 계층(Vehicle Control Layer)의 검증 없이 추진 장치를 직접 활성화하거나 안전 중요 액추에이터(Safety-Critical Actuator)를 조작하지 못하도록 해야 한다.

DBW 아키텍처는 차량 구성에 적합한 추진 바이 와이어(Propulsion-by-Wire), 조향 바이 와이어(Steering-by-Wire) 및 제동 바이 와이어(Braking-by-Wire) 기능을 포함해야 한다. 각 기능은 명령 입력, 액추에이터 출력, 위치 또는 상태 피드백, 통신 인터페이스, 전원 공급, 진단 신호 및 안전 상태 동작(Safe-State Behavior)을 정의해야 한다. 기능적 경계는 전체 자율제어 아키텍처를 재설계하지 않고 개별 액추에이터를 교체하거나 업그레이드할 수 있도록 충분한 모듈성(Modularity)을 유지해야 한다.

전용 차량 제어 장치(Vehicle Control Unit)는 자율 컴퓨팅 시스템(Autonomous Computing System)과 DBW 액추에이터 사이의 명령을 중계하고 관리해야 한다. 목표 속도, 가속도, 조향각, 곡률(Curvature) 또는 정지 요청과 같은 상위 수준 명령은 액추에이터 명령으로 변환되기 전에 차량 한계에 대해 검증되어야 한다. 제어기는 형식 오류, 오래된 명령, 충돌하는 명령, 물리적으로 불가능한 명령 또는 허용 범위를 벗어난 명령을 추진, 조향 또는 제동 하드웨어에 직접 전달하지 않고 거부해야 한다.

추진 제어(Propulsion Control)는 모터 토크, 회전 속도, 차량 속도, 진행 방향, 가속, 감속 및 적용 가능한 경우 회생 동작(Regenerative Behavior)을 결정론적으로 관리해야 한다. 명령 제한은 모터 및 인버터 정격, 배터리 성능, 차량 질량, 페이로드(Payload), 경사도, 노면 접지 조건 및 열적 한계를 고려해야 한다. 의도하지 않은 추진(Unexpected Propulsion)은 활성화 로직(Enable Logic), 명령 타당성 검사(Command Plausibility Checking), 통신 감시 및 독립적인 추진 억제 메커니즘(Propulsion-Inhibit Mechanism)을 통해 방지해야 한다.

조향 제어(Steering Control)는 명령된 차량 운동을 제어된 조향 액추에이터 요청으로 변환하는 동시에 실제 조향 위치를 지속적으로 감시해야 한다. 시스템은 조향각 제한, 조향 속도 제한, 중앙 위치(Center Position), 기계적 한계, 액추에이터 전류 또는 토크 제한 및 피드백 타당성을 정의해야 한다. 허용되는 동적 또는 기계적 한계를 초과하는 조향 명령은 차량의 불안정한 운동이나 기계적 손상을 발생시키기 전에 제한하거나 거부해야 한다.

제동 제어(Braking Control)는 자율, 수동, 성능 저하 및 비상 조건에서 예측 가능한 감속과 정지를 제공해야 한다. 상용 제동(Service Braking)과 비상 또는 주차 브레이크(Emergency or Parking Brake) 기능은 차량 설계에 따라 조정하되 적절한 독립성을 유지해야 한다. 배터리 상태, 인버터 고장, 저속, 노면 접지 조건 또는 전원 상실로 인해 회생 제동 능력이 감소하거나 사라질 수 있으므로 제동 시스템은 회생 제동(Regenerative Braking)에만 의존해서는 안 된다.

명령 경로(Command Path)와 피드백 경로(Feedback Path)는 서로 별도로 취급해야 한다. 조향각, 휠 토크, 제동 요청 또는 속도 명령이 성공적으로 전송되었다는 이유만으로 해당 명령이 실제 수행되었다고 판단해서는 안 된다. 실제 액추에이터 위치, 속도, 토크, 압력, 전류, 제동 상태 또는 기타 사용 가능한 피드백을 감시하여 응답을 확인해야 한다. 명령과 피드백 사이의 불일치가 지속되는 경우 진단 고장(Diagnostic Fault)을 발생시키고 정의된 성능 저하 상태(Degraded State) 또는 안전 상태(Safe State) 대응을 시작해야 한다.

DBW 통신(DBW Communication)은 CAN, CAN FD, 자동차 이더넷(Automotive Ethernet) 또는 해당 응용 분야에 적합하고 검증된 다른 결정론적 전송 방식(Deterministic Transport)과 같은 관리된 네트워크 인터페이스를 사용해야 한다. 메시지에는 신호 스케일링, 단위, 범위, 갱신 주기, 타임아웃 한계, 카운터, 상태 필드 및 진단 정보를 정의해야 한다. 안전 관련 명령은 시스템 설계가 지원하는 경우 생존 카운터(Alive Counter), 순서 감시(Sequence Monitoring), 체크섬(Checksum), 순환 중복 검사(CRC) 또는 이에 상응하는 무결성 보호 메커니즘을 포함해야 한다.

모든 이동 중요 인터페이스(Motion-Critical Interface)에 대해 통신 타임아웃 동작(Communication Timeout Behavior)을 명확하게 정의해야 한다. 유효한 명령 스트림(Command Stream)이 상실되었을 때 액추에이터가 마지막 추진 또는 조향 명령을 무기한 유지해서는 안 된다. 수신 제어기는 지정된 타임아웃 내에서 오래된 정보를 감지하고 승인된 성능 저하 상태 또는 안전 상태로 전환해야 한다. 타임아웃 임계값은 제어 주파수, 네트워크 지연, 차량 동역학(Vehicle Dynamics), 정지 거리 및 액추에이터 응답 시간을 고려해야 한다.

DBW 상태 관리(DBW State Management)는 차량 요구사항에 따라 초기화(Initialization), 대기(Standby), 수동 제어(Manual Control), 자율주행 준비(Autonomous-Ready), 자율주행 활성(Autonomous-Active), 성능 저하(Degraded), 비상(Emergency), 고장(Fault) 및 종료(Shutdown) 상태를 구분해야 한다. 상태 간 전환은 정의된 전제조건이 충족되는 경우에만 수행해야 한다. 자율 이동에는 유효한 안전 상태, 허용 가능한 위치 추정, 정상적인 DBW 통신, 사용 가능한 제동 기능, 유효한 액추에이터 피드백 및 기타 프로젝트별 이동 활성화 조건이 요구되어야 한다.

시스템은 부팅, 소프트웨어 재시작, 유지보수, 충전, 캘리브레이션(Calibration), 통신 복구 또는 제어기 교체 과정에서 의도하지 않은 이동을 방지하기 위해 명시적인 활성화 및 억제 로직(Enable and Inhibit Logic)을 사용해야 한다. 추진 활성화는 단순히 고장이 존재하지 않는다는 조건이 아니라 정의된 조건을 의도적으로 충족한 경우에만 허용되어야 한다. 안전 회로는 자율 컴퓨팅 소프트웨어 상태와 관계없이 추진을 억제하거나 제동을 요청할 수 있는 권한을 유지해야 한다.

비상정지 동작(Emergency-Stop Operation)은 정의된 안전 경로(Safety Path)를 통해 정상적인 자율 이동 명령보다 우선해야 한다. 비상정지(E-Stop)가 활성화되면 차량 안전 아키텍처에 따라 추진력을 제거하거나 억제하고 적절한 정지 메커니즘을 작동시켜야 한다. 비상정지 상태에서 복구하려면 제어된 리셋 조건(Controlled Reset Condition)을 충족해야 하며, 비상정지 장치가 해제되었다는 이유만으로 이전 이동 명령을 자동으로 재개해서는 안 된다.

DBW 구성요소의 전력 아키텍처(Power Architecture)는 중요도에 따라 추진, 조향, 제동, 차량 제어 및 안전 감시 기능 사이에 충분한 독립성을 유지해야 한다. 보조 센서, 페이로드, 고성능 컴퓨터 또는 비핵심 전력 분기의 고장이 차량을 안전하게 정지시키는 데 필요한 전기 기능을 불필요하게 비활성화해서는 안 된다. 필요한 경우 전압 감시, 저전압 감지, 과전류 보호, 접지 및 과도전압 보호(Transient Protection)를 적용해야 한다.

부분적인 전기 고장 이후에도 조향 및 제동 기능을 사용할 수 있는지 아키텍처 설계 단계에서 고려해야 한다. 차량 위험 평가(Vehicle Risk Assessment)에서 단일 고장 이후에도 지속적인 제어가 필요하다고 판단되는 경우 이중 전원 공급(Redundant Power Feed), 백업 에너지(Backup Energy), 중복 센싱(Redundant Sensing), 독립 제어 경로, 기계적 대체 수단(Mechanical Fallback) 또는 기타 적절한 방안을 평가해야 한다. 공통 원인 고장(Common-Cause Failure)은 명목상 중복된 채널도 동시에 무력화할 수 있으므로 분석 없이 단순히 중복성을 추가해서는 안 되며 안전 요구사항에 따라 적용해야 한다.

수동 및 자율 제어 인터페이스(Manual and Autonomous Control Interface)는 명확하게 정의된 제어 권한(Command Authority)을 가져야 한다. 차량이 수동 운전, 원격 제어(Remote Control), 정비 제어 또는 원격운전(Teleoperation)을 지원하는 경우 이러한 모드와 자율 제어 사이의 우선순위 및 전환 규칙을 문서화해야 한다. 여러 제어기가 동시에 충돌하는 액추에이터 명령을 제어되지 않은 방식으로 발생시켜서는 안 된다. 제어권 전환에는 필요한 경우 명령 중립화(Command Neutralization), 상태 확인 및 적절한 운전자 또는 시스템 승인을 포함해야 한다.

차량 동역학 제약조건(Vehicle Dynamics Constraint)은 DBW 명령 검증에 포함되어야 한다. 최대 속도, 가속도, 감속도, 조향각, 조향 속도, 횡가속도(Lateral Acceleration), 곡률 및 기타 적용 가능한 한계는 차량 형상과 운용 조건에 따라 설정해야 한다. 페이로드, 지형, 경사, 기상, 위치 추정 품질, 제한 구역 또는 성능 저하 상태에 따라 서로 다른 제한값을 적용할 수 있으며, 이 경우 현재 활성화된 제한값 세트는 관리 및 진단 가능해야 한다.

DBW 진단(DBW Diagnostics)은 제어기 통신, 액추에이터 피드백, 공급 전압, 온도, 모터 또는 액추에이터 전류, 센서 타당성, 명령 추종(Command Tracking), 제어기 내부 고장 및 사용 가능한 안전 관련 상태를 지속적으로 감시해야 한다. 진단 이벤트에는 비정상적인 차량 동작을 재구성할 수 있도록 충분한 타임스탬프와 운용 상황 정보를 포함해야 한다. 엔지니어링, 생산 및 정비 도구가 DBW 고장을 일관되게 해석할 수 있도록 고장 코드(Fault Code)와 상태 정의를 관리해야 한다.

차량 운동에 영향을 미치는 캘리브레이션 파라미터(Calibration Parameter)는 구성 관리(Configuration Control)되어야 한다. 여기에는 조향 중앙 위치 및 조향비(Steering Ratio), 액추에이터 방향, 휠 직경, 휠베이스, 속도 변환 계수, 제동 응답 특성, 토크 제한, 가속도 제한, 데드 밴드(Dead Band), 명령 오프셋 및 제어 게인(Control Gain)이 포함될 수 있다. 잘못된 캘리브레이션은 모든 하드웨어 구성요소가 정상적으로 동작하는 경우에도 위험한 차량 운동을 발생시킬 수 있으므로 이러한 값의 변경에는 정의된 승인 및 검증 절차가 필요하다.

DBW 시스템은 결정론적인 시동 및 종료 시퀀스(Deterministic Startup and Shutdown Sequence)를 지원해야 한다. 전원 인가 시 통신, 피드백, 구성, 안전 상태 및 제어기 초기화가 검증될 때까지 액추에이터 출력을 억제해야 한다. 종료 과정에서는 추진력을 제어된 방식으로 감소시키거나 비활성화하고, 차량 이동을 정지시키며, 필요한 제동 또는 주차 기능을 설정하고, 요구되는 고장 및 운용 데이터를 보존해야 한다.

검증(Verification)은 정상 명령 추종, 가속 및 감속, 조향 응답, 제동 성능, 통신 중단, 오래된 명령, 손상된 메시지, 액추에이터 피드백 상실, 센서 불일치, 제어기 재설정, 전원 중단, 저전압, 비상정지, 모드 전환 및 고장 복구를 포함해야 한다. 시험은 대표적인 차량 운용 조건에서 유효한 명령의 올바른 실행뿐만 아니라 유효하지 않은 명령의 올바른 거부 또는 영향 억제(Containment)를 확인해야 한다.

고장 주입 시험(Fault-Injection Testing)은 개별 고장이 제어되지 않은 차량 운동을 발생시키지 않는다는 것을 입증해야 한다. 대표적인 고장에는 아키텍처에 따라 통신 상실, 고정된 명령(Frozen Command), 타당하지 않은 피드백, 액추에이터 포화(Actuator Saturation), 전원 상실, 제어기 재부팅, 센서 분리, 조향 고장, 추진 고장 및 제동 고장이 포함되어야 한다. 그에 따른 차량 응답은 정의된 성능 저하 상태 및 안전 상태 요구사항과 비교하고 추적성 확보를 위해 기록해야 한다.

승인된 DBW 구성은 제어기, 액추에이터, 네트워크 메시지, 전기 인터페이스, 소프트웨어 버전, 캘리브레이션 파라미터, 안전 한계, 진단 및 검증 결과에 대한 관리된 정의를 유지해야 한다. 조향, 추진, 제동, 명령 권한, 통신 타이밍 또는 안전 상태 동작에 영향을 미치는 변경은 엔지니어링 검토(Engineering Review) 및 회귀 시험(Regression Testing)을 거쳐야 한다. 최종 목적은 상위 수준 소프트웨어에 차량 운동 권한을 직접 넘기지 않으면서 자율 운행을 가능하게 하는 예측 가능하고 고장 인지형(Fault-Aware) 차량 제어 인터페이스를 구축하는 것이다.

##  

## 11.04. Outdoor Safety Requirement

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

Outdoor vehicle safety requirements shall define the measures necessary to prevent unacceptable risk during autonomous, manual, remote, maintenance, charging, startup, shutdown, and degraded operation. The safety architecture shall address hazards arising from vehicle motion, propulsion, steering, braking, electrical power, perception, localization, communication, environmental exposure, payloads, and interaction with people, vehicles, infrastructure, and terrain.

Safety requirements shall be derived from a documented risk assessment covering the intended operating environment and foreseeable misuse. Hazard analysis shall consider collision, crushing, trapping, rollover, runaway motion, unintended acceleration, steering failure, insufficient braking, localization loss, perception degradation, communication failure, electrical faults, thermal events, and loss of control on slopes or low-friction surfaces. Risk controls shall be traceable to identified hazards.

The safety concept shall use layered protection rather than relying on a single sensor, software process, communication channel, or AI function. Preventive controls, monitoring functions, operational limits, independent safety mechanisms, emergency stopping, and fault containment shall work together so that failure of the primary autonomous function does not automatically result in hazardous vehicle motion. Independence shall be proportional to the assessed risk and required safety integrity.

A dedicated safety control path shall supervise motion-critical conditions independently from high-level autonomous computing where required. Safety controllers, emergency-stop circuits, propulsion inhibit interfaces, braking requests, safety sensors, and associated power circuits shall retain sufficient authority to place the vehicle into a defined safe state. Safety action shall not depend solely on ROS 2, an AI model, a general-purpose operating system, or the primary autonomous computer.

The vehicle shall provide emergency-stop devices appropriate to its size, operating environment, and accessibility requirements. Activation of an E-Stop shall override normal motion commands, inhibit or remove propulsion, and initiate the defined stopping response. Emergency-stop circuits shall be monitored for faults where required, and release of an activated device shall not automatically restart autonomous operation or restore the previous motion command.

Safe stopping behavior shall be defined for normal protective stops, emergency stops, communication loss, localization failure, critical sensor failure, controller faults, and power abnormalities. Stopping performance shall consider vehicle mass, payload, velocity, slope, surface friction, actuator delay, brake capability, and environmental conditions. The selected stopping strategy shall avoid both uncontrolled continuation of motion and unnecessarily hazardous instantaneous actions.

Propulsion safety shall prevent unintended torque and uncontrolled acceleration. Propulsion enable shall require defined motion-permission conditions, and loss of those conditions shall cause an appropriate inhibit or controlled deceleration response. Command plausibility, velocity limits, acceleration limits, direction checks, actuator feedback, communication timeout, and propulsion status shall be monitored. A single stale or corrupted command shall not produce indefinite vehicle motion.

Steering safety shall monitor commanded and actual steering states and detect excessive deviation, implausible position, actuator saturation, communication loss, or other conditions that could compromise directional control. Steering angle and steering rate shall remain within defined limits appropriate to vehicle speed and geometry. When reliable steering control cannot be maintained, the system shall restrict motion or transition to a safe state according to the hazard analysis.

Braking shall remain available to achieve the required safe stopping performance under defined fault conditions. The safety concept shall consider service braking, regenerative braking, parking braking, and emergency braking as applicable to the vehicle architecture. Regenerative braking shall not be treated as the sole safety stopping mechanism where battery, inverter, motor, low-speed, traction, or electrical faults can reduce its effectiveness.

Perception safety shall address the detection of people, vehicles, obstacles, structures, terrain boundaries, and other hazards relevant to the operational design domain. Safety-related sensors shall provide adequate coverage for the vehicle geometry, direction of travel, speed, and stopping distance. Blind zones, sensor occlusion, contamination, adverse weather, lighting conditions, sensor failure, and mounting changes shall be considered when defining safety coverage.

Localization safety shall monitor GNSS/RTK, IMU, odometry, map-based localization, or other positioning sources used to authorize autonomous motion. RTK fixed status alone shall not constitute sufficient evidence of localization integrity. Position accuracy, heading validity, correction age, timestamp integrity, solution consistency, and disagreement between independent sources shall be evaluated, with degraded localization resulting in defined restrictions or safe-state transitions.

Vehicle speed shall be controlled according to operating conditions rather than by a single unrestricted maximum value. Safety limits may depend on pedestrian proximity, obstacle density, route geometry, curvature, slope, surface condition, visibility, localization quality, sensor coverage, payload, weather, or restricted zones. The active speed limit shall be communicated consistently to motion control and shall not be bypassed by normal autonomous planning commands.

The vehicle shall maintain safety margins between detection range, system reaction time, braking response, and stopping distance. Safety sensor coverage shall extend sufficiently beyond the required stopping envelope under applicable operating conditions. Validation shall include worst-case combinations of speed, payload, slope, surface friction, communication delay, sensor update time, processing latency, actuator response, and braking performance rather than evaluating each factor independently.

Outdoor terrain hazards shall include slopes, curbs, holes, drop-offs, uneven ground, loose surfaces, water, mud, vegetation, and obstacles capable of affecting stability or traction. The vehicle safety concept shall define allowable slope, ground clearance, obstacle capability, lateral stability, and terrain restrictions. Conditions that could cause rollover, grounding, wheel slip, loss of braking effectiveness, or loss of steering authority shall be detected or prevented through operational constraints.

Environmental conditions shall be incorporated into safety requirements because rain, fog, snow, dust, mud, direct sunlight, darkness, temperature, vibration, and contamination can degrade sensors and electrical systems. The vehicle shall detect relevant sensor degradation where practical and shall not assume nominal perception performance under all weather conditions. Environmental operating limits and corresponding degraded behaviors shall be documented for the intended deployment.

Communication loss shall not result in uncontrolled motion. Loss of fleet communication, remote-control links, correction services, cloud connectivity, or other external networks shall be classified according to their safety relevance. Functions required for immediate vehicle safety should remain locally executable whenever practical. Where continued operation depends on a lost communication service, the vehicle shall transition to a predefined restricted mode or controlled stop.

Manual, remote, teleoperation, autonomous, and service-control modes shall have clearly defined authority and transition rules. Conflicting control sources shall not simultaneously command motion without arbitration. Transfer of control shall verify vehicle state, communication availability, operator or system authorization, and command neutrality where applicable. Maintenance or service modes shall prevent unintended autonomous activation while personnel may be working near hazardous mechanisms.

Electrical safety shall address battery isolation, overcurrent protection, short circuits, ground faults where applicable, connector faults, damaged harnesses, water ingress, thermal overload, and unexpected power restoration. Safety-critical controllers and stopping functions shall receive appropriately protected power. A failure in a payload, auxiliary computer, sensor, lighting circuit, or other noncritical branch shall not unnecessarily remove the electrical capability required to place the vehicle into a safe state.

Safety-related faults shall be classified according to severity and permitted vehicle response. Some faults may allow continued operation with reduced speed or restricted functionality, while others shall require an immediate protective stop, controlled stop, or emergency action. Degraded operation shall be explicitly defined and shall not become an indefinite state in which multiple accumulated faults gradually remove the safety assumptions of the original design.

The vehicle shall provide visible, audible, or other appropriate status indications to communicate operational states where interaction with people is expected. Indications may distinguish standby, autonomous operation, remote operation, warning, fault, emergency stop, or other relevant conditions. Human-machine indications shall support situational awareness but shall not replace physical safety measures, obstacle detection, controlled speed, or emergency stopping functions.

Diagnostics and event recording shall support reconstruction of safety-relevant incidents. The system shall record applicable motion commands, vehicle velocity, steering state, brake state, safety sensor status, localization quality, operating mode, communication state, emergency-stop events, controller faults, and relevant timestamps. Logs shall be sufficiently synchronized and protected so engineering teams can determine the sequence of events surrounding abnormal behavior.

Changes to vehicle mass, payload, tires, brakes, steering hardware, sensors, computing equipment, software, calibration, route conditions, or maximum speed shall be evaluated for their effect on the safety concept. A previously validated stopping distance or stability limit shall not automatically remain valid after physical or software modifications. Safety-relevant configuration changes shall undergo controlled review, impact assessment, and appropriate regression testing.

Safety validation shall include normal operation, obstacle detection, pedestrian interaction, emergency stopping, maximum permitted speed, representative payloads, slopes, reduced-friction surfaces, sensor obstruction, localization degradation, communication interruption, controller reset, electrical faults, and degraded modes. Fault-injection testing shall verify that representative single failures are detected and produce the intended containment, restriction, stopping, or safe-state response.

Field validation shall be performed in environments representative of the intended operational design domain, including relevant road or pathway geometry, terrain, weather exposure, lighting, obstacles, communication conditions, and human interaction. Testing shall verify not only that the vehicle performs correctly when all systems are healthy, but also that safety mechanisms remain effective when sensing, localization, communication, actuation, or computing performance is degraded.

The released outdoor safety configuration shall maintain traceability among hazards, safety requirements, hardware and software mechanisms, calibration limits, verification procedures, test evidence, and approved operating conditions. The objective is to ensure that autonomous outdoor operation remains controlled when faults, environmental disturbances, human interaction, and uncertain terrain occur, and that the vehicle can reliably detect loss of required safety conditions and transition to an appropriate safe state.

옥외 차량 안전 요구사항(Outdoor Vehicle Safety Requirements)은 자율 운행(Autonomous Operation), 수동 운행(Manual Operation), 원격 운행(Remote Operation), 유지보수(Maintenance), 충전(Charging), 시동(Startup), 종료(Shutdown) 및 성능 저하 운행(Degraded Operation) 중 허용할 수 없는 위험을 방지하기 위해 필요한 조치를 정의해야 한다. 안전 아키텍처(Safety Architecture)는 차량 운동, 추진, 조향, 제동, 전력, 인지, 위치 추정, 통신, 환경 노출, 페이로드(Payload), 사람·차량·인프라 및 지형과의 상호작용에서 발생하는 위험을 다루어야 한다.

안전 요구사항은 의도된 운용 환경과 합리적으로 예측 가능한 오사용(Foreseeable Misuse)을 포함하는 문서화된 위험 평가(Risk Assessment)로부터 도출되어야 한다. 위험 분석(Hazard Analysis)은 충돌, 압착, 끼임, 전복, 폭주 이동, 의도하지 않은 가속, 조향 고장, 불충분한 제동, 위치 추정 상실, 인지 성능 저하, 통신 고장, 전기적 고장, 열적 사고 및 경사로나 저마찰 노면에서의 제어 상실을 고려해야 한다. 위험 통제(Risk Control)는 식별된 위험에 대해 추적성(Traceability)을 확보해야 한다.

안전 개념(Safety Concept)은 단일 센서, 소프트웨어 프로세스, 통신 채널 또는 AI 기능에 의존하지 않고 계층화된 보호(Layered Protection)를 사용해야 한다. 예방 제어(Preventive Control), 감시 기능, 운용 제한, 독립적인 안전 메커니즘, 비상정지 및 고장 영향 억제(Fault Containment)가 함께 작동하여 주 자율주행 기능의 고장이 자동으로 위험한 차량 운동으로 이어지지 않도록 해야 한다. 독립성 수준은 평가된 위험과 요구되는 안전 무결성(Safety Integrity)에 비례해야 한다.

필요한 경우 전용 안전 제어 경로(Dedicated Safety Control Path)는 상위 수준 자율 컴퓨팅(Autonomous Computing)과 독립적으로 이동 중요 조건(Motion-Critical Condition)을 감시해야 한다. 안전 제어기(Safety Controller), 비상정지 회로, 추진 억제 인터페이스(Propulsion Inhibit Interface), 제동 요청, 안전 센서 및 관련 전원 회로는 차량을 정의된 안전 상태(Safe State)로 전환할 수 있는 충분한 권한을 유지해야 한다. 안전 동작은 ROS 2, AI 모델, 범용 운영체제 또는 주 자율 컴퓨터에만 의존해서는 안 된다.

차량에는 차량 크기, 운용 환경 및 접근성 요구사항에 적합한 비상정지 장치(Emergency-Stop Device)를 제공해야 한다. 비상정지(E-Stop)가 활성화되면 정상 이동 명령보다 우선하여 추진을 억제하거나 제거하고 정의된 정지 동작을 시작해야 한다. 필요한 경우 비상정지 회로 자체의 고장을 감시해야 하며, 활성화된 장치가 해제되더라도 자율 운행을 자동으로 재시작하거나 이전 이동 명령을 복원해서는 안 된다.

안전 정지 동작(Safe Stopping Behavior)은 정상 보호 정지(Protective Stop), 비상정지, 통신 상실, 위치 추정 실패, 핵심 센서 고장, 제어기 고장 및 전원 이상에 대해 정의되어야 한다. 정지 성능은 차량 질량, 페이로드, 속도, 경사도, 노면 마찰, 액추에이터 지연, 제동 성능 및 환경 조건을 고려해야 한다. 선택된 정지 전략은 제어되지 않은 이동의 지속과 불필요하게 위험한 순간적 동작 모두를 방지해야 한다.

추진 안전(Propulsion Safety)은 의도하지 않은 토크와 제어되지 않은 가속을 방지해야 한다. 추진 활성화(Propulsion Enable)는 정의된 이동 허가 조건(Motion-Permission Condition)을 요구해야 하며, 해당 조건이 상실되면 적절한 추진 억제 또는 제어 감속(Controlled Deceleration)을 수행해야 한다. 명령 타당성, 속도 제한, 가속도 제한, 방향 검사, 액추에이터 피드백, 통신 타임아웃 및 추진 상태를 감시해야 하며, 하나의 오래되거나 손상된 명령이 차량을 무기한 이동시키지 못하도록 해야 한다.

조향 안전(Steering Safety)은 명령된 조향 상태와 실제 조향 상태를 감시하고 방향 제어를 저해할 수 있는 과도한 편차, 비정상적인 위치, 액추에이터 포화(Actuator Saturation), 통신 상실 또는 기타 이상 상태를 감지해야 한다. 조향각과 조향 속도는 차량 속도와 형상에 적합하게 정의된 제한 범위 내에서 유지되어야 한다. 신뢰할 수 있는 조향 제어를 유지할 수 없는 경우 위험 분석에 따라 차량 이동을 제한하거나 안전 상태로 전환해야 한다.

제동(Braking)은 정의된 고장 조건에서도 요구되는 안전 정지 성능을 달성할 수 있도록 유지되어야 한다. 안전 개념은 차량 아키텍처에 따라 상용 제동(Service Braking), 회생 제동(Regenerative Braking), 주차 제동(Parking Braking) 및 비상 제동(Emergency Braking)을 고려해야 한다. 배터리, 인버터, 모터, 저속, 접지력 또는 전기적 고장으로 회생 제동 효과가 감소할 수 있는 경우 회생 제동을 유일한 안전 정지 메커니즘으로 사용해서는 안 된다.

인지 안전(Perception Safety)은 운용 설계 영역(Operational Design Domain)과 관련된 사람, 차량, 장애물, 구조물, 지형 경계 및 기타 위험요소의 감지를 다루어야 한다. 안전 관련 센서는 차량 형상, 진행 방향, 속도 및 정지 거리에 적합한 충분한 감지 범위를 제공해야 한다. 안전 감지 범위를 정의할 때 사각지대(Blind Zone), 센서 가림(Occlusion), 오염, 악천후, 조명 조건, 센서 고장 및 장착 위치 변경을 고려해야 한다.

위치 추정 안전(Localization Safety)은 자율 이동을 허가하는 데 사용되는 GNSS/RTK, 관성측정장치(IMU), 오도메트리(Odometry), 지도 기반 위치 추정(Map-Based Localization) 또는 기타 위치 정보원을 감시해야 한다. RTK 고정 상태(RTK Fixed Status)만으로 충분한 위치 추정 무결성(Localization Integrity)이 확보되었다고 판단해서는 안 된다. 위치 정확도, 헤딩 유효성, 보정 데이터 경과 시간(Correction Age), 타임스탬프 무결성, 솔루션 일관성 및 독립적인 정보원 간 불일치를 평가하고, 위치 추정 성능 저하 시 정의된 제한 또는 안전 상태 전환을 수행해야 한다.

차량 속도는 하나의 제한 없는 최대값만을 사용하는 것이 아니라 운용 조건에 따라 제어되어야 한다. 안전 제한값은 보행자와의 거리, 장애물 밀도, 경로 형상, 곡률, 경사도, 노면 상태, 가시성, 위치 추정 품질, 센서 감지 범위, 페이로드, 기상 또는 제한 구역에 따라 달라질 수 있다. 현재 적용되는 속도 제한은 모션 제어(Motion Control)에 일관되게 전달되어야 하며 정상적인 자율 경로 계획 명령으로 우회할 수 없어야 한다.

차량은 감지 거리, 시스템 반응 시간, 제동 응답 및 정지 거리 사이에 안전 여유(Safety Margin)를 유지해야 한다. 안전 센서의 감지 범위는 적용 가능한 운용 조건에서 요구되는 정지 영역(Stopping Envelope)을 충분히 초과해야 한다. 검증에서는 속도, 페이로드, 경사도, 노면 마찰, 통신 지연, 센서 갱신 시간, 처리 지연, 액추에이터 응답 및 제동 성능을 각각 독립적으로 평가하는 것이 아니라 최악 조건의 조합을 포함해야 한다.

옥외 지형 위험(Outdoor Terrain Hazard)에는 경사면, 연석, 구멍, 단차 및 추락 지점(Drop-Off), 불규칙한 지면, 느슨한 노면, 물, 진흙, 식생 및 차량 안정성이나 접지력에 영향을 줄 수 있는 장애물이 포함되어야 한다. 차량 안전 개념은 허용 경사도, 지상고(Ground Clearance), 장애물 극복 능력, 횡방향 안정성(Lateral Stability) 및 지형 제한을 정의해야 한다. 전복, 하부 접촉(Grounding), 휠 슬립, 제동 효과 상실 또는 조향 권한 상실을 일으킬 수 있는 조건은 운용 제한을 통해 감지하거나 방지해야 한다.

비, 안개, 눈, 먼지, 진흙, 직사광선, 어둠, 온도, 진동 및 오염이 센서와 전기 시스템의 성능을 저하시킬 수 있으므로 환경 조건(Environmental Condition)을 안전 요구사항에 포함해야 한다. 가능한 경우 차량은 관련 센서 성능 저하를 감지해야 하며 모든 기상 조건에서 정상적인 인지 성능이 유지된다고 가정해서는 안 된다. 의도된 배치 환경에 대한 환경 운용 한계와 이에 대응하는 성능 저하 동작을 문서화해야 한다.

통신 상실(Communication Loss)은 제어되지 않은 차량 운동으로 이어져서는 안 된다. 플릿 통신(Fleet Communication), 원격 제어 링크, 보정 서비스, 클라우드 연결 또는 기타 외부 네트워크의 상실은 안전 관련성에 따라 분류해야 한다. 즉각적인 차량 안전에 필요한 기능은 가능한 경우 차량 내부에서 로컬로 실행할 수 있어야 한다. 운행 지속이 상실된 통신 서비스에 의존하는 경우 차량은 사전에 정의된 제한 모드(Restricted Mode) 또는 제어 정지(Controlled Stop)로 전환해야 한다.

수동, 원격, 원격운전(Teleoperation), 자율 및 정비 제어 모드는 명확하게 정의된 제어 권한과 전환 규칙을 가져야 한다. 충돌하는 제어원이 중재(Arbitration) 없이 동시에 이동 명령을 발생시켜서는 안 된다. 제어권 전환 시 차량 상태, 통신 가용성, 운전자 또는 시스템 권한 및 필요한 경우 명령 중립 상태(Command Neutrality)를 확인해야 한다. 유지보수 또는 정비 모드에서는 작업자가 위험한 기구 주변에서 작업하는 동안 의도하지 않은 자율 기능 활성화를 방지해야 한다.

전기 안전(Electrical Safety)은 배터리 절연, 과전류 보호, 단락, 필요한 경우 접지 고장, 커넥터 고장, 손상된 하네스, 수분 침투, 열 과부하 및 예상하지 못한 전원 복구를 다루어야 한다. 안전 중요 제어기와 정지 기능에는 적절하게 보호된 전원을 공급해야 한다. 페이로드, 보조 컴퓨터, 센서, 조명 회로 또는 기타 비핵심 분기의 고장이 차량을 안전 상태로 전환하는 데 필요한 전기적 기능을 불필요하게 제거해서는 안 된다.

안전 관련 고장(Safety-Related Fault)은 심각도와 허용 가능한 차량 대응에 따라 분류해야 한다. 일부 고장은 속도 감소 또는 기능 제한 상태에서 운행을 계속할 수 있지만, 다른 고장은 즉각적인 보호 정지, 제어 정지 또는 비상 동작을 요구할 수 있다. 성능 저하 운행은 명확하게 정의되어야 하며 여러 고장이 누적되어 원래 설계의 안전 가정을 점진적으로 제거하는 무기한 상태로 지속되어서는 안 된다.

사람과의 상호작용이 예상되는 경우 차량은 운용 상태를 전달하기 위한 시각적, 청각적 또는 기타 적절한 상태 표시(Status Indication)를 제공해야 한다. 표시 기능은 대기, 자율 운행, 원격 운행, 경고, 고장, 비상정지 또는 기타 관련 상태를 구분할 수 있다. 인간-기계 표시(Human-Machine Indication)는 상황 인식(Situational Awareness)을 지원해야 하지만 물리적 안전 수단, 장애물 감지, 제한 속도 또는 비상정지 기능을 대체해서는 안 된다.

진단 및 이벤트 기록(Diagnostics and Event Recording)은 안전 관련 사고의 재구성을 지원해야 한다. 시스템은 적용 가능한 이동 명령, 차량 속도, 조향 상태, 제동 상태, 안전 센서 상태, 위치 추정 품질, 운용 모드, 통신 상태, 비상정지 이벤트, 제어기 고장 및 관련 타임스탬프를 기록해야 한다. 로그(Log)는 엔지니어링 팀이 비정상 동작 전후의 사건 순서를 판단할 수 있도록 충분히 동기화되고 보호되어야 한다.

차량 질량, 페이로드, 타이어, 브레이크, 조향 하드웨어, 센서, 컴퓨팅 장비, 소프트웨어, 캘리브레이션, 경로 조건 또는 최대 속도의 변경은 안전 개념에 미치는 영향을 평가해야 한다. 기존에 검증된 정지 거리 또는 안정성 한계가 물리적 또는 소프트웨어 변경 이후에도 자동으로 유효하다고 간주해서는 안 된다. 안전 관련 구성 변경은 관리된 검토, 영향 평가(Impact Assessment) 및 적절한 회귀 시험(Regression Testing)을 거쳐야 한다.

안전 검증(Safety Validation)은 정상 운행, 장애물 감지, 보행자 상호작용, 비상정지, 최대 허용 속도, 대표적인 페이로드, 경사면, 저마찰 노면, 센서 가림, 위치 추정 성능 저하, 통신 중단, 제어기 재설정, 전기적 고장 및 성능 저하 모드를 포함해야 한다. 고장 주입 시험(Fault-Injection Testing)을 통해 대표적인 단일 고장이 감지되고 의도된 영향 억제, 제한, 정지 또는 안전 상태 대응을 발생시키는지 검증해야 한다.

현장 검증(Field Validation)은 관련 도로 또는 경로 형상, 지형, 기상 노출, 조명, 장애물, 통신 조건 및 사람과의 상호작용을 포함하여 의도된 운용 설계 영역을 대표하는 환경에서 수행해야 한다. 시험에서는 모든 시스템이 정상일 때 차량이 올바르게 작동하는지만 확인하는 것이 아니라 센싱, 위치 추정, 통신, 구동 또는 컴퓨팅 성능이 저하된 경우에도 안전 메커니즘이 효과적으로 유지되는지 검증해야 한다.

승인된 옥외 안전 구성(Released Outdoor Safety Configuration)은 위험요소, 안전 요구사항, 하드웨어 및 소프트웨어 메커니즘, 캘리브레이션 한계, 검증 절차, 시험 증거(Test Evidence) 및 승인된 운용 조건 사이의 추적성을 유지해야 한다. 최종 목적은 고장, 환경적 교란, 사람과의 상호작용 및 불확실한 지형이 발생하는 상황에서도 옥외 자율 운행을 통제된 상태로 유지하고, 차량이 요구되는 안전 조건의 상실을 신뢰성 있게 감지하여 적절한 안전 상태로 전환할 수 있도록 하는 것이다.

##  

## 11.05. Outdoor Test Requirement

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

Outdoor vehicle testing shall verify that the complete vehicle satisfies its electrical, control, localization, perception, communication, safety, environmental, and autonomous-operation requirements under conditions representative of the intended deployment. Testing shall evaluate the integrated vehicle rather than only individual components because interactions among propulsion, steering, braking, sensors, computing, power, networks, terrain, and software can create system-level failures not visible during bench testing.

The test program shall be derived from approved system requirements, hazard analysis, interface specifications, operating limits, and the intended operational design domain. Each requirement shall be linked to an appropriate verification method such as inspection, analysis, bench testing, vehicle testing, fault injection, or field validation. Test cases shall define configuration, prerequisites, environmental conditions, procedure, measured parameters, acceptance criteria, and required evidence.

The test vehicle configuration shall be controlled before formal verification begins. Hardware versions, software releases, firmware, calibration data, sensor mounting positions, tire specifications, vehicle mass, payload, battery configuration, network definitions, and safety parameters shall be recorded. Any configuration change during testing shall be documented so results obtained from different vehicle configurations are not incorrectly treated as equivalent evidence.

Electrical testing shall verify battery interfaces, power distribution, DC/DC conversion, protection devices, grounding, voltage rails, current consumption, startup behavior, shutdown behavior, and auxiliary power outputs. Measurements shall include nominal and worst-case voltage drop, steady-state current, peak current, inrush current, transient response, and relevant thermal conditions. Protection behavior shall be confirmed without creating uncontrolled motion or secondary electrical hazards.

Power integrity shall be evaluated during simultaneous high-load operation, including propulsion, steering, braking, computing, sensing, communication, lighting, and representative payload operation where applicable. Tests shall determine whether rapid acceleration, steering activity, actuator transients, or auxiliary loads cause unacceptable voltage disturbance, controller reset, sensor dropout, communication errors, or localization degradation. Brownout recovery shall also be verified.

Propulsion testing shall verify commanded velocity, acceleration, deceleration, direction, torque response, velocity limiting, and propulsion inhibit behavior. Testing shall cover unloaded and representative payload conditions together with applicable slopes and surface conditions. The vehicle shall demonstrate predictable response to valid commands and shall reject or safely contain invalid, stale, conflicting, or out-of-range propulsion commands according to the approved DBW design rules.

Steering testing shall verify steering-angle command tracking, center calibration, steering-rate limits, mechanical limits, feedback accuracy, repeatability, and response under representative vehicle loads. Dynamic tests shall confirm that steering behavior remains stable throughout the approved speed range. Communication interruption, actuator saturation, invalid feedback, controller reset, or other representative steering faults shall produce the specified degraded or safe-state response.

Braking tests shall establish stopping performance under representative combinations of vehicle mass, payload, speed, slope, and surface friction. Service braking, emergency braking, parking braking, and regenerative braking shall be evaluated where applicable. Testing shall verify that sufficient stopping capability remains when regenerative braking is unavailable or reduced and that braking faults are detected and handled according to the defined safety architecture.

Stopping-distance validation shall include the complete sensing-to-stop chain rather than brake hardware alone. Detection range, sensor update period, processing latency, network delay, decision time, DBW response, actuator delay, tire-road friction, and mechanical braking distance shall be considered. Worst-case combinations relevant to the operational design domain shall be evaluated to demonstrate that safety sensor coverage provides adequate stopping margin.

GNSS/RTK testing shall verify static and dynamic positioning accuracy, RTK convergence, fix-state transitions, heading performance, correction age, communication recovery, repeatability, and operation under representative satellite visibility. Tests shall include open-sky conditions and applicable obstructed environments such as trees, buildings, bridges, retaining structures, or other deployment-specific features capable of producing multipath or degraded reception.

Localization testing shall evaluate the integrated use of GNSS/RTK, IMU, wheel odometry, steering feedback, LiDAR localization, visual localization, or other configured sources. Controlled GNSS degradation and outage tests shall confirm that the system detects loss of localization integrity rather than continuing autonomous operation on unreliable coordinates. Recovery behavior and transition between normal, degraded, and restricted localization states shall be verified.

Perception testing shall verify detection of relevant people, vehicles, obstacles, structures, terrain boundaries, and other hazards throughout the required sensor coverage. Representative target sizes, positions, approach directions, vehicle speeds, and distances shall be included. Tests shall also evaluate blind zones, partial occlusion, sensor contamination, mounting tolerances, and degraded sensing conditions relevant to the intended outdoor environment.

Environmental perception tests shall address variations in daylight, darkness, shadows, direct sunlight, rain, fog, dust, mud, or other applicable conditions. The purpose shall not be to assume identical sensor performance under every environment, but to identify operating limits and verify appropriate degradation detection. When perception quality becomes insufficient for the current speed or route, the vehicle shall restrict operation or execute the specified safe response.

Communication testing shall verify CAN, CAN FD, Ethernet, wireless, remote-control, fleet, RTK correction, and other configured interfaces as applicable. Message timing, bandwidth, latency, timeout detection, integrity checking, reconnect behavior, and network loading shall be measured. Tests shall confirm that communication loss does not cause indefinite continuation of the last motion command and that locally required safety functions remain available.

Time-synchronization testing shall verify timestamps and clock relationships among GNSS, IMU, cameras, LiDAR, radar, wheel sensors, computing nodes, and recorded diagnostic data where applicable. GNSS time, PPS, PTP, hardware triggering, or other implemented mechanisms shall be tested according to required accuracy. Loss of synchronization shall be detectable, and resulting sensor-fusion behavior shall comply with the defined degraded-operation strategy.

Autonomous driving tests shall evaluate route following, waypoint navigation, path tracking, obstacle avoidance, stopping, restarting, turning, reversing, and other functions required by the intended application. Tests shall include representative speeds, payloads, route geometry, slopes, surface conditions, and traffic interactions. Autonomous performance shall be evaluated together with safety constraints rather than only measuring successful completion of the planned route.

Terrain testing shall cover representative slopes, uneven surfaces, curbs, obstacles, depressions, loose ground, low-friction surfaces, mud, water, vegetation, or other conditions relevant to the approved operational domain. Tests shall verify ground clearance, traction, stability, steering authority, braking capability, and obstacle traversal limits. Conditions approaching rollover, grounding, excessive wheel slip, or loss of control shall be evaluated without exceeding controlled test safety limits.

Safety-function testing shall verify emergency stops, protective stops, propulsion inhibition, safety sensing, speed restrictions, mode transitions, warning indications, and safe-state behavior. Emergency-stop testing shall confirm stopping response and verify that releasing the E-Stop does not automatically resume motion. Safety mechanisms shall remain effective during representative failures of autonomous computing, communication, localization, sensing, or noncritical electrical functions.

Fault-injection testing shall intentionally introduce controlled failures to verify diagnostic coverage and system response. Representative faults may include sensor disconnection, communication timeout, corrupted or frozen commands, invalid actuator feedback, GNSS loss, RTK correction loss, controller reboot, undervoltage, network interruption, steering fault, braking fault, or propulsion fault. Each injected condition shall produce the documented containment, degradation, stopping, or recovery behavior.

Environmental and durability testing shall evaluate the electrical and electronic system against applicable temperature, humidity, water, dust, vibration, shock, corrosion, and mechanical exposure requirements. Vehicle-level tests shall pay particular attention to connectors, harness routing, sensor mounts, antennas, enclosures, cooling systems, and moving cable interfaces. Post-test inspection shall identify loosening, abrasion, leakage, deformation, corrosion, or electrical degradation.

Electromagnetic compatibility testing shall evaluate whether propulsion electronics, motors, inverters, DC/DC converters, radios, computing equipment, and high-current switching interfere with GNSS, IMU, cameras, LiDAR, communication networks, or control electronics. Testing shall also assess susceptibility to representative external disturbances. EMC issues detected only during vehicle operation shall be documented and corrected before release.

Diagnostics and logging shall be verified throughout the test program. Recorded information should permit reconstruction of vehicle speed, command state, steering, braking, localization quality, perception status, communication state, safety events, controller faults, and relevant electrical conditions. Timestamp consistency and log retention shall be sufficient to correlate failures across distributed controllers and computing systems during engineering analysis.

Field validation shall use routes and environments representative of actual deployment and shall include repeated operation rather than a single successful demonstration. Testing shall evaluate variation in weather, lighting, GNSS reception, communication quality, terrain, payload, traffic, and human interaction as applicable. Repeated failures, intermittent anomalies, or location-specific problems shall be recorded and resolved or incorporated into approved operational restrictions.

Regression testing shall be performed when changes affect safety-relevant hardware, software, firmware, calibration, sensors, actuators, vehicle mass, tires, braking, steering, network configuration, power architecture, or operating limits. The regression scope shall be determined through change-impact analysis. Previously completed tests may be reused only when their configuration and assumptions remain valid for the modified vehicle.

Test completion shall require objective evidence demonstrating compliance with defined acceptance criteria. Evidence may include measurement files, diagnostic logs, photographs where required by the test procedure, configuration records, calibration records, test reports, and identified anomalies with disposition. Failed or conditionally accepted tests shall remain traceable to corrective actions and subsequent verification rather than being removed from the validation history.

The released outdoor vehicle shall maintain traceability from requirements and hazards through test cases, configurations, measured results, failures, corrective actions, and final acceptance evidence. The objective of the outdoor test requirement is to demonstrate not only that the vehicle operates successfully under nominal conditions, but that it remains predictable, diagnosable, controllable, and capable of reaching an appropriate safe state when real-world disturbances and failures occur.

옥외 차량 시험(Outdoor Vehicle Testing)은 완성 차량이 의도된 배치 환경을 대표하는 조건에서 전기, 제어, 위치 추정, 인지, 통신, 안전, 환경 및 자율 운행 요구사항을 충족하는지 검증해야 한다. 추진, 조향, 제동, 센서, 컴퓨팅, 전력, 네트워크, 지형 및 소프트웨어 사이의 상호작용으로 벤치 시험(Bench Testing)에서는 발견하기 어려운 시스템 수준 고장이 발생할 수 있으므로 개별 구성요소뿐만 아니라 통합 차량 전체를 평가해야 한다.

시험 프로그램(Test Program)은 승인된 시스템 요구사항, 위험 분석(Hazard Analysis), 인터페이스 사양, 운용 한계 및 의도된 운용 설계 영역(Operational Design Domain)을 기반으로 수립해야 한다. 각 요구사항은 검사, 분석, 벤치 시험, 차량 시험, 고장 주입(Fault Injection) 또는 현장 검증(Field Validation)과 같은 적절한 검증 방법과 연결되어야 한다. 시험 항목에는 구성, 사전조건, 환경 조건, 절차, 측정 파라미터, 합격 기준 및 요구 증거를 정의해야 한다.

정식 검증을 시작하기 전에 시험 차량 구성(Test Vehicle Configuration)을 관리해야 한다. 하드웨어 버전, 소프트웨어 릴리스, 펌웨어, 캘리브레이션 데이터, 센서 장착 위치, 타이어 사양, 차량 질량, 페이로드(Payload), 배터리 구성, 네트워크 정의 및 안전 파라미터를 기록해야 한다. 시험 중 구성 변경이 발생한 경우 서로 다른 차량 구성에서 획득한 결과를 동일한 검증 증거로 잘못 취급하지 않도록 해당 변경을 문서화해야 한다.

전기 시험(Electrical Testing)은 배터리 인터페이스, 전력 분배, DC/DC 변환, 보호 장치, 접지, 전압 레일, 소비 전류, 시동 동작, 종료 동작 및 보조 전원 출력을 검증해야 한다. 측정에는 정상 및 최악 조건의 전압 강하, 정상 상태 전류, 피크 전류, 돌입 전류(Inrush Current), 과도 응답(Transient Response) 및 관련 열적 조건을 포함해야 한다. 보호 동작은 제어되지 않은 차량 이동이나 이차적인 전기적 위험을 발생시키지 않는 상태에서 확인해야 한다.

전력 무결성(Power Integrity)은 추진, 조향, 제동, 컴퓨팅, 센싱, 통신, 조명 및 해당되는 경우 대표적인 페이로드를 동시에 높은 부하로 운용하는 조건에서 평가해야 한다. 급가속, 조향 동작, 액추에이터 과도 부하 또는 보조 부하가 허용할 수 없는 전압 변동, 제어기 재설정, 센서 단절, 통신 오류 또는 위치 추정 성능 저하를 발생시키는지 확인해야 한다. 브라운아웃 복구(Brownout Recovery) 또한 검증해야 한다.

추진 시험(Propulsion Testing)은 명령 속도, 가속, 감속, 진행 방향, 토크 응답, 속도 제한 및 추진 억제 동작을 검증해야 한다. 시험은 무부하 및 대표적인 페이로드 조건과 함께 적용 가능한 경사 및 노면 조건을 포함해야 한다. 차량은 유효한 명령에 대해 예측 가능한 응답을 나타내야 하며 승인된 DBW 설계 규칙(Drive-by-Wire Design Rules)에 따라 유효하지 않거나 오래되었거나 충돌하거나 허용 범위를 벗어난 추진 명령을 거부하거나 안전하게 억제해야 한다.

조향 시험(Steering Testing)은 조향각 명령 추종, 중앙 위치 캘리브레이션, 조향 속도 제한, 기계적 한계, 피드백 정확도, 반복성 및 대표적인 차량 부하 조건에서의 응답을 검증해야 한다. 동적 시험(Dynamic Test)을 통해 승인된 속도 범위 전체에서 조향 동작이 안정적으로 유지되는지 확인해야 한다. 통신 중단, 액추에이터 포화, 유효하지 않은 피드백, 제어기 재설정 또는 기타 대표적인 조향 고장은 지정된 성능 저하 상태(Degraded State) 또는 안전 상태(Safe State) 대응을 발생시켜야 한다.

제동 시험(Braking Test)은 차량 질량, 페이로드, 속도, 경사도 및 노면 마찰의 대표적인 조합에서 정지 성능을 확인해야 한다. 해당되는 경우 상용 제동(Service Braking), 비상 제동(Emergency Braking), 주차 제동(Parking Braking) 및 회생 제동(Regenerative Braking)을 평가해야 한다. 회생 제동이 사용 불가능하거나 감소된 경우에도 충분한 정지 능력이 유지되며, 제동 고장이 정의된 안전 아키텍처에 따라 감지되고 처리되는지 검증해야 한다.

정지 거리 검증(Stopping-Distance Validation)은 제동 하드웨어만이 아니라 센싱부터 정지까지의 전체 체인(Sensing-to-Stop Chain)을 포함해야 한다. 감지 거리, 센서 갱신 주기, 처리 지연, 네트워크 지연, 의사결정 시간, DBW 응답, 액추에이터 지연, 타이어-노면 마찰 및 기계적 제동 거리를 고려해야 한다. 운용 설계 영역과 관련된 최악 조건 조합을 평가하여 안전 센서의 감지 범위가 충분한 정지 여유(Stopping Margin)를 제공하는지 입증해야 한다.

GNSS/RTK 시험은 정적 및 동적 위치 정확도, RTK 수렴, 픽스 상태(Fix-State) 전환, 헤딩 성능, 보정 데이터 경과 시간(Correction Age), 통신 복구, 반복성 및 대표적인 위성 가시성 조건에서의 동작을 검증해야 한다. 시험은 개방된 상공(Open-Sky) 조건과 함께 나무, 건물, 교량, 옹벽 또는 다중경로(Multipath)나 수신 성능 저하를 발생시킬 수 있는 배치 환경별 구조물과 같은 적용 가능한 차폐 환경을 포함해야 한다.

위치 추정 시험(Localization Testing)은 GNSS/RTK, 관성측정장치(IMU), 휠 오도메트리(Wheel Odometry), 조향 피드백, 라이다 위치 추정(LiDAR Localization), 비전 기반 위치 추정(Visual Localization) 또는 기타 구성된 정보원의 통합 사용을 평가해야 한다. 제어된 GNSS 성능 저하 및 단절 시험을 통해 시스템이 신뢰할 수 없는 좌표를 사용하여 자율 운행을 계속하지 않고 위치 추정 무결성(Localization Integrity)의 상실을 감지하는지 확인해야 한다. 정상, 성능 저하 및 제한된 위치 추정 상태 사이의 복구 동작과 전환을 검증해야 한다.

인지 시험(Perception Testing)은 요구되는 센서 감지 범위 전체에서 관련 사람, 차량, 장애물, 구조물, 지형 경계 및 기타 위험요소의 감지를 검증해야 한다. 대표적인 대상 크기, 위치, 접근 방향, 차량 속도 및 거리를 포함해야 한다. 시험에서는 의도된 옥외 환경과 관련된 사각지대(Blind Zone), 부분적인 가림(Partial Occlusion), 센서 오염, 장착 공차 및 성능 저하 센싱 조건도 평가해야 한다.

환경 인지 시험(Environmental Perception Test)은 주간 조명, 어둠, 그림자, 직사광선, 비, 안개, 먼지, 진흙 또는 기타 적용 가능한 조건의 변화를 다루어야 한다. 시험의 목적은 모든 환경에서 동일한 센서 성능을 가정하는 것이 아니라 운용 한계를 식별하고 적절한 성능 저하 감지를 검증하는 것이다. 인지 품질이 현재 속도 또는 경로에 충분하지 않은 경우 차량은 운행을 제한하거나 지정된 안전 대응을 실행해야 한다.

통신 시험(Communication Testing)은 해당되는 경우 CAN, CAN FD, 이더넷(Ethernet), 무선 통신, 원격 제어, 플릿(Fleet), RTK 보정 및 기타 구성된 인터페이스를 검증해야 한다. 메시지 타이밍, 대역폭, 지연, 타임아웃 감지, 무결성 검사, 재연결 동작 및 네트워크 부하를 측정해야 한다. 통신 상실이 마지막 이동 명령의 무기한 지속을 발생시키지 않으며 차량 내부에서 필요한 안전 기능이 계속 사용 가능한지 확인해야 한다.

시간 동기화 시험(Time-Synchronization Testing)은 해당되는 경우 GNSS, IMU, 카메라, 라이다, 레이더, 휠 센서, 컴퓨팅 노드 및 기록된 진단 데이터 사이의 타임스탬프와 클록 관계를 검증해야 한다. GNSS 시간, 초당 펄스(PPS), 정밀 시간 프로토콜(PTP), 하드웨어 트리거링 또는 기타 구현된 메커니즘을 요구 정확도에 따라 시험해야 한다. 동기화 상실은 감지 가능해야 하며 이에 따른 센서 융합 동작은 정의된 성능 저하 운용 전략을 준수해야 한다.

자율주행 시험(Autonomous Driving Test)은 의도된 응용 분야에 필요한 경로 추종, 웨이포인트 내비게이션(Waypoint Navigation), 경로 추적(Path Tracking), 장애물 회피, 정지, 재출발, 선회, 후진 및 기타 기능을 평가해야 한다. 시험에는 대표적인 속도, 페이로드, 경로 형상, 경사도, 노면 상태 및 교통 상호작용을 포함해야 한다. 자율주행 성능은 계획된 경로의 성공적인 완료 여부만 측정하지 않고 안전 제약조건과 함께 평가해야 한다.

지형 시험(Terrain Testing)은 승인된 운용 영역과 관련된 대표적인 경사면, 불규칙한 노면, 연석, 장애물, 함몰부, 느슨한 지면, 저마찰 노면, 진흙, 물, 식생 또는 기타 조건을 포함해야 한다. 시험에서는 지상고(Ground Clearance), 접지력(Traction), 안정성, 조향 권한, 제동 능력 및 장애물 통과 한계를 검증해야 한다. 전복, 하부 접촉(Grounding), 과도한 휠 슬립 또는 제어 상실에 접근하는 조건은 관리된 시험 안전 한계를 초과하지 않는 범위에서 평가해야 한다.

안전 기능 시험(Safety-Function Testing)은 비상정지, 보호 정지, 추진 억제, 안전 센싱, 속도 제한, 모드 전환, 경고 표시 및 안전 상태 동작을 검증해야 한다. 비상정지 시험은 정지 응답을 확인하고 비상정지 장치의 해제가 자동으로 차량 이동을 재개하지 않는지 검증해야 한다. 안전 메커니즘은 자율 컴퓨팅, 통신, 위치 추정, 센싱 또는 비핵심 전기 기능의 대표적인 고장 상황에서도 유효하게 유지되어야 한다.

고장 주입 시험(Fault-Injection Testing)은 진단 범위(Diagnostic Coverage)와 시스템 대응을 검증하기 위해 의도적으로 제어된 고장을 발생시켜야 한다. 대표적인 고장에는 센서 분리, 통신 타임아웃, 손상되거나 고정된 명령, 유효하지 않은 액추에이터 피드백, GNSS 상실, RTK 보정 상실, 제어기 재부팅, 저전압, 네트워크 중단, 조향 고장, 제동 고장 또는 추진 고장이 포함될 수 있다. 각 고장 조건은 문서화된 영향 억제, 성능 저하, 정지 또는 복구 동작을 발생시켜야 한다.

환경 및 내구 시험(Environmental and Durability Testing)은 적용 가능한 온도, 습도, 물, 먼지, 진동, 충격, 부식 및 기계적 노출 요구사항에 대해 전기·전자 시스템을 평가해야 한다. 차량 수준 시험에서는 특히 커넥터, 하네스 배선, 센서 마운트, 안테나, 인클로저(Enclosure), 냉각 시스템 및 가동 케이블 인터페이스에 주의를 기울여야 한다. 시험 후 검사를 통해 풀림, 마모, 누수, 변형, 부식 또는 전기적 성능 저하를 식별해야 한다.

전자기 적합성 시험(Electromagnetic Compatibility Testing)은 추진 전자장치, 모터, 인버터, DC/DC 컨버터, 무선 장치, 컴퓨팅 장비 및 고전류 스위칭이 GNSS, IMU, 카메라, 라이다, 통신 네트워크 또는 제어 전자장치에 간섭을 발생시키는지 평가해야 한다. 또한 대표적인 외부 전자기 교란에 대한 내성(Susceptibility)을 평가해야 한다. 차량 운행 중에만 발견되는 EMC 문제도 문서화하고 제품 출시 전에 수정해야 한다.

진단 및 로깅(Diagnostics and Logging)은 전체 시험 프로그램에 걸쳐 검증되어야 한다. 기록된 정보는 차량 속도, 명령 상태, 조향, 제동, 위치 추정 품질, 인지 상태, 통신 상태, 안전 이벤트, 제어기 고장 및 관련 전기적 조건을 재구성할 수 있어야 한다. 타임스탬프 일관성과 로그 보존(Log Retention)은 엔지니어링 분석 과정에서 분산 제어기 및 컴퓨팅 시스템 사이의 고장을 상호 연계할 수 있을 정도로 충분해야 한다.

현장 검증(Field Validation)은 실제 배치 환경을 대표하는 경로와 환경을 사용해야 하며 한 번의 성공적인 시연이 아니라 반복적인 운행을 포함해야 한다. 시험에서는 해당되는 경우 기상, 조명, GNSS 수신, 통신 품질, 지형, 페이로드, 교통 및 사람과의 상호작용 변화를 평가해야 한다. 반복되는 고장, 간헐적 이상 또는 특정 위치에서 발생하는 문제는 기록하여 해결하거나 승인된 운용 제한(Operational Restriction)에 반영해야 한다.

회귀 시험(Regression Testing)은 안전 관련 하드웨어, 소프트웨어, 펌웨어, 캘리브레이션, 센서, 액추에이터, 차량 질량, 타이어, 제동, 조향, 네트워크 구성, 전력 아키텍처 또는 운용 한계에 영향을 미치는 변경이 발생할 때 수행해야 한다. 회귀 시험 범위는 변경 영향 분석(Change-Impact Analysis)을 통해 결정해야 한다. 기존에 완료된 시험은 해당 시험의 구성과 가정이 변경된 차량에서도 계속 유효한 경우에만 재사용할 수 있다.

시험 완료(Test Completion)를 위해서는 정의된 합격 기준을 충족한다는 객관적인 증거(Objective Evidence)가 필요하다. 증거에는 측정 파일, 진단 로그, 시험 절차에서 요구하는 경우 사진, 구성 기록, 캘리브레이션 기록, 시험 보고서 및 처리 결과가 포함된 이상 항목(Anomaly)이 포함될 수 있다. 실패하거나 조건부 승인된 시험은 검증 이력에서 제거하지 않고 시정 조치(Corrective Action) 및 후속 검증과의 추적성을 유지해야 한다.

출시된 옥외 차량(Released Outdoor Vehicle)은 요구사항과 위험요소에서 시험 항목, 차량 구성, 측정 결과, 고장, 시정 조치 및 최종 승인 증거에 이르는 추적성(Traceability)을 유지해야 한다. 옥외 시험 요구사항의 최종 목적은 차량이 정상 조건에서 성공적으로 운행한다는 것뿐만 아니라 실제 환경에서 교란과 고장이 발생하는 경우에도 예측 가능하고(Predictable), 진단 가능하며(Diagnosable), 제어 가능하고(Controllable), 적절한 안전 상태에 도달할 수 있음을 입증하는 것이다.
