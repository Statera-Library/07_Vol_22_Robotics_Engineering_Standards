**Volume 22. Hills Robotics Engineering Standards**


# Chapter 12. HRS-012 Cargo UAV

##  

## 12.01. UAV EE Architecture

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

The UAV electrical and electronic architecture shall establish a layered, fault-contained foundation for cargo aircraft in which propulsion, flight control, avionics, payload, communication, and utility functions are separated according to criticality. The architecture shall define electrical boundaries, power domains, data interfaces, redundancy paths, and failure containment so that a fault in a noncritical subsystem cannot propagate into flight-critical functions.

The architecture shall support the Cargo UAV product family defined within the robotics engineering standards and shall provide a common engineering baseline that can scale from experimental platforms to large cargo UAV configurations. Platform-specific implementations may vary in voltage, propulsion power, payload capacity, and redundancy level, but the fundamental partitioning philosophy, interface control, protection strategy, and verification approach shall remain consistent.

Electrical power shall be organized into clearly identified propulsion, avionics, mission, payload, and auxiliary domains. High-power propulsion circuits shall be physically and electrically separated from low-voltage avionics wherever practical. Power distribution shall include appropriately coordinated contactors, circuit protection, isolation devices, current measurement, and controlled switching so that abnormal loads can be disconnected without unnecessarily removing power from flight-critical equipment.

Flight-critical electrical loads shall receive power through architectures designed to avoid credible single-point failures. Flight control computers, essential navigation sensors, critical communication equipment, actuator control electronics, and required monitoring functions shall use independent or redundant supply paths where the aircraft safety assessment requires continued operation. Backup energy shall provide sufficient transition capability when the primary generation or distribution path becomes unavailable.

The propulsion electrical domain shall integrate energy sources, power conversion equipment, motor controllers or inverters, propulsion motors, and associated protection and monitoring devices. For hybrid-electric or turbine-electric cargo UAVs, generation and propulsion distribution shall be coordinated with battery-supported avionics power. Propulsion faults shall be detected and isolated at the smallest practical electrical boundary while preserving controllability through remaining propulsion channels.

The avionics domain shall provide deterministic and traceable interfaces among the flight control computer, autopilot functions, IMU/AHRS, GNSS, air-data sensors, actuator controllers, navigation equipment, and health-monitoring systems. Its architecture shall remain logically independent from high-bandwidth mission computing so that perception, logistics, payload processing, or AI workloads cannot compromise the timing or availability of essential flight-control functions.

Communication networks shall be partitioned according to function, bandwidth, determinism, and safety criticality. Suitable interfaces may include aerospace data buses, deterministic Ethernet, CAN-based networks, serial links, and dedicated discrete I/O where appropriate. Gateways between network domains shall control data flow and prevent uncontrolled coupling between flight-critical avionics, mission computers, payload systems, maintenance interfaces, and external communication equipment.

Cargo management shall form a controlled electrical domain connected to the aircraft through defined power and data interfaces. Cargo weight sensing, center-of-gravity monitoring, lock and release mechanisms, payload identification, and environmental monitoring shall report their status to the relevant aircraft systems without creating dependencies that can destabilize flight control. Safety-critical cargo release or locking functions shall include independent state confirmation where required.

Sensor architecture shall distinguish sensors required for basic aircraft stabilization and navigation from sensors supporting autonomy, perception, obstacle detection, landing assistance, or mission intelligence. IMU, AHRS, GNSS, altitude, air-data, and other essential navigation sources shall be assigned appropriate redundancy and independent electrical paths. Additional cameras, LiDAR, radar, or AI perception sensors shall normally reside in mission-oriented domains with controlled interfaces to avionics.

Grounding, bonding, shielding, and electromagnetic compatibility shall be treated as system-level architectural properties rather than component-level corrections. High-current switching loops, motor phases, inverter cables, antennas, GNSS receivers, sensor wiring, and digital communication links shall be routed and segregated according to their electromagnetic characteristics. Structural bonding and reference-ground strategies shall minimize common-mode interference while supporting lightning and transient protection requirements.

The architecture shall incorporate continuous electrical health monitoring for major power sources, distribution channels, converters, propulsion controllers, avionics supplies, and critical loads. Voltage, current, temperature, insulation status, breaker or contactor state, and relevant diagnostic information shall be collected with sufficient integrity to support fault detection, maintenance, and flight decisions. Diagnostic coverage shall distinguish transient anomalies from persistent or safety-significant failures.

Fault management shall follow a detect, isolate, reconfigure, and recover philosophy appropriate to the aircraft safety objectives. The electrical architecture shall provide sufficient observability for the flight control system to determine which resources remain available after a failure. Reconfiguration may transfer loads to redundant buses, isolate damaged propulsion branches, activate backup supplies, degrade mission functions, or initiate a controlled landing when continued normal operation cannot be assured.

Physical implementation shall maintain separation between redundant channels where a common physical event could defeat electrical redundancy. Harness routing, connectors, power distribution units, computers, sensors, and communication paths shall consider fire zones, vibration, thermal exposure, moisture, mechanical damage, and maintenance access. Redundant wiring routed through the same vulnerable location shall not automatically be considered independent simply because separate electrical circuits are used.

The architecture shall provide defined interfaces for ground power, charging, maintenance, software loading, diagnostics, and preflight inspection. Maintenance interfaces shall permit engineers to verify power integrity, communication status, sensor health, stored faults, configuration identity, and redundancy availability without uncontrolled access to flight-critical networks. Ground operations shall prevent unintended propulsion activation and shall provide clear electrical states for servicing and cargo handling.

Configuration management shall preserve traceability between the electrical architecture, wiring diagrams, interface control documents, network definitions, software configuration, component part numbers, protection settings, and verification evidence. Any change affecting power demand, fault containment, network loading, redundancy, electromagnetic compatibility, or safety assumptions shall trigger an engineering impact assessment before release. Architecture baselines shall therefore remain synchronized with aircraft configuration throughout development.

Verification shall demonstrate correct operation not only under nominal conditions but also during representative electrical failures. Testing shall include power-up and shutdown sequencing, bus transfer, source loss, converter failure, communication interruption, sensor loss, propulsion-channel isolation, degraded voltage, abnormal load behavior, and restoration where applicable. Hardware-in-the-loop and aircraft-level tests should confirm that implemented fault responses match the intended architecture.

The resulting UAV E/E architecture shall serve as the common technical framework linking avionics, safety, communication, propulsion, cargo management, testing, and certification activities within the Cargo UAV engineering standards. Detailed requirements for avionics, UAV safety, communication, and certification are addressed by the subsequent HRS_012 standards, while this architecture establishes the electrical partitioning, interfaces, redundancy principles, and design constraints upon which those standards depend.

무인항공기(UAV) 전기전자(E/E) 아키텍처는 추진(Propulsion), 비행 제어(Flight Control), 항공전자(Avionics), 페이로드(Payload), 통신(Communication), 유틸리티(Utility) 기능을 중요도(Criticality)에 따라 분리하는 계층화되고 고장 격리(Fault-Contained)된 기반 구조를 구축해야 한다. 아키텍처는 전기적 경계(Electrical Boundary), 전력 도메인(Power Domain), 데이터 인터페이스(Data Interface), 이중화 경로(Redundancy Path), 고장 격리(Failure Containment)를 정의하여 비핵심 서브시스템(Noncritical Subsystem)의 고장이 비행 필수 기능(Flight-Critical Function)으로 전파되지 않도록 해야 한다.

아키텍처는 로보틱스 엔지니어링 표준(Robotics Engineering Standards)에서 정의된 화물 무인항공기(Cargo UAV) 제품군을 지원해야 하며, 실험용 플랫폼(Experimental Platform)에서 대형 화물 무인항공기(Large Cargo UAV) 구성까지 확장할 수 있는 공통 엔지니어링 기준(Common Engineering Baseline)을 제공해야 한다. 플랫폼별 구현은 전압, 추진 출력, 화물 적재 용량 및 이중화 수준에 따라 달라질 수 있지만, 기본적인 분할 철학(Partitioning Philosophy), 인터페이스 제어(Interface Control), 보호 전략(Protection Strategy), 검증 접근법(Verification Approach)은 일관되게 유지되어야 한다.

전력(Electrical Power)은 명확하게 식별된 추진(Propulsion), 항공전자(Avionics), 임무(Mission), 페이로드(Payload), 보조(Auxiliary) 도메인으로 구성해야 한다. 고출력 추진 회로(High-Power Propulsion Circuit)는 가능한 경우 저전압 항공전자(Low-Voltage Avionics)와 물리적·전기적으로 분리해야 한다. 전력 분배(Power Distribution)는 적절하게 협조된 접촉기(Contactor), 회로 보호(Circuit Protection), 절연 장치(Isolation Device), 전류 측정(Current Measurement), 제어 스위칭(Controlled Switching)을 포함하여 비정상 부하를 차단하면서 비행 필수 장비의 전원을 불필요하게 제거하지 않도록 해야 한다.

비행 필수 전기 부하(Flight-Critical Electrical Load)는 신뢰 가능한 단일 고장점(Single-Point Failure)을 방지하도록 설계된 아키텍처를 통해 전력을 공급받아야 한다. 비행 제어 컴퓨터(Flight Control Computer), 필수 항법 센서(Essential Navigation Sensor), 핵심 통신 장비(Critical Communication Equipment), 액추에이터 제어 전자장치(Actuator Control Electronics), 필수 모니터링 기능은 항공기 안전성 평가(Aircraft Safety Assessment)에서 지속적인 작동이 요구되는 경우 독립적이거나 이중화된 전원 경로를 사용해야 한다. 백업 에너지(Backup Energy)는 주 발전 또는 배전 경로를 사용할 수 없게 되었을 때 충분한 전환 능력을 제공해야 한다.

추진 전기 도메인(Propulsion Electrical Domain)은 에너지원(Energy Source), 전력 변환 장비(Power Conversion Equipment), 모터 제어기 또는 인버터(Motor Controller or Inverter), 추진 모터(Propulsion Motor), 관련 보호 및 모니터링 장치를 통합해야 한다. 하이브리드 전기(Hybrid-Electric) 또는 터빈 전기(Turbine-Electric) 화물 무인항공기의 경우 발전 및 추진 전력 분배는 배터리 지원 항공전자 전원(Battery-Supported Avionics Power)과 조정되어야 한다. 추진 고장은 가능한 최소 전기적 경계에서 감지 및 격리하면서 잔여 추진 채널을 통한 제어 가능성(Controllability)을 유지해야 한다.

항공전자 도메인(Avionics Domain)은 비행 제어 컴퓨터(Flight Control Computer), 자동조종 기능(Autopilot Function), 관성측정장치/자세방위기준시스템(IMU/AHRS), 위성항법시스템(GNSS), 대기자료 센서(Air-Data Sensor), 액추에이터 제어기(Actuator Controller), 항법 장비(Navigation Equipment), 상태 모니터링 시스템(Health-Monitoring System) 사이에 결정론적이고 추적 가능한 인터페이스를 제공해야 한다. 항공전자 아키텍처는 고대역폭 임무 컴퓨팅(High-Bandwidth Mission Computing)과 논리적으로 독립되어 인지, 물류, 페이로드 처리 또는 인공지능(AI) 워크로드가 필수 비행 제어 기능의 타이밍이나 가용성을 저해하지 않도록 해야 한다.

통신 네트워크(Communication Network)는 기능, 대역폭(Bandwidth), 결정성(Determinism), 안전 중요도(Safety Criticality)에 따라 분할해야 한다. 적절한 인터페이스에는 항공우주 데이터 버스(Aerospace Data Bus), 결정론적 이더넷(Deterministic Ethernet), CAN 기반 네트워크(CAN-Based Network), 직렬 링크(Serial Link), 필요한 경우 전용 디스크리트 입출력(Dedicated Discrete I/O)이 포함될 수 있다. 네트워크 도메인 간 게이트웨이(Gateway)는 데이터 흐름을 제어하고 비행 필수 항공전자, 임무 컴퓨터, 페이로드 시스템, 정비 인터페이스 및 외부 통신 장비 사이의 비제어 결합을 방지해야 한다.

화물 관리(Cargo Management)는 정의된 전력 및 데이터 인터페이스를 통해 항공기에 연결되는 제어된 전기 도메인(Controlled Electrical Domain)을 구성해야 한다. 화물 중량 감지(Cargo Weight Sensing), 무게중심 모니터링(Center-of-Gravity Monitoring), 잠금 및 해제 메커니즘(Lock and Release Mechanism), 페이로드 식별(Payload Identification), 환경 모니터링(Environmental Monitoring)은 비행 제어를 불안정하게 만들 수 있는 종속성을 생성하지 않으면서 관련 항공기 시스템에 상태를 보고해야 한다. 안전 필수 화물 해제 또는 잠금 기능은 필요한 경우 독립적인 상태 확인(Independent State Confirmation)을 포함해야 한다.

센서 아키텍처(Sensor Architecture)는 기본적인 항공기 안정화 및 항법에 필요한 센서와 자율비행(Autonomy), 인지(Perception), 장애물 감지(Obstacle Detection), 착륙 지원(Landing Assistance), 임무 지능(Mission Intelligence)을 지원하는 센서를 구분해야 한다. 관성측정장치(IMU), 자세방위기준시스템(AHRS), 위성항법시스템(GNSS), 고도(Altitude), 대기자료(Air Data) 및 기타 필수 항법 소스에는 적절한 이중화와 독립적인 전기 경로를 할당해야 한다. 추가 카메라, 라이다(LiDAR), 레이더(Radar), 인공지능 인지 센서는 일반적으로 항공전자와 제어된 인터페이스를 갖는 임무 중심 도메인에 배치해야 한다.

접지(Grounding), 본딩(Bonding), 차폐(Shielding), 전자파 적합성(EMC)은 개별 부품 수준에서 사후 보정하는 항목이 아니라 시스템 수준의 아키텍처 특성으로 다루어야 한다. 고전류 스위칭 루프, 모터 상(Phase), 인버터 케이블, 안테나, 위성항법 수신기, 센서 배선 및 디지털 통신 링크는 각각의 전자기적 특성에 따라 배선하고 분리해야 한다. 구조 본딩(Structural Bonding)과 기준 접지(Reference Ground) 전략은 공통 모드 간섭(Common-Mode Interference)을 최소화하면서 낙뢰 및 과도현상 보호(Lightning and Transient Protection) 요구사항을 지원해야 한다.

아키텍처는 주요 전원, 배전 채널, 변환기(Converter), 추진 제어기, 항공전자 전원 및 핵심 부하에 대한 지속적인 전기 상태 모니터링(Electrical Health Monitoring)을 포함해야 한다. 전압, 전류, 온도, 절연 상태(Insulation Status), 차단기 또는 접촉기 상태 및 관련 진단 정보를 충분한 무결성(Integrity)으로 수집하여 고장 감지, 정비 및 비행 의사결정을 지원해야 한다. 진단 범위(Diagnostic Coverage)는 일시적인 이상과 지속적이거나 안전에 중요한 고장을 구분할 수 있어야 한다.

고장 관리(Fault Management)는 항공기의 안전 목표에 적합한 감지(Detect), 격리(Isolate), 재구성(Reconfigure), 복구(Recover) 철학을 따라야 한다. 전기전자 아키텍처는 비행 제어 시스템이 고장 발생 이후에도 사용 가능한 자원을 판단할 수 있도록 충분한 관측 가능성(Observability)을 제공해야 한다. 재구성은 부하를 이중화 버스로 전환하거나 손상된 추진 분기를 격리하고, 백업 전원을 활성화하거나 임무 기능을 축소하며, 정상 운항을 지속할 수 없는 경우 제어 착륙(Controlled Landing)을 시작하는 방식으로 수행할 수 있다.

물리적 구현(Physical Implementation)은 공통 물리적 사건이 전기적 이중화를 동시에 무력화할 가능성이 있는 경우 이중화 채널 사이의 분리를 유지해야 한다. 하네스 라우팅(Harness Routing), 커넥터(Connector), 전력 분배 장치(PDU), 컴퓨터, 센서 및 통신 경로는 화재 구역, 진동, 열 노출, 습기, 기계적 손상 및 정비 접근성을 고려해야 한다. 서로 다른 전기 회로를 사용하더라도 이중화 배선이 동일한 취약 위치를 통과한다면 자동적으로 독립된 것으로 간주해서는 안 된다.

아키텍처는 지상 전원(Ground Power), 충전(Charging), 정비(Maintenance), 소프트웨어 로딩(Software Loading), 진단(Diagnostics), 비행 전 점검(Preflight Inspection)을 위한 명확한 인터페이스를 제공해야 한다. 정비 인터페이스는 비행 필수 네트워크에 대한 비제어 접근 없이 엔지니어가 전원 무결성, 통신 상태, 센서 상태, 저장된 고장 정보, 구성 식별(Configuration Identity), 이중화 가용성을 확인할 수 있도록 해야 한다. 지상 운용 중에는 의도하지 않은 추진 시스템 작동을 방지하고 정비 및 화물 취급을 위한 명확한 전기적 상태를 제공해야 한다.

구성 관리(Configuration Management)는 전기 아키텍처, 배선도(Wiring Diagram), 인터페이스 제어 문서(Interface Control Document), 네트워크 정의, 소프트웨어 구성, 부품 번호, 보호 설정 및 검증 증거(Verification Evidence) 사이의 추적성(Traceability)을 유지해야 한다. 전력 수요, 고장 격리, 네트워크 부하, 이중화, 전자파 적합성 또는 안전 가정에 영향을 미치는 변경은 릴리스 전에 엔지니어링 영향 평가(Engineering Impact Assessment)를 수행해야 한다. 따라서 아키텍처 기준선(Architecture Baseline)은 개발 전 과정에서 항공기 구성과 동기화되어야 한다.

검증(Verification)은 정상 조건뿐만 아니라 대표적인 전기적 고장 조건에서도 올바른 작동을 입증해야 한다. 시험에는 전원 인가 및 종료 순서, 버스 전환(Bus Transfer), 전원 소스 상실, 변환기 고장, 통신 중단, 센서 상실, 추진 채널 격리, 저전압 상태, 비정상 부하 동작 및 해당되는 경우 복구가 포함되어야 한다. 하드웨어 인 더 루프(Hardware-in-the-Loop) 및 항공기 수준 시험을 통해 실제 구현된 고장 대응이 의도된 아키텍처와 일치하는지 확인해야 한다.

최종 무인항공기 전기전자 아키텍처(UAV E/E Architecture)는 화물 무인항공기 엔지니어링 표준(Cargo UAV Engineering Standards) 내에서 항공전자, 안전, 통신, 추진, 화물 관리, 시험 및 인증 활동을 연결하는 공통 기술 프레임워크(Common Technical Framework) 역할을 해야 한다. 항공전자, 무인항공기 안전, 통신 및 인증에 관한 상세 요구사항은 후속 HRS_012 표준에서 다루며, 본 아키텍처는 해당 표준의 기반이 되는 전기적 분할, 인터페이스, 이중화 원칙 및 설계 제약조건을 확립한다.

##  

## 12.02. Avionics Standard

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

The avionics system shall provide the flight-critical computing, sensing, communication, and control infrastructure required for safe operation of the Cargo UAV product family. Its design shall maintain clear separation between flight-critical avionics and mission-oriented computing while providing controlled interfaces between them. The avionics architecture shall support deterministic operation, fault containment, redundancy, diagnostics, and configuration traceability throughout the aircraft lifecycle.

The Flight Control Computer shall form the primary computational element of the flight-critical avionics domain. It shall execute stabilization, guidance, navigation, flight-mode management, actuator command generation, and safety-related monitoring functions within defined timing constraints. Processing capacity, memory, I/O resources, and communication bandwidth shall include sufficient engineering margin so that worst-case operating conditions do not compromise deterministic flight-control execution.

Where required by the aircraft safety assessment, flight-control computing shall use redundant processing channels with independent power, communication, and monitoring paths. Redundant computers shall exchange sufficient status information to detect disagreement, loss of execution, corrupted data, or timing violations. The architecture shall define how control authority is retained or transferred following a channel failure and shall prevent an erroneous processor from uncontrolled propagation of invalid commands.

The avionics sensor set shall provide reliable information describing aircraft attitude, angular rate, acceleration, position, velocity, altitude, heading, and other states required by the flight-control functions. IMU, AHRS, GNSS, air-data, magnetometer, and altitude sensors shall be selected and integrated according to their required accuracy, update rate, latency, environmental capability, and safety criticality. Critical measurements shall employ redundancy where loss or corruption could create an unacceptable flight condition.

Sensor interfaces shall preserve measurement integrity from the sensing element to the flight-control application. Sampling rate, timestamp accuracy, communication latency, signal conditioning, filtering, coordinate conventions, scaling, units, and validity information shall be explicitly defined. Sensor data shall include sufficient status information for the avionics software to distinguish valid measurements from degraded, unavailable, stale, or implausible data before such information is used for control or navigation.

Navigation architecture shall support appropriate combinations of GNSS, inertial navigation, altitude sensing, heading references, and other aiding sources required by the intended operating environment. Sensor fusion shall continue to provide bounded navigation performance when individual aiding sources become temporarily unavailable. GNSS degradation, multipath, interference, or loss shall be detected where practical, and the aircraft shall transition to an appropriate degraded navigation mode rather than silently relying on invalid position information.

Avionics communication shall use interfaces appropriate to data criticality, determinism, bandwidth, and required fault tolerance. Aerospace data buses, deterministic Ethernet, CAN-based communication, serial interfaces, and discrete I/O may be applied according to system requirements. Flight-control traffic shall be protected from excessive mission or payload traffic, and gateways shall enforce controlled exchange between avionics, mission computing, payload, propulsion, and external communication domains.

Time synchronization shall provide a common temporal reference for flight computers, navigation sensors, data acquisition devices, and other avionics equipment requiring correlated information. Timestamp generation and distribution shall be designed so that sensor fusion, control execution, event reconstruction, and flight-data analysis remain consistent. Loss or degradation of synchronization shall be detectable, and critical functions shall define acceptable timing uncertainty and behavior when the common time reference becomes unavailable.

The avionics power architecture shall provide stable and protected electrical supplies under normal, transient, and defined failure conditions. Flight-critical computers and essential sensors shall use independent or redundant supply paths when required to avoid single-point loss of control. Voltage monitoring, undervoltage and overvoltage protection, current limitation, filtering, and controlled power sequencing shall prevent disturbances originating in propulsion or payload equipment from destabilizing essential avionics.

Flight-control actuator interfaces shall provide deterministic command delivery and reliable feedback for propulsion, aerodynamic control surfaces, steering mechanisms, or other flight-control devices applicable to the aircraft configuration. Command interfaces shall include validity and timeout mechanisms so that stale or corrupted commands cannot remain active indefinitely. Position, speed, current, temperature, or other available feedback shall support closed-loop control, diagnostics, and detection of actuator degradation.

The avionics system shall incorporate built-in monitoring capable of detecting processor faults, communication loss, sensor disagreement, power abnormalities, timing violations, memory errors, and other relevant failures. Watchdogs and health-monitoring functions shall operate with sufficient independence to detect loss of normal software execution. Diagnostic information shall identify the affected channel or subsystem and provide fault status to flight-control, maintenance, and flight-data recording functions as appropriate.

Fault handling shall follow defined detection, isolation, reconfiguration, and recovery behavior. The avionics system shall determine whether a detected failure permits continued normal flight, requires degraded operation, demands transfer to redundant equipment, or necessitates a controlled landing or other predefined safe response. Fault reactions shall be deterministic and shall avoid unnecessary simultaneous shutdown of healthy resources when isolation of the affected component is sufficient.

Mission computers and AI processing platforms may exchange navigation, perception, trajectory, or mission information with avionics, but they shall not obtain unrestricted authority over flight-critical control paths. Interfaces shall define data ownership, validity, rate limits, command permissions, timeout behavior, and failure responses. Safety-related control shall remain protected from mission software crashes, excessive network traffic, corrupted AI outputs, or unauthorized commands originating outside the trusted avionics domain.

Avionics hardware shall be selected and installed for the environmental conditions associated with Cargo UAV operation. Temperature, altitude, vibration, shock, humidity, electromagnetic interference, power transients, and mechanical installation shall be considered according to the aircraft configuration and certification objectives. Connectors, harnesses, mounting structures, cooling provisions, and equipment locations shall maintain electrical integrity and serviceability throughout the defined operational environment.

Software and hardware configuration shall be uniquely identifiable and traceable to the aircraft configuration. Flight-control software, bootloaders, programmable devices, calibration data, communication databases, sensor parameters, and hardware revisions shall be managed under configuration control. Software loading and update mechanisms shall include integrity verification and shall prevent incompatible or unapproved configurations from being inadvertently introduced into flight-critical equipment.

Verification shall demonstrate avionics behavior under nominal, boundary, degraded, and fault conditions. Testing shall address computer startup, sensor initialization, communication timing, redundant-channel operation, sensor failures, network interruption, power disturbances, actuator interface faults, watchdog operation, navigation degradation, and recovery behavior. Software-in-the-loop, hardware-in-the-loop, bench, integration, and aircraft-level testing shall provide traceable evidence that implemented functions satisfy allocated requirements.

The HRS_012_02 Avionics Standard shall operate as the detailed avionics baseline beneath the UAV E/E architecture defined by HRS_012_01 and shall interface with the subsequent UAV safety, communication, and certification standards. Together these requirements establish a disciplined avionics framework in which computing, navigation, sensing, communication, control, redundancy, diagnostics, configuration management, and verification remain coordinated throughout Cargo UAV development and operation.

항공전자 시스템(Avionics System)은 화물 무인항공기(Cargo UAV) 제품군의 안전한 운용에 필요한 비행 필수 컴퓨팅(Flight-Critical Computing), 센싱(Sensing), 통신(Communication), 제어(Control) 인프라를 제공해야 한다. 설계 시 비행 필수 항공전자(Flight-Critical Avionics)와 임무 중심 컴퓨팅(Mission-Oriented Computing)을 명확하게 분리하면서 이들 사이에 제어된 인터페이스를 제공해야 한다. 항공전자 아키텍처(Avionics Architecture)는 항공기 수명주기 전반에 걸쳐 결정론적 동작(Deterministic Operation), 고장 격리(Fault Containment), 이중화(Redundancy), 진단(Diagnostics), 구성 추적성(Configuration Traceability)을 지원해야 한다.

비행 제어 컴퓨터(Flight Control Computer)는 비행 필수 항공전자 도메인(Flight-Critical Avionics Domain)의 핵심 연산 요소를 구성해야 한다. 비행 제어 컴퓨터는 정의된 타이밍 제약조건 내에서 안정화(Stabilization), 유도(Guidance), 항법(Navigation), 비행 모드 관리(Flight-Mode Management), 액추에이터 명령 생성(Actuator Command Generation), 안전 관련 모니터링 기능을 실행해야 한다. 처리 성능, 메모리, 입출력(I/O) 자원 및 통신 대역폭에는 최악 조건에서도 결정론적인 비행 제어 실행을 저해하지 않도록 충분한 엔지니어링 여유(Engineering Margin)를 확보해야 한다.

항공기 안전성 평가(Aircraft Safety Assessment)에서 요구되는 경우 비행 제어 컴퓨팅은 독립적인 전원, 통신 및 모니터링 경로를 갖는 이중화 처리 채널(Redundant Processing Channel)을 사용해야 한다. 이중화 컴퓨터는 불일치, 실행 중단, 데이터 손상 또는 타이밍 위반을 감지할 수 있도록 충분한 상태 정보를 교환해야 한다. 아키텍처는 채널 고장 이후 제어 권한(Control Authority)을 유지하거나 전환하는 방법을 정의하고, 오류가 발생한 프로세서가 유효하지 않은 명령을 통제 없이 전파하지 못하도록 해야 한다.

항공전자 센서 구성(Avionics Sensor Set)은 항공기 자세, 각속도, 가속도, 위치, 속도, 고도, 방위 및 비행 제어 기능에 필요한 기타 상태를 나타내는 신뢰성 높은 정보를 제공해야 한다. 관성측정장치(IMU), 자세방위기준시스템(AHRS), 위성항법시스템(GNSS), 대기자료 센서(Air-Data Sensor), 자기계(Magnetometer), 고도 센서(Altitude Sensor)는 요구되는 정확도, 갱신 주기, 지연시간(Latency), 환경 대응 능력 및 안전 중요도에 따라 선정하고 통합해야 한다. 정보의 손실이나 손상이 허용할 수 없는 비행 상태를 초래할 수 있는 핵심 측정값에는 이중화를 적용해야 한다.

센서 인터페이스(Sensor Interface)는 센싱 요소에서 비행 제어 애플리케이션까지 측정 무결성(Measurement Integrity)을 유지해야 한다. 샘플링 속도, 타임스탬프 정확도, 통신 지연시간, 신호 조절(Signal Conditioning), 필터링, 좌표계 규약(Coordinate Convention), 스케일링, 단위 및 유효성 정보를 명확하게 정의해야 한다. 센서 데이터에는 항공전자 소프트웨어가 제어 또는 항법에 해당 정보를 사용하기 전에 정상, 성능 저하, 사용 불가, 오래된 데이터 또는 비현실적인 데이터를 구분할 수 있도록 충분한 상태 정보가 포함되어야 한다.

항법 아키텍처(Navigation Architecture)는 의도된 운용 환경에 필요한 위성항법시스템(GNSS), 관성항법(Inertial Navigation), 고도 센싱(Altitude Sensing), 방위 기준(Heading Reference) 및 기타 보조 정보원의 적절한 조합을 지원해야 한다. 센서 융합(Sensor Fusion)은 개별 보조 정보원이 일시적으로 사용 불가능해지는 경우에도 제한된 범위 내의 항법 성능을 지속적으로 제공해야 한다. 위성항법시스템의 성능 저하, 다중경로(Multipath), 간섭 또는 신호 상실을 가능한 범위에서 감지해야 하며, 항공기는 잘못된 위치 정보를 계속 사용하는 대신 적절한 성능 저하 항법 모드(Degraded Navigation Mode)로 전환해야 한다.

항공전자 통신(Avionics Communication)은 데이터 중요도, 결정성(Determinism), 대역폭 및 요구되는 고장 허용성(Fault Tolerance)에 적합한 인터페이스를 사용해야 한다. 시스템 요구사항에 따라 항공우주 데이터 버스(Aerospace Data Bus), 결정론적 이더넷(Deterministic Ethernet), CAN 기반 통신(CAN-Based Communication), 직렬 인터페이스(Serial Interface), 디스크리트 입출력(Discrete I/O)을 적용할 수 있다. 비행 제어 트래픽은 과도한 임무 또는 페이로드 트래픽으로부터 보호되어야 하며, 게이트웨이(Gateway)는 항공전자, 임무 컴퓨팅, 페이로드, 추진 및 외부 통신 도메인 사이의 데이터 교환을 통제해야 한다.

시간 동기화(Time Synchronization)는 비행 컴퓨터, 항법 센서, 데이터 수집 장치 및 상호 연관된 정보가 필요한 기타 항공전자 장비에 공통 시간 기준(Common Temporal Reference)을 제공해야 한다. 타임스탬프 생성 및 분배는 센서 융합, 제어 실행, 이벤트 재구성(Event Reconstruction), 비행 데이터 분석이 일관성을 유지하도록 설계해야 한다. 동기화의 손실 또는 성능 저하는 감지할 수 있어야 하며, 핵심 기능은 허용 가능한 시간 불확실성과 공통 시간 기준을 사용할 수 없을 때의 동작을 정의해야 한다.

항공전자 전원 아키텍처(Avionics Power Architecture)는 정상, 과도현상(Transient), 정의된 고장 조건에서 안정적이고 보호된 전원을 제공해야 한다. 비행 필수 컴퓨터와 필수 센서는 단일 고장으로 제어 기능 전체가 상실되는 것을 방지하기 위해 필요한 경우 독립적이거나 이중화된 전원 경로를 사용해야 한다. 전압 모니터링, 저전압 및 과전압 보호, 전류 제한, 필터링 및 제어된 전원 시퀀싱(Controlled Power Sequencing)을 통해 추진 또는 페이로드 장비에서 발생하는 교란이 필수 항공전자를 불안정하게 만드는 것을 방지해야 한다.

비행 제어 액추에이터 인터페이스(Flight-Control Actuator Interface)는 항공기 구성에 적용되는 추진 장치, 공력 제어면(Aerodynamic Control Surface), 조향 메커니즘 또는 기타 비행 제어 장치에 대해 결정론적인 명령 전달과 신뢰성 높은 피드백을 제공해야 한다. 명령 인터페이스에는 오래되거나 손상된 명령이 무기한 활성 상태로 유지되지 않도록 유효성 및 타임아웃(Timeout) 메커니즘을 포함해야 한다. 위치, 속도, 전류, 온도 또는 기타 이용 가능한 피드백은 폐루프 제어(Closed-Loop Control), 진단 및 액추에이터 성능 저하 감지를 지원해야 한다.

항공전자 시스템은 프로세서 고장, 통신 손실, 센서 불일치, 전원 이상, 타이밍 위반, 메모리 오류 및 기타 관련 고장을 감지할 수 있는 내장 모니터링(Built-In Monitoring) 기능을 포함해야 한다. 워치독(Watchdog)과 상태 모니터링(Health Monitoring) 기능은 정상적인 소프트웨어 실행의 상실을 감지할 수 있도록 충분한 독립성을 확보해야 한다. 진단 정보는 영향을 받은 채널이나 서브시스템을 식별하고 필요에 따라 비행 제어, 정비 및 비행 데이터 기록 기능에 고장 상태를 제공해야 한다.

고장 처리(Fault Handling)는 정의된 감지(Detection), 격리(Isolation), 재구성(Reconfiguration), 복구(Recovery) 동작을 따라야 한다. 항공전자 시스템은 감지된 고장이 정상 비행의 지속을 허용하는지, 성능 저하 운용(Degraded Operation)이 필요한지, 이중화 장비로 전환해야 하는지 또는 제어 착륙(Controlled Landing)이나 기타 사전에 정의된 안전 대응이 필요한지를 판단해야 한다. 고장 대응은 결정론적이어야 하며, 영향을 받은 구성요소만 격리하는 것으로 충분한 경우 정상 자원을 불필요하게 동시에 종료하지 않아야 한다.

임무 컴퓨터(Mission Computer)와 인공지능 처리 플랫폼(AI Processing Platform)은 항법, 인지, 궤적 또는 임무 정보를 항공전자 시스템과 교환할 수 있지만, 비행 필수 제어 경로에 대해 제한 없는 권한을 가져서는 안 된다. 인터페이스는 데이터 소유권(Data Ownership), 유효성, 전송률 제한(Rate Limit), 명령 권한, 타임아웃 동작 및 고장 대응을 정의해야 한다. 안전 관련 제어는 임무 소프트웨어의 충돌, 과도한 네트워크 트래픽, 손상된 인공지능 출력 또는 신뢰된 항공전자 도메인 외부에서 발생한 비인가 명령으로부터 보호되어야 한다.

항공전자 하드웨어(Avionics Hardware)는 화물 무인항공기 운용과 관련된 환경 조건에 적합하도록 선정하고 설치해야 한다. 온도, 고도, 진동, 충격, 습도, 전자기 간섭(Electromagnetic Interference), 전원 과도현상 및 기계적 설치 조건을 항공기 구성과 인증 목표에 따라 고려해야 한다. 커넥터, 하네스, 장착 구조물, 냉각 설비(Cooling Provision) 및 장비 배치는 정의된 운용 환경 전체에서 전기적 무결성과 정비성(Serviceability)을 유지해야 한다.

소프트웨어 및 하드웨어 구성(Configuration)은 항공기 구성과 연계하여 고유하게 식별되고 추적 가능해야 한다. 비행 제어 소프트웨어, 부트로더(Bootloader), 프로그래머블 장치(Programmable Device), 캘리브레이션 데이터(Calibration Data), 통신 데이터베이스, 센서 파라미터 및 하드웨어 개정 사항은 구성 관리(Configuration Control)하에 관리해야 한다. 소프트웨어 로딩 및 업데이트 메커니즘은 무결성 검증(Integrity Verification)을 포함하고, 호환되지 않거나 승인되지 않은 구성이 비행 필수 장비에 의도치 않게 적용되는 것을 방지해야 한다.

검증(Verification)은 정상, 경계, 성능 저하 및 고장 조건에서 항공전자 시스템의 동작을 입증해야 한다. 시험은 컴퓨터 기동, 센서 초기화, 통신 타이밍, 이중화 채널 동작, 센서 고장, 네트워크 중단, 전원 교란, 액추에이터 인터페이스 고장, 워치독 동작, 항법 성능 저하 및 복구 동작을 포함해야 한다. 소프트웨어 인 더 루프(Software-in-the-Loop), 하드웨어 인 더 루프(Hardware-in-the-Loop), 벤치 시험(Bench Test), 통합 시험(Integration Test), 항공기 수준 시험(Aircraft-Level Test)을 통해 구현된 기능이 할당된 요구사항을 충족한다는 추적 가능한 증거를 제공해야 한다.

HRS_012_02 항공전자 표준(Avionics Standard)은 HRS_012_01에서 정의한 무인항공기 전기전자 아키텍처(UAV E/E Architecture)의 하위 상세 항공전자 기준으로 기능하며, 후속 무인항공기 안전, 통신 및 인증 표준과 연계되어야 한다. 이러한 요구사항은 컴퓨팅, 항법, 센싱, 통신, 제어, 이중화, 진단, 구성 관리 및 검증이 화물 무인항공기의 개발과 운용 전반에서 일관되게 조정되는 체계적인 항공전자 프레임워크(Avionics Framework)를 확립한다.

##  

## 12.03. UAV Safety Requirement

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

The Cargo UAV safety architecture shall protect people, property, payload, aircraft, and surrounding airspace from hazards arising from electrical, electronic, software, propulsion, communication, navigation, and mechanical failures. Safety requirements shall be derived systematically from the intended operational concept, aircraft configuration, operating environment, payload characteristics, and identified hazards, and shall remain traceable through design, verification, and operational approval.

A structured safety assessment shall identify hazardous conditions associated with loss of thrust, loss of control, incorrect flight commands, navigation errors, power failures, communication loss, cargo malfunction, unintended release, sensor faults, and common-cause failures. Each hazard shall be evaluated according to its potential consequence and operational context. Resulting safety objectives shall be allocated to systems, hardware, software, operational procedures, and independent protection mechanisms.

The aircraft shall be designed so that no credible single electrical or electronic failure causes an uncontrolled hazardous flight condition where the safety assessment requires fault tolerance. Flight-critical functions shall use appropriate redundancy, independence, monitoring, or fail-safe behavior. Redundant channels shall be sufficiently separated in power, communication, computation, sensing, and physical installation to prevent one fault from simultaneously disabling nominally independent safety resources.

Flight-control safety shall maintain aircraft controllability following defined failures of computers, sensors, communication channels, or actuators. The system shall detect loss of execution, invalid commands, timing violations, disagreement between redundant channels, and unavailable control resources. When normal control capability cannot be maintained, the aircraft shall transition deterministically to an appropriate degraded mode, contingency procedure, controlled landing, or other predefined safe response.

Propulsion safety shall address failures of batteries, generators, converters, inverters, motor controllers, motors, propellers or rotors, and associated distribution circuits. Electrical protection shall isolate short circuits, overcurrent, abnormal voltage, overheating, insulation faults, and other hazardous conditions without unnecessarily removing healthy propulsion channels. Remaining propulsion capability shall be continuously evaluated so that flight-control functions can respond appropriately to degraded thrust availability.

Energy-storage systems shall incorporate monitoring and protection appropriate to their chemistry, voltage, capacity, and installation. Battery voltage, current, temperature, state information, and relevant fault indicators shall be available to safety-related monitoring functions. Protection against overcharge, over-discharge, excessive current, thermal propagation, insulation degradation, and unintended energization shall be considered, together with physical containment and isolation appropriate to the aircraft configuration.

Navigation safety shall prevent undetected dependence on invalid position, velocity, attitude, altitude, or heading information. Critical sensors shall provide validity information and shall be monitored for plausibility, disagreement, timeout, excessive drift, and loss of communication. GNSS interference, degradation, multipath, or loss shall trigger defined responses where relevant, and alternative navigation sources shall support continued safe operation when required by the operational safety objectives.

Communication loss shall not by itself result in uncontrolled aircraft behavior. Command-and-control and datalink functions shall include link-status monitoring, timeout criteria, authentication where applicable, and predefined lost-link behavior. The aircraft shall determine an appropriate response according to mission phase and available navigation capability, such as continuing a validated route, entering a holding condition, returning to a designated location, or executing a controlled landing.

Cargo safety shall ensure that payload carriage does not compromise aircraft stability, structural limits, propulsion capability, electrical integrity, or flight-control performance. Cargo weight, center-of-gravity condition, locking status, and other safety-relevant payload states shall be verified before flight where applicable. A cargo release mechanism shall be protected against unintended activation, and safety-critical lock or release states shall use independent confirmation when required by the hazard assessment.

The safety architecture shall distinguish flight-critical avionics from mission computing, AI processing, perception systems, payload equipment, and nonessential utilities. Failure, restart, overload, excessive traffic, corrupted output, or unauthorized behavior in a noncritical domain shall not directly compromise essential flight-control functions. Gateways and interface controls shall constrain data flow and command authority between safety domains according to explicitly defined permissions and failure behavior.

Safety monitoring shall continuously supervise critical power, computing, sensing, communication, propulsion, actuator, and cargo functions. Health information shall be evaluated using defined limits, validity checks, watchdogs, heartbeat mechanisms, cross-channel comparison, and fault-detection logic as appropriate. Detected faults shall be recorded with sufficient timestamp and configuration information to support flight decisions, post-flight investigation, maintenance, and safety verification.

Common-cause and common-mode failures shall be considered explicitly when evaluating redundancy. Two components shall not be regarded as truly independent merely because they are duplicated. Shared power sources, network switches, software, cooling systems, harness routes, connectors, environmental exposure, installation zones, or configuration errors may defeat multiple channels simultaneously. Physical and functional separation shall therefore be demonstrated for safety-significant redundant resources.

Emergency and contingency behavior shall be defined for credible combinations of degraded conditions. The aircraft shall establish deterministic responses for conditions such as propulsion degradation, critical sensor loss, flight-computer failure, low energy state, communication loss, navigation degradation, cargo anomaly, or electrical distribution failure. Automatic responses shall be coordinated so that independently triggered protection functions do not generate conflicting commands or unnecessarily escalate a recoverable condition.

Ground safety shall prevent hazardous activation during charging, maintenance, software loading, cargo handling, and preflight operations. Propulsion enable conditions shall require explicitly defined prerequisites, and maintenance states shall inhibit unintended actuator or propulsion commands. Ground personnel shall be provided with clear indications of energized systems, stored energy, detected faults, and aircraft readiness so that servicing activities can be performed under controlled electrical and operational conditions.

Safety-related software, hardware, calibration data, network definitions, and configuration parameters shall be controlled throughout the product lifecycle. Changes affecting flight control, propulsion, navigation, redundancy, fault detection, cargo handling, or emergency behavior shall undergo documented safety impact assessment. Verification evidence shall remain linked to the applicable configuration so that previously demonstrated safety claims are not assumed to remain valid after uncontrolled modification.

Safety verification shall include nominal operation, single faults, relevant multiple faults, boundary conditions, degraded modes, and transitions between normal and contingency states. Analysis and testing shall verify fault detection latency, isolation, redundancy switching, lost-link behavior, navigation degradation, propulsion failures, power faults, sensor disagreement, cargo safety functions, and controlled landing behavior. SIL, HIL, bench, ground, and flight testing shall be applied according to verification needs.

The HRS_012_03 UAV Safety Requirement shall operate with the UAV E/E architecture defined by HRS_012_01 and the avionics requirements defined by HRS_012_02, while providing the safety foundation for communication and certification activities addressed by subsequent HRS_012 standards. The resulting framework shall maintain traceability from identified hazards through safety requirements, architectural controls, implementation, verification evidence, operational limitations, and final aircraft configuration.

화물 무인항공기(Cargo UAV) 안전 아키텍처(Safety Architecture)는 전기, 전자, 소프트웨어, 추진, 통신, 항법 및 기계적 고장으로 발생하는 위험으로부터 사람, 재산, 화물, 항공기 및 주변 공역을 보호해야 한다. 안전 요구사항(Safety Requirement)은 의도된 운용 개념(Operational Concept), 항공기 구성, 운용 환경, 화물 특성 및 식별된 위험요소(Hazard)를 기반으로 체계적으로 도출되어야 하며, 설계, 검증 및 운용 승인 전 과정에서 추적 가능성을 유지해야 한다.

체계적인 안전성 평가(Safety Assessment)를 통해 추력 상실, 제어 상실, 잘못된 비행 명령, 항법 오류, 전원 고장, 통신 두절, 화물 시스템 오작동, 의도하지 않은 화물 해제, 센서 고장 및 공통 원인 고장(Common-Cause Failure)과 관련된 위험 상태를 식별해야 한다. 각 위험요소는 잠재적 결과와 운용 상황에 따라 평가해야 한다. 도출된 안전 목표(Safety Objective)는 시스템, 하드웨어, 소프트웨어, 운용 절차 및 독립적인 보호 메커니즘에 할당해야 한다.

항공기는 안전성 평가에서 고장 허용성(Fault Tolerance)이 요구되는 경우 신뢰 가능한 단일 전기 또는 전자 고장이 제어 불가능한 위험 비행 상태를 초래하지 않도록 설계해야 한다. 비행 필수 기능(Flight-Critical Function)에는 적절한 이중화(Redundancy), 독립성(Independence), 모니터링 또는 고장 안전 동작(Fail-Safe Behavior)을 적용해야 한다. 이중화 채널은 하나의 고장이 명목상 독립적인 안전 자원을 동시에 무력화하지 않도록 전원, 통신, 컴퓨팅, 센싱 및 물리적 설치 측면에서 충분히 분리해야 한다.

비행 제어 안전(Flight-Control Safety)은 컴퓨터, 센서, 통신 채널 또는 액추에이터에 정의된 고장이 발생한 이후에도 항공기의 제어 가능성(Controllability)을 유지해야 한다. 시스템은 실행 중단, 유효하지 않은 명령, 타이밍 위반, 이중화 채널 간 불일치 및 사용 불가능한 제어 자원을 감지해야 한다. 정상적인 제어 능력을 유지할 수 없는 경우 항공기는 적절한 성능 저하 모드(Degraded Mode), 비상 절차(Contingency Procedure), 제어 착륙(Controlled Landing) 또는 사전에 정의된 기타 안전 대응으로 결정론적으로 전환해야 한다.

추진 안전(Propulsion Safety)은 배터리, 발전기, 변환기(Converter), 인버터(Inverter), 모터 제어기, 모터, 프로펠러 또는 로터(Rotor) 및 관련 배전 회로의 고장을 고려해야 한다. 전기적 보호 기능은 정상적인 추진 채널을 불필요하게 제거하지 않으면서 단락, 과전류, 비정상 전압, 과열, 절연 고장 및 기타 위험 상태를 격리해야 한다. 잔여 추진 능력(Remaining Propulsion Capability)을 지속적으로 평가하여 비행 제어 기능이 감소된 추력 가용성에 적절하게 대응할 수 있도록 해야 한다.

에너지 저장 시스템(Energy-Storage System)은 배터리 화학 특성, 전압, 용량 및 설치 조건에 적합한 모니터링과 보호 기능을 포함해야 한다. 배터리 전압, 전류, 온도, 상태 정보 및 관련 고장 지표를 안전 관련 모니터링 기능에서 사용할 수 있어야 한다. 과충전, 과방전, 과도한 전류, 열 전파(Thermal Propagation), 절연 성능 저하 및 의도하지 않은 전원 인가에 대한 보호와 함께 항공기 구성에 적합한 물리적 봉쇄(Physical Containment) 및 격리를 고려해야 한다.

항법 안전(Navigation Safety)은 잘못된 위치, 속도, 자세, 고도 또는 방위 정보에 항공기가 감지 없이 의존하는 것을 방지해야 한다. 핵심 센서는 유효성 정보를 제공하고 타당성(Plausibility), 불일치, 타임아웃(Timeout), 과도한 드리프트(Drift) 및 통신 상실에 대해 모니터링되어야 한다. 위성항법시스템(GNSS)의 간섭, 성능 저하, 다중경로(Multipath) 또는 신호 상실은 관련되는 경우 정의된 대응을 발생시켜야 하며, 운용 안전 목표에서 요구하는 경우 대체 항법 정보원이 지속적인 안전 운용을 지원해야 한다.

통신 두절(Communication Loss)은 그 자체로 항공기의 제어 불가능한 동작을 초래해서는 안 된다. 명령 및 제어(Command-and-Control)와 데이터링크(Datalink) 기능에는 링크 상태 모니터링, 타임아웃 기준, 해당되는 경우 인증(Authentication), 사전에 정의된 링크 상실 동작(Lost-Link Behavior)이 포함되어야 한다. 항공기는 임무 단계와 사용 가능한 항법 능력에 따라 검증된 경로의 지속 비행, 대기 상태 진입, 지정 위치로 복귀 또는 제어 착륙과 같은 적절한 대응을 결정해야 한다.

화물 안전(Cargo Safety)은 화물 운송이 항공기 안정성, 구조적 한계, 추진 능력, 전기적 무결성 또는 비행 제어 성능을 저해하지 않도록 해야 한다. 해당되는 경우 비행 전에 화물 중량, 무게중심(Center of Gravity) 상태, 잠금 상태 및 기타 안전 관련 화물 상태를 확인해야 한다. 화물 해제 메커니즘(Cargo Release Mechanism)은 의도하지 않은 작동으로부터 보호되어야 하며, 안전 필수 잠금 또는 해제 상태에는 위험성 평가에서 요구되는 경우 독립적인 상태 확인(Independent Confirmation)을 적용해야 한다.

안전 아키텍처는 비행 필수 항공전자(Flight-Critical Avionics)를 임무 컴퓨팅(Mission Computing), 인공지능 처리(AI Processing), 인지 시스템(Perception System), 페이로드 장비(Payload Equipment) 및 비필수 유틸리티(Nonessential Utility)와 구분해야 한다. 비핵심 도메인의 고장, 재시작, 과부하, 과도한 트래픽, 손상된 출력 또는 비인가 동작이 필수 비행 제어 기능을 직접적으로 저해해서는 안 된다. 게이트웨이(Gateway)와 인터페이스 제어 기능은 명확하게 정의된 권한 및 고장 동작에 따라 안전 도메인 사이의 데이터 흐름과 명령 권한을 제한해야 한다.

안전 모니터링(Safety Monitoring)은 핵심 전원, 컴퓨팅, 센싱, 통신, 추진, 액추에이터 및 화물 기능을 지속적으로 감시해야 한다. 상태 정보(Health Information)는 필요에 따라 정의된 한계값, 유효성 검사, 워치독(Watchdog), 하트비트(Heartbeat) 메커니즘, 채널 간 비교 및 고장 감지 로직을 이용하여 평가해야 한다. 감지된 고장은 비행 의사결정, 비행 후 조사, 정비 및 안전 검증을 지원할 수 있도록 충분한 타임스탬프와 구성 정보를 포함하여 기록해야 한다.

이중화 평가에서는 공통 원인 고장(Common-Cause Failure)과 공통 모드 고장(Common-Mode Failure)을 명시적으로 고려해야 한다. 두 개의 구성요소가 단순히 중복되어 있다는 이유만으로 완전히 독립적인 것으로 간주해서는 안 된다. 공유 전원, 네트워크 스위치, 소프트웨어, 냉각 시스템, 하네스 경로, 커넥터, 환경 노출, 설치 구역 또는 구성 오류로 인해 여러 채널이 동시에 무력화될 수 있다. 따라서 안전에 중요한 이중화 자원에 대해서는 물리적 및 기능적 분리(Physical and Functional Separation)를 입증해야 한다.

비상 및 우발 상황 동작(Emergency and Contingency Behavior)은 신뢰 가능한 성능 저하 조건의 조합에 대해 정의되어야 한다. 항공기는 추진 성능 저하, 핵심 센서 상실, 비행 컴퓨터 고장, 낮은 에너지 상태, 통신 두절, 항법 성능 저하, 화물 이상 또는 배전 고장 등의 조건에 대해 결정론적인 대응을 설정해야 한다. 자동 대응은 독립적으로 작동하는 보호 기능들이 서로 충돌하는 명령을 생성하거나 복구 가능한 상태를 불필요하게 악화시키지 않도록 상호 조정되어야 한다.

지상 안전(Ground Safety)은 충전, 정비, 소프트웨어 로딩, 화물 취급 및 비행 전 운용 과정에서 위험한 작동을 방지해야 한다. 추진 활성화 조건(Propulsion Enable Condition)은 명확하게 정의된 선행 조건을 요구해야 하며, 정비 상태에서는 의도하지 않은 액추에이터 또는 추진 명령을 억제해야 한다. 지상 작업자가 통제된 전기 및 운용 조건에서 정비 작업을 수행할 수 있도록 전원 인가 시스템, 저장 에너지, 감지된 고장 및 항공기 준비 상태(Aircraft Readiness)를 명확하게 표시해야 한다.

안전 관련 소프트웨어, 하드웨어, 캘리브레이션 데이터(Calibration Data), 네트워크 정의 및 구성 파라미터(Configuration Parameter)는 제품 수명주기 전체에서 관리되어야 한다. 비행 제어, 추진, 항법, 이중화, 고장 감지, 화물 처리 또는 비상 동작에 영향을 미치는 변경에는 문서화된 안전 영향 평가(Safety Impact Assessment)를 수행해야 한다. 검증 증거(Verification Evidence)는 해당 구성과 지속적으로 연결되어야 하며, 통제되지 않은 변경 이후에도 이전에 입증된 안전 주장이 계속 유효하다고 가정해서는 안 된다.

안전 검증(Safety Verification)은 정상 운용, 단일 고장, 관련 다중 고장, 경계 조건, 성능 저하 모드 및 정상 상태와 비상 상태 사이의 전환을 포함해야 한다. 분석 및 시험을 통해 고장 감지 지연시간(Fault Detection Latency), 격리, 이중화 전환, 링크 상실 동작, 항법 성능 저하, 추진 고장, 전원 고장, 센서 불일치, 화물 안전 기능 및 제어 착륙 동작을 검증해야 한다. 검증 필요성에 따라 소프트웨어 인 더 루프(SIL), 하드웨어 인 더 루프(HIL), 벤치 시험(Bench Test), 지상 시험(Ground Test) 및 비행 시험(Flight Test)을 적용해야 한다.

HRS_012_03 무인항공기 안전 요구사항(UAV Safety Requirement)은 HRS_012_01에서 정의된 무인항공기 전기전자 아키텍처(UAV E/E Architecture) 및 HRS_012_02에서 정의된 항공전자 요구사항(Avionics Requirement)과 연계되어야 하며, 후속 HRS_012 표준에서 다루는 통신 및 인증 활동을 위한 안전 기반을 제공해야 한다. 최종 프레임워크는 식별된 위험요소에서 안전 요구사항, 아키텍처 제어, 구현, 검증 증거, 운용 제한(Operational Limitation) 및 최종 항공기 구성에 이르는 전체 과정의 추적성을 유지해야 한다.

##  

## 12.04. UAV Communication Standard

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

The Cargo UAV communication architecture shall provide reliable, deterministic, secure, and traceable exchange of information among flight-control avionics, propulsion systems, navigation sensors, mission computers, payload equipment, ground control stations, and external services. Communication interfaces shall be selected according to safety criticality, latency, bandwidth, distance, redundancy, and environmental requirements while preserving separation between flight-critical and noncritical traffic.

Communication networks shall be partitioned into functional domains so that failures or excessive traffic in mission, payload, maintenance, or external networks cannot compromise flight-critical communication. Flight-control, propulsion, navigation, payload, mission, and ground-link traffic shall use defined interfaces and controlled gateways. Network boundaries shall establish permitted message flows, priorities, bandwidth allocation, failure behavior, and command authority for each connected subsystem.

Flight-critical communication shall provide deterministic timing appropriate to control-loop and safety requirements. Maximum latency, jitter, update period, timeout, and message age shall be defined for signals used by flight control, navigation, propulsion, and actuator functions. Communication resources shall include sufficient margin under worst-case network loading, and lower-priority traffic shall not delay safety-critical messages beyond their allocated timing constraints.

Internal aircraft networks may use aerospace data buses, deterministic Ethernet, CAN-based protocols, serial communication, or discrete interfaces according to system requirements. Protocol selection shall consider bandwidth, topology, fault containment, equipment compatibility, determinism, electromagnetic environment, and certification objectives. Bridges and gateways shall not create uncontrolled dependencies between communication technologies or safety domains.

Command-and-control communication between the aircraft and Ground Control Station shall maintain reliable exchange of aircraft status, operator commands, mission information, alerts, and contingency data. The link shall provide defined update rates, timeout thresholds, connection-state monitoring, and degraded-link behavior. Loss of the command-and-control link shall be detected within a specified interval and shall invoke the predefined lost-link response defined by the aircraft safety architecture.

Datalink architecture shall distinguish safety-relevant command-and-control traffic from high-bandwidth mission or payload data whenever practical. Video, imagery, LiDAR information, maintenance files, and other large data streams shall not consume communication resources required for aircraft control. Quality-of-service mechanisms, traffic prioritization, separate logical channels, or physically independent links shall be applied where necessary to maintain essential communication performance.

Communication with navigation and surveillance infrastructure shall use interfaces appropriate to the aircraft operational concept and regulatory environment. GNSS correction information, Remote ID, transponder-related data, UTM information, weather data, or other external services may be integrated when required by the mission. Loss or corruption of an external service shall be detectable, and flight-critical behavior shall not depend on an external data source beyond the assumptions established by the safety assessment.

Communication with UTM or fleet-management infrastructure shall support controlled exchange of aircraft identity, position, trajectory, mission status, operational constraints, and relevant alerts where required. Interfaces shall define message ownership, update rate, timestamp, validity, and failure handling. Cloud or fleet services shall remain separated from direct low-level flight-control authority unless an explicitly approved safety architecture provides the necessary protection and verification.

Time synchronization shall establish a consistent temporal reference across flight computers, sensors, communication gateways, mission systems, and data recorders. Messages requiring temporal correlation shall include timestamps referenced to an identified time source. Synchronization accuracy shall be appropriate to sensor fusion, navigation, control, event reconstruction, and diagnostics, and degradation or loss of the common time reference shall be detectable by affected systems.

Message definitions shall be controlled through approved interface specifications and communication databases. Each signal or message shall define its identifier, source, destination, data type, unit, scaling, valid range, update rate, timeout, default behavior, and validity information where applicable. Changes to message definitions shall be configuration controlled so that incompatible software or network databases cannot be introduced into an operational aircraft configuration.

Communication integrity mechanisms shall detect corrupted, duplicated, missing, delayed, stale, or out-of-sequence information where such failures could affect system behavior. Depending on interface criticality, mechanisms may include checksums, sequence counters, timestamps, message authentication, heartbeat supervision, timeout monitoring, and end-to-end protection. Receiving functions shall validate critical information before allowing it to influence flight-control or safety-related decisions.

Network redundancy shall be provided where communication loss could prevent continued safe operation. Redundant paths shall avoid unnecessary common points of failure such as shared switches, gateways, power supplies, connectors, harness routes, antennas, or communication processors. Switching or failover behavior shall be deterministic, and the system shall detect whether redundant channels are healthy, degraded, unavailable, or providing inconsistent information.

Wireless communication shall consider coverage, propagation, interference, antenna placement, polarization, frequency allocation, environmental effects, and expected operating range. Antenna systems shall be installed to minimize shadowing by the airframe, propulsion structures, payload, or other antennas. Where multiple wireless links provide redundancy, their independence shall be evaluated against common interference, shared equipment, power loss, and geographic coverage limitations.

Communication security shall protect command, control, configuration, maintenance, and mission interfaces against unauthorized access or manipulation according to the identified cybersecurity risks. Authentication, integrity protection, access control, secure key management, and encryption shall be applied where appropriate. Security mechanisms shall not introduce uncontrolled latency or failure modes into flight-critical communication, and loss of a security service shall result in explicitly defined system behavior.

Maintenance and software-loading interfaces shall be separated from operational flight-control communication and enabled only under controlled conditions. Diagnostic access shall permit authorized personnel to retrieve network status, fault records, configuration information, and communication statistics without unintentionally commanding flight-critical equipment. Software or configuration transfer shall include integrity checks and controls preventing unauthorized or incompatible data from being installed.

Communication monitoring shall provide sufficient observability to identify link loss, excessive latency, packet or frame errors, bus overload, gateway faults, synchronization degradation, authentication failures, and abnormal traffic. Relevant events shall be recorded with timestamps and configuration information to support troubleshooting, flight-data analysis, safety investigation, and maintenance. Diagnostic coverage shall distinguish local equipment faults from broader network or external-link failures.

Verification shall demonstrate communication performance under nominal, maximum-load, degraded, and failure conditions. Testing shall address latency, jitter, throughput, message timeout, network congestion, gateway behavior, redundant-link switching, corrupted data, lost communication, electromagnetic disturbances, synchronization loss, and security-related behavior. SIL, HIL, bench, integration, ground, and flight testing shall provide traceable evidence that communication requirements are satisfied.

The HRS_012_04 UAV Communication Standard shall operate within the UAV E/E architecture established by HRS_012_01, the avionics framework of HRS_012_02, and the safety requirements of HRS_012_03, while providing communication evidence required by HRS_012_05 certification activities. The resulting architecture shall maintain controlled, deterministic, secure, and verifiable information exchange from onboard sensors and actuators through aircraft networks to ground, fleet, and external operational systems.

화물 무인항공기(Cargo UAV) 통신 아키텍처(Communication Architecture)는 비행 제어 항공전자(Flight-Control Avionics), 추진 시스템(Propulsion System), 항법 센서(Navigation Sensor), 임무 컴퓨터(Mission Computer), 페이로드 장비(Payload Equipment), 지상통제소(Ground Control Station) 및 외부 서비스 사이에서 신뢰성 있고 결정론적이며 안전하고 추적 가능한 정보 교환을 제공해야 한다. 통신 인터페이스는 안전 중요도, 지연시간, 대역폭, 통신 거리, 이중화 및 환경 요구사항에 따라 선정하고 비행 필수 트래픽과 비핵심 트래픽의 분리를 유지해야 한다.

통신 네트워크(Communication Network)는 임무, 페이로드, 정비 또는 외부 네트워크의 고장이나 과도한 트래픽이 비행 필수 통신을 저해하지 않도록 기능별 도메인(Functional Domain)으로 분할해야 한다. 비행 제어, 추진, 항법, 페이로드, 임무 및 지상 링크 트래픽은 정의된 인터페이스와 제어된 게이트웨이(Gateway)를 사용해야 한다. 네트워크 경계는 연결된 각 서브시스템에 대해 허용되는 메시지 흐름, 우선순위, 대역폭 할당, 고장 동작 및 명령 권한을 정의해야 한다.

비행 필수 통신(Flight-Critical Communication)은 제어 루프(Control Loop) 및 안전 요구사항에 적합한 결정론적 타이밍(Deterministic Timing)을 제공해야 한다. 비행 제어, 항법, 추진 및 액추에이터 기능에서 사용하는 신호에 대해 최대 지연시간, 지터(Jitter), 갱신 주기, 타임아웃(Timeout), 메시지 수명(Message Age)을 정의해야 한다. 통신 자원은 최악의 네트워크 부하 조건에서도 충분한 여유를 확보해야 하며, 낮은 우선순위의 트래픽이 안전 필수 메시지를 할당된 타이밍 제약조건 이상으로 지연시켜서는 안 된다.

항공기 내부 네트워크는 시스템 요구사항에 따라 항공우주 데이터 버스(Aerospace Data Bus), 결정론적 이더넷(Deterministic Ethernet), CAN 기반 프로토콜(CAN-Based Protocol), 직렬 통신(Serial Communication) 또는 디스크리트 인터페이스(Discrete Interface)를 사용할 수 있다. 프로토콜 선정 시 대역폭, 토폴로지(Topology), 고장 격리(Fault Containment), 장비 호환성, 결정성, 전자기 환경 및 인증 목표를 고려해야 한다. 브리지(Bridge)와 게이트웨이는 서로 다른 통신 기술 또는 안전 도메인 사이에 통제되지 않은 종속성을 생성해서는 안 된다.

항공기와 지상통제소(Ground Control Station) 사이의 명령 및 제어 통신(Command-and-Control Communication)은 항공기 상태, 운용자 명령, 임무 정보, 경고 및 비상 정보를 신뢰성 있게 교환할 수 있어야 한다. 링크에는 정의된 갱신 주기, 타임아웃 임계값, 연결 상태 모니터링 및 링크 성능 저하 동작을 적용해야 한다. 명령 및 제어 링크의 상실은 지정된 시간 내에 감지되어야 하며 항공기 안전 아키텍처에서 정의한 사전 설정 링크 상실 대응(Lost-Link Response)을 실행해야 한다.

데이터링크 아키텍처(Datalink Architecture)는 가능한 경우 안전 관련 명령 및 제어 트래픽과 고대역폭 임무 또는 페이로드 데이터를 구분해야 한다. 비디오, 영상, 라이다(LiDAR) 정보, 정비 파일 및 기타 대용량 데이터 스트림이 항공기 제어에 필요한 통신 자원을 점유해서는 안 된다. 필수 통신 성능을 유지하기 위해 필요한 경우 서비스 품질(Quality of Service), 트래픽 우선순위화, 별도의 논리 채널 또는 물리적으로 독립된 링크를 적용해야 한다.

항법 및 감시 인프라와의 통신은 항공기의 운용 개념(Operational Concept)과 규제 환경에 적합한 인터페이스를 사용해야 한다. 임무에서 요구되는 경우 위성항법시스템 보정 정보(GNSS Correction Information), 원격 식별(Remote ID), 트랜스폰더 관련 데이터(Transponder-Related Data), 무인항공기 교통관리(UTM) 정보, 기상 데이터 또는 기타 외부 서비스를 통합할 수 있다. 외부 서비스의 상실이나 데이터 손상은 감지할 수 있어야 하며, 비행 필수 동작은 안전성 평가에서 설정한 가정의 범위를 넘어 외부 데이터 소스에 의존해서는 안 된다.

무인항공기 교통관리(UTM) 또는 플릿 관리(Fleet Management) 인프라와의 통신은 필요한 경우 항공기 식별 정보, 위치, 궤적, 임무 상태, 운용 제약조건 및 관련 경고의 제어된 교환을 지원해야 한다. 인터페이스는 메시지 소유권, 갱신 주기, 타임스탬프, 유효성 및 고장 처리를 정의해야 한다. 클라우드 또는 플릿 서비스는 필요한 보호 및 검증을 제공하는 명시적으로 승인된 안전 아키텍처가 존재하지 않는 한 저수준 비행 제어 권한으로부터 분리되어야 한다.

시간 동기화(Time Synchronization)는 비행 컴퓨터, 센서, 통신 게이트웨이, 임무 시스템 및 데이터 기록 장치 전반에 일관된 시간 기준(Temporal Reference)을 설정해야 한다. 시간적 상관관계가 필요한 메시지에는 식별된 시간 소스(Time Source)를 기준으로 하는 타임스탬프를 포함해야 한다. 동기화 정확도는 센서 융합, 항법, 제어, 이벤트 재구성(Event Reconstruction) 및 진단에 적합해야 하며, 공통 시간 기준의 성능 저하 또는 상실을 관련 시스템에서 감지할 수 있어야 한다.

메시지 정의(Message Definition)는 승인된 인터페이스 사양 및 통신 데이터베이스를 통해 관리해야 한다. 각 신호 또는 메시지에는 해당되는 경우 식별자, 송신원, 목적지, 데이터 형식, 단위, 스케일링, 유효 범위, 갱신 주기, 타임아웃, 기본 동작 및 유효성 정보를 정의해야 한다. 메시지 정의의 변경은 구성 관리(Configuration Control)를 적용하여 호환되지 않는 소프트웨어 또는 네트워크 데이터베이스가 운용 항공기 구성에 도입되는 것을 방지해야 한다.

통신 무결성 메커니즘(Communication Integrity Mechanism)은 이러한 고장이 시스템 동작에 영향을 줄 수 있는 경우 손상, 중복, 누락, 지연, 오래되거나 순서가 뒤바뀐 정보를 감지해야 한다. 인터페이스 중요도에 따라 체크섬(Checksum), 시퀀스 카운터(Sequence Counter), 타임스탬프, 메시지 인증(Message Authentication), 하트비트 감시(Heartbeat Supervision), 타임아웃 모니터링 및 종단 간 보호(End-to-End Protection)를 적용할 수 있다. 수신 기능은 핵심 정보가 비행 제어 또는 안전 관련 의사결정에 영향을 미치도록 허용하기 전에 해당 정보의 유효성을 검증해야 한다.

통신 상실로 인해 안전한 운항을 지속할 수 없는 경우 네트워크 이중화(Network Redundancy)를 제공해야 한다. 이중화 경로는 공유 스위치, 게이트웨이, 전원 공급 장치, 커넥터, 하네스 경로, 안테나 또는 통신 프로세서와 같은 불필요한 공통 고장점을 회피해야 한다. 전환 또는 페일오버(Failover) 동작은 결정론적이어야 하며, 시스템은 이중화 채널이 정상, 성능 저하, 사용 불가능 또는 상호 불일치 상태인지를 감지할 수 있어야 한다.

무선 통신(Wireless Communication)은 통신 범위, 전파 특성, 간섭, 안테나 배치, 편파(Polarization), 주파수 할당, 환경 영향 및 예상 운용 거리를 고려해야 한다. 안테나 시스템은 기체, 추진 구조물, 페이로드 또는 다른 안테나에 의한 음영(Shadowing)을 최소화하도록 설치해야 한다. 여러 무선 링크가 이중화를 제공하는 경우 공통 간섭, 공유 장비, 전원 상실 및 지리적 통신 범위 제한에 대한 독립성을 평가해야 한다.

통신 보안(Communication Security)은 식별된 사이버보안 위험(Cybersecurity Risk)에 따라 명령, 제어, 구성, 정비 및 임무 인터페이스를 비인가 접근이나 조작으로부터 보호해야 한다. 필요한 경우 인증(Authentication), 무결성 보호(Integrity Protection), 접근 제어(Access Control), 안전한 키 관리(Secure Key Management) 및 암호화(Encryption)를 적용해야 한다. 보안 메커니즘이 비행 필수 통신에 통제되지 않은 지연시간이나 고장 모드를 발생시켜서는 안 되며, 보안 서비스 상실 시 시스템 동작을 명확하게 정의해야 한다.

정비 및 소프트웨어 로딩 인터페이스(Maintenance and Software-Loading Interface)는 운용 비행 제어 통신과 분리하고 통제된 조건에서만 활성화해야 한다. 진단 접근은 승인된 작업자가 비행 필수 장비에 의도하지 않은 명령을 전달하지 않으면서 네트워크 상태, 고장 기록, 구성 정보 및 통신 통계를 확인할 수 있도록 해야 한다. 소프트웨어 또는 구성 전송에는 무결성 검사와 함께 비인가 또는 호환되지 않는 데이터의 설치를 방지하는 제어 기능을 포함해야 한다.

통신 모니터링(Communication Monitoring)은 링크 상실, 과도한 지연시간, 패킷 또는 프레임 오류, 버스 과부하, 게이트웨이 고장, 동기화 성능 저하, 인증 실패 및 비정상 트래픽을 식별할 수 있도록 충분한 관측 가능성(Observability)을 제공해야 한다. 관련 이벤트는 문제 해결, 비행 데이터 분석, 안전 조사 및 정비를 지원할 수 있도록 타임스탬프와 구성 정보를 포함하여 기록해야 한다. 진단 범위(Diagnostic Coverage)는 개별 장비 고장과 광범위한 네트워크 또는 외부 링크 고장을 구분할 수 있어야 한다.

검증(Verification)은 정상, 최대 부하, 성능 저하 및 고장 조건에서 통신 성능을 입증해야 한다. 시험에서는 지연시간, 지터, 처리량(Throughput), 메시지 타임아웃, 네트워크 혼잡, 게이트웨이 동작, 이중화 링크 전환, 손상된 데이터, 통신 상실, 전자기 교란, 동기화 상실 및 보안 관련 동작을 다루어야 한다. 소프트웨어 인 더 루프(SIL), 하드웨어 인 더 루프(HIL), 벤치 시험(Bench Test), 통합 시험(Integration Test), 지상 시험(Ground Test) 및 비행 시험(Flight Test)을 통해 통신 요구사항 충족에 대한 추적 가능한 증거를 제공해야 한다.

HRS_012_04 무인항공기 통신 표준(UAV Communication Standard)은 HRS_012_01에서 수립한 무인항공기 전기전자 아키텍처(UAV E/E Architecture), HRS_012_02의 항공전자 프레임워크(Avionics Framework), HRS_012_03의 안전 요구사항(Safety Requirement) 내에서 운용되어야 하며, HRS_012_05 인증 활동에 필요한 통신 관련 증거를 제공해야 한다. 최종 아키텍처는 탑재 센서와 액추에이터에서 항공기 내부 네트워크를 거쳐 지상, 플릿 및 외부 운용 시스템에 이르기까지 제어되고 결정론적이며 안전하고 검증 가능한 정보 교환을 유지해야 한다.

##  

## 12.05. UAV Certification Plan

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

The Cargo UAV certification plan shall establish a structured process for demonstrating that the aircraft, its electrical and electronic architecture, avionics, communication systems, propulsion interfaces, cargo functions, and safety mechanisms satisfy applicable certification requirements. The plan shall connect regulatory objectives with engineering requirements, design evidence, analysis, verification, testing, configuration control, and operational limitations throughout the development lifecycle.

Certification planning shall begin with definition of the aircraft configuration, intended operation, cargo capability, operating environment, airspace concept, autonomy level, propulsion architecture, and ground infrastructure. These characteristics shall establish the certification basis and determine which systems and functions require safety assessment, compliance evidence, environmental qualification, software or hardware assurance, ground testing, flight testing, and operational demonstration.

The certification basis shall identify applicable regulations, standards, special conditions, acceptable means of compliance, and authority-specific requirements relevant to the aircraft category and intended operation. Requirements shall be mapped to responsible engineering disciplines and verification activities. Where existing requirements do not adequately address novel UAV, autonomous, electric, hybrid-electric, or cargo functions, additional certification assumptions and compliance strategies shall be documented and agreed through the applicable approval process.

A compliance matrix shall provide traceability from each certification requirement to the corresponding aircraft requirement, design element, compliance method, verification procedure, test result, analysis, inspection, or supporting document. Compliance status shall be maintained throughout development so that open items, deviations, assumptions, and incomplete evidence remain visible. Changes to the certification basis or aircraft configuration shall trigger review of affected compliance records.

Safety assessment shall provide a major input to certification planning. Identified hazards and failure conditions shall be linked to safety objectives, system requirements, architectural mitigations, verification methods, and resulting evidence. Flight control, propulsion, electrical power, navigation, communication, cargo management, and emergency functions shall receive assurance appropriate to their safety significance. Common-cause failures and dependencies between redundant systems shall be included in the certification evidence.

The UAV E/E architecture shall be verified against the approved aircraft configuration and safety assumptions. Evidence shall demonstrate power-domain separation, protection coordination, redundant supply paths, fault containment, grounding, electromagnetic compatibility, network partitioning, and controlled interfaces between flight-critical and noncritical equipment. Electrical loads and power margins shall be evaluated for nominal, peak, transient, degraded, and defined failure conditions.

Avionics certification evidence shall demonstrate that flight-control computing, navigation sensing, actuator interfaces, time synchronization, monitoring, and redundancy satisfy allocated requirements. Software and programmable hardware shall be developed and verified using processes appropriate to their assigned assurance objectives. Configuration identification shall include software versions, hardware revisions, calibration data, communication databases, bootloaders, and other programmable items that can affect certified aircraft behavior.

Communication compliance shall address onboard networks, command-and-control links, datalinks, external services, and interfaces with ground or traffic-management infrastructure. Verification shall demonstrate required latency, determinism, integrity, availability, redundancy, lost-link behavior, and communication security where applicable. High-bandwidth mission or payload communication shall be shown not to interfere with resources required for flight-critical control and safety-related information exchange.

Environmental qualification shall demonstrate that electrical and electronic equipment remains suitable for the conditions expected during storage, ground operation, takeoff, flight, landing, and maintenance. Relevant testing may address temperature, altitude, vibration, shock, humidity, electromagnetic susceptibility and emissions, power input disturbances, and other environmental stresses identified by the certification basis. Qualification configurations shall be representative of production-intent hardware.

Ground verification shall progressively demonstrate aircraft integration before flight testing. Bench, software-in-the-loop, hardware-in-the-loop, subsystem, and aircraft-level tests shall verify power sequencing, network operation, sensor integration, actuator control, propulsion interfaces, redundancy, fault detection, cargo functions, emergency behavior, and maintenance interfaces. Ground-test results shall establish that identified hazards are sufficiently controlled before corresponding flight-test conditions are authorized.

Flight testing shall demonstrate aircraft behavior across the approved test envelope and shall verify requirements that cannot be adequately demonstrated by analysis or ground testing. Test points shall address normal operation, performance boundaries, navigation, communication, flight-control modes, propulsion response, cargo configurations, degraded conditions, contingency behavior, and controlled landing where applicable. Safety prerequisites and termination criteria shall be defined for each flight-test activity.

Cargo-related certification evidence shall demonstrate that payload installation, loading, restraint, locking, release, weight measurement, center-of-gravity determination, electrical interfaces, and environmental monitoring operate within defined aircraft limitations. Representative cargo configurations shall be considered during ground and flight testing. Unintended cargo release and incorrect cargo-state information shall be addressed through design assurance, independent confirmation, analysis, and verification where required by safety objectives.

Configuration management shall ensure that every certification test and analysis can be associated with an identifiable hardware, software, calibration, network, and aircraft configuration. Certification credit shall not be transferred automatically to configurations containing uncontrolled changes. Modifications affecting safety assumptions, electrical loads, interfaces, software behavior, communication timing, propulsion capability, payload limits, or environmental qualification shall undergo documented impact assessment and appropriate re-verification.

Certification documentation shall provide sufficient objective evidence for independent review and regulatory evaluation. The evidence set shall include applicable requirements, architecture descriptions, interface definitions, safety analyses, compliance matrices, design records, test plans, test procedures, test reports, qualification results, configuration records, anomaly dispositions, and operational limitations. Documents shall use controlled revisions so that the approved evidence set remains consistent with the aircraft configuration.

Anomalies discovered during verification or certification testing shall be recorded, analyzed, classified, and dispositioned through a controlled engineering process. Corrective actions shall identify affected requirements, safety analyses, software or hardware configurations, and previous verification results. Regression testing shall be performed where necessary to demonstrate that corrections resolve the original problem without introducing unacceptable effects into previously verified functions.

Certification readiness reviews shall evaluate whether requirements, design maturity, safety evidence, configuration status, verification results, open anomalies, and operational limitations are sufficiently complete to proceed to the next certification stage. Reviews shall be performed before major qualification campaigns, aircraft-level ground testing, critical flight testing, and final compliance submission. Unresolved items shall have documented ownership, disposition plans, and acceptance criteria.

Final certification evidence shall demonstrate an unbroken traceability chain from the certification basis through aircraft and system requirements, safety objectives, implementation, verification procedures, test results, configuration records, and approved operational limitations. The production or operational aircraft shall conform to the configuration represented by the compliance evidence. Continued configuration control shall preserve the validity of certification assumptions after initial approval.

The HRS_012_05 UAV Certification Plan shall integrate the UAV E/E architecture of HRS_012_01, avionics requirements of HRS_012_02, safety requirements of HRS_012_03, and communication requirements of HRS_012_04 into a unified compliance framework. It shall provide the final engineering pathway from requirements and safety analysis through qualification, ground and flight verification, evidence review, configuration conformity, and certification support for the Cargo UAV product family.

화물 무인항공기(Cargo UAV) 인증 계획(Certification Plan)은 항공기와 해당 전기전자 아키텍처(E/E Architecture), 항공전자(Avionics), 통신 시스템(Communication System), 추진 인터페이스(Propulsion Interface), 화물 기능(Cargo Function) 및 안전 메커니즘(Safety Mechanism)이 적용 가능한 인증 요구사항(Certification Requirement)을 충족함을 입증하기 위한 체계적인 프로세스를 수립해야 한다. 계획은 개발 수명주기 전반에 걸쳐 규제 목표(Regulatory Objective)를 엔지니어링 요구사항, 설계 증거, 분석, 검증, 시험, 구성 관리(Configuration Control) 및 운용 제한(Operational Limitation)과 연계해야 한다.

인증 계획은 항공기 구성(Aircraft Configuration), 의도된 운용(Intended Operation), 화물 운송 능력, 운용 환경, 공역 개념(Airspace Concept), 자율화 수준(Autonomy Level), 추진 아키텍처(Propulsion Architecture) 및 지상 인프라의 정의에서 시작해야 한다. 이러한 특성을 바탕으로 인증 기준(Certification Basis)을 수립하고 안전성 평가, 적합성 증거(Compliance Evidence), 환경 적합성 검증(Environmental Qualification), 소프트웨어 또는 하드웨어 보증(Assurance), 지상 시험, 비행 시험 및 운용 실증이 필요한 시스템과 기능을 결정해야 한다.

인증 기준(Certification Basis)은 항공기 범주와 의도된 운용에 관련된 적용 규정, 표준, 특별 조건(Special Condition), 허용 가능한 적합성 입증 방법(Acceptable Means of Compliance) 및 인증 당국별 요구사항을 식별해야 한다. 요구사항은 담당 엔지니어링 분야 및 검증 활동과 매핑해야 한다. 기존 요구사항이 새로운 무인항공기, 자율비행, 전기식, 하이브리드 전기식 또는 화물 기능을 충분히 다루지 못하는 경우 추가적인 인증 가정과 적합성 입증 전략을 문서화하고 해당 승인 절차를 통해 합의해야 한다.

적합성 매트릭스(Compliance Matrix)는 각각의 인증 요구사항에서 해당 항공기 요구사항, 설계 요소, 적합성 입증 방법(Compliance Method), 검증 절차, 시험 결과, 분석, 검사 또는 지원 문서까지의 추적성(Traceability)을 제공해야 한다. 개발 전반에서 적합성 상태를 관리하여 미해결 항목, 편차(Deviation), 가정 및 불완전한 증거가 명확하게 식별되도록 해야 한다. 인증 기준 또는 항공기 구성이 변경되면 영향을 받는 적합성 기록을 재검토해야 한다.

안전성 평가(Safety Assessment)는 인증 계획의 주요 입력으로 사용해야 한다. 식별된 위험요소(Hazard)와 고장 상태(Failure Condition)는 안전 목표(Safety Objective), 시스템 요구사항, 아키텍처 완화 대책(Architectural Mitigation), 검증 방법 및 최종 증거와 연결해야 한다. 비행 제어, 추진, 전력, 항법, 통신, 화물 관리 및 비상 기능에는 각각의 안전 중요도에 적합한 보증 수준을 적용해야 한다. 공통 원인 고장(Common-Cause Failure)과 이중화 시스템 간 종속성도 인증 증거에 포함해야 한다.

무인항공기 전기전자 아키텍처(UAV E/E Architecture)는 승인된 항공기 구성과 안전 가정을 기준으로 검증해야 한다. 증거를 통해 전력 도메인 분리(Power-Domain Separation), 보호 협조(Protection Coordination), 이중화 전원 경로, 고장 격리(Fault Containment), 접지(Grounding), 전자파 적합성(EMC), 네트워크 분할(Network Partitioning), 비행 필수 장비와 비핵심 장비 사이의 제어된 인터페이스를 입증해야 한다. 전기 부하와 전력 여유도는 정상, 최대, 과도, 성능 저하 및 정의된 고장 조건에서 평가해야 한다.

항공전자 인증 증거(Avionics Certification Evidence)는 비행 제어 컴퓨팅, 항법 센싱, 액추에이터 인터페이스, 시간 동기화(Time Synchronization), 모니터링 및 이중화가 할당된 요구사항을 충족함을 입증해야 한다. 소프트웨어 및 프로그래머블 하드웨어(Programmable Hardware)는 할당된 보증 목표에 적합한 프로세스를 사용하여 개발하고 검증해야 한다. 구성 식별에는 소프트웨어 버전, 하드웨어 개정 사항, 캘리브레이션 데이터(Calibration Data), 통신 데이터베이스, 부트로더(Bootloader) 및 인증된 항공기 동작에 영향을 줄 수 있는 기타 프로그래머블 항목이 포함되어야 한다.

통신 적합성(Communication Compliance)은 항공기 내부 네트워크, 명령 및 제어 링크(Command-and-Control Link), 데이터링크(Datalink), 외부 서비스, 지상 또는 교통관리 인프라와의 인터페이스를 다루어야 한다. 검증을 통해 요구되는 지연시간, 결정성(Determinism), 무결성(Integrity), 가용성(Availability), 이중화, 링크 상실 동작(Lost-Link Behavior) 및 해당되는 경우 통신 보안(Communication Security)을 입증해야 한다. 고대역폭 임무 또는 페이로드 통신이 비행 필수 제어 및 안전 관련 정보 교환에 필요한 자원을 방해하지 않음을 입증해야 한다.

환경 적합성 검증(Environmental Qualification)은 전기 및 전자 장비가 보관, 지상 운용, 이륙, 비행, 착륙 및 정비 과정에서 예상되는 환경 조건에 적합함을 입증해야 한다. 관련 시험에는 인증 기준에서 식별된 온도, 고도, 진동, 충격, 습도, 전자기 감수성 및 방출(Electromagnetic Susceptibility and Emissions), 전원 입력 교란(Power Input Disturbance) 및 기타 환경 스트레스가 포함될 수 있다. 적합성 시험 구성은 양산 의도 하드웨어(Production-Intent Hardware)를 대표할 수 있어야 한다.

지상 검증(Ground Verification)은 비행 시험에 앞서 항공기 통합 상태를 단계적으로 입증해야 한다. 벤치 시험(Bench Test), 소프트웨어 인 더 루프(SIL), 하드웨어 인 더 루프(HIL), 서브시스템 시험 및 항공기 수준 시험을 통해 전원 시퀀싱, 네트워크 동작, 센서 통합, 액추에이터 제어, 추진 인터페이스, 이중화, 고장 감지, 화물 기능, 비상 동작 및 정비 인터페이스를 검증해야 한다. 지상 시험 결과를 통해 해당 비행 시험 조건을 승인하기 전에 식별된 위험요소가 충분히 통제되고 있음을 입증해야 한다.

비행 시험(Flight Testing)은 승인된 시험 비행영역(Test Envelope) 전반에서 항공기 동작을 입증하고 분석 또는 지상 시험만으로 충분히 입증할 수 없는 요구사항을 검증해야 한다. 시험 항목은 정상 운용, 성능 한계, 항법, 통신, 비행 제어 모드, 추진 응답, 화물 구성, 성능 저하 조건, 비상 동작 및 해당되는 경우 제어 착륙(Controlled Landing)을 포함해야 한다. 각각의 비행 시험 활동에 대해 안전 선행 조건(Safety Prerequisite)과 시험 종료 기준(Termination Criteria)을 정의해야 한다.

화물 관련 인증 증거(Cargo-Related Certification Evidence)는 페이로드 설치, 적재, 구속(Restraint), 잠금, 해제, 중량 측정, 무게중심(Center of Gravity) 결정, 전기 인터페이스 및 환경 모니터링이 정의된 항공기 제한 범위 내에서 동작함을 입증해야 한다. 대표적인 화물 구성은 지상 및 비행 시험에서 고려해야 한다. 의도하지 않은 화물 해제와 잘못된 화물 상태 정보는 안전 목표에서 요구되는 경우 설계 보증(Design Assurance), 독립적인 확인, 분석 및 검증을 통해 다루어야 한다.

구성 관리(Configuration Management)는 모든 인증 시험과 분석이 식별 가능한 하드웨어, 소프트웨어, 캘리브레이션, 네트워크 및 항공기 구성과 연계되도록 해야 한다. 통제되지 않은 변경이 포함된 구성에 인증 크레딧(Certification Credit)을 자동으로 이전해서는 안 된다. 안전 가정, 전기 부하, 인터페이스, 소프트웨어 동작, 통신 타이밍, 추진 능력, 페이로드 제한 또는 환경 적합성에 영향을 미치는 변경에는 문서화된 영향 평가와 적절한 재검증(Re-Verification)을 수행해야 한다.

인증 문서(Certification Documentation)는 독립적인 검토와 규제 기관의 평가에 충분한 객관적 증거(Objective Evidence)를 제공해야 한다. 증거 세트에는 적용 요구사항, 아키텍처 설명, 인터페이스 정의, 안전성 분석, 적합성 매트릭스, 설계 기록, 시험 계획, 시험 절차, 시험 보고서, 적합성 시험 결과, 구성 기록, 이상사항 처리(Anomaly Disposition) 및 운용 제한이 포함되어야 한다. 승인된 증거 세트가 항공기 구성과 일관성을 유지하도록 문서에 통제된 개정(Controlled Revision)을 적용해야 한다.

검증 또는 인증 시험 중 발견된 이상사항(Anomaly)은 통제된 엔지니어링 프로세스를 통해 기록, 분석, 분류 및 처리해야 한다. 시정 조치(Corrective Action)는 영향을 받는 요구사항, 안전성 분석, 소프트웨어 또는 하드웨어 구성 및 기존 검증 결과를 식별해야 한다. 수정 사항이 기존 문제를 해결하면서 이미 검증된 기능에 허용할 수 없는 영향을 새롭게 발생시키지 않음을 입증하기 위해 필요한 경우 회귀 시험(Regression Testing)을 수행해야 한다.

인증 준비 검토(Certification Readiness Review)는 다음 인증 단계로 진행하기에 요구사항, 설계 성숙도, 안전 증거, 구성 상태, 검증 결과, 미해결 이상사항 및 운용 제한이 충분히 완성되었는지를 평가해야 한다. 주요 적합성 시험 캠페인, 항공기 수준 지상 시험, 핵심 비행 시험 및 최종 적합성 제출 전에 검토를 수행해야 한다. 미해결 항목에는 문서화된 담당자, 처리 계획 및 승인 기준(Acceptance Criteria)을 지정해야 한다.

최종 인증 증거(Final Certification Evidence)는 인증 기준에서 항공기 및 시스템 요구사항, 안전 목표, 구현, 검증 절차, 시험 결과, 구성 기록 및 승인된 운용 제한까지 이어지는 단절 없는 추적성 체인(Traceability Chain)을 입증해야 한다. 양산 또는 실제 운용 항공기는 적합성 증거가 대표하는 구성과 일치해야 한다. 최초 승인 이후에도 지속적인 구성 관리를 통해 인증 가정의 유효성을 유지해야 한다.

HRS_012_05 무인항공기 인증 계획(UAV Certification Plan)은 HRS_012_01의 무인항공기 전기전자 아키텍처(UAV E/E Architecture), HRS_012_02의 항공전자 요구사항(Avionics Requirement), HRS_012_03의 안전 요구사항(Safety Requirement), HRS_012_04의 통신 요구사항(Communication Requirement)을 하나의 통합 적합성 프레임워크(Unified Compliance Framework)로 결합해야 한다. 이를 통해 요구사항 및 안전성 분석에서 적합성 검증, 지상 및 비행 검증, 증거 검토, 구성 적합성(Configuration Conformity) 및 화물 무인항공기 제품군의 인증 지원(Certification Support)에 이르는 최종 엔지니어링 경로를 제공해야 한다.
