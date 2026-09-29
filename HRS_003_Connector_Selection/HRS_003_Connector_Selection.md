**Volume 22. Hills Robotics Engineering Standards**


# Chapter 03. HRS-003 Connector Selection

##  

## 03.01. Approved Connector List

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

The approved connector list establishes a controlled set of connector families that may be used in Hills Robotics electrical and electronic designs. Its purpose is to reduce unnecessary connector variation, improve harness interchangeability, simplify procurement, and ensure that connectors used across AMRs, manipulators, outdoor vehicles, UAVs, quadrupeds, and humanoids satisfy consistent engineering expectations.

Approval applies to a connector family and its defined configuration rather than merely to a manufacturer name. The engineering record should identify the series, housing type, contact system, pin-count range, allowable wire sizes, current and voltage limits, sealing capability, keying method, and applicable accessories. Terminals, seals, backshells, wedges, plugs, and mating components shall therefore be treated as part of the approved connection system.

Connector selection shall begin with the electrical function of the interface. Low-current sensor and signal circuits, communication networks, auxiliary power circuits, actuator power, battery distribution, and high-voltage interfaces impose different requirements on contact resistance, spacing, shielding, sealing, and mechanical retention. A connector approved for one circuit class shall not automatically be considered suitable for another solely because its pin count is sufficient.

For internal low-voltage electronics located inside protected enclosures, compact board-to-wire or wire-to-wire connector families may be approved when their voltage, current, temperature, vibration, and retention characteristics match the application. Connectors used for serviceable modules should include positive polarization and a reliable locking feature. Friction-only retention should be restricted to locations where environmental and mechanical loads are demonstrably controlled.

External robot interfaces require connector families designed for repeated vibration, contamination, and service exposure. Sealed automotive or industrial connectors are preferred where cables pass between chassis modules, sensors, actuators, power distribution units, and externally mounted equipment. The required environmental protection shall be selected according to the application-specific IP rating rules defined separately within the connector selection standard.

For automotive-style low-voltage power and control interfaces, approved families should provide robust secondary locking, terminal position assurance where appropriate, polarization, replaceable contacts, and sealed variants. Contact systems shall support the specified conductor cross-section without modifying terminals or seals. Designers shall not mix terminals, housings, seals, or secondary locks from nominally similar but unqualified connector families.

Industrial connectors may be approved for fixed or semi-fixed equipment interfaces where standardized field wiring, serviceability, and mechanical robustness are important. Circular connectors, M-series sensor connectors, industrial Ethernet connectors, and locking power connectors may be used when appropriate to the installation environment. Their use on moving robot structures additionally requires evaluation of vibration, cable bending, strain relief, and mating retention.

Communication connectors shall be selected together with the physical-layer requirements of the network. CAN, CAN FD, RS-485, Ethernet, EtherCAT, camera links, and time-synchronization interfaces may require controlled impedance, twisted pairs, shielding, or dedicated contact arrangements. An electrically compatible connector is not necessarily communication-qualified if its geometry, shield termination, or contact discontinuity degrades signal integrity at the required data rate.

Sensor connectors should favor standardized interfaces when this improves replacement and field service. LiDAR, cameras, radar, IMUs, GNSS receivers, safety sensors, encoders, and environmental sensors may use different approved families depending on bandwidth and power requirements. Where power and high-speed data share one connector, pin allocation shall maintain adequate separation and grounding so that switching noise does not compromise sensitive signal paths.

Actuator and motor interfaces require special attention to continuous current, peak current, contact heating, vibration, and disconnect behavior. Connector current ratings shall not be accepted directly from nominal catalog values without considering ambient temperature, number of simultaneously loaded contacts, enclosure temperature, conductor size, and duty cycle. High-current motor connectors should also provide mechanical keying that prevents accidental interchange with low-power interfaces.

High-voltage connector systems shall be maintained as a distinct approved category and shall comply with the dedicated HV connector rules defined elsewhere in HRS_003. Approved HV families should provide appropriate creepage and clearance, touch-safe construction, polarization, secure locking, and environmental sealing. Where required by system architecture, high-voltage interlock capability, shielding, and controlled connection sequencing shall be incorporated into the connector system.

Battery and charging connectors require separate consideration because they may experience high continuous current, repeated mating cycles, transient loads, and operator interaction. Approved families shall have clearly defined current derating, contact temperature limits, mating-cycle capability, and protection against reverse connection. Service-disconnect connectors shall additionally support safe handling procedures and prevent unintended exposure to energized conductive parts.

Safety-related interfaces should use connector configurations that minimize foreseeable assembly errors. Emergency-stop circuits, safety LiDAR, safety PLC I/O, brake control, and other safety functions should not depend solely on wire color or labels for correct connection. Unique keying, dedicated connector families, separated pin assignments, or other mistake-proofing measures should be applied according to the consequence of an incorrect connection.

Approved connector families shall be evaluated as complete harness interfaces, including cable exit direction and strain relief. A connector that satisfies electrical requirements may still be unacceptable when its backshell forces an excessive bend radius, interferes with neighboring components, or transfers cable motion directly into contacts. Straight and right-angle variants should therefore be approved independently when their mechanical installation characteristics differ significantly.

Serviceability is an essential approval criterion for robotics platforms expected to operate over long field lifetimes. Preferred connector families should permit visual verification of locking, controlled disconnection using normal service tools, replacement of damaged terminals where practical, and procurement of mating components throughout the expected product lifecycle. Connectors requiring destructive removal should be limited to interfaces intentionally designated as non-serviceable.

The approved list shall distinguish preferred, conditional, and legacy connector status where configuration management requires such differentiation. Preferred families are the default choice for new designs. Conditional families may be used only for defined environmental, packaging, supplier, or equipment constraints. Legacy connectors may remain on released products for compatibility but should not normally be introduced into new platforms without an engineering justification and formal approval.

Each released connector shall have controlled manufacturer and supplier information associated with the engineering BOM. Manufacturer part numbers should identify the exact housing, terminal, seal, accessory, and mating component rather than relying on descriptive names. Approved equivalent parts may be listed only after dimensional, electrical, material, environmental, tooling, and manufacturing compatibility have been verified through the applicable qualification process.

No connector shall be added to the approved list solely because it is commercially available or has been used successfully in an unrelated product. New connector families require engineering review against electrical load, environmental exposure, vibration, mating durability, sealing, assembly process, inspection capability, supplier stability, and service requirements. Qualification expectations shall follow the dedicated HRS_003 qualification requirement rather than being embedded informally in individual projects.

Connector standardization should also support manufacturing quality. Approved contacts should have defined crimp tools, applicators, strip lengths, pull-force expectations, and inspection criteria. Hand-crimp substitutions, generic terminals, or unverified tooling shall not be introduced merely to resolve short-term production shortages. Any temporary deviation should be documented through the engineering change process and assessed for both electrical and mechanical reliability.

Robotic platforms frequently combine low-voltage power, high-current actuators, high-speed data, safety circuits, and sensitive perception electronics within a compact structure. The approved connector strategy should therefore encourage functional differentiation through connector size, keying, color coding where appropriate, and physical placement. Maintenance personnel should be able to reconnect modules without creating credible cross-mating between incompatible electrical domains.

Connector selection shall remain consistent with harness design, grounding, communication, safety, and product-specific standards across the wider robotics engineering framework. The connector list is therefore not an isolated purchasing catalog but a controlled architectural resource linking electrical interfaces to manufacturing and lifecycle requirements. This supports consistent implementation across the broader electrical, communication, safety, AMR, manipulator, outdoor vehicle, UAV, quadruped, and humanoid engineering structure.

승인 커넥터 목록(Approved Connector List)은 힐스로보틱스(Hills Robotics)의 전기·전자 설계에서 사용할 수 있는 커넥터 제품군(Connector Family)을 통제된 형태로 정의한다. 그 목적은 불필요한 커넥터 종류의 증가를 줄이고, 와이어 하네스(Wire Harness)의 상호 호환성을 향상시키며, 조달을 단순화하고, AMR, 매니퓰레이터(Manipulator), 야외 차량(Outdoor Vehicle), UAV, 사족보행 로봇(Quadruped), 휴머노이드(Humanoid)에 적용되는 커넥터가 일관된 엔지니어링 요구사항을 충족하도록 하는 것이다.

승인은 단순히 제조사(Manufacturer)의 이름을 기준으로 하는 것이 아니라 커넥터 제품군(Connector Family)과 정의된 구성(Configuration)을 기준으로 적용되어야 한다. 엔지니어링 기록에는 시리즈(Series), 하우징 유형(Housing Type), 접점 시스템(Contact System), 핀 수 범위(Pin-count Range), 허용 전선 크기, 전류 및 전압 한계, 밀봉 성능(Sealing Capability), 키잉 방식(Keying Method), 적용 가능한 부속품을 식별해야 한다. 따라서 단자(Terminal), 실(Seal), 백셸(Backshell), 웨지(Wedge), 플러그(Plug), 상대 체결 부품(Mating Component)은 승인된 연결 시스템의 일부로 관리해야 한다.

커넥터 선정(Connector Selection)은 인터페이스(Interface)의 전기적 기능에서 시작해야 한다. 저전류 센서 및 신호 회로, 통신 네트워크(Communication Network), 보조 전원 회로, 액추에이터 전원(Actuator Power), 배터리 전력 분배(Battery Distribution), 고전압 인터페이스(High-voltage Interface)는 접촉 저항(Contact Resistance), 간격, 차폐(Shielding), 밀봉 및 기계적 유지력에 서로 다른 요구사항을 가진다. 특정 회로 등급에 승인된 커넥터라도 핀 수가 충분하다는 이유만으로 다른 회로에 적합하다고 판단해서는 안 된다.

보호된 인클로저(Enclosure) 내부에 위치하는 저전압 전자장치에는 전압, 전류, 온도, 진동 및 유지 특성이 적용 조건과 일치하는 경우 소형 보드-투-와이어(Board-to-Wire) 또는 와이어-투-와이어(Wire-to-Wire) 커넥터 제품군을 승인할 수 있다. 정비 가능한 모듈(Serviceable Module)에 사용되는 커넥터에는 확실한 극성 구조(Positive Polarization)와 신뢰성 있는 잠금 기능(Locking Feature)을 적용해야 한다. 마찰력만을 이용하는 고정 방식은 환경 및 기계적 하중이 충분히 통제되는 위치로 제한해야 한다.

로봇 외부 인터페이스(External Robot Interface)에는 반복적인 진동, 오염 및 정비 환경 노출에 대응하도록 설계된 커넥터 제품군을 적용해야 한다. 섀시 모듈(Chassis Module), 센서, 액추에이터, 전력 분배 장치(Power Distribution Unit) 및 외부 장착 장비 사이에 케이블이 연결되는 경우 밀봉형 자동차용 또는 산업용 커넥터를 우선적으로 사용한다. 필요한 환경 보호 수준은 커넥터 선정 표준 내에서 별도로 정의된 애플리케이션별 IP 등급(IP Rating) 규칙에 따라 선정해야 한다.

자동차형 저전압 전원 및 제어 인터페이스에는 견고한 이중 잠금(Secondary Locking), 필요한 경우 단자 위치 보증(Terminal Position Assurance), 극성 구조(Polarization), 교체 가능한 접점(Replaceable Contact), 밀봉형 제품을 제공하는 승인 제품군을 우선적으로 적용해야 한다. 접점 시스템은 단자나 실을 임의로 변경하지 않고 지정된 도체 단면적을 지원해야 한다. 설계자는 외형적으로 유사하더라도 검증되지 않은 서로 다른 커넥터 제품군의 단자, 하우징, 실 또는 이중 잠금 부품을 혼용해서는 안 된다.

산업용 커넥터(Industrial Connector)는 표준화된 현장 배선(Field Wiring), 정비성(Serviceability), 기계적 견고성이 중요한 고정 또는 반고정 장비 인터페이스에 승인할 수 있다. 원형 커넥터(Circular Connector), M-시리즈 센서 커넥터(M-series Sensor Connector), 산업용 이더넷 커넥터(Industrial Ethernet Connector), 잠금식 전원 커넥터(Locking Power Connector)는 설치 환경에 적합한 경우 사용할 수 있다. 움직이는 로봇 구조에 적용하는 경우에는 진동, 케이블 굽힘, 스트레인 릴리프(Strain Relief), 체결 유지력(Mating Retention)을 추가로 평가해야 한다.

통신 커넥터(Communication Connector)는 네트워크(Network)의 물리 계층(Physical Layer) 요구사항과 함께 선정해야 한다. CAN, CAN FD, RS-485, 이더넷(Ethernet), EtherCAT, 카메라 링크(Camera Link), 시간 동기화(Time Synchronization) 인터페이스에는 제어 임피던스(Controlled Impedance), 트위스트 페어(Twisted Pair), 차폐 또는 전용 접점 배열이 필요할 수 있다. 전기적으로 호환되는 커넥터라도 형상, 차폐 종단(Shield Termination), 접점 불연속성이 요구 데이터 속도에서 신호 무결성(Signal Integrity)을 저하시킨다면 통신용으로 적합하다고 판단해서는 안 된다.

센서 커넥터(Sensor Connector)는 교체성과 현장 정비성이 향상되는 경우 표준화된 인터페이스를 우선적으로 적용해야 한다. LiDAR, 카메라(Camera), 레이더(Radar), IMU, GNSS 수신기, 안전 센서(Safety Sensor), 인코더(Encoder), 환경 센서(Environmental Sensor)는 대역폭과 전원 요구사항에 따라 서로 다른 승인 제품군을 사용할 수 있다. 전원과 고속 데이터(High-speed Data)를 하나의 커넥터에서 함께 사용하는 경우 스위칭 노이즈(Switching Noise)가 민감한 신호 경로에 영향을 주지 않도록 적절한 핀 분리와 접지(Grounding)를 적용해야 한다.

액추에이터(Actuator) 및 모터 인터페이스(Motor Interface)는 연속 전류(Continuous Current), 피크 전류(Peak Current), 접점 발열(Contact Heating), 진동 및 분리 동작을 특별히 고려해야 한다. 커넥터의 전류 정격(Current Rating)은 주변 온도, 동시에 부하가 인가되는 접점 수, 인클로저 온도, 도체 크기 및 듀티 사이클(Duty Cycle)을 고려하지 않은 상태에서 카탈로그의 공칭값을 그대로 적용해서는 안 된다. 고전류 모터 커넥터에는 저전력 인터페이스와 잘못 연결되는 것을 방지할 수 있는 기계적 키잉(Mechanical Keying)을 적용하는 것이 바람직하다.

고전압 커넥터 시스템(High-voltage Connector System)은 별도의 승인 범주로 관리하며 HRS_003에서 정의하는 전용 고전압 커넥터 규칙(HV Connector Rules)을 준수해야 한다. 승인된 고전압 제품군은 적절한 연면거리(Creepage Distance)와 공간거리(Clearance), 접촉 안전 구조(Touch-safe Construction), 극성 구조, 확실한 잠금 및 환경 밀봉 기능을 제공해야 한다. 시스템 아키텍처(System Architecture)에서 요구되는 경우 고전압 인터록(High-voltage Interlock), 차폐 및 제어된 연결 순서(Controlled Connection Sequencing)를 커넥터 시스템에 포함해야 한다.

배터리 및 충전 커넥터(Battery and Charging Connector)는 높은 연속 전류, 반복적인 체결 주기(Mating Cycle), 과도 부하(Transient Load), 작업자의 직접적인 조작에 노출될 수 있으므로 별도로 고려해야 한다. 승인 제품군에는 전류 디레이팅(Current Derating), 접점 온도 한계(Contact Temperature Limit), 체결 수명 및 역접속 방지(Reverse Connection Protection)가 명확하게 정의되어야 한다. 서비스 디스커넥트 커넥터(Service-disconnect Connector)는 안전한 취급 절차를 지원하고 통전된 도전부가 의도하지 않게 노출되지 않도록 해야 한다.

안전 관련 인터페이스(Safety-related Interface)는 예측 가능한 조립 오류를 최소화할 수 있는 커넥터 구성을 사용해야 한다. 비상정지(Emergency Stop), 안전 LiDAR(Safety LiDAR), 안전 PLC 입출력(Safety PLC I/O), 브레이크 제어(Brake Control) 및 기타 안전 기능은 올바른 연결을 전선 색상이나 라벨에만 의존해서는 안 된다. 잘못된 연결로 인한 결과의 심각도에 따라 고유 키잉(Unique Keying), 전용 커넥터 제품군, 분리된 핀 할당 또는 기타 오류 방지(Mistake-proofing) 방법을 적용해야 한다.

승인된 커넥터 제품군은 케이블 인출 방향(Cable Exit Direction)과 스트레인 릴리프를 포함하는 완전한 하네스 인터페이스(Harness Interface)로 평가해야 한다. 전기적 요구사항을 충족하는 커넥터라도 백셸이 과도한 굽힘 반경(Bend Radius)을 유발하거나 주변 부품과 간섭하거나 케이블 움직임을 접점으로 직접 전달한다면 사용할 수 없다. 따라서 직선형(Straight)과 직각형(Right-angle) 제품은 기계적 설치 특성이 크게 다를 경우 독립적으로 승인해야 한다.

장기간 현장에서 운용되는 로봇 플랫폼(Robotics Platform)에서는 정비성(Serviceability)이 중요한 승인 기준이다. 선호되는 커넥터 제품군은 잠금 상태를 육안으로 확인할 수 있고, 일반적인 정비 도구로 통제된 분리가 가능하며, 가능한 경우 손상된 단자를 교체할 수 있어야 한다. 또한 예상되는 제품 수명주기(Product Lifecycle) 동안 상대 체결 부품을 지속적으로 조달할 수 있어야 한다. 파괴적인 제거가 필요한 커넥터는 의도적으로 비정비형(Non-serviceable)으로 지정된 인터페이스로 제한해야 한다.

승인 목록은 형상관리(Configuration Management)의 필요에 따라 선호(Preferred), 조건부(Conditional), 레거시(Legacy) 커넥터 상태를 구분해야 한다. 선호 제품군은 신규 설계의 기본 선택으로 사용한다. 조건부 제품군은 정의된 환경, 패키징(Packaging), 공급업체 또는 장비 제약이 있는 경우에만 사용할 수 있다. 레거시 커넥터는 기존 출시 제품의 호환성을 위해 유지할 수 있지만, 엔지니어링 타당성 검토와 공식 승인이 없는 경우 신규 플랫폼에 적용해서는 안 된다.

출시된 각 커넥터에는 엔지니어링 자재명세서(Engineering BOM)와 연계된 통제된 제조사 및 공급업체 정보가 있어야 한다. 제조사 부품번호(Manufacturer Part Number)는 단순한 설명 명칭이 아니라 정확한 하우징, 단자, 실, 부속품 및 상대 체결 부품을 식별해야 한다. 승인된 대체 부품(Approved Equivalent Part)은 치수, 전기적 특성, 재료, 환경 성능, 툴링(Tooling), 제조 호환성이 해당 검증 절차를 통해 확인된 경우에만 목록에 포함할 수 있다.

커넥터가 상업적으로 구매 가능하거나 관련 없는 다른 제품에서 성공적으로 사용되었다는 이유만으로 승인 목록에 추가해서는 안 된다. 신규 커넥터 제품군은 전기적 부하, 환경 노출, 진동, 체결 내구성(Mating Durability), 밀봉, 조립 공정, 검사 능력, 공급업체 안정성 및 정비 요구사항에 대한 엔지니어링 검토가 필요하다. 검증 요구사항(Qualification Requirement)은 개별 프로젝트에서 비공식적으로 정의하지 않고 별도의 HRS_003 검증 요구사항을 따라야 한다.

커넥터 표준화(Connector Standardization)는 제조 품질(Manufacturing Quality)도 지원해야 한다. 승인된 접점에는 정의된 압착 공구(Crimp Tool), 어플리케이터(Applicator), 피복 제거 길이(Strip Length), 인장력 기준(Pull-force Expectation), 검사 기준(Inspection Criteria)이 있어야 한다. 단기적인 생산 부족을 해결하기 위해 수동 압착 대체 방식, 범용 단자 또는 검증되지 않은 툴링을 임의로 도입해서는 안 된다. 일시적인 예외는 엔지니어링 변경 프로세스(Engineering Change Process)를 통해 문서화하고 전기적·기계적 신뢰성을 모두 평가해야 한다.

로봇 플랫폼은 제한된 구조 내부에 저전압 전원(Low-voltage Power), 고전류 액추에이터(High-current Actuator), 고속 데이터, 안전 회로(Safety Circuit), 민감한 인지 전자장치(Perception Electronics)를 함께 구성하는 경우가 많다. 따라서 승인 커넥터 전략은 커넥터 크기, 키잉, 필요한 경우 색상 코딩(Color Coding), 물리적 배치를 이용하여 기능을 명확히 구분하도록 해야 한다. 정비 작업자가 모듈을 재연결할 때 서로 호환되지 않는 전기 영역 사이에서 잘못된 교차 체결(Cross-mating)이 발생하지 않도록 설계해야 한다.

커넥터 선정은 전체 로봇 엔지니어링 표준 체계에서 하네스 설계(Harness Design), 접지(Grounding), 통신(Communication), 안전(Safety) 및 제품별 표준과 일관성을 유지해야 한다. 따라서 승인 커넥터 목록은 단순한 구매용 카탈로그가 아니라 전기적 인터페이스를 제조 및 수명주기 요구사항과 연결하는 통제된 아키텍처 자원(Architectural Resource)이다. 이를 통해 전기, 통신, 안전, AMR, 매니퓰레이터, 야외 차량, UAV, 사족보행 로봇 및 휴머노이드 엔지니어링 전반에서 일관된 구현을 지원할 수 있다.

##  

## 03.02. IP Rating by Application

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

The IP rating assigned to a connector shall reflect the actual environmental exposure of its installation rather than the general classification of the robot. A connector located inside a sealed electronics enclosure may require substantially less protection than an externally mounted connector on the same platform. Selection shall consider dust, water, condensation, cleaning procedures, mounting orientation, operating motion, and foreseeable service conditions.

IP ratings shall be interpreted according to the applicable ingress protection standard and shall not be treated as a general measure of connector quality. The first characteristic numeral represents protection against access and solid-particle ingress, while the second represents protection against water ingress under defined test conditions. Designers shall verify the precise qualification represented by the specified rating rather than relying only on labels such as waterproof or dustproof.

Connectors installed entirely inside dry, environmentally controlled electrical cabinets may generally use lower ingress protection when the enclosure itself provides the required environmental barrier. In such applications, connector selection should emphasize electrical rating, polarization, retention, serviceability, and contact reliability. The enclosure IP rating does not automatically transfer to exposed connectors installed through its walls or service openings.

Protected internal robot compartments that can experience dust, occasional condensation, or maintenance exposure should normally use connectors providing a moderate level of ingress resistance. IP4X or higher solid-object protection may be appropriate depending on enclosure design, while water protection should reflect realistic internal exposure. Where condensation is credible, material compatibility and contact corrosion resistance remain necessary even when direct water spray is unlikely.

For general industrial robot interfaces exposed to dust and occasional water splash, IP54 should be regarded as a practical minimum reference where the installation environment requires basic dust and splash protection. The final requirement shall nevertheless be determined from the actual hazard analysis. IP54 does not provide the same protection as sealed connector systems intended for washdown, outdoor weather, temporary immersion, or high-pressure cleaning.

External AMR connectors located near sensors, bumpers, chassis panels, or exposed harness routes should normally target at least IP65 when direct dust and water-jet exposure is credible. Connectors mounted close to wheels, floor level, suspension elements, or cleaning zones may require IP67 or higher because splash, accumulated water, mud, and temporary immersion can occur during normal operation or maintenance.

Indoor AMRs operating exclusively in clean warehouses may permit lower ratings for connectors protected by body panels, but floor-level interfaces require additional caution. Cleaning machines, wet floors, spilled liquids, and maintenance washing can create exposure conditions beyond the nominal indoor environment. The connector rating shall therefore be based on installation location and operating scenario rather than the indoor classification alone.

Outdoor AMRs and autonomous vehicles should generally use sealed external connectors rated at least IP67 where dust, rain, splash, mud, and temporary water accumulation are foreseeable. IP66 may be suitable where powerful water jets represent the governing condition without immersion requirements. Interfaces positioned underneath the chassis or near wheels should be assessed for combined water, contamination, vibration, and mechanical impact.

Where repeated or prolonged immersion is a credible operating condition, IP68 may be required. The manufacturer-defined immersion depth and duration associated with IP68 shall be documented because IP68 does not represent one universal immersion condition. Engineering approval shall confirm that the qualified depth, exposure time, cable configuration, and connector mating state correspond to the intended robot application.

IP69 or IP69K-class protection may be considered for connectors subjected to high-pressure and high-temperature washdown, particularly in sanitation, food-processing, agricultural, construction, or specialized industrial environments. Such ratings shall not be specified automatically for ordinary outdoor robots. High-pressure cleaning capability should be required only where the defined cleaning process creates the corresponding exposure and qualification need.

Manipulator connectors located inside fixed bases, electrical cabinets, or protected joint covers may use lower IP ratings when the surrounding structure provides adequate protection. Interfaces on exposed arms, wrists, tool changers, or end effectors require higher protection according to dust, coolant, lubricant, process debris, and cleaning exposure. Motion shall also be considered because repeated cable flexing can degrade sealing around cable exits.

Tool changer and end-effector interfaces deserve specific evaluation because frequent mating can progressively affect sealing surfaces. A connector initially qualified to IP67 may not retain equivalent protection after contamination, mechanical wear, damaged seals, or improper mating. Where ingress protection is safety- or reliability-critical, inspection intervals, allowable mating cycles, seal condition, and replacement criteria shall be included in maintenance requirements.

Sensor interfaces for LiDAR, cameras, radar, GNSS, ultrasonic sensors, and external perception modules should typically use sealed connectors when installed outside protected housings. IP65 may be sufficient for sheltered positions, while IP67 is preferred for direct outdoor exposure. Sensors mounted low on the chassis or in splash zones may require IP67, IP68, or application-specific higher protection based on the defined operating environment.

Quadruped robots require particular attention because connectors can operate close to the ground while experiencing dust, rain, mud, vegetation, impact, and rapid body motion. External leg and body interfaces should normally use robust sealed connector systems, with IP67 serving as a practical baseline for demanding field operation. Higher protection may be necessary for robots expected to traverse standing water or undergo intensive cleaning.

Humanoid robots may contain numerous internal connectors protected by structural covers, allowing differentiated IP requirements rather than applying one high rating throughout the platform. Exposed connectors around feet, lower legs, hands, service ports, and externally mounted sensors require greater protection. Interfaces near joints shall additionally account for movement, seal deformation, cable strain, and contamination introduced during maintenance.

Cargo UAV connector requirements shall consider rain, airborne dust, humidity, condensation, altitude-related environmental changes, and ground handling. Externally exposed avionics, propulsion, lighting, sensor, and cargo interfaces should use appropriately sealed connector systems. Selection shall also consider weight and vibration because unnecessarily high sealing requirements can increase connector mass, size, mating force, and harness complexity.

Battery and charging interfaces shall be evaluated separately from ordinary signal connectors. These interfaces may be exposed during battery replacement, charging, maintenance, or outdoor operation and may encounter moisture while significant electrical energy is available. Required IP protection shall be defined for both mated and unmated conditions, because many connector systems achieve their specified sealing performance only when completely mated.

The specified IP rating applies only to the connector configuration represented by the qualification test. Housing, terminal, seal, backshell, cable diameter, blanking plug, assembly method, and mating condition can all influence sealing performance. Substituting a wire outside the approved seal range, omitting a cavity plug, damaging a seal, or incorrectly assembling a backshell can invalidate the intended ingress protection even when the housing part number is unchanged.

Unused connector cavities shall be sealed using approved cavity plugs when required by the connector system. Unmated service connectors shall use qualified protective caps where environmental exposure can occur. Temporary tape, generic rubber covers, grease, or field-applied sealant shall not be considered equivalent to a qualified sealing component unless specifically validated through the applicable engineering qualification and change-control process.

Ingress protection shall be evaluated together with connector orientation and harness routing. Downward-facing interfaces, drip loops, drainage paths, and protected mounting positions can reduce direct exposure, whereas upward-facing connectors may collect water around sealing interfaces. Mechanical packaging should prevent standing water from remaining at connector boundaries and should avoid routing that transfers water along the harness directly toward the connector.

Environmental sealing shall not compromise pressure equalization or create hidden condensation problems within enclosed modules. Temperature cycling can produce internal pressure changes that draw moisture through marginal seals or cable interfaces. Where sealed electronic compartments experience substantial thermal cycling, the complete enclosure architecture, vents, glands, connectors, and drainage strategy shall be considered together rather than treating each connector independently.

An IP rating alone does not demonstrate resistance to salt, oils, fuels, hydraulic fluids, cleaning chemicals, ultraviolet radiation, or other environmental agents. Applications exposed to such substances require separate material compatibility evaluation. Similarly, IP qualification does not replace vibration, temperature, mating durability, corrosion, EMC, electrical load, or mechanical retention testing required by the connector qualification process.

The engineering drawing and BOM shall identify the required IP rating where it is a controlled interface characteristic. The requirement should also specify whether the rating applies when mated, unmated, capped, or under another defined configuration. Supplier documentation and qualification evidence shall be retained so that production, quality, service, and engineering teams can verify that the released connector configuration satisfies the intended application.

IP requirements shall be reviewed whenever connector location, enclosure design, robot operating environment, cleaning procedure, cable routing, or service concept changes. Moving an approved connector from a protected internal position to an external location can create a new environmental requirement even when its electrical function remains unchanged. Such changes shall therefore trigger engineering review rather than automatic reuse of the previous connector approval.

Application-based IP selection ultimately provides a graded protection strategy across the robotics platform. Protected electronics may use moderate ingress protection, while exposed sensors, actuators, chassis interfaces, batteries, and outdoor equipment receive progressively stronger sealing according to their actual exposure. This approach avoids both under-protection that reduces reliability and unnecessary over-specification that increases cost, size, weight, and service complexity.

커넥터에 지정되는 IP 등급(IP Rating)은 로봇 전체의 일반적인 환경 분류가 아니라 해당 커넥터가 실제로 설치되는 위치의 환경 노출 조건을 반영해야 한다. 밀폐된 전자장치 인클로저(Enclosure) 내부의 커넥터는 동일한 플랫폼의 외부 장착 커넥터보다 훨씬 낮은 보호 수준으로도 충분할 수 있다. 선정 시에는 먼지, 물, 결로(Condensation), 세척 절차, 장착 방향, 작동 중 움직임 및 예상 가능한 정비 조건을 고려해야 한다.

IP 등급은 적용 가능한 침투 보호 표준(Ingress Protection Standard)에 따라 해석해야 하며, 커넥터의 전반적인 품질 수준을 나타내는 지표로 취급해서는 안 된다. 첫 번째 특성 숫자는 접근 및 고형 입자 침투에 대한 보호 수준을 나타내며, 두 번째 숫자는 정의된 시험 조건에서 물의 침투에 대한 보호 수준을 나타낸다. 설계자는 단순히 방수(Waterproof) 또는 방진(Dustproof)이라는 표현에 의존하지 말고 지정된 등급이 의미하는 정확한 검증 조건을 확인해야 한다.

건조하고 환경이 통제된 전기 캐비닛(Electrical Cabinet) 내부에 완전히 설치되는 커넥터는 인클로저 자체가 필요한 환경 장벽을 제공하는 경우 상대적으로 낮은 침투 보호 수준을 적용할 수 있다. 이러한 용도에서는 전기 정격(Electrical Rating), 극성 구조(Polarization), 체결 유지력(Retention), 정비성(Serviceability), 접점 신뢰성(Contact Reliability)을 중심으로 커넥터를 선정해야 한다. 인클로저의 IP 등급이 벽면이나 정비 개구부에 노출된 커넥터에 자동으로 적용되는 것은 아니다.

먼지, 간헐적인 결로 또는 정비 과정의 환경 노출이 발생할 수 있는 보호된 로봇 내부 구획에는 일반적으로 중간 수준의 침투 저항(Ingress Resistance)을 제공하는 커넥터를 사용해야 한다. 인클로저 설계에 따라 IP4X 이상의 고형물 보호가 적절할 수 있으며, 방수 수준은 현실적으로 예상되는 내부 노출 조건을 반영해야 한다. 직접적인 물 분사가 예상되지 않더라도 결로 가능성이 있다면 재료 호환성(Material Compatibility)과 접점 부식 저항(Contact Corrosion Resistance)을 고려해야 한다.

먼지와 간헐적인 물 튀김에 노출되는 일반적인 산업용 로봇 인터페이스(Industrial Robot Interface)의 경우 기본적인 방진 및 방수 보호가 필요한 설치 환경에서는 IP54를 실용적인 최소 기준으로 고려할 수 있다. 그러나 최종 요구사항은 실제 위험 분석(Hazard Analysis)을 통해 결정해야 한다. IP54는 세척, 야외 기상 조건, 일시적 침수 또는 고압 세척을 고려하여 설계된 밀봉형 커넥터 시스템(Sealed Connector System)과 동일한 보호 수준을 제공하지 않는다.

센서, 범퍼, 섀시 패널 또는 외부로 노출된 하네스 경로 근처에 위치하는 AMR 외부 커넥터는 직접적인 먼지와 물 분사에 노출될 가능성이 있는 경우 일반적으로 최소 IP65 수준을 목표로 해야 한다. 바퀴, 바닥면, 서스펜션(Suspension) 구성품 또는 세척 구역과 가까운 위치에 장착되는 커넥터는 정상적인 운용이나 정비 중 물 튀김, 고인 물, 진흙 및 일시적 침수가 발생할 수 있으므로 IP67 이상의 보호 수준이 필요할 수 있다.

청결한 창고에서만 운용되는 실내 AMR(Indoor AMR)은 차체 패널로 보호되는 커넥터에 상대적으로 낮은 등급을 허용할 수 있지만, 바닥면에 가까운 인터페이스는 추가적인 주의가 필요하다. 청소 장비, 젖은 바닥, 액체 유출 및 유지보수 세척은 명목상의 실내 환경을 넘어서는 노출 조건을 만들 수 있다. 따라서 커넥터 등급은 단순한 실내 운용 분류가 아니라 실제 설치 위치와 운용 시나리오(Operating Scenario)를 기준으로 결정해야 한다.

야외 AMR(Outdoor AMR)과 자율주행 차량(Autonomous Vehicle)은 먼지, 비, 물 튀김, 진흙 및 일시적인 물 고임이 예상되는 외부 커넥터에 일반적으로 최소 IP67 수준의 밀봉형 커넥터를 적용해야 한다. 침수 요구사항은 없지만 강한 물 분사가 주요 환경 조건인 경우 IP66이 적합할 수 있다. 섀시 하부 또는 바퀴 근처의 인터페이스는 물, 오염물질, 진동 및 기계적 충격이 복합적으로 작용하는 조건을 평가해야 한다.

반복적이거나 장시간의 침수가 현실적으로 예상되는 운용 조건에서는 IP68이 필요할 수 있다. IP68에 해당하는 제조사 정의 침수 깊이(Immersion Depth)와 지속 시간(Duration)을 반드시 문서화해야 한다. IP68은 하나의 보편적인 침수 조건을 의미하지 않기 때문이다. 엔지니어링 승인(Engineering Approval) 과정에서는 검증된 수심, 노출 시간, 케이블 구성 및 커넥터 체결 상태가 실제 로봇 적용 조건과 일치하는지 확인해야 한다.

고압 및 고온 세척에 노출되는 커넥터에는 IP69 또는 IP69K 등급의 보호를 고려할 수 있으며, 특히 위생, 식품 가공, 농업, 건설 또는 특수 산업 환경에서 중요하다. 그러나 이러한 등급을 일반적인 야외 로봇에 자동으로 지정해서는 안 된다. 고압 세척 보호 성능은 정의된 세척 공정(Cleaning Process)이 실제로 해당 수준의 환경 노출과 검증 필요성을 발생시키는 경우에만 요구해야 한다.

고정 베이스(Fixed Base), 전기 캐비닛 또는 보호된 관절 커버 내부에 위치하는 매니퓰레이터(Manipulator) 커넥터는 주변 구조물이 충분한 보호 기능을 제공하는 경우 낮은 IP 등급을 사용할 수 있다. 외부에 노출된 암(Arm), 손목(Wrist), 툴 체인저(Tool Changer), 엔드 이펙터(End Effector)의 인터페이스는 먼지, 냉각수, 윤활유, 공정 잔해 및 세척 노출에 따라 더 높은 보호 수준이 필요하다. 반복적인 케이블 굽힘이 케이블 인출부의 밀봉 성능을 저하시킬 수 있으므로 움직임도 함께 고려해야 한다.

툴 체인저와 엔드 이펙터 인터페이스는 반복적인 체결이 밀봉 표면(Sealing Surface)의 성능을 점진적으로 저하시킬 수 있으므로 별도의 평가가 필요하다. 최초에 IP67로 검증된 커넥터라도 오염, 기계적 마모, 실(Seal) 손상 또는 불완전한 체결이 발생하면 동일한 보호 성능을 유지하지 못할 수 있다. 침투 보호가 안전이나 신뢰성에 중요한 경우 검사 주기, 허용 체결 횟수, 실 상태 및 교체 기준을 유지보수 요구사항에 포함해야 한다.

LiDAR, 카메라(Camera), 레이더(Radar), GNSS, 초음파 센서(Ultrasonic Sensor) 및 외부 인지 모듈(Perception Module)의 센서 인터페이스는 보호된 하우징 외부에 설치되는 경우 일반적으로 밀봉형 커넥터를 사용해야 한다. 차폐된 위치에는 IP65가 충분할 수 있지만 직접적인 야외 노출에는 IP67을 우선적으로 고려한다. 섀시 하부나 물 튀김 구역에 장착되는 센서는 정의된 운용 환경에 따라 IP67, IP68 또는 애플리케이션별로 더 높은 보호 수준이 필요할 수 있다.

사족보행 로봇(Quadruped Robot)은 커넥터가 지면 가까이에서 작동하면서 먼지, 비, 진흙, 식생, 충격 및 빠른 차체 움직임에 노출될 수 있으므로 특별한 주의가 필요하다. 외부 다리 및 차체 인터페이스에는 견고한 밀봉형 커넥터 시스템을 적용해야 하며, 가혹한 현장 운용에서는 IP67을 실용적인 기준선(Baseline)으로 고려할 수 있다. 고인 물을 통과하거나 강도 높은 세척을 수행해야 하는 로봇에는 더 높은 보호 수준이 필요할 수 있다.

휴머노이드 로봇(Humanoid Robot)은 구조 커버로 보호되는 다수의 내부 커넥터를 포함할 수 있으므로 플랫폼 전체에 하나의 높은 IP 등급을 일률적으로 적용하기보다 위치에 따라 차등화된 IP 요구사항을 적용할 수 있다. 발, 하퇴부, 손, 정비 포트(Service Port), 외부 장착 센서 주변의 노출 인터페이스에는 더 높은 보호 수준이 필요하다. 관절 근처의 인터페이스는 움직임, 실 변형(Seal Deformation), 케이블 변형력 및 정비 과정에서 유입되는 오염물질도 함께 고려해야 한다.

화물 UAV(Cargo UAV)의 커넥터 요구사항은 비, 공기 중 먼지, 습도, 결로, 고도 변화에 따른 환경 조건 및 지상 취급(Ground Handling)을 고려해야 한다. 외부에 노출되는 항공전자(Avionics), 추진 시스템(Propulsion), 조명, 센서 및 화물 인터페이스에는 적절하게 밀봉된 커넥터 시스템을 사용해야 한다. 지나치게 높은 밀봉 요구사항은 커넥터의 질량, 크기, 체결력 및 하네스 복잡성을 증가시킬 수 있으므로 중량과 진동도 함께 고려해야 한다.

배터리 및 충전 인터페이스(Battery and Charging Interface)는 일반 신호 커넥터와 별도로 평가해야 한다. 이러한 인터페이스는 배터리 교체, 충전, 정비 또는 야외 운용 중 외부에 노출될 수 있으며, 상당한 전기 에너지가 존재하는 상태에서 습기에 접촉할 가능성이 있다. 많은 커넥터 시스템이 완전히 체결된 상태에서만 지정된 밀봉 성능을 제공하므로 요구되는 IP 보호 수준은 체결 상태(Mated Condition)와 비체결 상태(Unmated Condition)를 모두 고려하여 정의해야 한다.

지정된 IP 등급은 검증 시험(Qualification Test)에서 사용된 커넥터 구성에만 적용된다. 하우징(Housing), 단자(Terminal), 실, 백셸(Backshell), 케이블 직경, 블랭킹 플러그(Blanking Plug), 조립 방법 및 체결 상태는 모두 밀봉 성능에 영향을 줄 수 있다. 승인된 실 범위를 벗어난 전선을 사용하거나 캐비티 플러그(Cavity Plug)를 누락하거나 실을 손상시키거나 백셸을 잘못 조립하면 하우징 부품번호가 동일하더라도 의도된 침투 보호 성능이 무효화될 수 있다.

사용하지 않는 커넥터 캐비티(Connector Cavity)는 커넥터 시스템에서 요구하는 경우 승인된 캐비티 플러그를 사용하여 밀봉해야 한다. 체결되지 않은 정비용 커넥터는 환경에 노출될 가능성이 있는 경우 검증된 보호 캡(Protective Cap)을 사용해야 한다. 임시 테이프, 범용 고무 커버, 그리스(Grease) 또는 현장에서 도포하는 실런트(Sealant)는 해당 엔지니어링 검증 및 변경관리(Change Control) 절차를 통해 별도로 검증되지 않는 한 검증된 밀봉 부품과 동등한 것으로 간주해서는 안 된다.

침투 보호는 커넥터 방향(Connector Orientation) 및 하네스 라우팅(Harness Routing)과 함께 평가해야 한다. 아래쪽을 향하는 인터페이스, 드립 루프(Drip Loop), 배수 경로(Drainage Path), 보호된 장착 위치는 직접적인 환경 노출을 감소시킬 수 있지만 위쪽을 향하는 커넥터는 밀봉 인터페이스 주변에 물이 고일 수 있다. 기계적 패키징(Mechanical Packaging)은 커넥터 경계에 물이 지속적으로 고이지 않도록 해야 하며, 하네스를 따라 물이 직접 커넥터로 이동하는 배선 경로를 피해야 한다.

환경 밀봉(Environmental Sealing)은 압력 평형(Pressure Equalization)을 방해하거나 밀폐된 모듈 내부에 숨겨진 결로 문제를 발생시켜서는 안 된다. 온도 사이클링(Temperature Cycling)은 내부 압력 변화를 발생시켜 불완전한 실이나 케이블 인터페이스를 통해 습기를 유입시킬 수 있다. 밀폐형 전자 구획에서 큰 온도 변화가 발생하는 경우 각각의 커넥터를 독립적으로 판단하기보다 전체 인클로저 아키텍처, 벤트(Vent), 글랜드(Gland), 커넥터 및 배수 전략을 함께 고려해야 한다.

IP 등급만으로 염분, 오일, 연료, 유압유, 세척 화학물질, 자외선(Ultraviolet Radiation) 또는 기타 환경 물질에 대한 내성을 입증할 수는 없다. 이러한 물질에 노출되는 애플리케이션에는 별도의 재료 호환성 평가가 필요하다. 마찬가지로 IP 검증은 커넥터 검증 과정에서 요구되는 진동, 온도, 체결 내구성(Mating Durability), 부식, EMC, 전기적 부하 및 기계적 유지력 시험을 대체하지 않는다.

IP 등급이 통제되는 인터페이스 특성(Controlled Interface Characteristic)인 경우 엔지니어링 도면(Engineering Drawing)과 자재명세서(BOM)에 요구되는 IP 등급을 명시해야 한다. 또한 해당 등급이 체결 상태, 비체결 상태, 보호 캡 장착 상태 또는 기타 정의된 구성 중 어느 조건에 적용되는지도 명시해야 한다. 생산, 품질, 정비 및 엔지니어링 조직이 출시된 커넥터 구성이 의도된 애플리케이션을 충족하는지 확인할 수 있도록 공급업체 문서와 검증 근거를 유지해야 한다.

커넥터 위치, 인클로저 설계, 로봇 운용 환경, 세척 절차, 케이블 라우팅 또는 정비 개념(Service Concept)이 변경될 때마다 IP 요구사항을 재검토해야 한다. 승인된 커넥터를 보호된 내부 위치에서 외부 위치로 이동하면 전기적 기능이 동일하더라도 새로운 환경 요구사항이 발생할 수 있다. 따라서 이러한 변경에는 기존 커넥터 승인을 자동으로 재사용하지 말고 엔지니어링 검토를 수행해야 한다.

애플리케이션 기반 IP 선정(Application-based IP Selection)은 궁극적으로 로봇 플랫폼 전체에 단계적인 보호 전략(Graded Protection Strategy)을 제공한다. 보호된 전자장치는 중간 수준의 침투 보호를 적용할 수 있으며, 외부에 노출되는 센서, 액추에이터, 섀시 인터페이스, 배터리 및 야외 장비에는 실제 환경 노출 수준에 따라 점진적으로 강화된 밀봉 성능을 적용한다. 이러한 접근 방식은 신뢰성을 저하시키는 보호 부족과 비용, 크기, 중량 및 정비 복잡성을 증가시키는 불필요한 과도 사양(Over-specification)을 동시에 방지할 수 있다.

##  

## 03.03. HV Connector Rules

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

High-voltage connectors shall be treated as safety-critical electrical interfaces rather than as scaled versions of low-voltage connectors. Their selection and integration shall address operating voltage, transient voltage, continuous and peak current, insulation coordination, environmental exposure, mechanical loads, service conditions, and foreseeable misuse. HV interfaces shall remain clearly distinguishable from LV signal and power connections throughout the robot architecture.

The HV connector voltage rating shall exceed the maximum voltage that can occur at the interface under normal operation and defined abnormal conditions. Selection shall consider battery maximum charge voltage, regenerative conditions, switching transients, converter behavior, and applicable overvoltage categories. Nominal battery voltage alone shall not be used as the basis for connector voltage qualification or insulation design.

Continuous current capability shall be determined from the actual thermal environment rather than directly adopting the connector catalog rating. Conductor size, contact resistance, ambient temperature, enclosure temperature, simultaneously loaded contacts, duty cycle, cooling conditions, and allowable temperature rise shall be considered. Peak current capability shall also be verified for acceleration, actuator startup, charging, and transient power demands.

Creepage and clearance distances shall be appropriate for the maximum working voltage, transient conditions, pollution degree, insulation material, and environmental exposure of the application. Connector geometry shall preserve the required insulation separation both while fully mated and during defined service conditions. Contamination, condensation, conductive dust, and mechanical wear shall be considered where they can reduce effective insulation performance.

HV connector systems shall provide touch-safe protection against accidental contact with hazardous energized conductors. Exposed conductive HV contacts shall not become accessible during normal handling, intended servicing, or foreseeable partial disconnection. Where stored electrical energy remains after system shutdown, the connector design shall be coordinated with discharge circuits and service procedures so that safe voltage is achieved before hazardous contacts become accessible.

Mechanical polarization and keying shall prevent incorrect mating between HV circuits of different voltage classes, polarity, or functions. HV connectors shall also be physically differentiated from low-voltage connectors where credible cross-mating could create a hazard. Color coding may support identification but shall not serve as the only means of preventing an electrically incompatible connection.

Positive mechanical locking shall be provided for HV connectors subjected to vibration, vehicle motion, manipulator movement, UAV operation, or repeated handling. The locking mechanism shall resist unintended separation under the defined mechanical environment and should provide clear indication of complete engagement. Connector retention shall not depend solely on cable tension, friction, or operator judgment.

Where required by the system safety architecture, a high-voltage interlock loop, or HVIL, shall detect incomplete mating, unintended disconnection, opened service covers, or other defined HV access conditions. The interlock shall be coordinated with the contactor and power control strategy so that hazardous power is removed before the main HV contacts become accessible or separate under load.

The connector mating sequence shall be controlled when electrical safety depends on contact timing. Protective ground, shield, interlock, pilot, and main power contacts may require defined make-first or break-last behavior depending on the architecture. Designers shall use connector systems specifically engineered for the required sequencing rather than assuming that mechanical connector travel inherently provides safe electrical timing.

HV connectors shall not normally be connected or disconnected while carrying load unless the connector system is specifically designed and qualified for that operation. Contactors, precharge circuits, discharge circuits, and system control logic should establish a de-energized condition before manual separation. Any interface intentionally designed for hot-plug or load-break operation requires dedicated qualification and explicit engineering approval.

Precharge architecture shall be coordinated with HV connectors where large DC-link capacitance or power electronic loads are present. The connector shall not be expected to absorb uncontrolled inrush current caused by charging downstream capacitors during mating. Precharge completion, main contactor closure, and connector interlock status should be managed as part of a defined power-up and power-down state sequence.

Environmental sealing requirements shall follow the installation environment and the application-specific IP rules. External HV connectors on outdoor robots, exposed battery systems, propulsion equipment, or charging interfaces may require IP67, IP68, or other qualified protection. The specified ingress rating shall be verified for the actual housing, seal, cable diameter, backshell, cavity plugs, and mating condition used in production.

HV connector materials shall be compatible with expected temperature, humidity, vibration, oils, cleaning agents, salt exposure, ultraviolet radiation, and other relevant environmental conditions. An IP rating alone does not demonstrate resistance to chemical degradation or corrosion. Material compatibility and environmental durability shall therefore be evaluated separately where the operating environment creates such exposure.

Cable shielding and connector shield termination shall be designed according to EMC requirements for inverter, motor, DC/DC converter, charger, and other high-frequency power electronic circuits. Where shield continuity is required, the connector should provide a low-impedance termination suitable for the frequency range of concern. Long shield pigtails should be avoided where they significantly degrade high-frequency shielding effectiveness.

HV cable conductor size and connector contact size shall be engineered as one electrical and thermal interface. A large conductor shall not be reduced locally merely to fit an undersized connector terminal without documented analysis and approval. Likewise, a high-current connector does not compensate for an undersized cable. Cable ampacity, terminal heating, voltage drop, mechanical strain, and fault current shall be evaluated together.

Strain relief shall prevent cable weight, bending, vibration, and external forces from being transferred directly to HV contacts or seals. Minimum bend radius shall be maintained near the connector, particularly for large shielded power cables. Connector mounting and harness routing shall provide sufficient service clearance while preventing repeated cable motion from loosening the connector or degrading environmental sealing.

Battery connectors and service disconnects require additional protection because they may remain energized independently of the main vehicle or robot contactors. Their design shall prevent reverse polarity, unintended reconnection, and accidental access to hazardous voltage. Where manual service disconnects are provided, their removal sequence, touch protection, stored-energy discharge, and lockout procedure shall be explicitly defined.

Charging connectors shall be selected according to charging voltage, maximum continuous current, communication or pilot requirements, mating frequency, environmental exposure, and operator interaction. Temperature monitoring should be considered where high-current charging can produce significant contact heating. Charging interfaces shall prevent unintended energization before correct mating and shall coordinate disconnection with charger power control.

HV interfaces used on mobile manipulators, quadrupeds, humanoids, and other articulated robots shall account for repeated motion and dynamic loading. Connectors should preferably be located away from high-flex zones unless specifically designed for such service. Where HV wiring crosses joints, cable routing, flex life, strain relief, abrasion protection, and fault containment shall be evaluated as part of the complete moving harness system.

Outdoor autonomous vehicles and heavy AMRs may contain multiple HV domains for traction, auxiliary power, high-power actuators, and charging. Connector keying and architecture shall prevent accidental interchange among these domains. Interfaces located underneath the chassis or near wheels require additional consideration of impact, stone exposure, water, mud, conductive contamination, and maintenance accessibility.

Cargo UAV HV connectors shall account for vibration, mass, packaging volume, altitude, temperature variation, propulsion current, and maintenance requirements. Connector mass reduction shall not compromise insulation, locking, current capability, or touch protection. Propulsion and battery interfaces should be arranged to minimize the probability that a single connector fault can disable multiple redundant power channels when redundancy is required.

HV connectors shall be positioned so that routine maintenance on unrelated LV electronics does not unnecessarily expose personnel to hazardous-voltage interfaces. Physical segregation, covers, barriers, labeling, and controlled service access should support the electrical architecture. Service procedures shall define isolation, verification of de-energization, discharge waiting time where applicable, and conditions for reconnecting HV components.

Connector housings, cables, and associated HV components shall use consistent identification where required by the product architecture and applicable regulations or standards. Identification should remain visible during assembly and service. Labels shall indicate relevant hazards or circuit information when necessary, but markings shall supplement rather than replace physical protection, polarization, interlocking, and safe system design.

Each released HV connector configuration shall be controlled through the engineering drawing and BOM. The record shall identify the exact housing, contacts, seals, backshell, shielding components, HVIL components, cavity plugs, mating connector, cable range, and approved tooling where applicable. Substituting apparently compatible components shall not be permitted without engineering review and qualification.

Crimping and termination processes for HV contacts shall use approved tooling and controlled process parameters. Conductor preparation, strip length, shield preparation, crimp geometry, pull force, seal installation, and visual inspection criteria shall be defined. Poor termination can create localized resistance and thermal runaway even when the connector housing itself satisfies the required voltage and current ratings.

HV connector qualification shall address the conditions relevant to the intended product, including electrical withstand, insulation resistance, contact resistance, temperature rise, vibration, mechanical shock, mating durability, environmental sealing, corrosion, and thermal cycling as applicable. Safety-related functions such as HVIL operation, touch protection, keying, and controlled disconnection shall also be verified where incorporated.

Any change to connector family, contact material, terminal size, cable cross-section, seal, backshell, supplier, manufacturing process, mounting location, or operating environment shall be evaluated for its effect on the released HV interface. Changes that can affect electrical, thermal, mechanical, environmental, EMC, or safety performance require documented engineering review before implementation.

The HV connector rules ultimately establish a coordinated interface between power architecture, harness design, protection, grounding, EMC, safety, manufacturing, and service. A compliant HV connection is therefore not defined by connector voltage and current ratings alone. It is a qualified system in which electrical insulation, thermal capability, touch protection, interlocking, mechanical retention, environmental sealing, and lifecycle control work together.

고전압 커넥터(HV Connector)는 저전압 커넥터(Low-voltage Connector)의 단순한 대형 버전이 아니라 안전 필수 전기 인터페이스(Safety-critical Electrical Interface)로 취급해야 한다. 커넥터의 선정과 통합 과정에서는 동작 전압, 과도 전압(Transient Voltage), 연속 및 피크 전류, 절연 협조(Insulation Coordination), 환경 노출, 기계적 하중, 정비 조건 및 예측 가능한 오사용을 고려해야 한다. 고전압 인터페이스(HV Interface)는 로봇 아키텍처 전체에서 저전압 신호 및 전원 연결과 명확하게 구분되어야 한다.

고전압 커넥터의 전압 정격(Voltage Rating)은 정상 운전 및 정의된 비정상 조건에서 해당 인터페이스에 발생할 수 있는 최대 전압보다 높아야 한다. 선정 과정에서는 배터리 최대 충전 전압, 회생 조건(Regenerative Condition), 스위칭 과도현상(Switching Transient), 컨버터(Converter) 동작 및 적용 가능한 과전압 범주(Overvoltage Category)를 고려해야 한다. 커넥터 전압 검증이나 절연 설계의 기준으로 배터리 공칭 전압만을 사용해서는 안 된다.

연속 전류 용량(Continuous Current Capability)은 커넥터 카탈로그의 정격을 그대로 적용하지 않고 실제 열 환경(Thermal Environment)을 기준으로 결정해야 한다. 도체 크기, 접촉 저항(Contact Resistance), 주변 온도, 인클로저(Enclosure) 내부 온도, 동시에 부하가 인가되는 접점 수, 듀티 사이클(Duty Cycle), 냉각 조건 및 허용 온도 상승을 고려해야 한다. 가속, 액추에이터 기동, 충전 및 과도 전력 요구에 대해서는 피크 전류 용량(Peak Current Capability)도 검증해야 한다.

연면거리(Creepage Distance)와 공간거리(Clearance Distance)는 최대 동작 전압, 과도 조건, 오염도(Pollution Degree), 절연 재료 및 애플리케이션의 환경 노출에 적합해야 한다. 커넥터 형상은 완전히 체결된 상태와 정의된 정비 조건 모두에서 필요한 절연 간격을 유지해야 한다. 유효 절연 성능을 저하시킬 수 있는 오염, 결로(Condensation), 도전성 먼지 및 기계적 마모도 고려해야 한다.

고전압 커넥터 시스템은 위험한 통전 도체(Hazardous Energized Conductor)에 우발적으로 접촉하는 것을 방지할 수 있는 접촉 안전 보호(Touch-safe Protection)를 제공해야 한다. 노출된 고전압 접점은 정상적인 취급, 의도된 정비 또는 예상 가능한 부분 분리 과정에서 접근 가능해서는 안 된다. 시스템 종료 후에도 저장된 전기 에너지가 남아 있는 경우 위험한 접점에 접근하기 전에 안전 전압에 도달하도록 커넥터 설계를 방전 회로(Discharge Circuit) 및 정비 절차와 연계해야 한다.

기계적 극성 구조(Mechanical Polarization)와 키잉(Keying)은 서로 다른 전압 등급, 극성 또는 기능을 갖는 고전압 회로 사이의 잘못된 체결을 방지해야 한다. 잘못된 교차 체결(Cross-mating)이 위험을 발생시킬 가능성이 있는 경우 고전압 커넥터는 저전압 커넥터와 물리적으로도 구분되어야 한다. 색상 코딩(Color Coding)은 식별을 보조할 수 있지만 전기적으로 호환되지 않는 연결을 방지하는 유일한 수단으로 사용해서는 안 된다.

진동, 차량 움직임, 매니퓰레이터(Manipulator) 동작, UAV 운용 또는 반복적인 취급에 노출되는 고전압 커넥터에는 확실한 기계적 잠금(Positive Mechanical Locking)을 적용해야 한다. 잠금 메커니즘은 정의된 기계적 환경에서 의도하지 않은 분리를 방지할 수 있어야 하며, 완전한 체결 상태를 명확하게 확인할 수 있는 구조가 바람직하다. 커넥터의 유지력은 케이블 장력, 마찰력 또는 작업자의 판단에만 의존해서는 안 된다.

시스템 안전 아키텍처(System Safety Architecture)에서 요구되는 경우 고전압 인터록 루프(High-voltage Interlock Loop, HVIL)는 불완전한 체결, 의도하지 않은 분리, 개방된 정비 커버 또는 기타 정의된 고전압 접근 상태를 감지해야 한다. 인터록(Interlock)은 접촉기(Contactor) 및 전력 제어 전략과 연계하여 위험한 전력이 제거된 후에 주 고전압 접점이 접근 가능해지거나 부하 상태에서 분리되도록 해야 한다.

전기적 안전이 접점의 동작 순서에 의존하는 경우 커넥터 체결 순서(Mating Sequence)를 제어해야 한다. 보호 접지(Protective Ground), 차폐(Shield), 인터록, 파일럿(Pilot), 주 전력 접점(Main Power Contact)은 아키텍처에 따라 선접촉(Make-first) 또는 후분리(Break-last) 동작이 요구될 수 있다. 설계자는 단순히 커넥터의 기계적 이동이 안전한 전기적 타이밍을 제공한다고 가정하지 말고 필요한 접점 순서를 위해 특별히 설계된 커넥터 시스템을 사용해야 한다.

고전압 커넥터는 해당 동작을 위해 특별히 설계되고 검증되지 않은 경우 일반적으로 부하가 흐르는 상태에서 연결하거나 분리해서는 안 된다. 수동 분리 전에 접촉기, 프리차지 회로(Precharge Circuit), 방전 회로 및 시스템 제어 로직(System Control Logic)을 통해 무전압 상태를 만들어야 한다. 핫플러그(Hot-plug) 또는 부하 차단(Load-break)을 의도적으로 지원하는 인터페이스에는 별도의 검증과 명시적인 엔지니어링 승인이 필요하다.

대용량 DC 링크 커패시턴스(DC-link Capacitance) 또는 전력전자 부하가 존재하는 경우 프리차지 아키텍처(Precharge Architecture)를 고전압 커넥터와 연계해야 한다. 커넥터 체결 과정에서 하류 커패시터를 충전하면서 발생하는 제어되지 않은 돌입전류(Inrush Current)를 커넥터가 직접 흡수하도록 설계해서는 안 된다. 프리차지 완료, 주 접촉기 폐쇄 및 커넥터 인터록 상태는 정의된 전원 인가 및 차단 상태 시퀀스(State Sequence)의 일부로 관리하는 것이 바람직하다.

환경 밀봉(Environmental Sealing) 요구사항은 설치 환경 및 애플리케이션별 IP 규칙(IP Rules)을 따라야 한다. 야외 로봇, 외부 노출 배터리 시스템, 추진 장비 또는 충전 인터페이스의 외부 고전압 커넥터에는 IP67, IP68 또는 기타 검증된 보호 수준이 필요할 수 있다. 지정된 침투 보호 등급(Ingress Protection Rating)은 실제 생산에 사용되는 하우징, 실(Seal), 케이블 직경, 백셸(Backshell), 캐비티 플러그(Cavity Plug) 및 체결 상태에 대해 검증해야 한다.

고전압 커넥터 재료는 예상되는 온도, 습도, 진동, 오일, 세척제, 염분 노출, 자외선(Ultraviolet Radiation) 및 기타 관련 환경 조건과 호환되어야 한다. IP 등급만으로 화학적 열화(Chemical Degradation) 또는 부식에 대한 내성을 입증할 수는 없다. 따라서 운용 환경에서 이러한 노출이 발생하는 경우 재료 호환성(Material Compatibility)과 환경 내구성(Environmental Durability)을 별도로 평가해야 한다.

케이블 차폐(Cable Shielding) 및 커넥터 차폐 종단(Shield Termination)은 인버터(Inverter), 모터, DC/DC 컨버터, 충전기 및 기타 고주파 전력전자 회로의 EMC 요구사항에 따라 설계해야 한다. 차폐 연속성(Shield Continuity)이 필요한 경우 커넥터는 문제가 되는 주파수 범위에 적합한 저임피던스 종단(Low-impedance Termination)을 제공하는 것이 바람직하다. 긴 차폐 피그테일(Shield Pigtail)이 고주파 차폐 효과를 크게 저하시키는 경우 이를 피해야 한다.

고전압 케이블 도체 크기와 커넥터 접점 크기는 하나의 전기적·열적 인터페이스로 통합하여 설계해야 한다. 대형 도체를 크기가 작은 커넥터 단자에 맞추기 위해 문서화된 분석과 승인 없이 국부적으로 축소해서는 안 된다. 마찬가지로 고전류 커넥터를 사용한다고 해서 크기가 부족한 케이블의 문제를 보완할 수는 없다. 케이블 허용전류(Ampacity), 단자 발열, 전압 강하, 기계적 변형력 및 고장 전류(Fault Current)를 함께 평가해야 한다.

스트레인 릴리프(Strain Relief)는 케이블 중량, 굽힘, 진동 및 외력이 고전압 접점이나 실에 직접 전달되지 않도록 해야 한다. 특히 대형 차폐 전력 케이블에서는 커넥터 주변의 최소 굽힘 반경(Minimum Bend Radius)을 유지해야 한다. 커넥터 장착 및 하네스 라우팅(Harness Routing)은 충분한 정비 공간을 제공하는 동시에 반복적인 케이블 움직임으로 인해 커넥터가 느슨해지거나 환경 밀봉 성능이 저하되지 않도록 해야 한다.

배터리 커넥터(Battery Connector)와 서비스 디스커넥트(Service Disconnect)는 주 차량 또는 로봇 접촉기와 독립적으로 통전 상태를 유지할 수 있으므로 추가적인 보호가 필요하다. 설계는 역극성(Reverse Polarity), 의도하지 않은 재연결 및 위험 전압에 대한 우발적 접근을 방지해야 한다. 수동 서비스 디스커넥트를 사용하는 경우 제거 순서, 접촉 안전 보호, 저장 에너지 방전 및 잠금 절차(Lockout Procedure)를 명확하게 정의해야 한다.

충전 커넥터(Charging Connector)는 충전 전압, 최대 연속 전류, 통신 또는 파일럿 요구사항, 체결 빈도, 환경 노출 및 작업자 상호작용을 기준으로 선정해야 한다. 고전류 충전으로 인해 상당한 접점 발열이 발생할 수 있는 경우 온도 모니터링(Temperature Monitoring)을 고려해야 한다. 충전 인터페이스는 올바른 체결 전에 의도하지 않은 전원 인가가 발생하지 않도록 해야 하며, 분리 동작은 충전기 전력 제어와 연계해야 한다.

모바일 매니퓰레이터(Mobile Manipulator), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 기타 관절형 로봇(Articulated Robot)에 사용되는 고전압 인터페이스는 반복적인 움직임과 동적 하중(Dynamic Loading)을 고려해야 한다. 커넥터는 해당 용도로 특별히 설계되지 않은 경우 높은 굽힘이 반복되는 영역을 피해서 배치하는 것이 바람직하다. 고전압 배선이 관절을 통과하는 경우 케이블 라우팅, 굽힘 수명(Flex Life), 스트레인 릴리프, 마모 보호 및 고장 격리(Fault Containment)를 전체 가동 하네스 시스템의 일부로 평가해야 한다.

야외 자율주행 차량(Outdoor Autonomous Vehicle)과 중량급 AMR(Heavy AMR)은 구동, 보조 전원, 고출력 액추에이터 및 충전을 위한 여러 개의 고전압 영역(HV Domain)을 포함할 수 있다. 커넥터 키잉과 아키텍처는 이러한 영역 사이의 우발적인 교차 연결을 방지해야 한다. 섀시 하부 또는 바퀴 주변에 위치하는 인터페이스는 충격, 돌 튐, 물, 진흙, 도전성 오염 및 정비 접근성을 추가로 고려해야 한다.

화물 UAV(Cargo UAV)의 고전압 커넥터는 진동, 질량, 패키징 체적(Packaging Volume), 고도, 온도 변화, 추진 전류 및 정비 요구사항을 고려해야 한다. 커넥터의 질량을 줄이기 위해 절연, 잠금, 전류 용량 또는 접촉 안전 보호를 희생해서는 안 된다. 이중화(Redundancy)가 요구되는 경우 하나의 커넥터 고장으로 여러 개의 이중화 전력 채널(Redundant Power Channel)이 동시에 상실될 가능성을 최소화하도록 추진 및 배터리 인터페이스를 구성해야 한다.

고전압 커넥터는 관련 없는 저전압 전자장치의 일상적인 유지보수 과정에서 작업자가 불필요하게 위험 전압 인터페이스에 노출되지 않도록 배치해야 한다. 물리적 분리(Physical Segregation), 커버, 배리어(Barrier), 라벨 및 통제된 정비 접근을 통해 전기 아키텍처를 지원해야 한다. 정비 절차에는 절연(Isolation), 무전압 상태 확인(Verification of De-energization), 필요한 경우 방전 대기 시간 및 고전압 구성품의 재연결 조건을 정의해야 한다.

커넥터 하우징, 케이블 및 관련 고전압 구성품에는 제품 아키텍처와 적용되는 규정 또는 표준에서 요구하는 경우 일관된 식별 체계(Identification)를 적용해야 한다. 이러한 식별 표시는 조립 및 정비 과정에서도 확인할 수 있어야 한다. 필요한 경우 라벨을 통해 관련 위험 또는 회로 정보를 표시해야 하지만, 이러한 표시는 물리적 보호, 극성 구조, 인터록 및 안전한 시스템 설계를 대체해서는 안 된다.

출시되는 각 고전압 커넥터 구성은 엔지니어링 도면(Engineering Drawing)과 자재명세서(BOM)를 통해 통제해야 한다. 기록에는 정확한 하우징, 접점, 실, 백셸, 차폐 구성품, HVIL 구성품, 캐비티 플러그, 상대 커넥터(Mating Connector), 케이블 적용 범위 및 필요한 경우 승인된 툴링(Tooling)을 명시해야 한다. 외형상 호환되는 것으로 보이는 구성품이라도 엔지니어링 검토 및 검증 없이 대체해서는 안 된다.

고전압 접점의 압착(Crimping) 및 종단(Termination) 공정에는 승인된 툴링과 통제된 공정 파라미터(Process Parameter)를 사용해야 한다. 도체 준비, 피복 제거 길이(Strip Length), 차폐 준비, 압착 형상(Crimp Geometry), 인장력(Pull Force), 실 설치 및 육안 검사 기준을 정의해야 한다. 커넥터 하우징 자체가 요구 전압 및 전류 정격을 만족하더라도 불량한 종단은 국부적인 저항 증가와 열폭주(Thermal Runaway)를 발생시킬 수 있다.

고전압 커넥터 검증(HV Connector Qualification)은 대상 제품에 관련된 조건에 따라 내전압(Electrical Withstand), 절연 저항(Insulation Resistance), 접촉 저항, 온도 상승, 진동, 기계적 충격, 체결 내구성(Mating Durability), 환경 밀봉, 부식 및 열 사이클링(Thermal Cycling)을 포함해야 한다. HVIL 동작, 접촉 안전 보호, 키잉 및 제어된 분리와 같은 안전 관련 기능이 적용된 경우 이러한 기능도 함께 검증해야 한다.

커넥터 제품군, 접점 재료, 단자 크기, 케이블 단면적, 실, 백셸, 공급업체, 제조 공정, 장착 위치 또는 운용 환경이 변경되는 경우 출시된 고전압 인터페이스에 미치는 영향을 평가해야 한다. 전기적, 열적, 기계적, 환경적, EMC 또는 안전 성능에 영향을 줄 수 있는 변경은 실제 적용 전에 문서화된 엔지니어링 검토(Documented Engineering Review)를 거쳐야 한다.

고전압 커넥터 규칙(HV Connector Rules)은 궁극적으로 전력 아키텍처(Power Architecture), 하네스 설계(Harness Design), 보호(Protection), 접지(Grounding), EMC, 안전(Safety), 제조(Manufacturing) 및 정비(Service) 사이의 통합된 인터페이스를 확립한다. 따라서 규정을 준수하는 고전압 연결은 단순히 커넥터의 전압 및 전류 정격만으로 정의되지 않는다. 전기 절연, 열적 용량, 접촉 안전 보호, 인터록, 기계적 유지력, 환경 밀봉 및 수명주기 관리(Lifecycle Control)가 함께 작동하는 검증된 시스템(Qualified System)으로 정의되어야 한다.

##  

## 03.04. Connector Drawing Standard

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

Connector drawings shall provide a controlled engineering definition of every electrical interface used within the robotics platform. The drawing shall communicate not only connector identity but also orientation, cavity numbering, circuit allocation, mating information, terminals, seals, wire requirements, and applicable assembly constraints. It shall serve as a common reference for electrical design, harness manufacturing, inspection, integration, and service.

Each connector used in a released design shall have a unique connector reference identifier consistent with the project electrical architecture and harness documentation. The identifier shall remain stable throughout the product lifecycle unless formal configuration control requires reassignment. The same identifier shall be used consistently in schematics, harness drawings, wiring tables, BOM records, diagnostic documentation, and service information.

The drawing shall identify the connector manufacturer, connector family or series, exact housing part number, gender where applicable, number of cavities, keying or polarization option, and mating connector. Generic descriptions such as "8-pin connector" are insufficient for released documentation. Manufacturer part numbers shall correspond to the exact approved configuration rather than to a visually similar connector within the same family.

Connector views shall clearly state the viewing direction used for cavity numbering. The drawing shall distinguish mating-face view, wire-side view, and any other orientation that could affect interpretation. Ambiguous cavity diagrams are prohibited because mirrored interpretation can reverse pin assignments during manufacturing or service. Orientation marks, locking features, keys, and reference geometry should be shown where necessary.

Cavity numbering shall follow the connector manufacturer's defined numbering whenever such numbering exists. Engineering documentation shall not create an alternative numbering system merely for drawing convenience. If manufacturer markings are difficult to observe after installation, the drawing may provide additional graphical references, but the official cavity identification shall remain traceable to the connector supplier documentation.

Every populated cavity shall identify the associated circuit or signal. The pin table should include cavity number, circuit name, signal name where applicable, wire identification, conductor size, and relevant electrical function. Power, ground, communication, safety, sensor, actuator, shield, interlock, and reserved circuits shall be distinguishable so that the connector definition can be understood without relying on undocumented engineering knowledge.

Unused cavities shall be explicitly identified rather than left ambiguous. The drawing shall distinguish unused cavities that remain open, cavities requiring sealing plugs, reserved cavities intended for future expansion, and positions intentionally blocked by connector configuration. For sealed connector systems, the required cavity plug or sealing component shall be specified whenever an unused position must remain environmentally protected.

Wire information associated with each cavity shall use the controlled harness design conventions. Conductor cross-section or approved gauge, wire identification, insulation requirements where relevant, and color coding shall be consistent with the harness drawing and BOM. Where twisted pairs, shielded cables, coaxial cables, or other special cable constructions are required, the connector drawing shall identify the relationship between those conductors and their assigned contacts.

Terminal information shall be controlled at the same level as the connector housing. Each contact position or applicable wire range shall reference the approved terminal part number and, where necessary, the associated wire seal. A housing shall not be considered fully defined without its compatible terminals and sealing components. Alternative terminals may be listed only when their approved application range and qualification status are clearly documented.

For sealed connectors, the drawing shall define all components required to achieve the specified ingress protection. This may include individual wire seals, interface seals, rear seals, cavity plugs, backshells, grommets, cable glands, and protective caps. The required IP rating shall be referenced when it is a controlled characteristic, together with any configuration restrictions necessary to preserve the qualified sealing performance.

High-voltage connector drawings shall include additional information required by the HV connector rules. Voltage class, polarity, high-voltage interlock loop assignments, shielding provisions, touch-safe features, keying, and relevant service constraints shall be documented where applicable. Main power contacts and HVIL or pilot contacts shall be clearly differentiated so that manufacturing and service personnel cannot confuse their functions.

Communication connector drawings shall preserve physical-layer requirements of the associated network. CAN, CAN FD, RS-485, Ethernet, EtherCAT, camera, and other high-speed interfaces may require defined twisted-pair assignments, pair polarity, shield termination, or controlled cable construction. Pin tables shall make these relationships explicit and shall avoid arbitrary reassignment that could degrade signal integrity or network interoperability.

Shield termination shall be represented separately from ordinary signal ground when the architecture requires chassis or connector-shell termination. The drawing shall identify whether the cable shield connects through a dedicated contact, connector shell, backshell, drain wire, or another defined method. Shielding instructions shall remain consistent with the grounding and EMC standards so that harness manufacturing does not unintentionally alter the intended EMC architecture.

Safety-related circuits shall be clearly identifiable within connector documentation. Emergency-stop, brake, safety sensor, interlock, redundant control, and other safety functions should include sufficient identification to prevent accidental reassignment or substitution. Where redundant channels pass through the same connector, channel allocation and separation shall be shown clearly and coordinated with the applicable safety architecture requirements.

Connector drawings shall indicate the mating relationship between harness-side and equipment-side interfaces. Both connector identifiers and exact mating part numbers should be traceable where the mating half is controlled by Hills Robotics. For purchased sensors, actuators, controllers, or other equipment with supplier-defined connectors, the drawing shall reference the equipment interface and supplier documentation necessary to establish compatibility.

Mechanical orientation shall be documented when connector rotation or mounting direction affects harness routing, accessibility, drainage, sealing, or mating. Right-angle backshell orientation, cable exit direction, panel mounting position, and key location should be shown when relevant. A connector drawing shall not imply that mechanically different orientations are interchangeable when packaging or environmental performance depends on their installed direction.

Connector location information should provide sufficient context to associate the interface with the corresponding robot module or harness branch. The drawing may reference a zone, module, subsystem, or harness segment rather than reproducing complete vehicle packaging. Location terminology shall remain consistent with the electrical architecture so that design, manufacturing, and service teams refer to the same physical interface using the same designation.

Service connectors and diagnostic interfaces shall be identified according to their intended accessibility and usage. The documentation should indicate when a connector is intended for production test, calibration, diagnostics, software update, maintenance, or emergency service. Interfaces that shall not be disconnected during normal service should include an appropriate restriction or reference to the applicable service procedure.

The connector drawing shall reference required strain-relief and backshell arrangements where these components affect interface reliability. Cable clamps, boots, grommets, backshells, or other support components shall be identified when necessary to prevent cable loads from reaching terminals or seals. Minimum bend-radius or cable-exit constraints should be stated when violation could damage the connector, cable, or environmental sealing.

Crimp and termination requirements shall be traceable from the connector documentation to the applicable manufacturing specification. Approved tooling, applicators, strip dimensions, crimp parameters, pull-force requirements, or inspection criteria need not all be reproduced on every drawing when controlled elsewhere, but the drawing shall provide sufficient references to ensure that the correct manufacturing standard can be unambiguously identified.

Connector tables shall use standardized terminology, units, abbreviations, and field order across robotics projects wherever practical. Consistent drawing structure reduces interpretation errors and allows engineers, technicians, suppliers, and automated engineering tools to process connector information more reliably. Project-specific additions may be introduced when necessary, but they shall not redefine established fields without configuration approval.

The engineering BOM shall remain synchronized with the connector drawing. Housing, terminal, seal, plug, backshell, protective cap, and other controlled connector components shown on the drawing shall correspond to released BOM items. Components shall not exist only in graphical notes or informal assembly instructions when they are required for production, sealing, electrical performance, safety, or serviceability.

Drawing revision status shall be controlled through the engineering change process. Any modification to pin assignment, connector family, terminal, wire size, sealing component, keying, mating interface, or safety-related function shall be evaluated for downstream impact. Changes shall be coordinated with schematics, harness drawings, BOMs, software interface definitions, manufacturing instructions, test procedures, and service documentation where affected.

Pin-assignment changes require particular care because physical compatibility can conceal electrical incompatibility. A connector housing may remain unchanged while a revised pinout creates risk to existing harnesses, modules, test equipment, or field-service parts. When backward compatibility cannot be maintained, the drawing and change record shall clearly identify the incompatibility and define appropriate keying, revision, or replacement controls.

Released connector drawings shall be sufficiently complete for independent verification by manufacturing and quality personnel. Inspectors should be able to confirm connector identity, cavity population, terminal selection, seals, plugs, wire assignments, orientation, and mating configuration without relying on verbal instructions. Any information necessary to determine whether the interface has been assembled correctly shall be controlled and traceable.

Digital connector data used by electrical CAD, harness design, PLM, or manufacturing systems shall remain consistent with the released engineering drawing. Library symbols, cavity definitions, manufacturer part numbers, terminal mappings, and mating relationships should be managed as controlled engineering data. Automated data exchange shall reduce duplicate entry but shall not bypass engineering review or configuration management.

The connector drawing standard ultimately creates a single authoritative definition of each physical electrical interface. By integrating connector identity, cavity allocation, wiring, terminals, sealing, mating, orientation, manufacturing references, and revision control, the drawing connects electrical architecture with production reality. Consistent documentation reduces wiring errors, improves traceability, supports serviceability, and enables reliable reuse across robotics platforms.

커넥터 도면(Connector Drawing)은 로봇 플랫폼 내에서 사용되는 모든 전기 인터페이스(Electrical Interface)에 대해 통제된 엔지니어링 정의를 제공해야 한다. 도면에는 커넥터 식별 정보뿐만 아니라 방향, 캐비티 번호(Cavity Numbering), 회로 할당, 상대 체결 정보(Mating Information), 단자(Terminal), 실(Seal), 전선 요구사항 및 적용 가능한 조립 제약조건을 포함해야 한다. 또한 전기 설계, 하네스 제조, 검사, 시스템 통합 및 정비에서 공통 기준으로 사용되어야 한다.

출시 설계(Released Design)에 사용되는 각 커넥터에는 프로젝트의 전기 아키텍처(Electrical Architecture) 및 하네스 문서와 일관된 고유 커넥터 참조 식별자(Connector Reference Identifier)를 부여해야 한다. 해당 식별자는 공식적인 형상관리(Configuration Control)에 따라 재지정해야 하는 경우를 제외하고 제품 수명주기 전체에서 유지되어야 한다. 동일한 식별자는 회로도, 하네스 도면, 배선표, 자재명세서(BOM), 진단 문서 및 정비 정보에서 일관되게 사용해야 한다.

도면에는 커넥터 제조사, 커넥터 제품군 또는 시리즈, 정확한 하우징 부품번호(Housing Part Number), 해당되는 경우 성별(Gender), 캐비티 수, 키잉(Keying) 또는 극성 구조(Polarization) 옵션 및 상대 커넥터(Mating Connector)를 명시해야 한다. "8핀 커넥터"와 같은 일반적인 설명은 출시 문서로 충분하지 않다. 제조사 부품번호는 동일 제품군에서 외형이 유사한 커넥터가 아니라 정확하게 승인된 구성을 나타내야 한다.

커넥터 뷰(Connector View)에는 캐비티 번호를 해석하기 위한 관찰 방향(Viewing Direction)을 명확하게 표시해야 한다. 도면은 체결면 뷰(Mating-face View), 전선측 뷰(Wire-side View) 및 해석에 영향을 줄 수 있는 기타 방향을 명확하게 구분해야 한다. 모호한 캐비티 도면은 제조 또는 정비 과정에서 좌우가 반전되어 핀 할당이 뒤바뀔 수 있으므로 허용하지 않는다. 필요한 경우 방향 표시, 잠금 구조, 키(Key) 및 기준 형상(Reference Geometry)을 표시해야 한다.

캐비티 번호는 제조사가 정의한 번호 체계가 존재하는 경우 해당 체계를 따라야 한다. 엔지니어링 문서는 단순히 도면 작성의 편의를 위해 별도의 번호 체계를 만들어서는 안 된다. 설치 후 제조사 표시를 확인하기 어려운 경우 도면에 추가적인 그래픽 기준을 제공할 수 있지만, 공식 캐비티 식별 정보는 커넥터 공급업체 문서까지 추적 가능해야 한다.

사용되는 모든 캐비티에는 연결되는 회로 또는 신호를 식별해야 한다. 핀 테이블(Pin Table)에는 캐비티 번호, 회로명, 해당되는 경우 신호명, 전선 식별 정보, 도체 크기 및 관련 전기 기능을 포함하는 것이 바람직하다. 전원, 접지(Ground), 통신, 안전, 센서, 액추에이터, 차폐(Shield), 인터록(Interlock) 및 예약 회로(Reserved Circuit)를 명확하게 구분하여 문서화되지 않은 엔지니어링 지식에 의존하지 않고 커넥터 정의를 이해할 수 있도록 해야 한다.

사용하지 않는 캐비티는 모호하게 비워두지 말고 명시적으로 식별해야 한다. 도면에서는 개방 상태로 유지되는 미사용 캐비티, 밀봉 플러그(Sealing Plug)가 필요한 캐비티, 향후 확장을 위해 예약된 캐비티 및 커넥터 구성에 의해 의도적으로 차단된 위치를 구분해야 한다. 밀봉형 커넥터 시스템(Sealed Connector System)의 경우 미사용 위치에서도 환경 보호 성능을 유지해야 한다면 필요한 캐비티 플러그(Cavity Plug) 또는 밀봉 부품을 지정해야 한다.

각 캐비티에 연결되는 전선 정보는 통제된 하네스 설계 규칙(Harness Design Convention)을 따라야 한다. 도체 단면적 또는 승인된 전선 규격(Gauge), 전선 식별 정보, 필요한 경우 절연 요구사항 및 색상 코딩(Color Coding)은 하네스 도면과 자재명세서와 일치해야 한다. 트위스트 페어(Twisted Pair), 차폐 케이블(Shielded Cable), 동축 케이블(Coaxial Cable) 또는 기타 특수 케이블 구조가 필요한 경우 커넥터 도면에서 해당 도체와 할당된 접점 사이의 관계를 식별해야 한다.

단자 정보(Terminal Information)는 커넥터 하우징과 동일한 수준으로 통제해야 한다. 각 접점 위치 또는 적용 가능한 전선 범위에는 승인된 단자 부품번호를 참조해야 하며, 필요한 경우 관련 전선 실(Wire Seal)도 함께 명시해야 한다. 호환되는 단자와 밀봉 부품이 정의되지 않은 하우징은 완전하게 정의된 것으로 간주해서는 안 된다. 대체 단자는 승인된 적용 범위와 검증 상태(Qualification Status)가 명확하게 문서화된 경우에만 목록에 포함할 수 있다.

밀봉형 커넥터의 경우 도면에는 지정된 침투 보호(Ingress Protection)를 달성하기 위해 필요한 모든 구성품을 정의해야 한다. 여기에는 개별 전선 실, 인터페이스 실(Interface Seal), 후면 실(Rear Seal), 캐비티 플러그, 백셸(Backshell), 그로밋(Grommet), 케이블 글랜드(Cable Gland) 및 보호 캡(Protective Cap)이 포함될 수 있다. IP 등급(IP Rating)이 통제되는 특성인 경우 요구 IP 등급과 검증된 밀봉 성능을 유지하기 위해 필요한 구성 제한조건을 함께 참조해야 한다.

고전압 커넥터(HV Connector) 도면에는 고전압 커넥터 규칙(HV Connector Rules)에서 요구하는 추가 정보를 포함해야 한다. 해당되는 경우 전압 등급(Voltage Class), 극성, 고전압 인터록 루프(High-voltage Interlock Loop, HVIL) 할당, 차폐 구조, 접촉 안전 기능(Touch-safe Feature), 키잉 및 관련 정비 제약조건을 문서화해야 한다. 주 전력 접점(Main Power Contact)과 HVIL 또는 파일럿 접점(Pilot Contact)은 제조 및 정비 작업자가 기능을 혼동하지 않도록 명확하게 구분해야 한다.

통신 커넥터(Communication Connector) 도면은 해당 네트워크의 물리 계층(Physical Layer) 요구사항을 유지해야 한다. CAN, CAN FD, RS-485, 이더넷(Ethernet), EtherCAT, 카메라 및 기타 고속 인터페이스에는 정의된 트위스트 페어 할당, 페어 극성(Pair Polarity), 차폐 종단(Shield Termination) 또는 통제된 케이블 구조가 필요할 수 있다. 핀 테이블에서는 이러한 관계를 명확하게 표현하고 신호 무결성(Signal Integrity) 또는 네트워크 상호운용성(Network Interoperability)을 저하시킬 수 있는 임의의 핀 재할당을 피해야 한다.

아키텍처에서 섀시(Chassis) 또는 커넥터 셸(Connector Shell) 종단이 요구되는 경우 차폐 종단은 일반적인 신호 접지(Signal Ground)와 별도로 표시해야 한다. 도면에는 케이블 차폐가 전용 접점, 커넥터 셸, 백셸, 드레인 와이어(Drain Wire) 또는 기타 정의된 방법 중 어떤 방식으로 연결되는지 식별해야 한다. 하네스 제조 과정에서 의도된 EMC 아키텍처가 임의로 변경되지 않도록 차폐 지침은 접지 및 EMC 표준과 일관성을 유지해야 한다.

안전 관련 회로(Safety-related Circuit)는 커넥터 문서에서 명확하게 식별할 수 있어야 한다. 비상정지(Emergency Stop), 브레이크, 안전 센서(Safety Sensor), 인터록, 이중화 제어(Redundant Control) 및 기타 안전 기능에는 우발적인 재할당이나 대체를 방지할 수 있는 충분한 식별 정보를 포함하는 것이 바람직하다. 이중화 채널(Redundant Channel)이 동일한 커넥터를 통과하는 경우 채널 할당 및 분리를 명확하게 표시하고 적용되는 안전 아키텍처 요구사항과 연계해야 한다.

커넥터 도면에는 하네스측(Harness-side) 인터페이스와 장비측(Equipment-side) 인터페이스 사이의 상대 체결 관계를 표시해야 한다. 상대 체결부가 힐스로보틱스(Hills Robotics)의 관리 대상인 경우 양쪽 커넥터 식별자와 정확한 상대 부품번호를 추적할 수 있어야 한다. 공급업체가 정의한 커넥터를 사용하는 구매 센서, 액추에이터, 제어기 또는 기타 장비의 경우 호환성을 확립하는 데 필요한 장비 인터페이스와 공급업체 문서를 참조해야 한다.

커넥터 회전 또는 장착 방향이 하네스 라우팅(Harness Routing), 접근성, 배수, 밀봉 또는 체결에 영향을 미치는 경우 기계적 방향(Mechanical Orientation)을 문서화해야 한다. 필요한 경우 직각 백셸(Right-angle Backshell)의 방향, 케이블 인출 방향(Cable Exit Direction), 패널 장착 위치 및 키 위치를 표시해야 한다. 패키징(Packaging)이나 환경 성능이 설치 방향에 따라 달라지는 경우 기계적으로 서로 다른 방향을 상호 교환 가능한 것으로 표현해서는 안 된다.

커넥터 위치 정보는 해당 인터페이스를 관련 로봇 모듈 또는 하네스 분기(Harness Branch)와 연계할 수 있을 정도의 충분한 맥락을 제공해야 한다. 도면은 전체 차량 패키징을 다시 표현하는 대신 구역(Zone), 모듈, 서브시스템(Subsystem) 또는 하네스 구간을 참조할 수 있다. 설계, 제조 및 정비 조직이 동일한 물리적 인터페이스를 동일한 명칭으로 지칭할 수 있도록 위치 관련 용어는 전기 아키텍처와 일관성을 유지해야 한다.

정비용 커넥터(Service Connector) 및 진단 인터페이스(Diagnostic Interface)는 의도된 접근성과 사용 목적에 따라 식별해야 한다. 문서에는 커넥터가 생산 시험(Production Test), 캘리브레이션(Calibration), 진단, 소프트웨어 업데이트, 유지보수 또는 비상 정비를 위한 것인지 표시하는 것이 바람직하다. 정상적인 정비 중 분리해서는 안 되는 인터페이스에는 적절한 제한사항 또는 관련 정비 절차에 대한 참조를 포함해야 한다.

커넥터 도면에는 인터페이스 신뢰성에 영향을 미치는 경우 필요한 스트레인 릴리프(Strain Relief) 및 백셸 구성을 참조해야 한다. 케이블 하중이 단자나 실에 전달되는 것을 방지하기 위해 필요한 경우 케이블 클램프(Cable Clamp), 부트(Boot), 그로밋, 백셸 또는 기타 지지 부품을 식별해야 한다. 요구사항을 위반할 경우 커넥터, 케이블 또는 환경 밀봉 성능이 손상될 수 있다면 최소 굽힘 반경(Minimum Bend Radius)이나 케이블 인출 제약조건도 명시해야 한다.

압착(Crimp) 및 종단(Termination) 요구사항은 커넥터 문서에서 적용되는 제조 규격까지 추적할 수 있어야 한다. 승인된 툴링(Tooling), 어플리케이터(Applicator), 피복 제거 치수(Strip Dimension), 압착 파라미터(Crimp Parameter), 인장력 요구사항(Pull-force Requirement) 또는 검사 기준을 다른 통제 문서에서 관리하는 경우 모든 도면에 반복하여 기재할 필요는 없다. 그러나 올바른 제조 표준을 명확하게 식별할 수 있도록 충분한 참조 정보를 제공해야 한다.

커넥터 테이블(Connector Table)은 가능한 한 로봇 프로젝트 전반에서 표준화된 용어, 단위, 약어 및 필드 순서를 사용해야 한다. 일관된 도면 구조는 해석 오류를 줄이고 엔지니어, 기술자, 공급업체 및 자동화된 엔지니어링 도구가 커넥터 정보를 더욱 신뢰성 있게 처리하도록 한다. 필요한 경우 프로젝트별 항목을 추가할 수 있지만 형상 승인(Configuration Approval) 없이 기존에 정의된 필드의 의미를 변경해서는 안 된다.

엔지니어링 자재명세서(Engineering BOM)는 커넥터 도면과 항상 동기화되어야 한다. 도면에 표시되는 하우징, 단자, 실, 플러그, 백셸, 보호 캡 및 기타 통제 대상 커넥터 구성품은 출시된 BOM 항목과 일치해야 한다. 생산, 밀봉, 전기적 성능, 안전 또는 정비성에 필요한 구성품을 그래픽 주석이나 비공식 조립 지침에만 존재하도록 관리해서는 안 된다.

도면 개정 상태(Drawing Revision Status)는 엔지니어링 변경 프로세스(Engineering Change Process)를 통해 통제해야 한다. 핀 할당, 커넥터 제품군, 단자, 전선 크기, 밀봉 부품, 키잉, 상대 체결 인터페이스 또는 안전 관련 기능이 변경되는 경우 후속 영향(Downstream Impact)을 평가해야 한다. 영향을 받는 경우 회로도, 하네스 도면, BOM, 소프트웨어 인터페이스 정의, 제조 지침, 시험 절차 및 정비 문서와 변경 내용을 연계해야 한다.

핀 할당 변경(Pin-assignment Change)은 물리적 호환성이 전기적 비호환성을 숨길 수 있으므로 특별한 주의가 필요하다. 커넥터 하우징이 변경되지 않더라도 변경된 핀아웃(Pinout)은 기존 하네스, 모듈, 시험 장비 또는 현장 정비 부품에 위험을 발생시킬 수 있다. 하위 호환성(Backward Compatibility)을 유지할 수 없는 경우 도면과 변경 기록에서 해당 비호환성을 명확하게 식별하고 적절한 키잉, 개정 또는 교체 관리 방법을 정의해야 한다.

출시된 커넥터 도면은 제조 및 품질 담당자가 독립적으로 검증할 수 있을 정도로 충분히 완전해야 한다. 검사자는 구두 지시에 의존하지 않고 커넥터 식별, 캐비티 구성(Cavity Population), 단자 선정, 실, 플러그, 전선 할당, 방향 및 상대 체결 구성을 확인할 수 있어야 한다. 인터페이스가 올바르게 조립되었는지 판단하는 데 필요한 모든 정보는 통제되고 추적 가능해야 한다.

전기 CAD(Electrical CAD), 하네스 설계, 제품 수명주기 관리(Product Lifecycle Management, PLM) 또는 제조 시스템에서 사용하는 디지털 커넥터 데이터(Digital Connector Data)는 출시된 엔지니어링 도면과 일관성을 유지해야 한다. 라이브러리 심볼(Library Symbol), 캐비티 정의, 제조사 부품번호, 단자 매핑(Terminal Mapping) 및 상대 체결 관계는 통제된 엔지니어링 데이터로 관리하는 것이 바람직하다. 자동화된 데이터 교환은 중복 입력을 줄여야 하지만 엔지니어링 검토 또는 형상관리를 우회해서는 안 된다.

커넥터 도면 표준(Connector Drawing Standard)은 궁극적으로 각각의 물리적 전기 인터페이스에 대한 단일 권위 정의(Single Authoritative Definition)를 구축한다. 커넥터 식별, 캐비티 할당, 배선, 단자, 밀봉, 상대 체결, 방향, 제조 참조 및 개정 관리를 통합함으로써 도면은 전기 아키텍처와 실제 생산을 연결한다. 일관된 문서화는 배선 오류를 줄이고 추적성(Traceability)을 향상시키며 정비성을 지원하고 다양한 로봇 플랫폼에서 신뢰성 있는 재사용을 가능하게 한다.

##  

## 03.05. Qualification Requirement

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

Connector qualification shall demonstrate that each released connector system can maintain its required electrical, mechanical, environmental, and safety performance throughout the intended product lifecycle. Qualification applies to the complete interface configuration rather than only to the connector housing. Contacts, seals, wires, backshells, cavity plugs, mating components, assembly processes, and installation conditions shall be included where they influence performance.

The qualification level shall be derived from the connector application and its associated risk. Internal signal connectors inside protected electronics, external sensor interfaces, actuator power connectors, safety circuits, battery connections, and high-voltage interfaces do not require identical test severity. Engineering shall define qualification conditions from actual voltage, current, environment, vibration, motion, service frequency, and consequence of failure.

Qualification evidence may include supplier test reports, recognized component certifications, previous internal qualification, application-specific testing, or a combination of these sources. Supplier data shall be reviewed for applicability to the released configuration. A connector shall not be considered qualified merely because its family has passed tests using different contacts, wire sizes, seals, cable construction, environmental conditions, or mating arrangements.

Electrical qualification shall verify that the connector supports the required operating voltage and current with adequate margin. Contact resistance, insulation resistance, dielectric withstand capability, voltage drop, leakage, and temperature rise shall be evaluated as applicable. Measurements should be performed before and after environmental or mechanical durability testing when degradation of contacts or insulation could affect long-term electrical performance.

Contact resistance shall remain sufficiently low and stable to prevent excessive voltage drop and localized heating. Qualification should evaluate initial resistance as well as resistance change after vibration, thermal cycling, mating durability, corrosion exposure, or other relevant stresses. High-current connectors require particular attention because small increases in contact resistance can generate substantial heat and accelerate further interface degradation.

Temperature-rise testing shall represent realistic electrical loading and thermal installation conditions. Current, conductor size, simultaneously energized contacts, ambient temperature, enclosure conditions, and duty cycle should correspond to the intended application or an appropriately conservative test condition. Acceptance criteria shall ensure that contact, terminal, insulation, seal, and housing temperatures remain within their allowable limits.

Insulation resistance and dielectric withstand testing shall confirm adequate electrical isolation between adjacent contacts and between energized conductors and accessible conductive structures. Test voltage and acceptance limits shall reflect the application voltage and insulation requirements. High-voltage interfaces require additional consideration of creepage, clearance, pollution, condensation, contamination, and transient voltage conditions.

Mechanical qualification shall verify connector retention, locking integrity, terminal retention, cable strain resistance, and robustness against handling loads. The connector shall remain correctly mated under the expected robot vibration, acceleration, shock, and cable forces. Mechanical testing shall include mounting arrangements representative of production because connector behavior can differ significantly when unsupported or installed differently from the actual product.

Vibration testing shall reflect the location and platform on which the connector is installed. Interfaces near motors, wheels, suspension systems, manipulators, propulsion equipment, or articulated joints may experience substantially different vibration spectra. Testing should verify electrical continuity during vibration where intermittent contact is critical and should inspect locking mechanisms, terminals, seals, housings, and cable supports afterward.

Mechanical shock testing shall be applied where impacts, drops, abrupt vehicle motion, manipulator collisions, landing loads, or transportation events are credible. Qualification shall confirm that the connector does not crack, unlock, deform, lose terminal retention, or create intermittent electrical connections. Safety-related and high-power interfaces require particular attention when mechanical damage could produce hazardous system behavior.

Mating durability shall be evaluated according to the expected number of connection cycles during manufacturing, testing, maintenance, battery replacement, tool changing, or normal operation. Qualification shall verify contact resistance, retention force, locking function, polarization, seal condition, and physical damage after the required cycle count. Frequently serviced interfaces may require substantially higher mating durability than permanent internal connections.

Insertion and withdrawal forces shall remain compatible with intended assembly and service procedures. Excessive mating force can lead to incomplete engagement, damaged terminals, or unsafe service practices, while insufficient retention can allow unintended separation. Qualification should evaluate force characteristics over the expected tolerance range and after durability testing when wear can change mechanical behavior.

Terminal retention and crimp integrity shall be verified as part of connector qualification. Approved wire sizes, conductor constructions, terminals, seals, and tooling shall be used for representative samples. Pull-force testing, crimp dimensional inspection, conductor and insulation crimp evaluation, and visual examination should confirm that the termination process provides repeatable mechanical and electrical performance.

Environmental qualification shall reproduce the conditions relevant to the installation. Temperature extremes, thermal cycling, humidity, condensation, dust, water, salt, chemicals, ultraviolet exposure, and corrosion shall be considered according to the product environment. Not every connector requires every test; however, exclusion of an environmental test shall be justified by the actual installation and protection provided by the surrounding system.

Thermal cycling shall evaluate differential expansion and contraction among contacts, housings, seals, cables, and mounting structures. Repeated temperature changes can alter contact pressure, damage seals, loosen components, or draw moisture into the connector. Electrical continuity, contact resistance, insulation condition, locking integrity, and sealing performance should be reassessed after cycling when these characteristics are relevant.

Ingress protection qualification shall verify the required IP rating using the production-representative connector configuration. Housing, seals, wire diameters, cavity plugs, backshells, cable glands, protective caps, and mating state shall match the intended application. A previously tested housing does not establish IP compliance when the released assembly uses different sealing components or cable dimensions outside the qualified range.

Chemical compatibility shall be evaluated where connectors can contact lubricants, hydraulic fluids, cleaning agents, fuels, battery materials, salt, or other process substances. Qualification should examine swelling, cracking, softening, corrosion, seal degradation, marking loss, and electrical deterioration. Material compatibility requirements shall be based on credible exposure rather than assumed from the connector's IP classification.

Corrosion resistance shall be considered for outdoor robots, UAVs, agricultural equipment, coastal operation, wet industrial environments, and other applications where moisture or contaminants can attack conductive surfaces. Testing shall verify that contacts, terminals, shielding components, locking hardware, and exposed metallic structures maintain acceptable electrical and mechanical performance after the defined exposure.

EMC-related connector qualification shall address shield continuity and termination performance where connectors form part of the electromagnetic compatibility architecture. Shielded motor, inverter, Ethernet, camera, sensor, and high-voltage interfaces may require low-impedance shell or backshell connections. Qualification shall verify that assembly tolerances and environmental aging do not compromise the intended shielding path.

Communication connectors shall be evaluated against the physical-layer requirements of the intended network. CAN, CAN FD, RS-485, Ethernet, EtherCAT, camera, and other high-speed links may require verification of continuity, pair integrity, impedance behavior, shielding, and error-free communication. Mechanical compatibility alone does not establish suitability for a communication interface operating at the required data rate.

Safety-related connector qualification shall consider failure modes that could defeat the associated safety function. Keying, polarization, locking, terminal retention, redundant channel allocation, interlock behavior, and resistance to incorrect assembly should be evaluated where relevant. Qualification evidence shall demonstrate that foreseeable connector faults are adequately prevented, detected, tolerated, or controlled by the system architecture.

High-voltage connector qualification shall additionally verify touch protection, insulation coordination, HVIL operation where used, controlled mating or disconnection behavior, temperature rise, sealing, shielding, and resistance to incorrect mating. Tests shall be coordinated with the HV connector rules and actual power architecture. Qualification of the connector shall not replace validation of contactors, precharge, discharge, or system-level HV safety functions.

Qualification samples shall represent production-intent components and manufacturing processes. Prototype connectors assembled with laboratory tools, non-production seals, substitute wires, or manually modified housings may be useful for development but shall not automatically establish production qualification. Deviations between test samples and released production configuration shall be documented and assessed before approval.

The qualification plan shall define test samples, configurations, sequence, environmental conditions, electrical loads, measurement methods, acceptance criteria, and required inspections before testing begins. Test sequencing should consider cumulative degradation when appropriate. For example, environmental and mechanical stresses may be followed by electrical measurements so that qualification demonstrates retained performance rather than only initial capability.

Failures observed during qualification shall be documented and investigated rather than removed from the data set without justification. The failure analysis should identify whether the cause is connector design, terminal selection, sealing, cable preparation, crimping, tooling, assembly, mounting, or test configuration. Corrective actions shall be verified before the connector configuration is released as qualified.

Qualification results shall be traceable to the exact connector configuration. Records should identify manufacturer part numbers, terminals, seals, wires, cable sizes, backshells, mating components, tooling, sample quantities, test conditions, results, deviations, and approval status. This traceability allows engineering to determine whether qualification remains valid when a component or application changes later in the product lifecycle.

A qualified connector shall not be assumed suitable for every robotics platform. Reuse is permitted when the new application remains within the validated electrical, mechanical, environmental, and service envelope. Moving a connector from a protected indoor AMR compartment to an outdoor chassis, high-vibration joint, high-current circuit, or UAV propulsion interface may require supplemental qualification even if the connector part number remains unchanged.

Changes to connector housing, terminal material, plating, wire size, seal, backshell, cable supplier, crimp tooling, manufacturing process, mounting orientation, environmental exposure, electrical loading, or mating frequency shall trigger qualification review. Engineering shall determine whether existing evidence remains applicable, supplemental testing is sufficient, or complete requalification is required before implementing the change.

The qualification requirement ultimately provides objective evidence that the approved connector list represents proven engineering interfaces rather than purchasing preferences. By combining electrical, mechanical, environmental, EMC, communication, safety, manufacturing, and lifecycle verification, connector qualification establishes confidence that released interfaces will remain reliable and serviceable across the intended robotics application.

커넥터 검증(Connector Qualification)은 출시되는 각 커넥터 시스템이 의도된 제품 수명주기(Product Lifecycle) 전체에서 요구되는 전기적, 기계적, 환경적 및 안전 성능을 유지할 수 있음을 입증해야 한다. 검증은 커넥터 하우징(Connector Housing)만이 아니라 완전한 인터페이스 구성(Interface Configuration)을 대상으로 한다. 성능에 영향을 미치는 경우 접점(Contact), 실(Seal), 전선, 백셸(Backshell), 캐비티 플러그(Cavity Plug), 상대 체결 부품(Mating Component), 조립 공정 및 설치 조건을 검증 범위에 포함해야 한다.

검증 수준(Qualification Level)은 커넥터의 적용 분야와 관련 위험을 기준으로 결정해야 한다. 보호된 전자장치 내부의 신호 커넥터, 외부 센서 인터페이스, 액추에이터 전원 커넥터, 안전 회로, 배터리 연결 및 고전압 인터페이스(High-voltage Interface)에 동일한 시험 강도를 적용할 필요는 없다. 엔지니어링에서는 실제 전압, 전류, 환경, 진동, 움직임, 정비 빈도 및 고장 결과를 기준으로 검증 조건을 정의해야 한다.

검증 근거(Qualification Evidence)에는 공급업체 시험 보고서, 공인된 부품 인증(Component Certification), 기존 내부 검증 결과, 애플리케이션별 시험(Application-specific Testing) 또는 이러한 자료의 조합을 사용할 수 있다. 공급업체 데이터는 출시되는 구성에 적용 가능한지 검토해야 한다. 서로 다른 접점, 전선 크기, 실, 케이블 구조, 환경 조건 또는 체결 구성을 사용한 시험을 통과했다는 이유만으로 동일 제품군의 커넥터가 검증되었다고 판단해서는 안 된다.

전기적 검증(Electrical Qualification)은 커넥터가 충분한 여유도를 가지고 요구되는 동작 전압 및 전류를 지원하는지 확인해야 한다. 적용되는 경우 접촉 저항(Contact Resistance), 절연 저항(Insulation Resistance), 내전압 성능(Dielectric Withstand Capability), 전압 강하, 누설 및 온도 상승을 평가해야 한다. 접점 또는 절연의 열화가 장기적인 전기 성능에 영향을 미칠 수 있는 경우 환경 또는 기계적 내구 시험 전후에 측정을 수행하는 것이 바람직하다.

접촉 저항은 과도한 전압 강하와 국부적인 발열을 방지할 수 있을 정도로 충분히 낮고 안정적으로 유지되어야 한다. 검증에서는 초기 저항뿐만 아니라 진동, 열 사이클링(Thermal Cycling), 체결 내구성(Mating Durability), 부식 노출 또는 기타 관련 스트레스 이후의 저항 변화도 평가해야 한다. 고전류 커넥터(High-current Connector)는 작은 접촉 저항 증가도 상당한 열을 발생시키고 인터페이스 열화를 가속할 수 있으므로 특별한 주의가 필요하다.

온도 상승 시험(Temperature-rise Testing)은 현실적인 전기 부하와 열적 설치 조건을 반영해야 한다. 전류, 도체 크기, 동시에 통전되는 접점 수, 주변 온도, 인클로저(Enclosure) 조건 및 듀티 사이클(Duty Cycle)은 실제 적용 조건 또는 적절하게 보수적으로 설정된 시험 조건과 일치해야 한다. 합격 기준(Acceptance Criteria)은 접점, 단자, 절연재, 실 및 하우징의 온도가 각각의 허용 한계 내에 유지되도록 설정해야 한다.

절연 저항 및 내전압 시험(Dielectric Withstand Testing)은 인접한 접점 사이와 통전 도체 및 접근 가능한 도전성 구조 사이에 충분한 전기적 절연이 확보되는지 확인해야 한다. 시험 전압과 합격 한계는 적용 전압 및 절연 요구사항을 반영해야 한다. 고전압 인터페이스에는 연면거리(Creepage Distance), 공간거리(Clearance Distance), 오염, 결로(Condensation), 오염물질 및 과도 전압 조건을 추가로 고려해야 한다.

기계적 검증(Mechanical Qualification)은 커넥터 유지력, 잠금 무결성(Locking Integrity), 단자 유지력, 케이블 변형 저항 및 취급 하중에 대한 견고성을 확인해야 한다. 커넥터는 예상되는 로봇의 진동, 가속도, 충격 및 케이블 하중에서도 올바른 체결 상태를 유지해야 한다. 커넥터의 거동은 지지되지 않은 상태나 실제 제품과 다른 방식으로 설치된 경우 크게 달라질 수 있으므로 기계적 시험에는 실제 생산을 대표하는 장착 구성을 적용해야 한다.

진동 시험(Vibration Testing)은 커넥터가 설치되는 위치와 플랫폼 특성을 반영해야 한다. 모터, 바퀴, 서스펜션(Suspension), 매니퓰레이터(Manipulator), 추진 장치 또는 관절 부근의 인터페이스는 서로 크게 다른 진동 스펙트럼(Vibration Spectrum)에 노출될 수 있다. 순간적인 접촉 단절이 중요한 경우 진동 중 전기적 연속성(Electrical Continuity)을 확인하고 시험 후에는 잠금 메커니즘, 단자, 실, 하우징 및 케이블 지지 구조를 검사하는 것이 바람직하다.

충격, 낙하, 급격한 차량 움직임, 매니퓰레이터 충돌, 착륙 하중 또는 운송 과정의 충격이 예상 가능한 경우 기계적 충격 시험(Mechanical Shock Testing)을 적용해야 한다. 검증을 통해 커넥터에 균열, 잠금 해제, 변형, 단자 유지력 상실 또는 간헐적인 전기 연결이 발생하지 않는지 확인해야 한다. 기계적 손상이 위험한 시스템 동작으로 이어질 수 있는 안전 관련 및 고전력 인터페이스에는 특별한 주의가 필요하다.

체결 내구성은 제조, 시험, 유지보수, 배터리 교체, 공구 교환 또는 정상 운용 과정에서 예상되는 연결 횟수를 기준으로 평가해야 한다. 검증에서는 요구되는 체결 횟수 이후 접촉 저항, 유지력, 잠금 기능, 극성 구조(Polarization), 실 상태 및 물리적 손상을 확인해야 한다. 빈번하게 정비되는 인터페이스는 영구적으로 설치되는 내부 연결보다 훨씬 높은 체결 내구성을 요구할 수 있다.

삽입력 및 분리력(Insertion and Withdrawal Forces)은 의도된 조립 및 정비 절차에 적합한 수준으로 유지되어야 한다. 지나치게 높은 체결력은 불완전한 체결, 단자 손상 또는 안전하지 않은 정비 작업을 유발할 수 있으며, 지나치게 낮은 유지력은 의도하지 않은 분리를 발생시킬 수 있다. 검증에서는 예상 공차 범위와 마모에 의해 기계적 특성이 변할 수 있는 내구 시험 이후의 힘 특성을 평가하는 것이 바람직하다.

단자 유지력(Terminal Retention)과 압착 무결성(Crimp Integrity)은 커넥터 검증의 일부로 확인해야 한다. 대표 시료에는 승인된 전선 크기, 도체 구조, 단자, 실 및 툴링(Tooling)을 사용해야 한다. 인장력 시험(Pull-force Testing), 압착 치수 검사, 도체 및 절연 압착 평가와 육안 검사를 통해 종단 공정(Termination Process)이 반복 가능한 기계적·전기적 성능을 제공하는지 확인해야 한다.

환경 검증(Environmental Qualification)은 실제 설치 위치와 관련된 환경 조건을 재현해야 한다. 제품 환경에 따라 극한 온도, 열 사이클링, 습도, 결로, 먼지, 물, 염분, 화학물질, 자외선(Ultraviolet Exposure) 및 부식을 고려해야 한다. 모든 커넥터에 모든 시험을 적용할 필요는 없지만 특정 환경 시험을 제외하는 경우 실제 설치 환경과 주변 시스템이 제공하는 보호 수준을 근거로 타당성을 설명해야 한다.

열 사이클링은 접점, 하우징, 실, 케이블 및 장착 구조 사이의 서로 다른 열팽창과 수축의 영향을 평가해야 한다. 반복적인 온도 변화는 접촉 압력을 변화시키거나 실을 손상시키고 구성품을 느슨하게 하거나 커넥터 내부로 습기를 유입시킬 수 있다. 관련되는 경우 사이클링 이후 전기적 연속성, 접촉 저항, 절연 상태, 잠금 무결성 및 밀봉 성능을 다시 평가하는 것이 바람직하다.

침투 보호 검증(Ingress Protection Qualification)은 생산을 대표하는 커넥터 구성을 사용하여 요구되는 IP 등급(IP Rating)을 확인해야 한다. 하우징, 실, 전선 직경, 캐비티 플러그, 백셸, 케이블 글랜드(Cable Gland), 보호 캡(Protective Cap) 및 체결 상태는 실제 적용 구성과 일치해야 한다. 출시 조립품이 서로 다른 밀봉 부품을 사용하거나 검증 범위를 벗어난 케이블 치수를 사용하는 경우 기존 하우징 시험 결과만으로 IP 적합성을 인정해서는 안 된다.

커넥터가 윤활유, 유압유, 세척제, 연료, 배터리 관련 물질, 염분 또는 기타 공정 물질에 접촉할 수 있는 경우 화학적 호환성(Chemical Compatibility)을 평가해야 한다. 검증에서는 팽윤, 균열, 연화, 부식, 실 열화, 표시 손실 및 전기적 성능 저하를 확인하는 것이 바람직하다. 재료 호환성 요구사항은 커넥터의 IP 분류로부터 추정하지 말고 현실적으로 예상 가능한 노출 조건을 기준으로 설정해야 한다.

야외 로봇, UAV, 농업 장비, 해안 지역 운용, 습윤 산업 환경 및 기타 수분이나 오염물질이 도전성 표면을 공격할 수 있는 애플리케이션에서는 내식성(Corrosion Resistance)을 고려해야 한다. 시험을 통해 접점, 단자, 차폐 구성품, 잠금 하드웨어 및 노출된 금속 구조물이 정의된 환경 노출 이후에도 허용 가능한 전기적·기계적 성능을 유지하는지 확인해야 한다.

커넥터가 전자파 적합성(Electromagnetic Compatibility, EMC) 아키텍처의 일부를 구성하는 경우 EMC 관련 검증에서는 차폐 연속성(Shield Continuity) 및 종단 성능(Termination Performance)을 평가해야 한다. 차폐형 모터, 인버터, 이더넷(Ethernet), 카메라, 센서 및 고전압 인터페이스에는 저임피던스 셸 또는 백셸 연결이 필요할 수 있다. 조립 공차 및 환경적 노화가 의도된 차폐 경로를 손상시키지 않는지 확인해야 한다.

통신 커넥터(Communication Connector)는 적용되는 네트워크의 물리 계층(Physical Layer) 요구사항에 따라 평가해야 한다. CAN, CAN FD, RS-485, 이더넷, EtherCAT, 카메라 및 기타 고속 링크에는 연속성, 페어 무결성(Pair Integrity), 임피던스 특성, 차폐 및 오류 없는 통신(Error-free Communication)에 대한 검증이 필요할 수 있다. 기계적으로 호환된다는 사실만으로 요구 데이터 속도로 동작하는 통신 인터페이스에 적합하다고 판단해서는 안 된다.

안전 관련 커넥터(Safety-related Connector)의 검증에서는 관련 안전 기능을 무력화할 수 있는 고장 모드(Failure Mode)를 고려해야 한다. 필요한 경우 키잉(Keying), 극성 구조, 잠금, 단자 유지력, 이중화 채널 할당(Redundant Channel Allocation), 인터록 동작 및 잘못된 조립에 대한 내성을 평가해야 한다. 검증 근거를 통해 예상 가능한 커넥터 고장이 시스템 아키텍처에서 적절하게 방지, 감지, 허용 또는 제어된다는 것을 입증해야 한다.

고전압 커넥터 검증(HV Connector Qualification)은 추가적으로 접촉 안전 보호(Touch Protection), 절연 협조(Insulation Coordination), 적용되는 경우 HVIL 동작, 제어된 체결 또는 분리 동작, 온도 상승, 밀봉, 차폐 및 잘못된 체결에 대한 방지 성능을 확인해야 한다. 시험은 고전압 커넥터 규칙(HV Connector Rules) 및 실제 전력 아키텍처와 연계해야 한다. 커넥터 검증이 접촉기(Contactor), 프리차지(Precharge), 방전 또는 시스템 수준의 고전압 안전 기능 검증을 대체해서는 안 된다.

검증 시료(Qualification Sample)는 양산 의도 부품(Production-intent Component)과 제조 공정을 대표해야 한다. 실험실용 툴, 비양산 실, 대체 전선 또는 수동으로 수정한 하우징을 사용하여 조립한 프로토타입 커넥터는 개발에는 유용할 수 있지만 자동으로 양산 검증을 입증하는 것은 아니다. 시험 시료와 출시되는 양산 구성 사이의 차이는 승인 전에 문서화하고 평가해야 한다.

검증 계획(Qualification Plan)은 시험을 시작하기 전에 시험 시료, 구성, 시험 순서, 환경 조건, 전기 부하, 측정 방법, 합격 기준 및 필요한 검사를 정의해야 한다. 필요한 경우 시험 순서는 누적 열화(Cumulative Degradation)를 고려해야 한다. 예를 들어 환경적·기계적 스트레스를 가한 후 전기적 측정을 수행함으로써 검증이 단순한 초기 성능이 아니라 스트레스 이후에도 유지되는 성능을 입증하도록 할 수 있다.

검증 과정에서 발생한 고장은 정당한 근거 없이 데이터에서 제외하지 말고 문서화하고 조사해야 한다. 고장 분석(Failure Analysis)을 통해 원인이 커넥터 설계, 단자 선정, 밀봉, 케이블 준비, 압착, 툴링, 조립, 장착 또는 시험 구성 중 어디에 있는지 식별하는 것이 바람직하다. 시정조치(Corrective Action)는 해당 커넥터 구성을 검증 완료 상태로 출시하기 전에 확인해야 한다.

검증 결과는 정확한 커넥터 구성까지 추적 가능해야 한다. 기록에는 제조사 부품번호, 단자, 실, 전선, 케이블 크기, 백셸, 상대 체결 부품, 툴링, 시료 수량, 시험 조건, 결과, 예외사항(Deviation) 및 승인 상태를 포함하는 것이 바람직하다. 이러한 추적성(Traceability)을 통해 제품 수명주기 이후에 구성품이나 적용 환경이 변경되었을 때 기존 검증의 유효성을 판단할 수 있다.

검증된 커넥터라고 해서 모든 로봇 플랫폼에 적합하다고 가정해서는 안 된다. 새로운 애플리케이션이 검증된 전기적, 기계적, 환경적 및 정비 범위 내에 있는 경우 재사용할 수 있다. 보호된 실내 AMR 구획에서 사용하던 커넥터를 야외 섀시, 고진동 관절, 고전류 회로 또는 UAV 추진 인터페이스로 이동하는 경우 부품번호가 동일하더라도 추가 검증(Supplemental Qualification)이 필요할 수 있다.

커넥터 하우징, 단자 재료, 도금(Plating), 전선 크기, 실, 백셸, 케이블 공급업체, 압착 툴링, 제조 공정, 장착 방향, 환경 노출, 전기 부하 또는 체결 빈도가 변경되는 경우 검증 검토(Qualification Review)를 수행해야 한다. 엔지니어링에서는 기존 검증 근거를 계속 적용할 수 있는지, 추가 시험만으로 충분한지 또는 변경을 적용하기 전에 완전한 재검증(Requalification)이 필요한지를 결정해야 한다.

검증 요구사항(Qualification Requirement)은 궁극적으로 승인 커넥터 목록(Approved Connector List)이 단순한 구매 선호도가 아니라 검증된 엔지니어링 인터페이스임을 객관적인 근거를 통해 입증한다. 전기적, 기계적, 환경적, EMC, 통신, 안전, 제조 및 수명주기 검증을 통합함으로써 커넥터 검증은 출시된 인터페이스가 의도된 로봇 애플리케이션 전반에서 신뢰성과 정비성을 지속적으로 유지할 수 있다는 확신을 제공한다.
