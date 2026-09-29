**Volume 22. Hills Robotics Engineering Standards**

# Chapter 02. HRS-002 Harness Design

## 02.01. Wire Gauge Selection Table

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

전선 굵기 선정(Wire Gauge Selection)은 로봇 플랫폼(Robotic Platform)에서 전류를 안전하고 신뢰성 있게 전달하기 위해 필요한 최소 도체 크기(Conductor Size)를 결정하는 과정이다. 선정된 도체는 허용 전류(Current-Carrying Capacity), 허용 전압 강하(Allowable Voltage Drop), 열적 한계(Thermal Limits), 기계적 강건성(Mechanical Robustness), 커넥터 호환성(Connector Compatibility), 환경 요구사항(Environmental Requirements)을 동시에 만족해야 한다. 따라서 전선 굵기 선정은 단순히 공칭 부하 전류(Nominal Load Current)에 따른 조회가 아니라 전기 시스템 설계(Electrical-System Design)의 관점에서 수행되어야 한다.

엔지니어링 전선 선정표(Engineering Wire Selection Table)는 승인된 각 도체 크기를 AWG(American Wire Gauge), 미터법 단면적(Metric Cross-Sectional Area)인 mm² 또는 실용적인 경우 두 가지 모두로 표시해야 한다. 각 크기에 대해서는 기준 전류 범위(Reference Current Range), 도체 저항(Conductor Resistance), 적용 가능한 온도 등급(Temperature Rating), 절연재 계열(Insulation Family), 일반적인 적용 등급(Application Class)을 연계하여 정의해야 한다. 이러한 값은 하네스 설계(Harness Design)의 공통 기준점을 제공하며, 최종 설계 승인 전에 프로젝트별 디레이팅(Derating)을 적용할 수 있도록 한다.

공칭 동작 전류(Nominal Operating Current)만을 전선 굵기 선정의 유일한 기준으로 직접 사용해서는 안 된다. 설계자는 연속 전류(Continuous Current), 간헐 전류(Intermittent Current), 피크 전류(Peak Current), 기동 또는 돌입 전류(Startup or Inrush Current), 적용되는 경우 회생 전류(Regenerative Current), 그리고 합리적으로 예상 가능한 비정상 동작 조건(Abnormal Operating Conditions)을 파악해야 한다. 모터, 액추에이터(Actuator), 펌프, 히터, 컴퓨팅 모듈(Compute Module), 센서, 조명 시스템, 보조 부하는 평균 소비전력이 유사하더라도 서로 크게 다른 전류 특성을 나타낼 수 있다.

연속 허용 전류(Continuous-Current Capacity)는 실제 설치 조건에서 도체와 절연재의 열적 허용 능력(Thermal Capability)을 기준으로 평가해야 한다. 자유 공기 중에 개별적으로 배선된 전선은 조밀한 번들(Bundle), 전선관(Conduit), 슬리브(Sleeve), 밀폐형 인클로저(Sealed Enclosure) 내부에 설치된 동일한 전선보다 열을 효과적으로 방출할 수 있다. 따라서 승인된 전선 굵기 표는 기준선(Baseline)으로 사용하며, 배선 조건이 열 전달을 제한하거나 국부 주변 온도를 증가시키는 경우 추가 디레이팅(Additional Derating)을 적용해야 한다.

전압 강하(Voltage Drop)는 허용 전류(Ampacity)와 독립적으로 검토해야 한다. 도체 저항, 회로 길이, 동작 전류, 커넥터 저항(Connector Resistance), 스플라이스 저항(Splice Resistance), 리턴 경로 저항(Return-Path Resistance)이 함께 부하에서 사용할 수 있는 전압을 결정한다. 따라서 긴 하네스 분기(Harness Branch)는 열적 허용 전류가 충분하더라도 더 굵은 도체가 필요할 수 있다. 민감한 전자장치와 고전류 액추에이터는 저전압으로 인해 리셋(Reset), 토크 감소(Torque Reduction), 통신 오류(Communication Fault), 불안정 동작이 발생할 수 있으므로 특별한 주의가 필요하다.

2선식 전원 및 리턴 회로(Two-Conductor Supply and Return Circuit)의 경우 전압 강하 분석에는 전력 분배 장치(Power Distribution Unit)에서 부하까지의 물리적 거리만이 아니라 전체 전기적 루프(Complete Electrical Loop)가 포함되어야 한다. 섀시 또는 구조물 접지(Chassis or Structural Grounding)를 의도적으로 사용하는 경우 해당 리턴 경로의 저항과 건전성(Integrity)도 고려해야 한다. 계산된 최악 조건 부하 전압(Worst-Case Load Voltage)은 예상되는 배터리 및 컨버터 조건에서 연결 장치에 규정된 동작 범위 이내를 유지해야 한다.

온도(Temperature)는 주요 디레이팅 변수(Derating Variable)이다. 모터, 인버터(Inverter), DC/DC 컨버터(DC/DC Converter), 배터리, 제동 부품, 전력 저항(Power Resistor), 밀폐된 컴퓨팅 구획(Compute Compartment) 주변의 하네스 구간은 일반적인 로봇 환경보다 훨씬 높은 주변 온도에 노출될 수 있다. 전선 선정 시 외부 주변 온도와 도체 자체의 온도 상승을 함께 고려해야 하며, 최종 온도는 전선 절연재, 단자(Terminal), 실(Seal), 인접 재료의 검증된 정격 온도 이하를 유지해야 한다.

여러 전류 전달 도체가 함께 배선되는 경우 번들 디레이팅(Bundle Derating)을 고려해야 한다. 인접 회로에서 발생한 열은 전체 하네스의 평형 온도(Equilibrium Temperature)를 상승시킬 수 있으며, 특히 여러 모터 또는 액추에이터 전원선이 동시에 동작하는 경우 그 영향이 커질 수 있다. 설계 검토에서는 개별 전선의 허용 전류만을 그대로 적용하지 않고 부하가 인가된 도체 수, 번들 직경(Bundle Diameter), 듀티 사이클(Duty Cycle), 보호 피복(Protective Covering), 환기 상태, 배선 환경을 함께 고려해야 한다.

디지털 입력(Digital Input), 저전력 센서, 제어 신호(Control Signal), 진단 라인(Diagnostic Line)과 같은 일반적인 저전류 신호 회로는 전기적·기계적 요구사항이 허용하는 경우 더 작은 도체를 사용할 수 있다. 그러나 전기적으로 허용 가능한 가장 가는 전선이 움직이는 로봇에 자동으로 적합한 것은 아니다. 반복 굽힘(Repeated Bending), 진동(Vibration), 조립 취급, 커넥터 단자 한계, 마모(Abrasion), 유지보수 작업으로 인해 전류 용량만으로 결정되는 크기보다 더 큰 실질적인 최소 도체 크기가 요구될 수 있다.

통신 배선(Communication Wiring)은 일반적인 전력선 규칙보다 물리 계층 규격(Physical-Layer Specification)을 우선하여 선정해야 한다. CAN, CAN FD, 이더넷(Ethernet), 차동 엔코더 인터페이스(Differential Encoder Interface), 직렬 통신(Serial Communication) 및 기타 고속 네트워크(High-Speed Network)는 제어 임피던스(Controlled Impedance), 트위스트 페어(Twisted Pair), 차폐(Shielding), 규정된 정전용량(Capacitance), 특정 도체 형상(Conductor Geometry)을 요구할 수 있다. 임의로 도체 크기를 증가시키면 케이블 특성이 변경될 수 있으므로 인증된 통신 케이블(Qualified Communication Cable)의 사용을 대신할 수 없다.

모터 및 액추에이터 회로(Motor and Actuator Circuit)는 전기적 부하가 매우 동적으로 변화하므로 특별한 고려가 필요하다. 도체는 연속 동작 전류를 견디면서 가속 피크(Acceleration Peak), 스톨 관련 과도 전류(Stall-Related Transient), 제동 에너지(Braking Energy), 반복 듀티 사이클을 과도한 온도 상승이나 전압 손실 없이 지원해야 한다. PWM 제어 드라이브(PWM-Controlled Drive)를 사용하는 경우 케이블 구조, 전자파 적합성(EMC), 차폐, 접지(Grounding), 배선 분리(Routing Separation)를 도체 단면적과 함께 평가해야 한다.

배터리, 주 전력 분배(Main Power Distribution), 인버터 및 고전류 직류 회로(High-Current DC Circuit)는 최악 조건의 시스템 전류와 고장 보호 협조(Fault-Protection Coordination)를 기준으로 크기를 결정해야 한다. 선정된 도체는 의도된 동작 범위 전체에서 관련 퓨즈(Fuse), 회로 차단기(Circuit Breaker), 전자식 보호 장치(Electronic Protection Device)에 의해 적절하게 보호되어야 한다. 보호 장치는 하류 도체, 단자, 스플라이스, 커넥터 또는 분배 인터페이스의 안전한 열적 허용 능력을 초과하는 전류가 지속적으로 흐르도록 허용해서는 안 된다.

따라서 전선 굵기와 퓨즈 선정(Fuse Selection)은 하나의 통합된 설계 활동으로 조정되어야 한다. 도체는 정상 및 일시적인 동작 전류를 안전하게 전달해야 하며, 보호 장치는 도체 손상이 발생하기 전에 비정상 전류를 차단해야 한다. 불필요한 퓨즈 동작(Nuisance Opening)을 방지하기 위해 도체의 허용 능력을 재평가하지 않은 상태에서 퓨즈 정격을 높이는 것은 금지된다. 이는 단순한 운용 문제를 하네스 과열 또는 화재 위험으로 전환시킬 수 있기 때문이다.

커넥터 단자의 허용 능력(Connector Terminal Capability) 또한 전선 선정에 제한 조건을 부과할 수 있다. 도체가 시스템 전류 및 전압 강하 요구사항을 만족하더라도 단면적이 단자의 승인된 크림프 범위(Crimp Range)를 벗어나면 사용할 수 없다. 반대로 커넥터 접점(Contact)의 전류 정격이 선정된 전선의 허용 능력보다 낮을 수도 있다. 따라서 전선, 단자, 커넥터 하우징(Connector Housing), 실, 크림프 공구(Crimp Tooling), 회로 보호는 하나의 전기적 상호접속 시스템(Electrical Interconnection System)으로 통합 검증해야 한다.

기계적 배선 요구사항(Mechanical Routing Requirements) 역시 도체 선정에 영향을 주어야 한다. 관절 조인트(Articulated Joint), 서스펜션(Suspension), 조향 기구(Steering Mechanism), 매니퓰레이터(Manipulator), 휴머노이드 팔다리(Humanoid Limb), 기타 지속적으로 움직이는 인터페이스를 통과하는 하네스에는 반복 굽힘에 적합한 도체가 필요하다. 일반적인 전선 구조보다 미세 연선 플렉시블 케이블(Fine-Stranded Flexible Cable)이 적합할 수 있지만, 실제 로봇의 운동 프로파일에 대해 굽힘 반경(Bend Radius), 비틀림 하중(Torsional Loading), 스트레인 릴리프(Strain Relief), 마모 보호, 예상 사이클 수명(Cycle Life)을 검증해야 한다.

안전 관련 장치(Safety-Related Device)에 전원을 공급하는 회로의 전선 크기는 적절한 엔지니어링 마진(Engineering Margin)을 포함하고 안전 아키텍처(Safety Architecture)와 일관성을 유지해야 한다. 비상 정지 회로(Emergency-Stop Circuit), 안전 제어기(Safety Controller), 제동 인터페이스(Braking Interface), 안전 센서(Safety Sensor), 컨택터 제어(Contactor Control), 이중화 전원 경로(Redundant Power Path)는 열적 또는 기계적 한계에 근접하여 동작하는 도체에 의존해서는 안 된다. 설계 검토에서는 단선(Open Circuit), 전원 단락(Short to Power), 접지 단락(Short to Ground), 도체 간 단락(Short Between Conductors)과 관련된 고장 모드를 고려해야 한다.

다중 전압 레일(Multiple Voltage Rail)을 사용하는 로봇 플랫폼은 각 전력 분배 도메인(Distribution Domain)에 대해 독립적인 전선 굵기 선정 계산을 수행해야 한다. 48 V 추진 회로(Propulsion Circuit), 24 V 액추에이터 회로, 12 V 보조 회로(Auxiliary Circuit), 5 V 전자장치 회로는 동일한 수준의 전력을 공급하더라도 매우 다른 전류가 흐를 수 있다. 특히 저전압 레일(Lower-Voltage Rail)은 동일한 도체 전압 강하가 전체 공급 전압에서 차지하는 비율이 더 크므로 전압 강하에 민감하며, 하류 장치의 동작 마진(Operating Margin)을 감소시킬 수 있다.

승인된 전선 선정표(Released Wire Selection Table)는 센서 및 신호(Sensor and Signal), 저전력 제어(Low-Power Control), 컴퓨팅 및 통신 장비(Compute and Communication Equipment), 보조 전원(Auxiliary Power), 액추에이터 전원(Actuator Power), 추진 전원(Propulsion Power), 배터리 분배(Battery Distribution), 안전 회로(Safety Circuit)와 같은 실용적인 회로 그룹별로 적용 분야를 분류하는 것이 바람직하다. 이러한 분류는 절대적인 전류 한계가 아니라 엔지니어링 지침이며, 최종 전선 굵기는 실제 부하 프로파일, 배선 길이, 온도, 번들링(Bundling), 보호 방식 및 인터페이스 요구사항을 기준으로 반드시 확인해야 한다.

승인된 표의 범위 또는 정의된 적용 범위를 벗어난 도체 크기를 선정하는 경우 문서화된 엔지니어링 근거(Documented Engineering Justification)가 필요하다. 해당 근거에는 전기 부하(Electrical Load), 전압 강하 계산, 열적 가정(Thermal Assumption), 설치 환경, 커넥터 호환성, 보호 전략(Protection Strategy), 적용 가능한 검증 자료(Validation Evidence)가 포함되어야 한다. 이를 통해 시제품 제작, 양산 승인, 서비스 수리 또는 공급업체 주도의 하네스 재설계 과정에서 문서화되지 않은 임의 대체를 방지할 수 있다.

하네스 도면(Harness Drawing)과 자재 명세서(Bill of Materials, BOM)는 제조 과정에서 모호성이 발생하지 않도록 승인된 도체 사양을 충분히 기록해야 한다. 필요한 정보에는 도체 크기, 절연 또는 케이블 사양, 회로 식별 정보(Circuit Identification), 적용 가능한 색상 또는 마킹(Marking), 단자 호환성, 필요한 경우 특수 환경 및 플렉스 요구사항(Flex Requirement)이 포함되어야 한다. 양산 과정의 부품 대체는 두 전선의 공칭 치수가 유사하다는 이유만으로 허용하지 않고 엔지니어링 변경 관리 프로세스(Engineering Change Process)를 통해 통제해야 한다.

검증(Verification)은 설계 계산과 필요한 경우 대표적인 동작 조건에서 수행되는 실제 측정을 포함해야 한다. 고전류 또는 열적으로 제한된 회로는 현실적인 주변 온도와 듀티 사이클 조건에서 평가해야 하며, 중요 위치에서 도체, 단자, 스플라이스 및 커넥터의 온도를 모니터링해야 한다. 또한 피크 동작 조건에서 부하 측 전압을 측정하여 조립된 로봇에서도 해석 단계의 가정이 유효한지 확인해야 한다.

전선 굵기 선정표(Wire Gauge Selection Table)는 궁극적으로 전기 아키텍처(Electrical Architecture), 하네스 설계, 커넥터 선정(Connector Selection), 회로 보호(Circuit Protection), 제조(Manufacturing), 검사(Inspection), 서비스(Service)를 연결하는 통제된 엔지니어링 기준선(Controlled Engineering Baseline)의 역할을 한다. 이를 일관되게 적용하면 과열, 과도한 전압 강하, 간헐적 고장(Intermittent Fault), 조기 굽힘 파손(Premature Flex Failure), 통제되지 않은 부품 편차를 줄일 수 있으며, AMR, 매니퓰레이터, 야외 차량(Outdoor Vehicle), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 기타 로봇 플랫폼 전반에서 재사용 가능한 하네스 설계를 지원할 수 있다.

## 02.02. Routing and Packaging Rules

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

배선 및 패키징 규칙(Routing and Packaging Rules)은 로봇의 전체 수명주기 동안 전기적 성능, 기계적 내구성, 열적 거동, 전자파 적합성(Electromagnetic Compatibility), 제조성(Manufacturability), 정비성(Serviceability)을 유지할 수 있도록 전기 하네스(Electrical Harness)를 물리적으로 설치하는 방법을 정의한다. 적절한 굵기로 선정된 전선도 잘못 배선되면 고장이 발생할 수 있으므로, 하네스 배선은 기계 설계 완료 후 수행하는 단순 설치 작업이 아니라 하나의 엔지니어링 서브시스템(Engineered Subsystem)으로 다루어야 한다.

하네스 배선은 기계 및 전기 아키텍처(Mechanical and Electrical Architecture) 단계에서 정의된 배선 통로(Corridor), 분기점(Branch Point), 고정 위치(Attachment Location), 커넥터 인터페이스(Connector Interface), 정비 구역(Service Zone)을 기반으로 수립해야 한다. 배선 경로는 적용 가능한 CAD 모델과 하네스 도면(Harness Drawing)에 표현하여 양산 전에 구조물, 액추에이터, 센서, 커버, 배터리, 컴퓨팅 모듈(Compute Module), 가동 기구와의 간섭을 평가할 수 있어야 한다. 조립 과정에서 엔지니어링 검토 없이 임의로 배선 경로를 변경해서는 안 된다.

하네스는 날카로운 모서리(Sharp Edge), 노출된 나사산, 버(Burr), 프레스 가공 모서리, 기계 가공 형상 및 절연재를 손상시킬 수 있는 기타 표면으로부터 충분히 이격해야 한다. 이러한 부위와의 근접을 피할 수 없는 경우 에지 가드(Edge Guard), 그로밋(Grommet), 슬리브(Sleeve), 전선관(Conduit), 내마모성 피복(Abrasion-Resistant Covering) 등의 보호 수단을 적용해야 한다. 보호 수단은 초기 조립 상태의 정적인 간격에만 의존하지 않고 진동과 움직임이 발생하는 조건에서도 유효해야 한다.

휠, 조향 기구(Steering Mechanism), 서스펜션 부품(Suspension Member), 기어, 벨트, 체인, 팬, 링크 장치(Linkage), 리니어 액추에이터(Linear Actuator), 매니퓰레이터(Manipulator), 관절 조인트(Articulated Joint)를 포함한 가동 부품으로부터 충분한 간격을 유지해야 한다. 배선은 하나의 기준 위치만이 아니라 전체 기계적 운동 범위(Complete Mechanical Range of Motion)에 걸쳐 평가해야 한다. 하네스가 과도하게 당겨지거나 끼이거나, 정격 이상으로 비틀리거나, 구조물 사이에 갇히거나, 움직이는 하드웨어와 접촉해서는 안 된다.

동적 하네스 구간(Dynamic Harness Section)은 제어된 여유 길이(Controlled Slack)와 규정된 굽힘 형상(Bend Geometry)을 가져야 한다. 움직임을 수용하면서 전선, 단자 또는 커넥터에 과도한 인장력이 전달되지 않도록 충분한 추가 길이를 확보해야 하지만, 루프를 형성하거나 주변 부품과 접촉할 수 있는 과도한 여유 길이도 피해야 한다. 굽힘 반경(Bend Radius)은 해당 케이블 사양을 준수해야 하며, 반복 굽힘이 발생하는 적용 분야에는 예상 운동과 사이클 수명(Cycle Life)에 대해 검증된 케이블 구조를 사용해야 한다.

회전 또는 관절 인터페이스를 통과하는 하네스는 로봇의 움직임으로 발생하는 굽힘, 비틀림, 신장, 압축의 실제 조합을 고려하여 설계해야 한다. 휴머노이드 관절(Humanoid Joint), 사족보행 로봇 다리(Quadruped Leg), 매니퓰레이터, 조향 시스템, 서스펜션 기구는 단순한 정적 굽힘 반경만으로 표현할 수 없는 복잡한 케이블 하중을 발생시킬 수 있다. 따라서 배선 검증에는 대표적인 운동 사이클과 전체 동작 영역(Operating Envelope)에 걸친 케이블 거동 관찰이 포함되어야 한다.

스트레인 릴리프(Strain Relief)는 외부의 기계적 하중이 커넥터 접점(Connector Contact), 크림프 접합부(Crimp Joint), 스플라이스(Splice), 센서 피그테일(Sensor Pigtail), 전자 어셈블리(Electronic Assembly)로 직접 전달되는 것을 방지해야 한다. 하네스 고정점은 연결과 분리에 필요한 서비스 루프(Service Loop)를 유지하면서 케이블 움직임을 제어할 수 있도록 커넥터에서 충분히 가까운 위치에 배치해야 한다. 커넥터가 특별히 구조적 지지 용도로 설계되고 검증되지 않은 경우 커넥터 본체를 지지되지 않은 하네스 질량의 구조적 지지물로 사용해서는 안 된다.

하네스 고정(Harness Retention)에는 설치 환경에 적합한 승인된 클립(Clip), 클램프(Clamp), 케이블 타이(Cable Tie), 채널(Channel), 브래킷(Bracket) 또는 동등한 장치를 사용해야 한다. 고정 간격은 처짐, 진동 증폭(Vibration Amplification), 제어되지 않는 움직임, 인접 부품과의 접촉을 방지할 수 있어야 한다. 고정 장치는 절연재를 압착하거나 통신 케이블을 변형시키거나 필요한 움직임을 제한하거나 장기간 동작 중 도체 피로(Conductor Fatigue)를 유발할 수 있는 집중 응력(Concentrated Stress)을 발생시키지 않으면서 하네스를 고정해야 한다.

케이블 타이(Cable Tie)는 제어된 장력으로 적용해야 하며 케이블 재킷(Cable Jacket) 또는 절연재를 절단하거나 눌러 자국을 만들거나 심하게 압축해서는 안 된다. 고속 통신 케이블, 차폐 케이블(Shielded Cable), 광 케이블(Optical Cable), 플렉시블 로봇 케이블(Flexible Robotic Cable)은 과도한 압축에 특히 민감할 수 있다. 반복적인 유지보수가 예상되는 경우 정비 후 배선의 반복성을 향상시키기 위해 일회용 타이보다 재사용 가능한 클램프 또는 전용 하네스 리테이너(Harness Retainer)를 고려해야 한다.

전력 회로와 신호 회로는 전자기 결합(Electromagnetic Coupling)을 줄이기 위해 가능한 경우 물리적으로 분리해야 한다. 고전류 배터리 케이블, 인버터 출력, 모터 상 도체(Motor Phase Conductor), PWM 구동 액추에이터 라인, 스위칭 전원 회로 및 기타 주요 노이즈원은 민감한 아날로그 센서, 엔코더 신호, 통신선 또는 저레벨 측정 회로와 동일한 비제어 번들(Uncontrolled Bundle)에 배선하지 않는 것이 바람직하다. 필요한 분리 거리는 각 회로의 전기적 특성과 전자파 적합성 위험(EMC Risk)을 반영해야 한다.

전력 하네스와 민감한 신호 하네스가 교차해야 하는 경우 패키징 조건이 허용한다면 병렬 노출을 최소화하고 가능한 한 직각에 가깝게 교차하도록 해야 한다. 노이즈가 많은 전력 도체와 민감한 회로 사이의 장거리 병렬 배선은 피해야 하며, 필요한 경우 이격 거리, 차폐(Shielding), 트위스트 페어(Twisted Pair), 필터링(Filtering), 접지된 배리어(Grounded Barrier) 또는 검증된 기타 전자파 적합성 대책을 적용해야 한다. 배선 결정은 시스템 접지 및 차폐 아키텍처(Grounding and Shielding Architecture)와 일관성을 유지해야 한다.

CAN, CAN FD, 이더넷(Ethernet), 시간 동기화 링크(Time-Synchronization Link), 카메라 인터페이스(Camera Interface), 엔코더 케이블(Encoder Cable) 및 기타 통신 네트워크는 각 인터페이스에서 요구하는 물리적 특성을 유지해야 한다. 배선과 고정 과정에서 과도한 꼬임 해제(Untwisting), 변형, 급격한 굽힘, 차폐 불연속(Shield Discontinuity), 제어되지 않은 분기 형상이 발생해서는 안 된다. 통신 케이블의 기계적 보호가 임피던스(Impedance), 차폐 효과(Shielding Effectiveness), 신호 무결성(Signal Integrity)을 저하시키지 않도록 패키징해야 한다.

열적 배선(Thermal Routing)은 모터, 인버터, DC/DC 컨버터(DC/DC Converter), 제동 부품, 히터, 전력 저항(Power Resistor), 배터리, 적용되는 경우 배기 또는 연소 관련 부품, 기타 집중적인 열원으로부터 적절한 이격 거리를 유지해야 한다. 충분한 기하학적 공간이 있다는 이유만으로 하네스를 고온 영역에 배치해서는 안 된다. 노출을 피할 수 없는 경우 내열 전선(Temperature-Rated Wire), 열 차단재(Thermal Barrier), 반사 슬리브(Reflective Sleeve), 차열판(Shield) 또는 증가된 이격 거리를 적용하고 검증해야 한다.

배터리와 고에너지 전력 분배(High-Energy Electrical Distribution) 주변의 배선은 정상 동작뿐 아니라 고장 조건(Fault Condition)도 고려해야 한다. 하네스는 마모, 구조 변형, 느슨해진 전도성 하드웨어 또는 정비 작업으로 발생할 수 있는 단락으로부터 보호되어야 한다. 양극 및 음극 고전류 도체는 통제된 방식으로 패키징해야 하며, 분기 회로는 국부적인 하네스 고장이 로봇 전체에 제어되지 않은 열적 손상으로 확산되지 않도록 보호해야 한다.

패널, 벌크헤드(Bulkhead), 구조 부재 또는 인클로저 벽을 통과하는 하네스에는 적절한 관통부 보호(Pass-Through Protection)를 적용해야 한다. 그로밋, 케이블 글랜드(Cable Gland), 밀폐형 피드스루(Sealed Feedthrough) 또는 동등한 인터페이스를 사용하여 절연재 손상을 방지하고 인클로저의 환경적 건전성(Environmental Integrity)을 유지해야 한다. 관통부는 날카로운 접촉점, 과도한 압축 또는 보호된 전자장치 구획으로의 물 유입 경로를 만들지 않으면서 제조 공차와 케이블 움직임을 수용해야 한다.

환경 패키징(Environmental Packaging)은 로봇의 의도된 운용 조건을 반영해야 한다. 야외 자율이동로봇(Outdoor AMR), 검사 차량(Inspection Vehicle), 농업용 로봇(Agricultural Robot), 화물 플랫폼(Cargo Platform) 및 기타 외부 노출 시스템은 물, 먼지, 진흙, 화학물질, 염분, 자외선(Ultraviolet Radiation), 돌 충격, 식생 접촉, 고압 세척(Pressure Washing)에 대한 보호가 필요할 수 있다. 하네스 피복, 커넥터, 실(Seal), 고정 하드웨어 및 배선 방향은 개별 부품이 아니라 통합된 환경 보호 시스템(Environmental Protection System)으로 선정해야 한다.

물이 고일 수 있는 낮은 위치와 케이블 루프는 특히 커넥터와 인클로저 진입부 주변에서 피해야 한다. 물에 노출될 가능성이 있는 경우 배선은 배수를 촉진하고 물이 하네스를 따라 커넥터 또는 전자 하우징으로 이동하는 것을 방지하도록 구성해야 한다. 필요한 경우 드립 루프(Drip Loop)를 의도적으로 적용할 수 있으며, 커넥터 방향, 백셸(Backshell) 설계, 실 및 케이블 글랜드가 함께 작용하여 전기 인터페이스에 수분이 축적되지 않도록 해야 한다.

하네스 배선은 조립성과 제조 반복성(Manufacturing Repeatability)을 지원해야 한다. 분기 위치, 브레이크아웃 방향(Breakout Direction), 클립 위치, 커넥터 방향, 식별 위치를 명확하게 정의하여 작업자 개인의 판단에 의존하지 않고 서로 다른 작업자가 일관되게 하네스를 설치할 수 있도록 해야 한다. 하네스를 자연스럽게 지정된 위치에 배치하도록 유도하는 기계적 형상을 사용하는 것이 바람직하며, 반복 가능한 패키징은 양산 제품 간의 이격 거리, 진동 거동, 정비 접근성, 전자파 적합성 성능 편차를 감소시킨다.

배선 경로와 고정 방식을 정의할 때 정비성(Serviceability)을 고려해야 한다. 정비 기술자가 관련 없는 하네스 구간을 불필요하게 분해하지 않고 주요 모듈을 분리하고, 센서를 교체하고, 배터리를 제거하고, 액추에이터를 정비하거나, 컴퓨팅 장비를 교환할 수 있어야 한다. 가능한 경우 커넥터와 식별 라벨(Identification Label)에 접근할 수 있어야 하며, 정상 동작 중 제어되지 않는 과도한 케이블을 만들지 않으면서 충분한 정비용 길이(Service Length)를 제공해야 한다.

하네스 분기(Harness Branch)는 설치, 검사, 진단, 수리를 모호함 없이 수행할 수 있도록 식별되어야 한다. 라벨, 전선 식별자(Wire Identifier), 커넥터 명칭(Connector Designation), 분기 표시 및 도면 참조 정보는 설치 후에도 판독할 수 있어야 한다. 식별 표시는 클램프, 마모, 열, 유체 또는 반복 굽힘으로 손상되지 않는 위치에 배치해야 하며, 식별 방식은 예상되는 환경 조건과 정비 수명(Service Life)에 적합해야 한다.

스플라이스(Splice)는 가능한 한 기계적으로 안정되고 환경적으로 보호되는 영역에 배치해야 한다. 심한 굽힘 지점, 지속적으로 움직이는 관절, 고진동 인터페이스, 배수 구역 또는 정비 접근이 불가능한 위치에 직접 배치해서는 안 된다. 여러 스플라이스가 좁은 하네스 구간에 집중되면 과도한 강성과 패키지 직경을 만들 수 있으므로 스플라이스 분포는 전기적 토폴로지(Electrical Topology)뿐 아니라 기계적 패키징 거동도 고려해야 한다.

안전 필수 기구(Safety-Critical Mechanism) 주변에 설치되는 하네스는 비상 정지 장치(Emergency-Stop Device), 브레이크, 조향 시스템, 안전 센서(Safety Sensor), 가드(Guard), 기계식 해제 기능(Mechanical Release Function)의 작동을 방해해서는 안 된다. 하나의 하네스 변위 또는 고정 실패가 안전 기구를 방해하여 허용할 수 없는 위험을 발생시키지 않아야 한다. 안전 관련 배선에는 기계적 손상, 공통 원인 고장(Common-Cause Failure), 위험 에너지 회로와의 분리를 고려하여 기능에 적합한 배선 보호를 적용해야 한다.

최소 이격 거리와 보호 요구사항은 최악 조건의 치수 공차(Dimensional Tolerance), 진동, 적재 하중(Payload), 서스펜션 움직임, 조향각(Steering Angle), 매니퓰레이터 위치 및 예상 구조 변형(Structural Deflection)을 고려하여 검증해야 한다. 공칭 CAD 모델에서 충분해 보이는 이격 거리가 실제 생산 또는 운용 과정에서는 사라질 수 있다. 따라서 패키징 검토에서는 공칭 기하학적 간격만을 적절한 설계의 증거로 인정하지 않고 공차 누적(Tolerance Accumulation)과 동적 움직임을 고려해야 한다.

하네스 설계는 모듈의 탈거 및 장착 경로(Removal and Installation Path)를 고려해야 한다. 전기 케이블이 체결부품, 냉각 필터, 진단 포트(Diagnostic Port), 퓨즈 패널(Fuse Panel), 배터리 차단 장치(Battery Disconnect), 교체 가능한 부품에 대한 접근을 의도치 않게 방해해서는 안 된다. 정비를 위해 하네스를 제거해야 하는 경우 관련 없는 부품을 파괴적으로 제거하거나 문서화되지 않은 재배선을 하지 않고도 승인된 배선 구성으로 복원할 수 있는 고정 방식을 사용해야 한다.

배선 요구사항은 하네스 도면, 설치 도면(Installation Drawing), CAD 데이터, 조립 지침(Assembly Instruction) 또는 기타 통제된 엔지니어링 기록(Controlled Engineering Record)에 문서화해야 한다. 중요 정보에는 고정점, 분기 위치, 보호 피복, 최소 굽힘 반경, 분리 구역(Separation Zone), 가동 인터페이스 요구사항, 환경 보호 및 특수 설치 제약조건이 포함되어야 한다. 육안 검사 기준(Visual Inspection Criteria)은 적합한 양산 설치 상태와 통제되지 않은 배선 상태를 명확하게 구분할 수 있을 정도로 구체적이어야 한다.

시제품 배선(Prototype Routing)은 양산 승인 전에 반드시 물리적으로 검사해야 한다. 3차원 CAD만으로는 케이블 유연성, 조립 편차, 중력, 진동 또는 작업자의 취급을 완전히 표현할 수 없기 때문이다. 대표 로봇을 예상되는 운동, 하중, 온도 및 환경 조건에서 운용하면서 주요 하네스 구간을 관찰해야 한다. 마찰, 인장, 과도한 움직임, 열 노출, 커넥터 하중 또는 고정 불안정성이 확인되면 반드시 설계 시정 조치(Corrective Design Action)를 수행해야 한다.

배선 및 패키징(Routing and Packaging)은 궁극적으로 모든 전기적 연결이 동작하는 기계적 환경을 결정한다. 이러한 규칙을 일관되게 적용하면 마모 고장(Abrasion Failure), 도체 피로, 커넥터 손상, 열적 열화(Thermal Degradation), 전자파 간섭(Electromagnetic Interference), 수분 침투(Water Ingress), 조립 편차 및 정비 오류를 줄일 수 있다. 통제된 배선 아키텍처(Controlled Routing Architecture)는 AMR, 매니퓰레이터, 야외 차량(Outdoor Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 기타 로봇 플랫폼 전반에서 신뢰성 있고 재사용 가능한 하네스 설계를 가능하게 한다.

## 02.03. Splice and Termination Standard

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

스플라이스 및 터미네이션 엔지니어링(Splice and Termination Engineering)은 로봇 와이어링 하네스(Robotic Wiring Harness) 내부에서 도체를 전기적·기계적으로 접속하는 방법을 정의한다. 모든 스플라이스(Splice), 크림프(Crimp), 단자(Terminal), 터미네이션(Termination)은 의도된 서비스 수명(Service Life) 동안 안정적인 전기 저항, 충분한 기계적 강도, 환경 보호 및 제조 반복성(Manufacturing Repeatability)을 제공해야 한다. 고장은 온전한 전선 구간보다 도체의 전환부에서 빈번하게 발생하므로 이러한 인터페이스는 엔지니어링된 접속점(Engineered Connection Point)으로 다루어야 한다.

스플라이스는 전기 아키텍처(Electrical Architecture), 하네스 토폴로지(Harness Topology), 전력 분배 전략(Power Distribution Strategy) 또는 패키징 제약조건(Packaging Constraint)에 의해 필요한 경우에만 사용해야 한다. 불필요한 스플라이스는 저항, 질량, 제조 복잡성, 검사 작업 및 잠재적 고장 지점을 증가시킨다. 따라서 분기 회로는 실용적인 하네스 제작, 모듈 분리, 정비성(Serviceability), 전원·접지·신호·통신 회로의 통제된 분배를 유지하면서 스플라이스 수를 최소화하도록 설계해야 한다.

선정된 스플라이스 기술(Splice Technology)은 도체 재질, 단면적, 절연재 유형, 전류 수준, 환경 노출 및 예상 기계적 하중과 호환되어야 한다. 검증된 공구와 공정 관리(Process Control)를 사용할 수 있는 양산 하네스에는 일반적으로 크림프형 스플라이스 슬리브(Crimped Splice Sleeve)를 우선 적용한다. 다른 기술은 별도로 검증된 경우 사용할 수 있지만 비공식적인 전선 꼬기, 관리되지 않은 납땜 접합 또는 현장식 접속(Field-Style Connection)을 승인된 양산 공정의 대체 방법으로 사용해서는 안 된다.

크림프 터미네이션(Crimp Termination)은 도체를 손상시키지 않으면서 신뢰할 수 있는 전기적 접촉과 기계적 고정력을 동시에 형성해야 한다. 도체 크림프(Conductor Crimp)는 안정적인 저저항 인터페이스를 형성할 수 있도록 연선을 충분히 압축해야 하지만 연선 절단, 과도한 변형 또는 단자 균열을 발생시켜서는 안 된다. 절연 지지 크림프(Insulation Support Crimp)가 제공되는 경우 절연재를 관통하거나 과도하게 압착하지 않으면서 절연재를 고정하고 도체 크림프에 전달되는 기계적 하중을 감소시켜야 한다.

전선 탈피(Wire Stripping)는 도체 연선을 찍거나 절단하거나 긁거나 과도하게 벌리지 않으면서 규정된 길이만큼 절연재를 제거해야 한다. 탈피 길이(Strip Length)는 도체가 지정된 크림프 영역(Crimp Zone)에 완전히 배치되도록 단자 또는 스플라이스 사양과 일치해야 한다. 도체가 지나치게 많이 노출되면 환경 보호와 전기적 이격 성능이 저하될 수 있으며, 탈피가 부족하면 절연재가 도체 크림프 내부에 들어가 저항 증가 또는 기계적 강도 부족을 발생시킬 수 있다.

모든 도체 연선은 승인된 터미네이션 사양에 따라 단자 배럴(Terminal Barrel) 또는 스플라이스 슬리브 내부로 정확하게 삽입되어야 한다. 접힌 연선, 누락된 연선, 이탈 연선(Stray Strand) 또는 크림프 영역 밖에 위치한 연선이 전기적 용량, 기계적 강도, 밀봉 또는 이격 거리에 영향을 미칠 수 있는 경우 허용해서는 안 된다. 미세 연선 플렉시블 로봇 케이블(Fine-Stranded Flexible Robotic Cable)은 높은 연선 수에 적합하도록 특별히 검증된 단자와 공구가 필요할 수 있으므로 각별한 주의가 필요하다.

단자 선정(Terminal Selection)은 승인된 전선 크기 범위와 호환되어야 한다. 특정 도체 단면적용으로 설계된 단자는 도체가 물리적으로 배럴 내부에 삽입된다는 이유만으로 현저하게 작거나 큰 전선에 사용해서는 안 된다. 전선, 단자, 실(Seal), 커넥터 하우징(Connector Housing), 크림프 형상(Crimp Geometry), 공구(Tooling)의 조합을 하나의 검증된 터미네이션 시스템(Qualified Termination System)으로 간주해야 하며, 부품 대체는 작업자의 판단이 아니라 엔지니어링 검토를 거쳐야 한다.

양산 크림핑(Production Crimping)에는 지정된 단자 계열에 적합한 관리된 공구를 사용해야 한다. 어플리케이터(Applicator), 수동 공구(Hand Tool), 반자동 장비(Semi-Automatic Machine), 자동 가공 장비(Automatic Processing Equipment)는 제조 품질 시스템(Manufacturing Quality System)에 따라 유지보수하고 교정해야 한다. 필요한 경우 공구 식별 정보와 관련 설정 파라미터를 추적할 수 있도록 하여 불량 터미네이션 발생 시 장비, 공구 상태, 자재 로트(Material Lot), 작업자 및 생산 공정과 연계하여 조사할 수 있어야 한다.

크림프 높이(Crimp Height), 적용되는 경우 크림프 폭(Crimp Width), 도체 위치, 절연 지지 상태, 벨마우스 형상(Bellmouth Formation), 브러시 길이(Brush Length), 단자 변형 및 기타 단자별 특성은 승인된 부품 및 공정 사양을 준수해야 한다. 중요 크림프에서는 외관 검사만으로 치수 공정 관리(Dimensional Process Control)를 대체해서는 안 된다. 측정된 크림프 파라미터는 전선과 단자 조합에 대해 검증된 동작 범위 내에서 압축 상태가 유지되고 있음을 보여주는 객관적인 근거를 제공한다.

인장력 시험(Pull-Force Testing)은 필요한 경우 대표적인 크림프 터미네이션의 기계적 건전성(Mechanical Integrity)을 검증하는 데 사용해야 한다. 시험 방법, 샘플링 빈도, 전선 크기, 단자 계열 및 최소 허용 인장력은 승인된 제조 또는 검증 요구사항을 따라야 한다. 인장 시험은 고정 강도를 검증하지만 그 자체만으로 전기적 품질을 입증하지는 못하므로 필요에 따라 육안 검사, 치수 관리 및 전기적 검증과 함께 수행해야 한다.

스플라이스와 터미네이션의 전기 저항(Electrical Resistance)은 해당 회로에 대해 충분히 낮고 안정적으로 유지되어야 한다. 고전류 배터리, 모터, 액추에이터, 히터 및 전력 분배 연결은 접촉 저항(Contact Resistance)의 작은 증가도 상당한 국부 발열을 발생시킬 수 있으므로 특히 민감하다. 저항 한계와 검증 방법은 회로 전류, 커넥터 설계, 도체 크기, 측정 능력 및 접촉 성능이 점진적으로 열화될 경우의 영향을 반영해야 한다.

여러 분기 도체를 연결하는 스플라이스는 개별 분기의 전류뿐만 아니라 전체 전류를 기준으로 평가해야 한다. 공통 도체(Common Conductor)와 스플라이스 요소는 최악 조건의 동시 부하에서 합산된 상류 전류를 안전하게 전달할 수 있어야 한다. 따라서 도체 단면적, 스플라이스 허용 용량, 퓨즈 협조(Fuse Coordination), 온도 상승 및 전압 강하를 함께 평가하여 분기 인터페이스가 배전 회로의 열적 또는 전기적 병목 지점이 되지 않도록 해야 한다.

스플라이스 위치(Splice Location)는 기계적 패키징을 고려하여 선정해야 한다. 가능한 경우 스플라이스를 안정적인 하네스 구간에 배치하고 반복 굽힘 영역, 관절 조인트(Articulated Joint), 심한 굽힘 지점, 고진동 인터페이스, 물이 고이는 영역 및 집중 열원으로부터 이격해야 한다. 스플라이스는 국부적으로 강성과 직경을 증가시키므로 부적절한 위치에 배치하면 응력 집중(Stress Concentration)이 발생하여 로봇 움직임 중 도체 피로를 가속하거나 인접 절연재를 손상시킬 수 있다.

여러 스플라이스를 하네스 번들의 동일한 길이 방향 위치에 불필요하게 집중해서는 안 된다. 스플라이스 위치를 서로 엇갈리게 배치(Staggering)하면 번들 직경의 급격한 증가, 과도한 강성, 조립 난이도 및 보호 피복과의 간섭을 줄일 수 있다. 이러한 배치는 식별성, 제조성, 검사 가능성 및 전기적 토폴로지와의 호환성을 유지해야 하며, 기계적 엇갈림 배치로 인해 통제되지 않은 회로 배선이 발생해서는 안 된다.

환경 보호(Environmental Protection)는 로봇의 의도된 적용 환경에 적합해야 한다. 수분, 먼지, 화학물질, 진흙, 염분, 세척액 또는 야외 조건에 노출되는 스플라이스와 터미네이션에는 밀봉형 커넥터(Sealed Connector), 접착제 내장 열수축 튜브(Adhesive-Lined Heat-Shrink Tubing), 검증된 스플라이스 실(Qualified Splice Seal), 부트(Boot) 또는 동등한 보호 수단이 필요할 수 있다. 환경 밀봉은 케이블의 유연성, 온도 범위 및 예상 기계적 움직임과 호환되면서 오염물질이 전도성 인터페이스에 도달하는 것을 방지해야 한다.

스플라이스 또는 터미네이션 보호에 사용되는 열수축 튜브(Heat-Shrink Tubing)는 적용 조건에 적합한 직경, 수축비(Shrink Ratio), 재질 및 온도 등급을 가져야 한다. 가열은 도체 절연재, 커넥터 실, 주변 부품 또는 스플라이스 자체를 손상시키지 않으면서 완전한 수축과 밀봉이 이루어지도록 제어해야 한다. 열수축 재료를 기계적으로 불량한 크림프 또는 기타 허용할 수 없는 터미네이션을 보완하는 수단으로 사용해서는 안 된다.

납땜(Soldering)은 해당 설계에서 특별히 요구되고 검증되지 않는 한 양산 하네스 터미네이션에 도입해서는 안 된다. 납은 연선 도체 내부로 침투하여 접합부 주변에 굽힘 응력이 집중되는 강성 전이 구간(Rigid Transition)을 형성할 수 있다. 납땜 연결이 기술적으로 필요한 경우 솔더 합금(Solder Alloy), 플럭스(Flux), 온도 프로파일, 청정도, 스트레인 릴리프(Strain Relief), 절연 복원, 작업 품질 기준(Workmanship Criteria), 검사 요구사항을 명확하게 정의하고 관리해야 한다.

차폐 케이블 터미네이션(Shielded Cable Termination)은 전기적 연속성과 전자파 성능을 모두 유지해야 하므로 별도의 관리가 필요하다. 차폐 브레이드(Shield Braid) 또는 포일(Foil)은 승인된 백셸(Backshell), 차폐 크림프(Shield Crimp), 드레인 와이어(Drain Wire) 방식 또는 동등한 인터페이스를 사용하여 접지 및 전자파 적합성 아키텍처(Grounding and EMC Architecture)에 따라 터미네이션해야 한다. 과도하게 긴 차폐 피그테일(Shield Pigtail), 통제되지 않은 차폐 제거 또는 일관되지 않은 터미네이션 형상은 임피던스를 증가시키고 고주파에서 차폐 효과를 저하시킬 수 있다.

통신 케이블 스플라이스(Communication Cable Splice)는 가능한 한 피해야 하며, 특히 이더넷(Ethernet)과 기타 임피던스 민감형 고속 인터페이스에서는 더욱 그러하다. 스플라이스가 불가피하고 인터페이스 설계상 허용되는 경우 도체 페어링(Conductor Pairing), 꼬임률(Twist Rate), 임피던스, 차폐, 분기 형상 및 터미네이션 길이를 관리해야 한다. 기계적으로 적합한 접속이라도 스플라이스 구간에서 원래 케이블의 물리 계층 특성(Physical-Layer Characteristics)을 유지하지 못하면 통신 성능을 저하시킬 수 있다.

고전류 링 단자(Ring Terminal), 러그(Lug), 버스바 인터페이스(Busbar Interface), 볼트 체결 터미네이션(Bolted Termination)에는 승인된 도체 준비 및 크림핑 공정을 사용해야 한다. 접촉면은 청결하게 유지하고 규정된 하드웨어, 체결 토크(Torque), 와셔(Washer), 풀림 방지 구조(Locking Feature), 환경 보호 수단을 적용하여 조립해야 한다. 케이블 질량과 진동은 별도로 지지하여 볼트 체결 전기 인터페이스에 지지되지 않은 고전류 케이블로 인한 지속적인 굽힘 모멘트나 인장 하중이 전달되지 않도록 해야 한다.

커넥터 하우징에 대한 단자 삽입(Terminal Insertion)은 크림핑 후 검증해야 한다. 각 접점(Contact)은 완전히 삽입되어 지정된 1차 잠금 구조(Primary Locking Feature)에 의해 유지되어야 하며, 제공되는 경우 2차 잠금 장치(Secondary Lock) 또는 단자 위치 보증 장치(Terminal Position Assurance)를 체결해야 한다. 전기적으로 연결된 것처럼 보이더라도 완전히 고정되지 않은 단자는 커넥터 체결, 진동 또는 정비 과정에서 빠져나와 진단하기 어려운 간헐적 고장(Intermittent Fault)을 발생시킬 수 있다.

커넥터 캐비티 실(Connector Cavity Seal)과 개별 전선 실(Individual Wire Seal)은 절단, 비틀림, 위치 이탈 또는 부적합한 전선 직경 없이 설치해야 한다. 절연재 외경은 선정된 실의 검증된 밀봉 범위 내에 있어야 한다. 환경 밀봉형 커넥터의 미사용 캐비티에는 필요한 경우 승인된 캐비티 플러그(Cavity Plug)를 설치해야 한다. 모든 사용 단자가 올바르게 크림핑되어 있더라도 하나의 열린 캐비티가 전체 커넥터의 환경 보호 성능을 저하시킬 수 있기 때문이다.

안전 관련 회로(Safety-Related Circuit)는 연결 성능 저하가 비상 정지(Emergency Stop), 제동, 안전 감지, 컨택터 제어(Contactor Control), 이중화 전력 분배(Redundant Power Distribution)에 직접 영향을 줄 수 있으므로 스플라이스 및 터미네이션 품질을 더욱 엄격하게 관리해야 한다. 이중화 회로의 공통 스플라이스 지점은 공통 원인 고장(Common-Cause Failure)의 가능성을 검토해야 한다. 안전 아키텍처에서 독립성이 요구되는 경우 터미네이션 및 하네스 토폴로지 전반에서 물리적·전기적 분리를 유지해야 한다.

모든 양산 스플라이스와 터미네이션은 정의된 합격 기준(Acceptance Criteria)에 따라 검사할 수 있어야 한다. 검사 항목에는 도체 위치, 절연재 위치, 연선 상태, 크림프 형상, 단자 손상, 실 설치, 잠금 상태, 스플라이스 보호, 식별 정보 및 작업 품질(Workmanship)이 포함될 수 있다. 중요 특성은 통제된 제조 문서(Controlled Manufacturing Documentation)에 정의하여 합격 여부가 주관적인 판단이나 개별 작업자의 경험에만 의존하지 않도록 해야 한다.

전기적 도통 시험(Electrical Continuity Testing)은 완성된 하네스 회로가 승인된 배선 정의와 일치하는지 확인해야 한다. 필요한 경우 단선(Open Circuit), 의도하지 않은 단락(Unintended Short), 오결선(Cross-Connection), 과도한 저항도 검출할 수 있어야 한다. 안전 회로, 고전류 회로 또는 통신 회로가 포함된 하네스는 단순한 도통 검사 이상의 추가 검증이 필요할 수 있으며, 이를 통해 기능 성능에 영향을 주는 조립 결함을 로봇에 통합하기 전에 식별해야 한다.

스플라이스, 단자, 커넥터 캐비티, 전선 식별자(Wire Identifier), 적용 가능한 부품 번호는 하네스 도면과 자재 명세서(Bill of Materials, BOM)에 일관되게 표현해야 한다. 제조 기록은 승인된 전선, 단자, 실, 커넥터, 스플라이스 부품 및 공구 사양까지 추적할 수 있도록 구성하는 것이 바람직하다. 검증된 터미네이션 시스템의 구성 요소를 변경하는 경우 사소해 보이는 대체품도 크림프 거동, 밀봉, 저항 또는 신뢰성을 변화시킬 수 있으므로 엔지니어링 변경 관리(Engineering Change Control)를 거쳐야 한다.

시제품 및 적격성 시험(Prototype and Qualification Testing)은 접속 신뢰성이 중요한 경우 관련 진동, 굽힘, 온도, 습도, 오염, 전류 부하 및 환경 조건을 재현해야 한다. 시험 후 검사와 전기적 측정을 통해 저항, 기계적 고정력, 밀봉 또는 물리적 상태가 열화되었는지 확인해야 한다. 시험 결과는 선정된 터미네이션 공정이 실제 로봇 운용 환경에 적합한지를 확인하는 근거로 사용해야 한다.

통제된 스플라이스 및 터미네이션 표준(Controlled Splice and Termination Standard)은 신뢰성 높은 로봇 와이어링 하네스를 제조하기 위한 기반을 제공한다. 부품의 일관된 선정, 검증된 공구, 치수 기반 크림프 관리, 기계적·전기적 검증, 환경 보호, 문서화 및 추적성(Traceability)은 간헐적 고장, 과열, 부식, 도체 피로 및 정비 고장을 감소시킨다. 이러한 원칙은 AMR, 매니퓰레이터(Manipulator), 야외 차량(Outdoor Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 기타 로봇 플랫폼 전반에서 반복 가능한 하네스 품질을 지원한다.

## 02.04. Drawing and BOM Standard

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

도면 및 자재 명세서 표준(Drawing and Bill of Materials Standard)은 로봇 와이어링 하네스(Robotic Wiring Harness)를 제조, 검사, 설치, 정비 및 재생산하는 데 필요한 통제된 엔지니어링 정보(Controlled Engineering Information)를 정의한다. 하네스 도면(Harness Drawing)과 자재 명세서(Bill of Materials, BOM)는 승인된 전기 설계를 일관되고 모호함 없이 표현해야 한다. 이들은 엔지니어링 형상 기준선(Engineering Configuration Baseline)의 일부를 구성하며 전기 아키텍처, 커넥터 정의, 회로 보호, 기계적 패키징 및 생산 요구사항과 항상 동기화되어야 한다.

각 하네스 어셈블리(Harness Assembly)는 고유한 부품 번호(Part Number), 개정 식별자(Revision Identifier), 설명 및 적용 제품 또는 서브시스템 참조 정보를 가져야 한다. 도면에는 완성 차량 하네스, 서브시스템 하네스, 분기 어셈블리(Branch Assembly), 어댑터(Adapter), 점퍼(Jumper) 또는 기타 정의된 전기 어셈블리 중 무엇을 나타내는지 명확하게 식별해야 한다. 식별 규칙은 비공식적인 파일명이나 현장 제조 지식에 의존하지 않고 시제품, 양산 제품, 서비스 부품 및 제품 파생형 전반의 형상 관리(Configuration Management)를 지원해야 한다.

하네스 도면은 커넥터, 단자(Terminal), 스플라이스(Splice), 접지(Ground), 분배 지점(Distribution Point) 및 기타 인터페이스 사이의 전기적 연결성(Electrical Connectivity)을 정의해야 한다. 모든 회로는 일관된 전선 식별자(Wire Identifier), 커넥터 명칭(Connector Designation), 캐비티 번호(Cavity Number), 회로명(Circuit Name)을 사용하여 전원에서 목적지까지 추적할 수 있어야 한다. 승인된 하네스 도면의 전기적 연결성은 관련 회로도(Schematic) 및 인터페이스 정의와 일치하여 서로 충돌하는 표현이 제조 공정에 유입되지 않도록 해야 한다.

커넥터 명칭은 적용되는 제품 형상(Product Configuration) 내에서 고유해야 하며 조립 및 정비 과정에서 사용되는 물리적 인터페이스와 대응해야 한다. 각 커넥터 정의에는 커넥터 부품 번호, 적용되는 경우 상대측 인터페이스(Mating Interface), 캐비티 번호 체계, 단자 유형, 밀봉 요구사항, 2차 잠금 장치(Secondary Locking Device), 미사용 캐비티 처리 방법을 포함하는 것이 바람직하다. 기계적으로 유사한 인터페이스를 혼동하여 오조립할 가능성이 있는 경우 방향 또는 키잉 정보(Keying Information)를 제공해야 한다.

전선 정보는 해석 없이 각 회로를 재현할 수 있을 정도로 충분하게 규정해야 한다. 일반적으로 필요한 속성에는 전선 식별자, 도체 크기(Conductor Size), 전선 또는 케이블 사양, 관리 대상인 경우 절연재 유형, 색상 또는 마킹(Marking), 소스 커넥터 및 캐비티, 목적지 커넥터 및 캐비티, 회로 기능이 포함된다. 플렉시블 구조(Flexible Construction), 차폐 케이블(Shielded Cable), 트위스트 페어(Twisted Pair), 온도 등급 또는 환경 적격성(Environmental Qualification)과 같은 특수 요구사항은 적용 상황에서 추정하도록 두지 않고 명시적으로 식별해야 한다.

전선 길이(Wire Length)는 정의된 치수 규칙(Dimensional Convention)을 사용하여 관리해야 한다. 도면에서는 적용되는 경우 절단 길이(Cut Length), 완성 하네스 치수(Finished Harness Dimension), 커넥터 간 치수(Connector-to-Connector Dimension), 분기 길이(Branch Length) 및 기타 측정 기준을 구분해야 한다. 공차(Tolerance)는 제조 능력과 설치 요구사항을 반영해야 한다. 길이 치수는 과도한 여유 길이, 커넥터 하중, 간섭 또는 양산 하네스 간의 통제되지 않은 편차를 발생시키지 않으면서 충분한 배선 및 정비 여유를 제공해야 한다.

분기점(Branch Point)과 브레이크아웃 위치(Breakout Location)는 물리적 하네스 토폴로지(Harness Topology)를 반복 가능하게 구현할 수 있도록 정의된 기준 형상으로부터 치수화해야 한다. 이러한 특성이 설치에 영향을 미치는 경우 도면에는 분기 방향, 분기 길이, 브레이크아웃 보호(Breakout Protection) 및 관련 고정 관계를 표시하는 것이 바람직하다. 하네스 분기는 의도된 기계적 배선 아키텍처(Mechanical Routing Architecture)와 일치해야 하며, 패키징, 움직임, 정비성 또는 전자파 적합성(EMC) 성능을 저해하면서 제조 편의성만을 목적으로 배치해서는 안 된다.

스플라이스는 고유한 식별자를 사용하여 표현하고 연결되는 모든 회로를 정의해야 한다. 도면 또는 관련 제조 데이터에는 승인된 스플라이스 부품, 도체 조합, 밀봉 또는 절연 방식 및 필요한 경우 위치 요구사항을 규정해야 한다. 여러 스플라이스는 검사와 추적성(Traceability)을 위해 서로 구분할 수 있어야 한다. 스플라이스 정보는 승인된 스플라이스 및 터미네이션 공정(Splice and Termination Process)과 일치해야 하며 제조 작업자가 독립적으로 접속 방법을 선택하도록 해서는 안 된다.

차폐 및 트위스트 통신 케이블(Shielded and Twisted Communication Cable)은 추가적인 도면 정보를 필요로 한다. 문서에는 페어 구성(Pair Membership), 차폐 연속성(Shield Continuity), 적용되는 경우 드레인 와이어 처리(Drain-Wire Treatment), 차폐 터미네이션 지점(Shield Termination Point), 꼬임 해제 또는 노출 도체 길이에 대한 제한사항을 표시해야 한다. CAN, CAN FD, 이더넷(Ethernet), 엔코더(Encoder), 카메라 또는 기타 민감한 인터페이스의 경우 도면 세부사항은 통신 아키텍처 및 전자파 적합성 설계에서 요구하는 물리 계층 특성(Physical-Layer Characteristics)을 유지해야 한다.

접지 회로(Ground Circuit)는 모호성이 발생할 가능성이 있는 경우 일반적인 접지 기호만 사용하는 대신 의도된 전기적 목적지를 식별해야 한다. 섀시 접지(Chassis Ground), 전력 리턴(Power Return), 신호 기준(Signal Reference), 차폐 터미네이션(Shield Termination), 보호 본딩(Protective Bonding) 및 기타 접지 기능은 서로 다른 아키텍처 요구사항을 가질 수 있다. 따라서 접지점 식별자(Ground-Point Identifier)와 관련 하드웨어는 하네스 도면, 접지 아키텍처, 기계적 설치 정보 및 BOM 사이에서 추적할 수 있어야 한다.

보호 피복(Protective Covering)은 유형과 적용 위치를 식별해야 한다. 전선관(Conduit), 브레이디드 슬리브(Braided Sleeve), 코루게이트 튜브(Corrugated Tube), 열수축 튜브(Heat-Shrink Tubing), 내마모 보호재(Abrasion Protection), 열 보호 슬리브(Thermal Sleeve), 차폐 재료(Shielding Material), 테이프(Tape), 부트(Boot) 및 기타 피복은 필요한 위치에 규정해야 한다. 보호 또는 조립에 영향을 미치는 경우 시작 및 종료 위치 또는 적용 범위를 치수로 정의해야 한다. 재료 선정은 온도, 유연성, 환경 및 난연성(Flammability) 요구사항과 일치해야 한다.

하네스 어셈블리의 일부로 공급되는 하네스 고정 부품(Harness Retention Component)은 도면과 BOM에 포함되어야 한다. 클립(Clip), 클램프(Clamp), 케이블 타이(Cable Tie), 브래킷(Bracket), 에지 보호재(Edge Protection), 그로밋(Grommet), 퍼트리 리테이너(Fir-Tree Retainer) 및 유사 부품은 필요한 경우 승인된 부품 번호와 설치 위치를 함께 식별해야 한다. 고정 하드웨어가 차량 또는 로봇의 기계 어셈블리에 속하는 경우 하네스 문서는 일관된 배선을 유지할 수 있도록 충분한 인터페이스 정보를 제공해야 한다.

라벨과 식별 마킹(Identification Marking)은 통제된 하네스 특성으로 정의해야 한다. 도면에는 필요한 전선 라벨, 커넥터 라벨, 분기 식별, 하네스 부품 번호 라벨, 개정 표시(Revision Marking) 및 기타 추적성 정보를 규정해야 한다. 라벨 위치는 설치 후에도 판독할 수 있어야 하며 실(Seal), 굽힘부, 클램프 또는 가동 인터페이스와 간섭해서는 안 된다. 마킹 재료는 예상되는 온도, 유체, 마모 및 정비 환경에 적합해야 한다.

BOM에는 승인된 하네스 형상을 제조하는 데 필요한 승인 부품만 포함해야 한다. 각 항목에는 통제된 부품 번호, 설명, 수량 또는 수량 산정 기준 및 조직에서 요구하는 기타 구매 정보를 포함해야 한다. 전선, 단자, 커넥터, 실, 캐비티 플러그(Cavity Plug), 스플라이스 부품, 보호 재료, 라벨, 클립, 체결부품 및 기타 조립 재료를 포함하여 제조가 문서화되지 않은 부품 대체에 의존하지 않도록 해야 한다.

BOM 수량은 재료의 특성을 반영해야 한다. 커넥터, 단자, 실, 클립 및 부트와 같은 개별 부품은 개수로 지정할 수 있으며, 전선, 튜브, 테이프 또는 슬리빙(Sleeving)은 정의된 제조 여유를 포함한 길이 기준 수량이 필요할 수 있다. 수량 규칙은 프로젝트 전반에서 일관되어야 하며 구매, 원가 산정, 재고 관리 및 생산 계획 과정에서 수동 수정이나 현장 가정 없이 승인된 BOM을 해석할 수 있어야 한다.

승인된 제조사 부품 번호(Manufacturer Part Number)와 내부 부품 번호(Internal Part Number)는 일관되게 관리해야 한다. 여러 동등 공급원을 허용하는 경우 승인된 대체품(Approved Alternative)은 작업 현장 문서에 비공식적으로 기입하는 것이 아니라 부품 관리 시스템(Component Control System)을 통해 공식적으로 정의해야 한다. 재질, 도금(Plating), 밀봉, 크림프 형상, 온도 성능, 치수 또는 공구 호환성의 차이가 하네스 성능에 영향을 미칠 수 있으므로 전기적 동등성만으로는 부품 대체의 충분한 근거가 되지 않는다.

단자, 실 및 커넥터의 호환성은 통제된 엔지니어링 데이터(Controlled Engineering Data)를 통해 확인할 수 있어야 한다. BOM에서 커넥터 하우징만 지정하면서 관련 단자, 전선 실, 캐비티 플러그, 2차 잠금 장치, 백셸(Backshell) 및 액세서리가 선정된 전선 범위와 환경 요구사항에 적합한지 확인하지 않는 방식은 허용해서는 안 된다. 전체 상호접속 시스템(Interconnection System)을 독립적으로 선택된 카탈로그 부품의 집합이 아니라 하나의 엔지니어링된 조합(Engineered Combination)으로 승인해야 한다.

BOM에서 사용하는 참조 명칭(Reference Designator)은 도면 및 기타 통제된 전기 문서에 표시된 명칭과 대응해야 한다. 커넥터, 스플라이스, 접지점, 퓨즈 인터페이스 또는 하네스 분기는 가능한 경우 관련 엔지니어링 기록 전체에서 동일한 식별자를 유지해야 한다. 일관된 참조 명칭은 설계 검토, 조립, 검사, 진단, 정비, 변경 관리 및 전기 엔지니어링 데이터베이스 간 자동 비교를 향상시킨다.

도면 주석(Drawing Note)은 형상이나 표 형식의 회로 정보만으로 효율적으로 전달하기 어려운 요구사항에 사용해야 한다. 주석에는 작업 품질 표준(Workmanship Standard), 크림프 요구사항, 허용 가능한 대체품, 배선 제한사항, 검사 기준, 시험 요구사항, 라벨링 규칙 또는 환경 제약조건 등을 정의할 수 있다. 주석은 간결하고 시험 또는 검증 가능해야 하며 개인의 해석에 의존하는 모호한 표현이 아니라 명확하게 정의된 특성에 적용되어야 한다.

제조 편차가 안전, 전기적 성능, 밀봉, 통신 무결성 또는 기계적 내구성에 영향을 미칠 수 있는 경우 중요 특성(Critical Characteristic)을 명시적으로 식별해야 한다. 구체적인 크림프 요구사항, 차폐 터미네이션 형상, 고전류 도체 구조, 분기 치수, 안전 회로 식별 또는 환경 밀봉 특성 등이 이에 포함될 수 있다. 도면은 이러한 특성에 대한 생산 관리와 검사를 수행할 수 있는 명확한 기준을 제공해야 한다.

하네스 도면은 하네스 제조 자체에 내재된 요구사항과 로봇 설치 과정에 적용되는 요구사항을 구분하는 것이 바람직하다. 이러한 구분은 공급업체가 자신의 범위를 벗어난 차량 수준 하드웨어에 대해 책임을 지는 것을 방지하면서 설치에 중요한 정보가 누락되지 않도록 한다. 따라서 하네스 제조 도면, 설치 도면(Installation Drawing), 기계 CAD는 동일한 승인 형상에 대해 통제되는 동시에 상호 보완적인 정보를 포함할 수 있다.

도면은 불필요하게 높은 정밀도를 요구하지 않으면서 적절한 치수 공차와 일반 작업 품질 요구사항을 정의해야 한다. 지나치게 엄격한 공차는 로봇 성능을 실질적으로 향상시키지 않으면서 비용과 제조 난이도를 증가시키며, 지나치게 느슨한 공차는 배선 간섭, 커넥터 하중 또는 일관되지 않은 서비스 루프(Service Loop)를 발생시킬 수 있다. 따라서 공차 선정은 기능적 필요성, 공정 능력(Process Capability), 기계적 패키징 환경을 반영해야 한다.

모든 승인된 하네스에는 관련 검증 정의(Verification Definition)가 있어야 한다. 적용 분야에 따라 양산 시험에는 도통 시험(Continuity Test), 단락 검출(Short-Circuit Detection), 오결선 검출(Cross-Connection Detection), 저항 측정, 절연 내력 시험(Dielectric Testing), 커넥터 고정 상태 검사 또는 육안 검사가 포함될 수 있다. 시험 지점과 합격 기준은 승인된 전기적 정의와 연계하여 하네스가 승인된 설계와 전기적으로 다르면서도 생산 검사를 통과하는 상황이 발생하지 않도록 해야 한다.

도면 및 BOM 개정(Revision)은 엔지니어링 변경 프로세스(Engineering Change Process)를 통해 관리해야 한다. 전선 굵기, 커넥터, 단자, 실, 스플라이스, 분기 길이, 보호 재료, 배선 관련 특성, 라벨 또는 기타 통제 특성의 변경은 승인 전에 후속 영향(Downstream Impact)을 평가해야 한다. 도면 개정, BOM 개정, 제조 지침, 구매 데이터, 검사 기준 및 적용 제품 형상은 항상 서로 동기화된 상태를 유지해야 한다.

개정 이력(Revision History)은 비공식적인 의사소통 내용을 다시 추적하지 않고도 무엇이 왜 변경되었는지를 이해할 수 있을 정도로 충분한 정보를 제공해야 한다. 중요한 변경사항은 관련 엔지니어링 변경 기록(Engineering Change Record)과 영향을 받는 제품 형상을 참조하는 것이 바람직하다. 폐기된 도면과 BOM이 의도치 않게 양산에 사용되는 것을 방지하는 동시에 정비, 현장 지원(Field Support), 고장 분석 또는 레거시 제품(Legacy Product)을 위해 필요한 경우 과거 형상을 검색할 수 있어야 한다.

디지털 하네스 데이터(Digital Harness Data)는 통제된 파일 명명 규칙, 디렉터리 구조, 개정 상태 및 승인 권한(Release Permission)을 사용해야 한다. 원본 CAD 또는 전기 설계 데이터, 생성된 도면, BOM 내보내기 파일(BOM Export), 제조 파일, 승인된 PDF 또는 이에 상응하는 기록은 동일한 형상 기준선과 연계되어야 한다. 도면과 BOM 사이에서 동일한 정보를 수작업으로 중복 입력하면 불일치 가능성이 증가하므로 실용적인 경우 자동 생성된 정보(Automatically Generated Information)를 우선 사용하는 것이 바람직하다.

설계 검토(Design Review)는 승인 전에 하네스 도면, BOM, 회로도, 커넥터 정의, 배선 정보 및 관련 엔지니어링 표준 사이의 일관성을 검증해야 한다. 검토자는 문서화된 정보만을 사용하여 모든 회로를 제조하고 검사할 수 있는지 확인하고, 필수 요구사항이 개인의 지식, 시제품 표시, 이메일 또는 구두 지시에만 존재하지 않는지 검증해야 한다. 승인된 문서만으로 의도된 하네스를 독립적으로 재현할 수 있어야 한다.

도면 및 BOM 표준(Drawing and BOM Standard)은 궁극적으로 로봇 하네스 엔지니어링을 위한 형상 관리 프레임워크(Configuration-Control Framework)를 제공한다. 정확한 회로 정의, 통제된 부품 선정, 치수 정보, 추적성, 개정 관리, 제조 요구사항 및 검증 기준은 반복 가능한 양산과 신뢰성 높은 정비를 가능하게 한다. 일관된 문서화는 AMR, 매니퓰레이터(Manipulator), 야외 차량(Outdoor Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 기타 로봇 플랫폼 전반에서 재사용 가능한 전기 설계를 지원한다.

## 02.05. Inspection Criteria

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

하네스 검사 기준(Harness Inspection Criteria)은 완성된 로봇 와이어링 하네스(Robotic Wiring Harness)가 승인된 전기 설계, 제조 요구사항 및 의도된 설치 환경에 부합하는지를 검증하기 위한 합격 조건(Acceptance Conditions)을 정의한다. 검사는 작업 품질(Workmanship), 부품 적합성, 전기적 건전성(Electrical Integrity), 기계적 보호, 식별 정보 및 형상 상태(Configuration Status)를 평가해야 한다. 합격 여부는 개별 작업자의 판단이나 통제되지 않은 시제품과의 비교가 아니라 관리된 기준(Controlled Criteria)에 따라 결정해야 한다.

검사는 최종 육안 검사(Final Visual Check)에만 의존하지 않고 제조 과정의 적절한 단계에서 수행해야 한다. 입고 부품, 탈피된 전선, 크림핑된 단자(Crimped Terminal), 스플라이스(Splice), 커넥터 조립, 보호 피복, 완성된 하네스 치수 및 전기 시험 결과는 각각 별도의 검증이 필요할 수 있다. 공정 단계 검사(Process-Stage Inspection)를 통해 결함이 커넥터 하우징, 열수축 튜브(Heat-Shrink Tubing), 슬리브(Sleeve), 전선관(Conduit), 테이프 또는 최종 패키징에 의해 가려지기 전에 발견할 수 있다.

검사자는 하네스 부품 번호, 개정(Revision), 제품 적용성 및 형상(Configuration)이 승인된 도면과 자재 명세서(Bill of Materials, BOM)에 일치하는지 확인해야 한다. 엔지니어링 변경 관리(Engineering Change Control)에 의해 명시적으로 승인되지 않는 한 서로 다른 개정의 부품이나 작업 지침을 혼용해서는 안 된다. 형상 검증은 특히 외관상 유사한 여러 하네스 파생형이 서로 다른 로봇 모델, 전압 아키텍처, 센서 패키지 또는 지역별 형상을 지원하는 경우 중요하다.

전선 유형과 도체 크기(Conductor Size)는 검증이 요구되는 모든 회로에서 승인된 설계와 일치해야 한다. 절연 사양, 색상, 마킹(Marking), 플렉시블 구조(Flexible Construction), 차폐(Shielding), 트위스트 페어 구성(Twisted-Pair Configuration), 온도 또는 환경 등급도 통제된 문서와 일치해야 한다. 전기적으로 도통되는 전선이라도 도체 또는 절연 사양이 승인된 형상과 다르다면 올바른 지점을 연결한다는 이유만으로 합격 처리해서는 안 된다.

전선 절연재(Wire Insulation)는 절단, 찍힘, 마모, 압착, 과열, 오염, 과도한 변형 또는 기타 육안으로 확인 가능한 손상이 있는지 검사해야 한다. 도체 연선을 노출시키거나 절연 건전성을 현저히 저하시키는 손상은 불합격 처리해야 한다. 경미한 표면 흔적은 주관적인 외관 판단이 아니라 정의된 작업 품질 한계(Workmanship Limit)에 따라 평가해야 한다. 특히 탈피 끝단, 스플라이스, 클램프 및 관통부 주변의 절연재는 가공 과정에서 손상되기 쉬우므로 주의 깊게 검사해야 한다.

탈피된 도체(Stripped Conductor)는 가능한 경우 터미네이션(Termination) 전에 검사해야 한다. 탈피 길이(Strip Length)는 적용되는 단자 또는 스플라이스 사양을 준수해야 하며 도체 연선은 손상되지 않고 올바르게 모여 있어야 한다. 절단되거나 찍히거나 누락되거나 접히거나 과도하게 벌어진 연선이 전류 용량, 기계적 강도 또는 크림프 품질을 저하시킬 수 있는 경우 허용해서는 안 된다. 의도된 도체 크림프 영역에 남아 있는 절연재도 허용할 수 없는 상태로 판단해야 한다.

크림핑된 단자는 올바른 도체 위치, 절연재 위치, 벨마우스(Bellmouth), 도체 브러시(Conductor Brush), 단자 형상 및 적용되는 경우 절연 지지(Insulation Support) 상태를 검사해야 한다. 크림프 내부에 이탈 연선(Stray Strand), 접힌 연선, 도체 크림프에 끼인 절연재, 균열된 단자 재료 또는 과도한 변형이 존재해서는 안 된다. 중요 크림프 특성은 검증된 터미네이션 공정(Qualified Termination Process)에서 요구하는 경우 크림프 높이(Crimp Height)와 같은 치수 측정을 통해 평가해야 한다.

단자를 커넥터 하우징에 삽입한 후에는 단자 고정 상태(Terminal Retention)를 확인해야 한다. 각 단자는 완전히 삽입되어 지정된 1차 잠금 구조(Primary Locking Feature)에 체결되어야 하며, 2차 잠금 장치(Secondary Lock) 또는 단자 위치 보증 장치(Terminal Position Assurance)가 지정된 경우 완전하게 설치되어야 한다. 커넥터 체결, 진동 또는 로봇 운용 중 빠져나올 수 있는 불완전 삽입 접점을 검출하기 위해 가벼운 고정력 확인 또는 승인된 검사 방법을 사용할 수 있다.

커넥터 하우징(Connector Housing)은 균열, 변형, 오염, 손상된 래치(Latch), 파손된 극성 구조(Polarization Feature) 또는 잘못된 부품 선정 여부를 검사해야 한다. 캐비티 번호와 접점 배치(Contact Population)는 승인된 커넥터 정의와 일치해야 한다. 커넥터에 실(Seal), 백셸(Backshell), 커버, 스트레인 릴리프(Strain Relief) 부품 또는 기타 액세서리가 사용되는 경우 이들 부품은 올바르게 설치되어야 하며 체결, 잠금 또는 전기 접점 결합을 방해해서는 안 된다.

개별 전선 실(Individual Wire Seal)과 캐비티 실(Cavity Seal)은 올바른 크기, 위치, 방향 및 물리적 상태를 검사해야 한다. 실은 절단되거나 비틀리거나 접히거나 위치가 이탈하거나 과도하게 압축되어서는 안 된다. 전선 절연재 외경은 실의 적용 범위와 호환되어야 하며, 필요한 경우 미사용 캐비티에는 승인된 캐비티 플러그(Cavity Plug)를 설치해야 한다. 단 하나의 밀봉 요소가 누락되거나 손상되어도 정상적으로 조립된 커넥터 전체의 환경 성능을 저하시킬 수 있다.

스플라이스는 승인된 회로 정의 및 스플라이스 공정에 따라 검증해야 한다. 검사에서는 올바른 전선 조합, 도체 크기, 스플라이스 부품, 크림프 상태, 절연 복원, 밀봉 및 적용되는 경우 식별 정보를 확인해야 한다. 스플라이스에는 허용 한계를 초과하는 노출 도체가 존재해서는 안 되며, 불완전한 밀봉, 과열, 과도한 강성 또는 조립 과정에서 발생한 기계적 손상의 흔적이 없어야 한다.

열수축 튜브 및 기타 스플라이스 보호재는 완전히 수축되어 의도된 보호 영역에 정확하게 위치해야 한다. 접착제 내장 재료(Adhesive-Lined Material)가 지정된 경우 주변 형상에 영향을 미치는 과도한 접착제 유출 없이 적절한 밀봉이 이루어진 흔적을 확인해야 한다. 탄 절연재, 불완전한 수축, 내부 오염물질, 급격한 전이부 또는 손상된 튜브가 환경 보호나 기계적 내구성을 저하시킬 경우 불합격 처리해야 한다.

차폐 케이블 터미네이션(Shielded Cable Termination)은 접지 및 전자파 적합성(EMC) 설계와 일치하는 연속성과 형상을 갖는지 검사해야 한다. 차폐 브레이드(Shield Braid), 포일(Foil), 드레인 와이어(Drain Wire), 백셸 또는 차폐 크림프(Shield Crimp)는 과도한 제거 또는 통제되지 않은 피그테일 길이 없이 지정된 위치에 터미네이션되어야 한다. 또한 차폐 터미네이션이 신호 도체, 커넥터 캐비티 또는 관련 없는 접지 구조와 의도하지 않은 접촉을 만들지 않는지 확인해야 한다.

트위스트 페어 및 통신 배선(Twisted-Pair and Communication Wiring)은 분기 및 터미네이션 전반에서 요구되는 페어 관계(Pair Relationship)를 유지해야 한다. 커넥터 또는 스플라이스 주변의 과도한 꼬임 해제, 잘못된 페어링, 통제되지 않은 분기 길이, 손상된 차폐 또는 클램프로 인한 변형은 해당 인터페이스 요구사항에 따라 평가해야 한다. CAN, CAN FD, 이더넷(Ethernet), 엔코더(Encoder), 카메라 및 기타 통신 회로는 육안으로 확인되는 도통 상태만으로 신호 무결성(Signal Integrity)을 입증할 수 없으므로 추가 검사가 필요할 수 있다.

하네스 치수는 승인된 치수 정의(Dimensional Definition)에 따라 검증해야 한다. 전체 길이, 분기 길이, 브레이크아웃 위치(Breakout Location), 커넥터 방향, 보호 피복 경계 및 기타 관리 대상 치수는 규정된 공차 이내를 유지해야 한다. 검사자와 공급업체가 반복 가능한 결과를 얻을 수 있도록 측정 방법에는 정의된 기준점을 사용해야 한다. 과도한 치수 편차는 설치 시 인장, 간섭, 부적절한 서비스 루프(Service Loop) 또는 제어되지 않은 움직임을 발생시킬 수 있다.

어셈블리에 포함된 하네스 배선 관련 부품은 클립(Clip), 클램프(Clamp), 타이(Tie), 브래킷(Bracket), 그로밋(Grommet) 및 기타 고정 부품(Retention Component)이 올바르게 설치되었는지 검사해야 한다. 리테이너(Retainer)는 규정된 위치와 방향으로 설치되어야 하며 절연재 또는 통신 케이블을 압착해서는 안 된다. 케이블 타이는 과도하게 조여서는 안 되며 날카롭게 절단된 끝단이 작업자 상해 또는 하네스 마모 위험을 발생시켜서는 안 된다. 고정 하드웨어는 필요한 하네스 유연성을 제한하지 않으면서 견고하게 유지되어야 한다.

보호 피복(Protective Covering)은 올바른 재료, 위치, 적용 범위 및 상태를 확인해야 한다. 브레이디드 슬리브(Braided Sleeve), 코루게이트 전선관(Corrugated Conduit), 내마모 보호재(Abrasion Protection), 열 보호 슬리브(Thermal Sleeve), 테이프, 부트(Boot), 에지 보호재(Edge Protection)는 취약한 케이블 구간을 노출시키지 않고 지정된 영역을 보호해야 한다. 보호 피복은 날카로운 모서리, 과도한 압착, 배수 방해 또는 움직임 제한을 발생시켜서는 안 되며 슬리브와 전선관 끝단은 예상되는 진동과 정비 취급 조건에서도 견고하게 유지되어야 한다.

라벨 및 식별 마킹(Label and Identification Marking)은 정확성, 판독성, 위치 및 내구성을 검사해야 한다. 하네스 부품 번호, 개정, 커넥터 식별자, 전선 라벨, 분기 라벨 및 기타 필수 마킹은 승인된 문서와 일치해야 한다. 라벨은 밀봉면을 덮거나 커넥터 잠금 구조를 방해하거나 클램프와 간섭하거나 심한 굽힘 영역에 위치해서는 안 된다. 누락되거나 판독할 수 없거나 잘못된 식별 정보는 형상 관리 결함(Configuration-Control Defect)으로 처리해야 한다.

전기적 도통 시험(Electrical Continuity Testing)은 정의된 소스에서 목적지까지 모든 필수 회로를 검증해야 한다. 시험은 단선(Open Circuit)을 검출해야 하며 시험 시스템이 지원하는 경우 회로 간 의도하지 않은 단락(Unintended Short)과 오결선(Cross-Connection)도 검출해야 한다. 도통 시험의 합격 여부는 작업자가 임의로 작성한 기준이 아니라 승인된 배선 정의에 따라 결정해야 한다. 시험 치구(Test Fixture)와 시험 프로그램도 형상 관리 대상이어야 하며 오래된 시험 데이터가 변경된 하네스를 잘못 승인하지 않도록 해야 한다.

단순한 도통 시험보다 높은 수준의 보증이 필요한 회로에는 저항 측정(Resistance Measurement)을 적용해야 한다. 고전류 전력 회로, 접지 경로, 안전 회로, 장거리 도체 및 중요 스플라이스 네트워크에는 최대 저항 기준(Maximum Resistance Criteria)이 필요할 수 있다. 필요한 경우 측정 방법은 치구 및 리드선 저항을 고려해야 한다. 예상보다 높은 저항은 불량 크림프, 손상된 연선, 잘못된 전선 굵기, 오염된 접점 또는 불량 스플라이스를 나타낼 수 있다.

고전압, 안전 필수 분리(Safety-Critical Separation) 또는 조밀하게 배치된 전력 회로를 포함하는 하네스에는 절연 및 유전체 검증(Insulation and Dielectric Verification)이 필요할 수 있다. 시험은 서로 절연되어야 하는 회로 사이 또는 회로와 노출된 전도성 구조 사이에 의도하지 않은 전도 경로가 존재하지 않는지 확인해야 한다. 시험 전압, 지속 시간, 누설 한계(Leakage Limit) 및 적용 제외 조건은 생산 현장에서 임의로 선정하지 않고 관련 전기 시험 요구사항에 따라 정의해야 한다.

기계적 인장 또는 고정력 시험(Mechanical Pull or Retention Testing)은 필요한 경우 승인된 공정에 따라 수행해야 한다. 대표 크림프 샘플은 도체 고정력을 검증하기 위해 파괴 시험을 수행할 수 있으며 커넥터 접점에는 비파괴 고정력 검사를 적용할 수 있다. 시험 빈도와 합격 한계는 전선 크기, 단자 계열, 생산 공정 및 위험도를 반영해야 한다. 인장 시험에 합격했다고 해서 올바른 크림프 치수와 육안 작업 품질 검사가 불필요해지는 것은 아니다.

고전류 터미네이션(High-Current Termination)은 작은 결함도 상당한 국부 발열을 발생시킬 수 있으므로 집중적인 검사가 필요하다. 링 단자(Ring Terminal), 러그(Lug), 버스바 연결(Busbar Connection), 배터리 인터페이스 및 전력 분배 터미네이션은 올바른 도체 준비, 크림프 상태, 접촉면 청정도, 하드웨어 및 스트레인 릴리프 상태를 확인해야 한다. 조립 토크가 하네스 제조 범위에 포함되는 경우 규정된 토크와 필요한 토크 확인 마킹(Witness Marking)을 검증하고 기록해야 한다.

안전 관련 하네스 회로(Safety-Related Harness Circuit)는 기능적 중요성에 적합한 수준의 검사 엄격성을 적용해야 한다. 비상 정지(Emergency Stop), 제동, 안전 센서, 컨택터(Contactor), 이중화 전원 및 기타 안전 기능은 올바른 회로 식별, 분리, 터미네이션 및 배선 관련 특성을 확인해야 한다. 검사는 공통으로 손상된 보호재, 의도하지 않은 공통 스플라이스 또는 잘못된 커넥터 접점 배치와 같이 이중화 기능을 무력화할 수 있는 공통 원인 결함(Common-Cause Defect)을 식별해야 한다.

최종 하네스 검사(Final Harness Inspection)는 어셈블리가 청결하며 느슨한 전선 연선, 금속 파편, 공정 잔류물, 이물질, 임시 라벨 또는 승인되지 않은 수리 흔적이 없는지 확인해야 한다. 커넥터는 보관 및 운송 중 오염되지 않도록 보호하는 것이 바람직하다. 완성된 하네스는 로봇에 설치되기 전에 단자, 실, 분기, 라벨 및 보호 피복이 손상되지 않도록 적절하게 포장해야 한다.

부적합 상태(Nonconforming Condition)는 적용 가능한 품질 관리 프로세스(Quality Process)에 따라 문서화해야 한다. 재작업(Rework) 또는 수리(Repair)는 승인된 방법에 따라 수행해야 하며 작업자가 결함을 수정할 수 있다고 판단한다는 이유만으로 임의로 수행해서는 안 된다. 수리된 영역은 필요에 따라 재검사하고 재시험해야 한다. 반복되는 크림프, 밀봉, 치수 또는 식별 문제는 공구, 교육, 재료 또는 문서상의 결함을 의미할 수 있으므로 반복 결함은 공정 조사(Process Investigation)로 이어져야 한다.

검사 기록(Inspection Record)은 제품 및 제조 공정에 적합한 추적성을 제공해야 한다. 기록에는 하네스 부품 번호, 개정, 일련번호 또는 로트 정보, 검사 날짜, 검사자, 시험 장비, 시험 프로그램 개정, 측정 특성 및 부적합 처리 결과가 포함될 수 있다. 중요 로봇 시스템 또는 안전 관련 적용 분야에서는 현장 고장을 생산 재료, 공구, 공정 및 검증 결과까지 추적할 수 있도록 보다 광범위한 기록이 필요할 수 있다.

검사 장비(Inspection Equipment)는 평가 대상 특성에 적합해야 하며 적용되는 품질 시스템에 따라 관리해야 한다. 크림프 마이크로미터(Crimp Micrometer), 인장 시험기(Pull Tester), 도통 시험기(Continuity Tester), 저항계(Resistance Meter), 절연 내력 시험기(Dielectric Tester), 토크 공구(Torque Tool), 치수 게이지(Dimensional Gauge), 시험 치구는 필요한 경우 정의된 주기에 따라 교정 또는 검증해야 한다. 부적절하거나 관리되지 않은 장비에서 얻은 검사 데이터는 제품 적합성을 입증하는 신뢰성 있는 근거로 간주해서는 안 된다.

검사 계획(Inspection Plan)은 모든 하네스에서 검증하는 특성과 샘플링 또는 공정 적격성(Process Qualification)을 통해 관리하는 특성을 구분해야 한다. 회로 도통, 형상 식별 및 주요 작업 품질 특성은 전수 검사가 필요할 수 있는 반면 파괴 인장 시험은 일반적으로 대표 샘플을 대상으로 수행한다. 샘플링 결정은 생산량, 공정 안정성, 결함의 영향, 안전 중요성 및 후속 시험에서 고장을 검출할 수 있는 능력을 고려해야 한다.

검사 기준은 하네스 도면, BOM, 스플라이스 및 터미네이션 요구사항, 배선 규칙(Routing Rules), 커넥터 표준 및 관련 전기 시험 요구사항과 항상 동기화되어야 한다. 전선 굵기, 단자 유형, 실, 분기 치수, 커넥터 접점 배치 또는 보호 방식에 영향을 미치는 설계 변경이 발생하면 관련 검사 기준도 함께 검토해야 한다. 엔지니어링 형상이 변경된 이후에도 제조에서 구형 합격 기준(Obsolete Acceptance Limit)을 계속 사용해서는 안 된다.

통제된 하네스 검사 시스템(Controlled Harness Inspection System)은 제조된 어셈블리가 로봇에 통합되기 전에 의도된 엔지니어링 설계에 부합한다는 객관적인 증거를 제공한다. 형상 검증, 작업 품질 검사, 치수 검사, 전기 시험, 기계적 검증, 추적성 및 결함의 통제된 처리를 결합하면 로봇 플랫폼 전반에서 간헐적 고장(Intermittent Fault), 과열, 수분 침투(Water Ingress), 조립 오류 및 현장 고장(Field Failure)을 줄일 수 있다.
