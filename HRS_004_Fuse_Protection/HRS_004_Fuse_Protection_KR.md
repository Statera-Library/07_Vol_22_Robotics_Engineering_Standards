**Volume 22. Hills Robotics Engineering Standards**

# Chapter 04. HRS-004 Fuse Protection

## 04.01. Fuse Selection Table

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

퓨즈 선정표(Fuse Selection Table)는 로봇 전기 시스템(Robotics Electrical Systems)의 과전류 보호 장치(Overcurrent Protection Device)를 선정하기 위한 표준화된 방법을 정의한다. 이는 배터리 전원 공급(Battery Feed), 전력 분배 장치(Power Distribution Unit), 모터 드라이브(Motor Drive), 컴퓨팅 장비(Computing Equipment), 센서(Sensor), 액추에이터(Actuator), 보조 부하(Auxiliary Load), 하위 분기 회로(Downstream Branch Circuit)에 적용된다. 퓨즈(Fuse)는 정상 동작 전류, 과도 기동 전류(Transient Startup Current), 예상되는 단시간 과부하를 허용하면서 배선과 연결 장비를 보호하도록 선정해야 한다.

각 보호 회로(Protected Circuit)는 공칭 시스템 전압(Nominal System Voltage), 최대 연속 부하 전류(Maximum Continuous Load Current), 예상 과도 전류(Transient Current), 도체 허용전류(Conductor Ampacity), 환경 온도(Environmental Temperature), 예상 고장 전류(Prospective Fault Current)를 기준으로 평가해야 한다. 퓨즈는 연결된 장치의 공칭 전류만으로 선정해서는 안 된다. 커넥터(Connector), 단자(Terminal), 스플라이스(Splice), 와이어 하니스 구간(Wire Harness Segment), 하위 전자장치를 포함한 전체 회로의 전기적 특성을 기준으로 허용 가능한 보호 수준을 결정해야 한다.

퓨즈의 연속 전류 정격(Continuous Current Rating)은 정상적인 부하 변동으로 인해 불필요한 차단(Nuisance Opening)이 발생하지 않도록 충분한 동작 여유를 제공해야 한다. 일반적인 엔지니어링 초기 기준으로 연속 운전 전류는 적용 가능한 모든 디레이팅 계수(Derating Factor)를 반영한 후의 실효 퓨즈 전류 용량보다 낮게 유지해야 한다. 최종 여유율은 단일한 고정 비율이 아니라 퓨즈 기술, 주변 온도, 인클로저 조건(Enclosure Condition), 제조사 특성, 부하 프로파일(Load Profile)을 반영하여 결정해야 한다.

퓨즈 전압 정격(Voltage Rating)은 정상 상태 및 합리적으로 예상 가능한 비정상 상태에서 보호 회로에 발생할 수 있는 최대 전압 이상이어야 한다. 직류 시스템(DC System)은 동등한 교류 전류보다 직류 고장 전류를 차단하기가 어렵기 때문에 특별한 주의가 필요하다. 저전압 또는 교류 용도로만 승인된 장치를 문서화된 적격성 검증(Qualification) 없이 고전압 직류 배터리, 추진 시스템, 액추에이터 또는 에너지 저장 회로에 대체 적용해서는 안 된다.

선정된 퓨즈의 차단 용량(Breaking Capacity)은 설치 지점에서 발생 가능한 최대 예상 단락 전류(Prospective Short-Circuit Current)를 초과해야 한다. 배터리에 직접 연결된 회로는 낮은 전원 임피던스(Source Impedance)와 높은 저장 에너지 때문에 정상 운전 전류보다 훨씬 큰 고장 전류를 발생시킬 수 있다. 따라서 배터리 내부 저항, 케이블 임피던스, 접촉 저항, 병렬 에너지원, 직류 링크 커패시턴스(DC-Link Capacitance) 등 초기 고장 전류를 증가시킬 수 있는 요소를 함께 고려해야 한다.

시간-전류 특성(Time-Current Characteristic)은 보호 대상 부하의 동작 특성과 일치시켜야 한다. 허용 가능한 과부하 에너지가 제한적인 회로에는 일반적으로 속단형 보호(Fast-Acting Protection)가 적합하며, 모터, 용량성 입력(Capacitive Input), 직류-직류 변환기(DC/DC Converter), 컴퓨팅 시스템 등 일시적인 돌입전류(Inrush Current)가 발생하는 부하에는 지연형 특성(Time-Delay Characteristic)이 필요할 수 있다. 정상적인 과도 현상은 허용하면서 도체나 부품이 열적 한계를 초과하기 전에 손상성 고장을 차단해야 한다.

와이어 보호(Wire Protection)는 퓨즈 선정의 핵심 제약 조건이다. 퓨즈 정격과 시간-전류 응답은 보호 경로에서 가장 작은 도체의 허용 전류 및 열적 내량(Thermal Withstand)과 협조되어야 한다. 커넥터 접점, 단자, 인쇄회로기판 배선(PCB Trace), 배전 버스바(Distribution Bar), 스플라이스의 전류 용량이 와이어보다 낮은 경우에도 이를 검토해야 한다. 불필요한 퓨즈 차단을 제거하기 위한 목적으로만 퓨즈 용량을 증가시키는 것은 전체 보호 회로를 다시 검증하지 않는 한 허용되지 않는다.

표준 선정표(Standard Selection Table)는 모든 부하를 동일하게 취급하지 않고 회로를 기능과 전기적 동작 특성에 따라 분류해야 한다. 대표적인 범주에는 저전력 센서 및 제어 전자장치, 컴퓨팅 및 통신 장비, 조명 및 보조 장치, 전기기계식 액추에이터(Electromechanical Actuator), 모터 제어기(Motor Controller), 추진 분기 회로(Propulsion Branch), 직류-직류 변환기 입력, 배터리 배전 회로, 고에너지 전력 분기 회로가 포함된다. 각 범주에는 적절한 퓨즈 계열, 정격 범위 및 응답 특성을 적용해야 한다.

저전력 전자 회로(Low-Power Electronic Circuit)는 상위 시스템을 불필요하게 차단하지 않으면서 국부 고장(Local Fault)을 격리할 수 있도록 분기 회로 용량에 적절히 근접한 보호 수준을 적용해야 한다. 센서, 통신 장치, 마이크로컨트롤러(MCU), 전자제어장치(ECU), 인터페이스 회로에는 소구경 도체와 민감한 전자장치가 사용될 수 있으므로 도체 및 커넥터의 제한이 특히 중요하다. 내부 전자 보호 기능이 존재하더라도 외부 퓨즈는 전원 분기의 하니스 보호(Harness Protection)와 고장 격리(Fault Isolation)를 제공해야 한다.

모터 드라이브(Motor Drive)와 액추에이터 회로(Actuator Circuit)는 가속 전류(Acceleration Current), 스톨 동작(Stall Behavior), 회생 상태(Regenerative Condition), 반복적인 과도 부하를 명시적으로 고려해야 한다. 퓨즈는 예상되는 정상 운전 피크 전류를 허용하면서 지속적인 과전류 또는 단락에 대한 보호 성능을 유지해야 한다. 가능한 경우 측정 또는 검증된 전류 프로파일을 사용하여 선정해야 하며, 모터 제어기에 명시된 피크 전류 용량을 그대로 허용 가능한 연속 퓨즈 정격으로 해석해서는 안 된다.

컴퓨팅 플랫폼(Computing Platform), 그래픽 처리 장치(GPU), 산업용 PC(Industrial PC), 젯슨 계열 제어기(Jetson-Class Controller), 네트워크 스위치(Network Switch), 라이다(LiDAR), 카메라(Camera) 등의 전자 부하는 내부 커패시턴스로 인해 상당한 입력 돌입전류가 발생할 수 있다. 퓨즈 선정 시 이러한 기동 현상과 실제 과부하를 구분해야 한다. 반복적인 전원 사이클링(Power Cycling)이 예상되는 경우 개별 펄스가 공칭 차단 임계값 이하이더라도 빈번한 고전류 펄스에 의해 퓨즈가 열화될 수 있으므로 누적 열 영향(Cumulative Thermal Effect)을 고려해야 한다.

배터리 및 전력 분배 장치(PDU) 적용에서는 가능한 경우 하위 회로의 고장이 가장 가까운 적절한 보호 장치에 의해 차단되도록 보호 계층(Protection Hierarchy)을 구성해야 한다. 따라서 메인 배터리 보호(Main Battery Protection), PDU 입력 보호, 분기 퓨즈(Branch Fuse), 장비 로컬 보호(Local Equipment Protection)는 독립적으로 선정하는 것이 아니라 상호 보호 협조(Protection Coordination)를 고려해야 한다. 이러한 구조는 고장 범위를 제한하고 영향을 받지 않은 로봇 기능을 유지하도록 지원한다.

환경 디레이팅(Environmental Derating)은 퓨즈가 제조사의 정격 기준 조건과 다른 환경에서 동작할 경우 적용해야 한다. 높은 주변 온도, 밀폐된 PDU 패키징, 인접 발열 부품, 제한된 공기 흐름, 진동, 반복적인 열 사이클(Thermal Cycling)은 실제 전류 용량과 수명에 영향을 줄 수 있다. 퓨즈 홀더(Fuse Holder)와 단자 역시 동일하게 고려해야 하며, 과도한 접촉 저항은 퓨즈 소자 자체가 공칭 정격 이내에서 동작하더라도 국부적인 발열을 발생시킬 수 있다.

승인된 각 퓨즈 선정에 대한 엔지니어링 문서(Engineering Documentation)에는 회로명, 시스템 전압, 정상 전류, 최대 연속 전류, 과도 전류 또는 돌입전류, 와이어 게이지(Wire Gauge), 도체 허용전류, 퓨즈 기술, 공칭 퓨즈 정격, 전압 정격, 차단 정격(Interrupt Rating), 응답 특성, 적용된 디레이팅 가정을 기록해야 한다. 제조사 부품 번호(Manufacturer Part Number)와 승인된 대체품은 비공식적인 부품 대체가 아니라 해당 HRS 퓨즈 자재명세서 표준(Fuse BOM Standard)을 통해 관리해야 한다.

기술적으로 가능한 경우 표준화된 선호 정격(Standardized Preferred Rating)을 사용하여 재고 복잡성, 제조 편차, 서비스 오류를 줄여야 한다. 선호 장치로 충분한 보호 성능이나 과도 전류 허용 성능을 확보할 수 없다는 분석 결과가 있는 경우 비표준 정격을 적용할 수 있다. 이러한 예외 사항은 회로 분석 및 검증 근거와 함께 문서화하여 향후 설계 변경 과정에서 의도적으로 선정된 보호 특성이 잘못 대체되지 않도록 해야 한다.

퓨즈 설치 위치(Fuse Placement)는 에너지원과 보호 장치 사이에 존재하는 비보호 도체(Unprotected Conductor)의 길이를 최소화해야 한다. 따라서 배터리 전원 분기의 1차 보호 장치는 패키징 및 안전 제약 조건이 허용하는 범위에서 전원 또는 배전 지점에 최대한 가깝게 배치해야 한다. 퓨즈 상류의 모든 도체 구간은 비보호 고에너지 경로(Unprotected High-Energy Path)로 취급하고 적절한 배선 경로, 절연, 기계적 보호, 이격 및 단락 위험 저감 대책을 적용해야 한다.

검증(Validation)은 정상 운전, 최대 지속 부하, 기동 또는 돌입 조건, 대표적인 과부하 및 적용 가능한 고장 조건을 포함해야 한다. 시험을 통해 정상적인 로봇 운전 중 불필요한 퓨즈 차단이 발생하지 않으며, 허용할 수 없는 고장 발생 시 보호 회로의 요구 열적 한계 내에서 퓨즈가 차단되는지 확인해야 한다. 실제 고장 시험이 현실적으로 어렵거나 위험한 경우 검증된 시간-전류 분석(Time-Current Analysis)과 부품 데이터를 이용하여 엔지니어링 평가를 지원할 수 있다.

HRS 퓨즈 선정표(HRS Fuse Selection Table)는 로봇 엔지니어링 체계(Robotics Engineering Framework)에 포함되는 자율이동로봇(AMR), 매니퓰레이터(Manipulator), 실외 자율주행차량(Outdoor Autonomous Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 향후 로봇 플랫폼에서 반복 가능하고 일관된 엔지니어링 의사결정을 확립하기 위한 것이다. 제품별 전기 아키텍처(Product-Specific Electrical Architecture)는 더 엄격한 요구사항을 적용할 수 있지만, 도체 보호, 충분한 차단 용량, 전압 적합성, 환경 디레이팅 및 협조된 고장 격리(Coordinated Fault Isolation)라는 기본 원칙을 완화해서는 안 된다.

## 04.02. Protection Coordination Rules

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

보호 협조(Protection Coordination)는 여러 보호 장치(Protective Device)가 상호 연계되어 동작하도록 구성함으로써 전기적 고장(Electrical Fault)을 가능한 한 가장 낮은 단계에서 격리하고, 정상적인 로봇 기능의 전원이 불필요하게 차단되지 않도록 하는 것을 의미한다. 보호 협조 전략은 제품 아키텍처(Product Architecture)에 따라 배터리 보호, 전력 분배 장치(PDU) 보호, 분기 퓨즈(Branch Fuse), 회로 차단기(Circuit Breaker), 전자식 보호 장치(Electronic Protection Device), 접촉기(Contactor), 모터 제어기(Motor Controller), 로컬 부하 보호(Local Load Protection)를 포함해야 한다.

기본 원칙은 고장 지점에 가장 가까운 보호 장치가 일반적으로 상위 보호 장치보다 먼저 동작하도록 하는 것이다. 예를 들어 센서 분기 회로에서 단락(Short Circuit)이 발생하면 메인 배터리 퓨즈(Main Battery Fuse)가 차단되는 대신 해당 분기 회로가 먼저 차단되어야 한다. 이러한 선택적 동작(Selective Operation)은 영향을 받는 전기 영역을 제한하고, 관련되지 않은 기능을 유지하며, 진단을 단순화하고, 하나의 국부 고장(Local Failure)이 전체 로봇 플랫폼을 정지시킬 가능성을 줄인다.

보호 시스템은 에너지원(Energy Source)에서 개별 부하 방향으로 계층 구조(Hierarchy)를 갖도록 설계해야 한다. 일반적인 구조는 배터리 단계 보호(Battery-Level Protection), 메인 배전 보호(Main Distribution Protection), PDU 분기 보호(PDU Branch Protection), 서브시스템 보호(Subsystem Protection), 로컬 장비 보호(Local Equipment Protection)로 구성된다. 각 단계는 명확한 보호 책임을 가져야 하며, 인접 단계는 전류 정격, 시간-전류 특성(Time-Current Characteristic), 고장 전류 처리 능력, 관련 도체 및 부품의 열적 내량(Thermal Withstand)을 기준으로 협조되어야 한다.

보호 협조는 과부하(Overload)와 단락(Short Circuit) 조건을 모두 고려해야 한다. 두 조건에서는 필요한 보호 동작이 크게 달라질 수 있기 때문이다. 중간 수준의 과부하는 하위 퓨즈나 전자식 전류 제한기(Electronic Current Limiter)가 선택적으로 동작할 수 있을 정도로 지속될 수 있지만, 심각한 단락에서는 여러 보호 장치가 순간 동작 영역(Instantaneous Operating Region)에 동시에 진입할 수 있다. 따라서 엔지니어링 분석은 하나의 가정된 고장 지점만이 아니라 예상 가능한 전체 고장 전류 범위에서 적절한 선택성(Discrimination)을 입증해야 한다.

시간-전류 특성 곡선(Time-Current Characteristic Curve)은 직렬로 연결된 보호 장치 사이의 보호 협조를 평가하는 데 사용해야 한다. 하위 보호 장치는 상위 보호 장치가 차단 조건에 도달하기 전에 해당 고장을 제거해야 하며, 제조 공차(Manufacturing Tolerance), 주변 온도, 노화(Aging), 과도 운전 조건을 고려할 수 있는 충분한 시간적 간격을 확보해야 한다. 공칭 전류 정격의 차이만으로 선택적 동작이 보장되는 것은 아니므로 특성 곡선의 중첩(Curve Overlap)을 면밀하게 검토해야 한다.

전류 정격 비율(Current-Rating Ratio)은 초기 보호 협조 지침으로 사용할 수 있지만 실제 장치 특성 분석을 대체해서는 안 된다. 공칭 정격이 서로 다른 두 퓨즈라도 고전류 동작 영역에서 특성 곡선이 상당 부분 중첩될 수 있다. 또한 퓨즈와 회로 차단기는 열적 과부하(Thermal Overload)와 자기식 또는 순간 고장(Magnetic or Instantaneous Fault)에 서로 다르게 반응할 수 있다. 따라서 보호 협조는 제조사의 시간-전류 데이터와 검증된 시스템 고장 조건을 기준으로 결정해야 한다.

사용 가능한 고장 전류(Available Fault Current)는 주요 배전 노드(Distribution Node)마다 계산하거나 보수적으로 추정해야 한다. 배터리 임피던스, 케이블 저항, 커넥터 저항, 버스바(Busbar), 접촉기, 직류-직류 변환기(DC/DC Converter), 병렬 전원, 에너지 저장 커패시터(Energy-Storage Capacitor)는 고장 전류의 크기에 영향을 줄 수 있다. 배전 경로를 따라 임피던스가 증가하므로 원격 분기에서 발생 가능한 고장 전류는 배터리 또는 메인 PDU 입력부에서 발생 가능한 전류와 상당히 다를 수 있다.

모든 보호 장치는 설치 위치에서 예상되는 고장 전류보다 높은 차단 정격(Interrupt Rating)을 가져야 한다. 보호 협조를 통해 부족한 차단 용량(Breaking Capacity)을 보완할 수는 없다. 먼저 차단될 것으로 예상되는 하위 보호 장치 역시 고장 전류를 안전하게 차단할 수 있어야 하며, 상위 보호 장치는 하위 장치가 차단에 실패하거나 고장이 하위 보호 지점보다 상류에서 발생할 경우 백업 보호(Backup Protection)를 제공할 수 있어야 한다.

도체 보호(Conductor Protection)는 전체 보호 협조 계층에서 항상 유효하게 유지되어야 한다. 각 보호 장치의 차단 시간(Clearing Time)은 와이어, 단자, 커넥터, 스플라이스(Splice), 인쇄회로기판 도체(PCB Conductor), 버스바가 허용 가능한 열적 스트레스(Thermal Stress)를 초과하지 않도록 해야 한다. 필요한 경우 일반적으로 I²t로 표현되는 전류 제곱-시간(Current-Squared Time) 기반 에너지 평가를 이용하여 고장 에너지와 도체 및 보호 대상 부품의 내량을 비교해야 한다.

모터 및 액추에이터 분기(Motor and Actuator Branch)는 모터 제어기의 보호 기능과 협조되어야 한다. 전자식 과전류 제한(Electronic Overcurrent Limiting), 상 전류 보호(Phase-Current Protection), 직류 버스 보호(DC-Bus Protection), 열 차단(Thermal Shutdown), 소프트웨어 기반 토크 제한(Software-Controlled Torque Limit)은 일부 비정상 조건에서 물리적 퓨즈보다 먼저 동작할 수 있다. 이러한 기능은 시스템 보호를 향상시킬 수 있지만 독립성, 고장 시 동작, 보호 능력이 명확하게 검증되지 않은 경우 필수적인 분기 고장 보호를 대체하는 것으로 간주해서는 안 된다.

직류-직류 변환기(DC/DC Converter)와 전력 전자 모듈(Electronic Power Module)은 추가적인 보호 협조 경계를 형성할 수 있다. 상위 및 하위 보호 장치를 선정할 때 입력 보호, 내부 전류 제한, 출력 단락 동작, 재시작 로직(Restart Logic)을 고려해야 한다. 출력 전류를 제한하는 변환기는 하위 퓨즈가 차단되지 않도록 만들 수 있으며, 입력 커패시터는 기동 또는 반복적인 전원 사이클링(Power Cycling) 중 높은 과도 전류를 발생시켜 상위 퓨즈에 영향을 줄 수 있다.

중요 부하(Critical Load) 및 안전 관련 부하(Safety-Related Load)는 시스템 수준의 고장 격리(Fault Containment) 목표와 협조되어야 한다. 비상 정지 회로(Emergency-Stop Circuit), 안전 제어기(Safety Controller), 제동 기능(Braking Function), 조향 기능(Steering Function), 필수 통신 장비 및 기타 안전 관련 부하는 관련 없는 보조 회로의 고장으로 인해 의도치 않게 전원이 차단되어서는 안 된다. 아키텍처가 허용하는 경우 안전 필수 전원 영역은 적절한 분리, 독립 분기, 이중화(Redundancy), 전용 보호를 적용하여 필수 기능의 공통 상실(Common Loss)을 방지해야 한다.

메인 배터리 보호 장치(Main Battery Protective Device)는 하위 보호 장치로 안전하게 격리할 수 없는 고에너지 고장(High-Energy Fault)에 대한 최종 보호 기능을 제공해야 한다. 해당 정격은 정상적인 시스템 수준의 피크 전류를 허용하면서 메인 도체와 배전 하드웨어를 보호해야 한다. 메인 보호 장치가 차단되면 거의 모든 로봇 전원이 제거될 수 있으므로 PDU 및 분기 보호 장치와의 보호 협조는 특히 중요하며, 최대 및 최소 예상 고장 전류 조건에서 모두 검증해야 한다.

PDU 보호(PDU Protection)는 전기 아키텍처를 관리 가능한 고장 격리 영역(Fault-Containment Zone)으로 분할해야 한다. 제품 요구사항에 따라 추진 시스템(Propulsion), 컴퓨팅(Computing), 인지 시스템(Perception), 통신(Communication), 매니퓰레이션(Manipulation), 보조 장비(Auxiliary Equipment), 안전 시스템(Safety System)을 별도의 보호 분기로 구성할 수 있다. 분기 구성은 전기적 위험과 기능적 의존성을 반영하여 하나의 영역에서 발생한 고장이 공유 도체를 통해 전파되거나 관련 없는 영역을 불필요하게 정지시키지 않도록 해야 한다.

보호 협조는 기동 순서(Startup Sequence)와 동시에 발생하는 과도 부하(Simultaneous Transient Load)도 고려해야 한다. 로봇 초기화 과정에서는 컴퓨터, 모터 제어기, 센서, 펌프, 팬, 액추에이터, 통신 장비가 짧은 시간 내에 연속 또는 동시에 활성화되어 정상 상태 소비 전류보다 상당히 큰 합산 전류(Aggregate Current)가 발생할 수 있다. 퓨즈와 회로 차단기의 협조는 검증된 기동 전류 프로파일을 허용하면서 동일한 운전 구간에서 발생하는 실제 과부하 또는 고장에 대한 보호 성능을 약화시키지 않아야 한다.

회생 에너지(Regenerative Energy)는 견인 드라이브(Traction Drive), 서보 드라이브(Servo Drive) 또는 기타 양방향 전력 변환기(Bidirectional Power Converter)가 포함된 시스템에서 고려해야 한다. 제동 또는 감속 과정에서 에너지가 부하에서 직류 버스와 배터리 방향으로 흐르면서 전류 방향과 버스 전압이 변할 수 있다. 따라서 보호 장치, 접촉기 및 배전 부품은 전기 에너지가 항상 배터리에서 부하 방향으로만 흐른다고 가정하지 말고 예상 가능한 양방향 운전 조건에서 평가해야 한다.

환경 조건(Environmental Condition)은 보호 협조 여유도(Coordination Margin)를 변화시킬 수 있다. 높은 온도는 실제 퓨즈 전류 용량을 감소시킬 수 있으며, 낮은 온도는 배터리의 고장 전류 공급 능력과 부하 기동 특성을 변화시킬 수 있다. 진동, 단자 저항, 인클로저 발열, 부품 노화, 반복적인 전류 펄스 역시 장치의 동작에 영향을 줄 수 있다. 따라서 보호 협조 검토에는 적절한 디레이팅(Derating)과 공차를 적용하여 목표 운전 환경과 서비스 수명 전체에서 선택적 보호가 유지되도록 해야 한다.

능동 차단(Active Disconnection)이 가능한 경우 고장 격리는 접촉기 및 셧다운 제어(Shutdown Control)와 협조되어야 한다. 제어기는 비정상 전류를 감지하여 퓨즈가 동작하기 전에 접촉기 개방을 명령할 수 있지만, 퓨즈는 제어 응답 능력을 초과하는 고장이나 제어 전자장치를 사용할 수 없는 상태에서 발생하는 고장에 대해 적절한 수동 보호(Passive Protection)를 계속 제공해야 한다. 따라서 능동 보호와 수동 보호는 서로 대체하는 기능이 아니라 상호 보완적인 보호 계층으로 설계해야 한다.

보호 동작은 진단성(Diagnostics)과 정비성(Serviceability)을 지원해야 한다. 분기 보호 장치가 동작하면 가능한 경우 PDU 모니터링, 전류 센싱(Current Sensing), 전압 피드백(Voltage Feedback), 고장 진단 코드(Diagnostic Trouble Code), 상위 감독 소프트웨어(Supervisory Software)를 통해 영향을 받은 전원 영역을 식별할 수 있어야 한다. 정비 문서는 보호 부품을 교체하기 전에 실제 하위 고장, 잘못 선정된 퓨즈, 손상된 커넥터, 열화된 하니스, 반복적인 과도 조건을 구분할 수 있도록 구성해야 한다.

보호 협조 검증(Protection Coordination Verification)은 정상 부하, 최대 연속 부하, 기동 및 돌입전류 이벤트, 대표적인 과부하, 하위 회로 단락, 배전 고장, 예상 가능한 고에너지 고장을 포함해야 한다. 분석 및 시험을 통해 어떤 보호 장치가 동작하는지, 차단 시간이 얼마인지, 결과적인 도체의 열적 스트레스가 어느 수준인지, 어떤 기능이 계속 전원을 공급받는지를 확인해야 한다. 예상하지 않은 상위 보호 장치의 차단이나 여러 보호 단계의 동시 동작이 발생하면 설계 승인 전에 원인을 분석하고 해결해야 한다.

최종 보호 협조 기록(Final Coordination Record)에는 보호 계층, 장치 정격, 시간-전류 특성, 예상 고장 전류, 도체 한계, 차단 정격, 환경 조건 가정, 검증 결과를 문서화해야 한다. 배터리 용량, 와이어 게이지(Wire Gauge), PDU 아키텍처, 모터 제어기, 변환기, 퓨즈 계열 또는 주요 부하 특성이 변경되는 경우 기존에 검증된 보호 협조가 더 이상 유효하지 않을 수 있으므로 반드시 재검토해야 한다.

HRS 보호 협조 규칙(HRS Protection Coordination Rules)은 엔지니어링 표준 체계 내의 자율이동로봇(AMR), 매니퓰레이터(Manipulator), 실외 자율주행차량(Outdoor Autonomous Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 기타 로봇 플랫폼에 공통적으로 적용할 수 있는 보호 설계 프레임워크를 제공한다. 그 목적은 단순히 전기적 손상을 방지하는 데 그치지 않고, 보호 장치, 배전 아키텍처, 도체, 전자장치 및 안전 기능이 하나의 협조된 시스템으로 동작하여 예측 가능한 고장 격리를 구현하는 것이다.

## 04.03. PDU Design Standard

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

전력 분배 장치(Power Distribution Unit, PDU)는 로봇 플랫폼의 주 에너지원(Primary Energy Source)과 분산 부하(Distributed Load) 사이에 제어된 전기적 인터페이스(Electrical Interface)를 제공해야 한다. PDU 설계는 정의된 아키텍처 내에서 전력 경로(Power Routing), 분기 보호(Branch Protection), 스위칭(Switching), 격리(Isolation), 모니터링(Monitoring), 진단(Diagnostics), 정비 인터페이스(Service Interface)를 통합해야 한다. PDU는 시스템 안전 개념(System Safety Concept)이 허용하는 범위에서 정상 기능의 전원을 유지하면서 예측 가능한 고장 격리(Fault Containment)를 지원해야 한다.

PDU 아키텍처는 단순히 커넥터 수나 패키징 편의성을 기준으로 구성하지 않고 제품의 전원 도메인 구조(Power-Domain Structure)를 기반으로 설계해야 한다. 추진(Propulsion), 구동(Actuation), 컴퓨팅(Computing), 인지(Perception), 통신(Communication), 안전(Safety), 보조 장비(Auxiliary Equipment), 페이로드 시스템(Payload System)은 전류 요구량, 중요도, 고장 특성, 기동 특성 및 기능적 의존성을 고려하여 적절한 배전 분기에 할당해야 한다. 서로 관련되지 않은 고에너지 부하와 민감한 전자 부하는 가능한 경우 분리해야 한다.

PDU 입력단(Input Stage)은 배터리 또는 상위 변환기(Upstream Converter)에서 공급되는 최대 연속 전류(Maximum Continuous Current)와 예상 가능한 과도 전류(Transient Current)를 처리할 수 있는 정격을 가져야 한다. 입력 도체, 단자, 버스바(Busbar), 접촉기(Contactor), 커넥터 및 보호 장치는 검증된 최대 운전 조건에서 전기적·열적 한계 이내에 있어야 한다. 설계 여유에는 제조 공차, 환경 디레이팅(Environmental Derating), 노화(Aging), 접속 저항 및 예상 가능한 제품 구성 변경을 포함해야 한다.

1차 보호(Primary Protection)는 비보호 고에너지 도체(Unprotected High-Energy Conductor)의 길이를 최소화할 수 있도록 입력 에너지 인터페이스에 가능한 한 가깝게 배치해야 한다. 입력 퓨즈(Input Fuse) 또는 회로 차단기(Circuit Breaker)는 최대 예상 고장 전류(Prospective Fault Current)에 대해 충분한 전압 정격, 전류 용량 및 차단 정격(Interrupt Rating)을 가져야 한다. 배터리에 별도의 보호 기능이 있는 경우 어느 한 장치가 모든 보호를 제공한다고 가정하지 말고 배터리 단계와 PDU 단계 보호 장치 간의 보호 협조(Protection Coordination)를 검증해야 한다.

내부 전력 분배(Internal Power Distribution)에 사용되는 도체 또는 버스바는 연속 전류, 피크 전류, 온도 상승(Temperature Rise), 전압 강하(Voltage Drop), 고장 내량(Fault Withstand)을 기준으로 선정해야 한다. 전류 밀도(Current Density)를 공칭 운전 전류만을 기준으로 결정해서는 안 된다. 고전류 경로는 불필요한 저항과 접속 지점을 최소화해야 하며, 기계 설계는 진동, 충격, 조립 편차 및 정비 작업으로 인한 풀림, 변형, 마모 또는 의도하지 않은 접촉을 방지해야 한다.

각 주요 출력 분기(Output Branch)에는 연결된 하니스와 부하에 적합한 보호 기능을 적용해야 한다. 퓨즈 또는 차단기 정격은 정상적인 기동 및 운전 과도 전류를 허용하면서 하위 경로에서 전류를 전달하는 가장 작은 요소를 보호해야 한다. 분기 보호는 HRS 퓨즈 선정(Fuse Selection) 및 보호 협조 원칙을 따라야 하며, 선택적 보호 협조(Selective Coordination)가 가능한 경우 하위 고장이 상위 PDU 또는 배터리 보호보다 먼저 국부적으로 격리되도록 해야 한다.

스위칭 장치(Switching Device)는 전류 수준과 기능 요구사항에 따라 릴레이(Relay), 접촉기(Contactor), 반도체 스위치(Solid-State Switch) 또는 지능형 전자식 전력 스위치(Intelligent Electronic Power Switch)를 사용할 수 있다. 연속 전류, 투입 전류(Making Current), 차단 전류(Breaking Current), 접촉 저항, 스위칭 수명 및 고장 시 동작을 평가해야 한다. 유도성 부하(Inductive Load)를 제어하는 장치에는 적절한 억제 회로(Suppression)를 적용하고, 반도체 스위칭 소자는 열 과부하와 과도 전기 스트레스로부터 보호해야 한다.

PDU는 시스템 아키텍처가 요구하는 경우 상시 전원(Permanently Powered), 스위칭 전원(Switched), 웨이크업 전원(Wake-Up), 안전 관련 전원(Safety-Related), 셧다운 제어 전원(Shutdown-Controlled Branch)을 구분해야 한다. 전원 시퀀싱(Power Sequencing)은 높은 돌입전류(Inrush Current)를 갖는 부하가 제어되지 않은 상태로 동시에 활성화되는 것을 방지해야 한다. 컴퓨팅 시스템, 모터 제어기, 센서, 통신 장비 및 보조 장치는 합산 기동 전류로 인한 과도한 전압 강하, 불필요한 퓨즈 차단 또는 의도하지 않은 배터리 보호 동작을 방지하기 위해 단계적 활성화가 필요할 수 있다.

안전 관련 전원 경로(Safety-Related Power Path)는 요구되는 안전 상태 개념(Safe-State Concept)에 따라 설계해야 한다. 비상 정지(Emergency Stop) 동작 시 특정 액추에이터 또는 추진 분기의 전원을 차단하면서도 안전 제어기, 제동 회로, 진단, 통신 또는 안전 상태를 달성하고 유지하는 데 필요한 기타 기능의 전원을 유지해야 할 수 있다. 따라서 PDU는 모든 안전 이벤트에서 전체 전원을 제거한다고 가정하지 말고 제어된 도메인 격리(Controlled Domain Isolation)를 지원해야 한다.

고전류 격리(High-Current Isolation)에 사용되는 접촉기는 코일 전압, 연속 전류, 고장 전류 처리 능력, 접점 용착 위험(Contact Welding Risk), 전기적 내구성(Electrical Endurance), 기계적 내구성(Mechanical Endurance)을 평가해야 한다. 필요한 경우 보조 접점(Auxiliary Contact) 또는 전압 센싱을 이용하여 명령된 상태를 확인해야 한다. 상당한 직류 링크 커패시턴스(DC-Link Capacitance)를 갖는 시스템에서는 고출력 모터 드라이브, 인버터 또는 변환기를 배터리 버스에 연결할 때 돌입전류를 제한하고 접촉기 손상을 방지하기 위해 프리차지 회로(Precharge Circuit)가 필요할 수 있다.

프리차지 기능(Precharge Function)은 메인 접촉기가 닫히기 전에 하위 용량성 버스(Capacitive Bus)의 충전을 제어해야 한다. 프리차지 저항(Precharge Resistance), 전력 정격, 동작 시간, 목표 전압 및 고장 감지 임계값은 실제 하위 커패시턴스와 시스템 전압을 기준으로 결정해야 한다. 제어 로직(Control Logic)은 메인 전력 경로를 활성화하기 전에 불완전한 프리차지, 접촉기 용착, 예상하지 않은 버스 전압 또는 과도하게 긴 프리차지 시간 등의 비정상 상태를 감지해야 한다.

전압 및 전류 모니터링(Voltage and Current Monitoring)은 의미 있는 시스템 수준 진단을 제공할 수 있는 지점에 적용하는 것이 바람직하다. 플랫폼 요구사항에 따라 PDU는 입력 전압, 총전류, 분기 전류, 스위칭 출력 전압, 접촉기 상태, 퓨즈 상태, 내부 온도 및 절연 관련 정보(Insulation-Related Information)를 모니터링할 수 있다. 측정 정확도와 샘플링 속도(Sampling Rate)는 PDU에 할당된 보호, 에너지 관리, 진단 및 예지 정비(Predictive Maintenance) 기능에 적합해야 한다.

PDU 진단(PDU Diagnostics)은 시스템 복구와 정비를 지원할 수 있을 정도로 전기적 고장을 구분해야 한다. 대표적인 감지 조건에는 입력 저전압(Undervoltage) 또는 과전압(Overvoltage), 분기 과전류, 단락, 개방 부하(Open Load), 퓨즈 차단, 접촉기 상태 불일치, 비정상 온도 및 통신 손실이 포함될 수 있다. 진단 정보는 일반적인 PDU 고장만 보고하는 것이 아니라 영향을 받은 전원 도메인을 식별하여 상위 감독 소프트웨어(Supervisory Software)가 적절한 성능 저하 운전(Degraded Operation) 또는 셧다운 전략을 적용할 수 있도록 해야 한다.

통신 인터페이스(Communication Interface)는 플랫폼의 네트워크 아키텍처와 PDU 기능의 중요도에 따라 선정해야 한다. 명령, 상태, 진단 및 에너지 정보를 전달하기 위해 CAN, CAN FD, Ethernet 또는 기타 승인된 인터페이스를 사용할 수 있다. 통신이 손실될 경우의 동작을 명확히 정의해야 하며, 필수적인 수동 보호(Passive Protection)는 네트워크 가용성과 독립적으로 계속 동작해야 한다. 안전 필수 차단 기능은 명확한 근거 없이 비안전 통신(Non-Safety Communication)에만 의존해서는 안 된다.

접지 및 귀환 전류 아키텍처(Grounding and Return-Current Architecture)는 단순한 패키징 세부사항이 아니라 PDU 설계의 일부로 정의해야 한다. 고전류 모터 및 액추에이터 귀환 경로는 스위칭 전류로 인해 센서, 컴퓨팅 장비 또는 통신 인터페이스에 허용할 수 없는 접지 전위차(Ground Offset)가 발생하지 않도록 관리해야 한다. 섀시 본딩(Chassis Bonding), 신호 기준(Signal Reference), 실드 종단(Shield Termination), 전력 귀환(Power Return), 보호 접지(Protective Grounding)는 해당 HRS 접지 및 전자기 적합성(EMC) 요구사항을 따라야 한다.

전자기 적합성(Electromagnetic Compatibility, EMC)은 PDU 경계와 내부 스위칭 노드(Switching Node) 모두에서 고려해야 한다. 접촉기, 릴레이, 직류-직류 변환기, 반도체 스위치 및 빠르게 변화하는 부하 전류는 전도성 및 방사성 방해(Conducted and Radiated Disturbance)를 발생시킬 수 있다. 적절한 억제, 필터링, 차폐, 접지, 케이블 분리 및 레이아웃을 적용하여 이러한 방해가 카메라, 라이다(LiDAR), 위성항법시스템(GNSS), 관성측정장치(IMU), 통신 네트워크, 안전 전자장치 또는 기타 민감한 로봇 서브시스템의 성능을 저하시키지 않도록 해야 한다.

열 설계(Thermal Design)는 도체 손실, 퓨즈 발열, 접촉 저항, 릴레이 또는 접촉기 손실, 반도체 손실 및 인접 열원을 고려해야 한다. 최대 연속 부하와 대표적인 과도 운전 조건에서 온도 상승을 평가해야 한다. 인클로저 온도, 공기 흐름, 장착 방향, 오염 및 주변 운전 온도 범위를 포함하여 보호 장치와 스위칭 부품이 인증된 운전 한계(Qualified Operating Limit) 내에서 유지되도록 해야 한다.

기계적 패키징(Mechanical Packaging)은 적용되는 플랫폼의 환경 조건으로부터 PDU를 보호하도록 설계해야 한다. 인클로저 재질, 밀봉(Sealing), 커넥터 방향, 스트레인 릴리프(Strain Relief), 장착 지점, 정비 접근성, 배수 및 오염 관리 방식은 실내, 실외, 이동형, 항공형 또는 보행 로봇 적용 환경에 따라 선정해야 한다. 요구되는 방진·방수 등급(Ingress Protection Rating)은 먼지, 물, 세척 공정, 결로 및 기타 제품별 위험에 대한 노출 조건과 일치해야 한다.

PDU는 안전한 제조 및 정비(Safe Manufacturing and Service)가 가능하도록 설계해야 한다. 입력 및 출력 연결부를 명확하게 식별해야 하며, 커넥터 키잉(Connector Keying) 또는 동등한 방법으로 극성 오류를 방지하는 것이 바람직하다. 정비 담당자가 보호 장치를 혼동 없이 식별할 수 있어야 한다. 교체 가능한 퓨즈는 유지보수 개념에 따라 접근할 수 있어야 하면서도 위험한 활선 도체와의 우발적 접촉이나 잘못된 정격의 퓨즈로 교체되는 것을 방지해야 한다.

설계 문서(Design Documentation)는 PDU 블록 아키텍처, 회로 인터페이스, 커넥터 핀 할당(Connector Pin Assignment), 와이어 및 버스바 정격, 보호 장치, 스위칭 장치, 모니터링 채널, 통신 인터페이스, 접지 전략, 열적 한계 및 진단 동작을 정의해야 한다. 자재명세서(Bill of Materials, BOM)는 승인된 부품과 적격 대체 부품을 명시해야 한다. 전기 도면에서는 전원 측(Source-Side), 보호 회로, 스위칭 회로, 비스위칭 회로, 안전 관련 회로 및 정비용 전원 경로를 명확하게 구분해야 한다.

PDU 검증(PDU Verification)은 최대 연속 부하, 복합 분기 부하(Combined Branch Loading), 기동 및 돌입전류 시퀀스, 전압 강하, 온도 상승, 과부하, 하위 단락, 보호 협조, 스위칭 내구성, 비정상 접촉기 동작, 통신 손실 및 관련 환경 조건을 포함해야 한다. 검증을 통해 고장이 의도된 전원 도메인 내에서 격리되고 도체, 커넥터, 스위칭 장치 및 보호 부품이 허용 가능한 한계 내에서 유지되는지 확인해야 한다.

배터리 전압, 배터리 용량, 최대 고장 전류, 분기 부하, 와이어 게이지(Wire Gauge), 커넥터 계열, 퓨즈 정격, 접촉기, 스위칭 장치, PDU 인클로저, 열 환경 또는 전원 도메인 아키텍처가 변경되는 경우 영향성 검토(Impact Review)를 수행해야 한다. 고장 전류, 열 성능, 보호 선택성(Protection Selectivity) 또는 안전 동작에 영향을 주는 변경사항은 생산 또는 현장 배포 전에 적절한 재분석(Reanalysis)과 재검증(Revalidation)을 수행해야 한다.

HRS PDU 설계 표준(HRS PDU Design Standard)은 엔지니어링 표준 체계에 포함되는 자율이동로봇(AMR), 매니퓰레이터(Manipulator), 실외 자율주행차량(Outdoor Autonomous Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 관련 로봇 시스템에 공통적인 전력 분배 프레임워크(Power-Distribution Framework)를 확립한다. 그 목적은 PDU를 단순히 퓨즈, 릴레이, 커넥터 및 배선의 수동적인 집합으로 구성하는 것이 아니라 체계적으로 설계된 전력 관리(Power Management) 및 고장 격리 서브시스템(Fault-Containment Subsystem)으로 구현하는 것이다.

## 04.04. HV Protection Rules

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

고전압 보호(High-Voltage Protection)는 위험한 직류(DC) 또는 교류(AC) 전원 도메인을 사용하는 로봇 플랫폼에서 감전(Electrical Shock), 화재(Fire), 열 손상(Thermal Damage), 제어되지 않은 에너지 방출(Uncontrolled Energy Release), 전기적 고장 전파(Electrical Fault Propagation)를 방지해야 한다. 보호 개념은 개별 고전압 부품을 독립적으로 다루는 것이 아니라 배터리 또는 발전기에서 접촉기(Contactor), 전력 분배 장치(PDU), 변환기(Converter), 인버터(Inverter), 하니스(Harness), 커넥터(Connector), 액추에이터(Actuator), 충전기(Charger), 정비 인터페이스(Service Interface)에 이르는 전체 에너지 경로를 포함해야 한다.

고전압 도메인(High-Voltage Domain)은 제품 안전 개념(Product Safety Concept)에 따라 저전압 제어, 통신, 센싱 및 사용자가 접근할 수 있는 회로와 물리적·전기적으로 분리해야 한다. 이러한 분리는 절연(Insulation), 연면거리(Creepage), 공간거리(Clearance), 커넥터 설계, 하니스 라우팅, 인클로저 구조, 접지 및 고장 조건을 고려해야 한다. 하나의 절연 또는 패키징 고장만으로 접근 가능한 도전성 부품이나 민감한 저전압 전자장치에 제어되지 않은 위험 전압이 발생해서는 안 된다.

모든 고전압 부품은 충전 전압, 회생 과전압(Regenerative Overvoltage), 변환기 과도전압(Converter Transient), 비정상 배터리 조건을 포함하여 예상 가능한 최대 운전 전압보다 높은 전압 정격을 가져야 한다. 공칭 배터리 전압만을 설계 전압으로 사용해서는 안 된다. 또한 절연 성능이나 전기적 내량을 감소시킬 수 있는 온도, 고도, 오염, 습도, 노화(Aging), 스위칭 과도현상(Switching Transient) 및 기타 환경 요소를 평가해야 한다.

1차 과전류 보호(Primary Overcurrent Protection)는 비보호 고전압 도체(Unprotected High-Voltage Conductor)의 길이를 최소화하도록 고에너지 전원에 가능한 한 가깝게 설치해야 한다. 메인 고전압 퓨즈(Main HV Fuse) 또는 동등한 보호 장치는 파열, 지속적인 아크(Sustained Arcing), 위험 물질 방출 없이 최대 예상 고장 전류를 안전하게 차단해야 한다. 전압 정격, 차단 용량(Breaking Capacity), 시간-전류 특성(Time-Current Characteristic), I²t 성능은 배터리, 도체, 접촉기, 버스바 및 하위 보호 장치와 협조되어야 한다.

고전압 분기 보호(HV Branch Protection)는 아키텍처가 선택적 보호(Selective Protection)를 허용하는 경우 관련되지 않은 전원 도메인을 불필요하게 차단하지 않으면서 국부적인 고장을 격리해야 한다. 견인(Traction), 고출력 구동(High-Power Actuation), 페이로드(Payload), 충전(Charging), 보조 전력 변환(Auxiliary Conversion) 및 기타 주요 고전압 분기에는 독립적인 보호 장치가 필요할 수 있다. 보호 협조(Protection Coordination)는 하위 고장이 일반적으로 가장 가까운 적절한 장치에 의해 제거되고, 메인 전원 보호는 심각한 고장이나 상위 고장에 대한 백업 보호(Backup Protection)로 유지되도록 해야 한다.

고전압 접촉기(HV Contactor)는 에너지원과 하위 고전압 버스 사이에 제어된 전기적 연결 및 격리(Isolation)를 제공해야 한다. 접촉기는 연속 전류, 투입 및 차단 능력, 고장 전류 노출, 코일 특성, 전기적 내구성(Electrical Endurance), 기계적 내구성(Mechanical Endurance), 접점 용착 위험(Contact-Welding Risk)을 기준으로 선정해야 한다. 설계에서는 접촉기가 개방 실패(Fail Open), 폐쇄 실패(Fail Closed), 용착(Welding)되거나 명령된 상태와 실제 상태가 불일치하는 경우의 영향을 고려해야 한다.

하위 인버터, 모터 드라이브, 변환기 또는 기타 장비에 상당한 직류 링크 커패시턴스(DC-Link Capacitance)가 존재하는 경우 프리차지 회로(Precharge Circuit)를 적용해야 한다. 프리차지는 메인 양극 또는 음극 접촉기가 전체 전류 경로를 형성하기 전에 연결 전류(Connection Current)를 제한해야 한다. 저항값, 전력 정격, 동작 시간 및 목표 버스 전압은 실제 시스템 커패시턴스와 운전 전압을 기준으로 계산하여 접촉기와 용량성 부하가 허용된 전기적 스트레스 범위 내에 유지되도록 해야 한다.

프리차지 제어(Precharge Control)는 정상 운전을 허용하기 전에 하위 고전압 버스가 예상된 전압 프로파일에 따라 상승하는지 확인해야 한다. 허용된 시간 내에 요구 전압에 도달하지 못하면 메인 접촉기의 폐쇄를 방지하거나 적절한 안전 대응(Safe Response)을 수행해야 한다. 비정상적으로 빠른 충전, 격리 이후에도 지속되는 버스 전압 또는 접촉기 폐쇄 전 예상하지 않은 전압은 접점 용착, 배선 고장 또는 의도하지 않은 에너지 경로의 잠재적 징후로 취급해야 한다.

고전압 시스템은 실제로 격리가 이루어졌는지를 검출할 수 있는 명확한 방법을 제공해야 한다. 전원, 버스 및 관련 접촉기 경계의 전압 센싱(Voltage Sensing)을 이용하여 활성화 및 비활성화 상태를 확인할 수 있다. 안전 개념에서 요구하는 경우 접촉기 보조 피드백(Auxiliary Feedback)과 측정된 전압을 비교하여 소프트웨어 상태 또는 코일 명령만으로 격리가 이루어졌다고 판단하지 않도록 해야 한다.

고전압 도메인과 섀시 또는 접근 가능한 도전성 구조 사이의 절연 상실(Loss of Isolation)이 허용할 수 없는 위험을 발생시킬 수 있는 경우 절연 감시(Insulation Monitoring)를 적용해야 한다. 감시 개념은 시스템 전압과 안전 요구사항에 적합한 수준에서 절연 열화(Insulation Degradation)를 감지해야 한다. 감지된 열화는 진단 정보를 생성하고, 필요한 경우 절연 상태가 위험 접촉 전압, 아크 또는 2차 고장으로 발전하기 전에 제어된 셧다운(Controlled Shutdown) 또는 격리를 수행해야 한다.

고전압 인터록 개념(High-Voltage Interlock Concept)은 요구되는 경우 지정된 고전압 커넥터와 인클로저의 의도하지 않은 개방, 분리 또는 정비 접근을 감지해야 한다. 고전압 인터록 루프(HV Interlock Loop)는 커넥터, 커버, 서비스 차단 장치(Service Disconnect), 접근 패널 등에 통합할 수 있으며, 연속성이 상실되면 정의된 대응을 시작하도록 구성할 수 있다. 인터록은 물리적 접촉 보호를 보완하는 기능이며 적절한 절연, 인클로저 설계 또는 안전 정비 절차를 대체해서는 안 된다.

고전압 셧다운(HV Shutdown) 이후 저장된 전기 에너지(Stored Electrical Energy)는 해당 제품 안전 개념에서 요구하는 시간 내에 허용 가능한 수준까지 감소시켜야 한다. 직류 링크 커패시터와 기타 에너지 저장 소자는 접촉기가 개방된 이후에도 위험 전압을 유지할 수 있으므로 필요한 경우 제어된 방전 경로(Controlled Discharge Path)를 제공해야 한다. 방전 저항(Discharge Resistor)과 관련 회로는 저장 에너지, 반복 동작, 열 조건 및 셧다운과 정비 작업에서 예상 가능한 고장 모드를 처리할 수 있는 정격을 가져야 한다.

비상 정지(Emergency Stop) 동작은 위험한 추진 또는 액추에이터 에너지를 제거하는 것과 안전 상태에 도달하거나 이를 유지하는 데 필요한 전원을 유지하는 것을 구분해야 한다. 플랫폼에 따라 제동(Braking), 조향(Steering), 비행 제어(Flight Control), 안전 제어기(Safety Controller), 통신 또는 진단 기능은 고전압 격리 이후에도 저전압 전원을 필요로 할 수 있다. 따라서 셧다운 아키텍처는 어떤 도메인을 즉시 차단하고, 어떤 도메인을 방전하며, 어떤 도메인의 전원을 유지할 것인지 정의해야 한다.

고전압 하니스(HV Harness)와 커넥터는 저전압 회로와의 우발적인 오접속을 방지하고 적절한 절연, 접촉 보호(Touch Protection), 기계적 유지력(Mechanical Retention), 환경 밀봉(Environmental Sealing), 스트레인 릴리프(Strain Relief)를 제공해야 한다. 배선 경로는 마모, 압착, 날카로운 모서리, 열원, 이동 메커니즘 및 충격 영역에 대한 노출을 최소화해야 한다. 가능한 경우 고전압 도체는 명확하게 식별할 수 있어야 하며 통신 및 민감한 센서 배선과 물리적으로 분리해야 한다.

커넥터 선정(Connector Selection)은 정격 전압, 연속 및 과도 전류, 연면거리, 공간거리, 환경 밀봉, 체결 반복 내구성(Mating-Cycle Durability), 접촉 안전 구조(Touch-Safe Construction), 단자 유지력 및 진동 환경에서의 동작을 고려해야 한다. 상당한 고전압 전류를 전달하는 연결부는 접촉 저항과 온도 상승도 평가해야 한다. 커넥터와 시스템 아키텍처가 부하 상태에서 분리되도록 특별히 설계되고 검증되지 않은 경우 부하 상태에서 커넥터가 분리되지 않도록 해야 한다.

접지 및 본딩(Grounding and Bonding)은 의도하지 않은 고전류 경로나 전자기 적합성 문제를 발생시키지 않으면서 접근 가능한 도전성 부품의 전압을 제어해야 한다. 섀시 본딩(Chassis Bonding), 보호 접지(Protective Grounding), 실드 종단(Shield Termination), 고전압 절연 전략(HV Isolation Strategy)을 통합적으로 정의해야 한다. 최초 절연 고장을 감지할 수 있고 후속 고장이 섀시 또는 구조 부재를 통해 제어되지 않은 전류를 발생시키지 않도록 단일 고장 및 다중 고장 조건을 고려해야 한다.

회생 시스템(Regenerative System)은 모터 또는 액추에이터에서 직류 버스 방향으로 반환되는 에너지에 대한 보호를 고려해야 한다. 배터리의 에너지 수용 한계(Battery Acceptance Limit), 인버터 제어, 직류 버스 전압, 접촉기 상태, 제동 전략을 상호 협조하여 회생으로 인해 과도한 버스 전압이 발생하지 않도록 해야 한다. 에너지원이 회생 전력을 수용할 수 없는 경우 전기적 정격을 초과하기 전에 적절한 제어 또는 에너지 관리 대응(Energy-Management Response)을 수행하도록 아키텍처를 구성해야 한다.

충전 인터페이스(Charging Interface)는 차량 또는 로봇 내부의 고전압 보호 아키텍처와 협조되어야 한다. 충전기 출력 전압 및 전류, 배터리 접촉기, 충전 접촉기, 프리차지 동작, 극성 보호(Polarity Protection), 절연 감시, 통신 및 고장 셧다운은 제어된 충전 상태(Controlled Charging State)를 형성해야 한다. 시스템은 노출된 인터페이스가 의도하지 않게 활성화되는 것을 방지하고 호환되지 않는 전압, 비정상 연결, 절연 고장 또는 충전을 위험하게 만들 수 있는 기타 조건을 감지해야 한다.

열 보호(Thermal Protection)는 고전압 퓨즈, 버스바, 접촉기, 커넥터, 케이블, 변환기 및 기타 고전류 부품에서 발생하는 열을 고려해야 한다. 최대 연속 부하, 과도 운전, 충전, 회생 및 관련 고장 조건에서 온도 상승을 평가해야 한다. 느슨한 단자 또는 증가하는 접촉 저항으로 발생하는 국부 발열(Localized Heating)은 과전류 보호 장치를 동작시킬 정도로 전류가 증가하지 않더라도 화재 위험을 발생시킬 수 있으므로 반드시 고려해야 한다.

고전압 진단(HV Diagnostics)은 안전 제어 및 정비에 충분한 수준으로 고장을 식별해야 한다. 관련 조건에는 과전압, 저전압, 과전류, 절연 열화, 프리차지 실패, 접촉기 용착, 접촉기 상태 불일치, 예상하지 않은 버스 전압, 방전 실패, 인터록 개방, 비정상 온도 및 통신 손실 등이 포함될 수 있다. 진단 정보는 경고(Warning)와 성능 저하 운전(Degraded Operation)에서 제어된 격리 및 즉각적인 셧다운에 이르는 적절한 대응을 지원해야 한다.

정비 설계(Service Design)는 고전압 시스템을 비활성화(Disable), 격리(Isolate), 확인(Verify), 복구(Restore)하기 위한 명확한 방법을 제공해야 한다. 플랫폼에 적합한 경우 서비스 차단 장치(Service Disconnect) 또는 동등한 격리 메커니즘을 제공하는 것이 바람직하다. 정비 절차에서는 접촉기를 개방하는 것만으로 모든 위험 전압이 제거되었다고 가정하지 말고 실제 비활성 상태(De-Energization)를 확인해야 한다. 고전압 도체와 단자에 접근하려면 제품 유지보수 및 안전 전략에 부합하는 의도적인 절차가 필요해야 한다.

검증(Verification)은 정상 운전, 최대 부하, 기동, 프리차지, 접촉기 스위칭, 회생, 충전, 과부하, 단락, 절연 열화, 인터록 동작, 비상 셧다운, 저장 에너지 방전 및 대표적인 부품 고장을 포함해야 한다. 시험과 분석을 통해 예상 가능한 고장 조건에서 보호 협조, 차단 능력, 절연 성능, 열적 한계, 격리 동작 및 정의된 안전 상태(Defined Safe State)로의 전환이 적절하게 이루어지는지 확인해야 한다.

시스템 전압, 배터리 구성, 고장 전류 공급 능력, 고전압 하니스, 커넥터, 퓨즈, 접촉기, 인버터, 변환기, 충전기, 접지 전략, 절연 시스템 또는 전원 도메인 아키텍처가 변경되는 경우 고전압 보호 영향성 검토(HV Protection Impact Review)를 수행해야 한다. 전기적 스트레스, 절연, 고장 에너지, 열적 동작 또는 셧다운 시퀀스에 영향을 주는 변경사항은 생산 승인 또는 현장 적용 전에 재분석하고 적절하게 재검증해야 한다.

HRS 고전압 보호 규칙(HRS High-Voltage Protection Rules)은 엔지니어링 표준 체계 내에서 고에너지 전기 시스템을 사용하는 자율이동로봇(AMR), 매니퓰레이터(Manipulator), 실외 자율주행차량(Outdoor Autonomous Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 미래 로봇 플랫폼에 공통적으로 적용할 수 있는 안전 프레임워크(Safety Framework)를 확립한다. 그 목적은 예방(Prevention), 감지(Detection), 격리(Isolation), 방전(Discharge), 진단(Diagnostics), 안전 상태 제어(Safe-State Control)가 상호 협조된 보호 계층으로 동작하는 제어된 에너지 관리(Controlled Energy Management)를 구현하는 것이다.

## 04.05. Fuse BOM Standard

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

퓨즈 자재명세서 표준(Fuse BOM Standard)은 로봇 전기 설계에서 승인된 퓨즈 부품, 퓨즈 홀더(Fuse Holder), 단자(Terminal), 액세서리 및 관련 보호 하드웨어를 규정하고 관리하는 방법을 정의한다. 이 표준은 회로 수준의 보호 요구사항을 제조 가능한 부품 정의로 변환하여 엔지니어링 과정에서 검증된 보호 특성이 구매, 생산, 정비 및 향후 제품 개정 과정에서도 유지되도록 한다.

각 퓨즈 자재명세서(BOM) 항목에는 부품 자체뿐만 아니라 전기적 기능과 보호 대상 회로를 식별할 수 있는 정보가 포함되어야 한다. 필수 엔지니어링 속성에는 공칭 퓨즈 전류, 전압 정격, 퓨즈 기술, 응답 특성(Response Characteristic), 차단 정격(Interrupt Rating), 패키지 또는 폼 팩터(Form Factor), 장착 방식, 적용 환경 정격 및 제조사 식별 정보가 포함되어야 한다. BOM은 외형이나 공칭 전류 정격만으로 부품이 선정되는 것을 방지할 수 있을 정도로 충분한 정보를 제공해야 한다.

제조사 부품 번호(Manufacturer Part Number)는 기본 승인 부품(Primary Approved Component)을 나타내야 하며 전기적 분석 및 검증에 사용된 장치와 정확하게 일치해야 한다. 동일한 제품군 내에 여러 정격 또는 응답 특성이 존재하는 경우 제조사 시리즈명만으로는 충분하지 않다. 따라서 구매 사양에는 전류 정격, 전압 등급, 동작 속도 특성, 패키지 구성, 단자 옵션 및 기타 안전 관련 차이를 구분할 수 있는 완전한 주문 정보를 유지해야 한다.

퓨즈 전류 정격(Fuse Current Rating)은 구매 편의를 위한 값이 아니라 관리되는 엔지니어링 파라미터(Controlled Engineering Parameter)로 기록해야 한다. 이 값은 부하 전류 분석, 도체 보호(Conductor Protection), 과도 전류 평가, 환경 디레이팅(Environmental Derating), 보호 협조(Protection Coordination)를 통해 결정된 정격과 일치해야 한다. 생산 담당자가 불필요한 퓨즈 차단을 해결하기 위해 임의로 퓨즈 정격을 증가시켜서는 안 되며, 정상 기동 및 운전 과도전류의 허용 여부를 확인하지 않고 더 낮은 정격으로 대체해서도 안 된다.

전압 정격(Voltage Rating)은 물리적으로 호환되는 두 퓨즈라도 서로 다른 전압에서 차단 성능이 크게 달라질 수 있으므로 BOM에 명확하게 포함해야 한다. 승인된 장치는 예상 가능한 최대 회로 전압 이상의 전압 정격을 가져야 한다. 특히 배터리 구동 로봇에서는 지속적인 직류 아크(DC Arcing)로 인해 동등한 저전압 교류 조건보다 차단이 어려울 수 있으므로 교류(AC)와 직류(DC) 정격을 상호 교환 가능한 것으로 취급해서는 안 된다.

예상 단락 에너지(Prospective Short-Circuit Energy)가 상당할 수 있는 회로에서는 차단 정격(Interrupt Rating) 또는 차단 용량(Breaking Capacity)을 문서화해야 한다. 배터리 직결 회로, 고전류 PDU, 추진 시스템, 액추에이터 및 고전압 분기는 특히 주의가 필요하다. 대체 퓨즈는 원래 부품과 전류 및 전압 정격이 동일하다는 이유만으로 승인해서는 안 되며, 설치 위치에서 발생할 수 있는 최대 고장 전류를 안전하게 차단할 수 있는 능력도 입증해야 한다.

퓨즈 응답 유형(Fuse Response Type)은 속단형(Fast-Acting), 지연형(Time-Delay) 또는 기타 인증된 시간-전류 분류(Time-Current Classification)와 같이 제조사가 정의한 특성을 기준으로 명확하게 관리해야 한다. 동일한 전류 정격을 가진 장치라도 모터 기동, 변환기 돌입전류(Inrush Current), 용량성 충전, 과부하 및 단락에 대한 응답이 크게 다를 수 있으므로 이 파라미터는 매우 중요하다. BOM은 최초 보호 협조 분석에서 사용한 시간-전류 동작 특성을 그대로 유지해야 한다.

패키지 크기와 기계적 인터페이스(Mechanical Interface)는 전기적 정격과 독립적으로 규정해야 한다. 카트리지형(Cartridge), 블레이드형(Blade), 볼트 체결형(Bolt-Down), 인쇄회로기판 장착형(PCB-Mounted), 고전류형 또는 기타 퓨즈 구조는 서로 다른 홀더, 단자, 이격거리, 설치 토크 및 정비 절차를 요구할 수 있다. 기계적으로 호환되는 대체품을 자동으로 전기적으로 동등하다고 간주해서는 안 되며, 전기적으로 유사하더라도 기계적 통합이 유지력, 절연, 냉각 또는 접촉 보호를 저해하는 경우 사용해서는 안 된다.

퓨즈 홀더(Fuse Holder)는 일반적인 액세서리가 아니라 관리되는 전기 부품(Controlled Electrical Component)으로 취급해야 한다. 정격 전압, 연속 전류, 접촉 저항, 단자 구성, 환경 성능, 온도 정격 및 승인된 퓨즈와의 호환성을 문서화해야 한다. 특히 오염, 진동, 잘못된 조립 토크 또는 반복적인 퓨즈 교체로 접촉 저항이 증가하는 경우 고전류 회로에서는 홀더의 발열이 시스템 성능을 제한하는 요소가 될 수 있다.

단자, 버스바 인터페이스(Busbar Interface), 체결 부품(Fastener), 커버, 절연 부트(Insulating Boot) 및 기타 퓨즈 관련 하드웨어가 보호 무결성(Protection Integrity)에 영향을 주는 경우 BOM에 포함해야 한다. 고전류 볼트 체결형 퓨즈는 허용 가능한 저항을 유지하기 위해 지정된 체결 부품 크기, 재질, 와셔 구성, 조임 토크 및 접촉면 상태에 의존할 수 있다. 이러한 지원 부품을 형상 관리(Configuration Control)에서 제외하면 기술적으로 올바른 퓨즈가 전기적으로 안전하지 않은 조립체에 설치될 수 있다.

승인 제조사 목록(Approved Manufacturer List)은 의도적으로 제한하여 관리해야 한다. 통제된 퓨즈 제품군을 중심으로 표준화하면 구매 복잡성, 조립 오류, 예비 부품 재고, 검증 작업 및 정비 혼란을 줄일 수 있다. 선호 퓨즈 제품군(Preferred Fuse Family)은 여러 로봇 플랫폼에서 반복적으로 사용되는 전류 및 전압 범위를 포괄하는 것이 바람직하며, 높은 고장 전류, 고전압, 환경 노출, 질량, 패키징 또는 인증 요구사항으로 인해 필요한 경우에는 특수 부품의 예외 적용을 허용할 수 있다.

대체 부품(Alternate Part)은 가격이나 공급 가능성만이 아니라 동등성(Equivalence)을 기준으로 분류해야 한다. 적격 대체품(Qualified Alternate)은 요구되는 전압 정격, 차단 능력, 환경 성능 및 기계적 호환성을 충족하거나 초과하면서 회로 보호와 보호 협조를 유지할 수 있는 시간-전류 특성을 제공해야 한다. I²t, 디레이팅 특성, 온도 응답, 치수 또는 단자 설계의 차이는 대체 제조사 부품 번호를 승인하기 전에 검토해야 한다.

부품 공급 부족(Component Shortage)이 발생하는 경우 대체 관리(Substitution Control)가 특히 중요하다. 구매 부서는 대체품이 이미 관리되는 BOM에서 승인되어 있지 않은 한 공칭 전류 정격이 동일하다는 이유만으로 독자적으로 퓨즈를 교체해서는 안 된다. 긴급 대체(Emergency Substitution)는 엔지니어링 검토와 문서화된 승인을 필요로 한다. 보호 협조 또는 고에너지 차단 성능에 영향을 주는 경우 생산 적용 전에 분석 또는 시험을 완료해야 한다.

형상 관리 시스템(Configuration-Management System)이 이러한 분류를 지원하는 경우 BOM은 선호 부품(Preferred), 승인 대체 부품(Approved Alternate), 제한 부품(Restricted), 단종 부품(Obsolete)을 구분하는 것이 바람직하다. 선호 부품은 정상적인 생산 선택이며 승인 대체 부품은 검증된 공급 유연성을 제공한다. 제한 부품은 특정 제품 또는 전압 도메인에만 사용할 수 있다. 단종되거나 대체된 부품은 신규 생산에 의도하지 않게 적용되지 않도록 하면서 과거 제품 구성과의 추적성을 유지해야 한다.

적용 정보(Application Information)는 각 퓨즈를 의도된 전기 도메인(Electrical Domain)과 연결해야 한다. 대표적인 분류에는 저전압 전자장치, 센서 전원, 컴퓨팅, 통신, 보조 장비, 모터 및 액추에이터 분기, PDU 입력, 배터리 출력, 충전 회로 및 고전압 배전이 포함될 수 있다. 이러한 연계는 특정 전기 환경에 대해 인증된 부품이 고장 전류, 전압 또는 과도 동작 특성이 크게 다른 다른 회로에 잘못 재사용되는 것을 방지하는 데 도움이 된다.

부품 선정과 관련된 경우 환경 적격성(Environmental Qualification)을 관리 정보에 포함해야 한다. 온도 범위, 진동 내성, 습도, 밀봉, 오염 노출, 고도 및 열 사이클링(Thermal Cycling)은 퓨즈 동작과 홀더 신뢰성 모두에 영향을 줄 수 있다. 따라서 실외 차량, 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped) 또는 기타 가혹 환경에서 사용하는 부품은 공칭 전기 정격이 유사하더라도 보호된 실내 전자 인클로저에 사용되는 부품과 다른 적격성 검증이 필요할 수 있다.

퓨즈 식별(Fuse Identification)은 제조 검사와 현장 정비를 지원해야 한다. 가능한 경우 설치 후에도 정격과 부품 유형을 확인할 수 있어야 하며, 그렇지 않은 경우 라벨, 도면, 정비 문서 또는 디지털 형상 기록(Digital Configuration Record)을 통해 식별할 수 있어야 한다. 색상만을 유일한 식별 방법으로 사용해서는 안 된다. 정비 담당자는 기억이나 고장 난 퓨즈의 물리적 크기 비교에 의존하지 않고 올바른 교체 부품을 결정할 수 있어야 한다.

BOM은 회로 설계, 회로도 참조 지정자(Schematic Reference Designation), 보호 분석, 물리적 설치 및 정비 교체 사이의 추적성(Traceability)을 유지해야 한다. 각 보호 분기는 전기 도면, 하니스 문서, PDU 도면, BOM 기록, 진단 정보 및 유지보수 지침 전체에서 추적할 수 있는 고유 참조 또는 관리 식별자와 연결되어야 한다. 이러한 추적성은 하나의 플랫폼에 여러 퓨즈 정격이 설치되는 경우 발생할 수 있는 모호성을 줄인다.

엔지니어링 릴리스(Engineering Release)에서는 BOM 데이터가 전기 회로도와 보호 설계에 일치하는지 확인해야 한다. 퓨즈 정격, 전압 등급, 응답 특성, 홀더 유형 및 승인된 제조사 부품 번호를 최신 승인 회로 분석과 비교해야 한다. 회로도 주석, BOM 설명, 구매 데이터베이스, 조립 도면 및 정비 문서 사이의 불일치는 검증된 보호 동작을 훼손할 수 있으므로 생산 승인 전에 해결해야 한다.

퓨즈, 홀더, 단자, 장착 구성 또는 관련 도체가 변경되는 경우 생산 변경 관리(Production Change Control)를 통해 검토해야 한다. 외관상 사소한 변경도 접촉 저항, 열 성능, 차단 능력 또는 보호 협조를 변화시킬 수 있다. 배터리 용량, 시스템 전압, 와이어 게이지(Wire Gauge), PDU 아키텍처, 모터 제어기, 변환기 또는 부하 프로파일이 변경되는 경우에도 기존 보호 가정이 더 이상 유효하지 않을 수 있으므로 영향을 받는 퓨즈 BOM 항목을 재검토해야 한다.

수입 검사(Incoming Inspection)와 제조 품질 관리(Manufacturing Quality Control)는 가능한 범위에서 주요 퓨즈 특성을 확인해야 한다. 부품 번호, 전류 정격, 전압 정격, 패키지, 제조사 및 물리적 상태가 승인된 BOM과 일치해야 한다. 설치 관리에서는 올바른 설치 위치, 홀더 체결 상태, 단자 조립 및 지정된 체결 토크를 확인해야 한다. 부적절한 조립은 공칭 퓨즈 전류를 초과하지 않으면서도 국부 발열을 발생시킬 수 있으므로 고전류 연결부는 특히 주의해서 관리해야 한다.

정비 교체 규칙(Service Replacement Rules)은 정확하게 승인된 부품 또는 공식적으로 승인된 동등 부품만 사용하도록 요구해야 한다. 임시 바이패스(Bypass), 브리징(Bridging), 과대 정격 퓨즈 설치 또는 검증되지 않은 회로 보호 장치로의 대체는 허용해서는 안 된다. 퓨즈가 반복적으로 차단되는 경우 더 높은 정격의 부품을 설치할 근거로 판단하지 말고 고장 진단이 필요한 증거로 취급해야 한다. 퓨즈 정격을 증가시키면 열 또는 고장 에너지가 하니스나 보호 대상 장비로 전달될 수 있다.

관리되는 퓨즈 자재명세서(Controlled Fuse BOM)는 제품 수명주기(Product Lifecycle) 전체에 걸쳐 유지해야 한다. 제조사 단종, 사양 변경, 공급업체 변경, 현장 고장 데이터 및 새로운 규제 또는 환경 요구사항에 따라 승인 부품을 재평가해야 할 수 있다. 개정 이력(Revision History)은 각 제품 릴리스에 어떤 퓨즈 구성이 사용되었는지를 보존하여 생산 제품과 현장 운용 로봇이 검증된 전기 아키텍처와 일치하는 보호 하드웨어를 사용하여 정비될 수 있도록 해야 한다.

HRS 퓨즈 자재명세서 표준(HRS Fuse BOM Standard)은 엔지니어링 표준 체계 내의 자율이동로봇(AMR), 매니퓰레이터(Manipulator), 실외 자율주행차량(Outdoor Autonomous Vehicle), 화물 무인항공기(Cargo UAV), 사족보행 로봇(Quadruped), 휴머노이드(Humanoid) 및 기타 로봇 플랫폼에 공통적으로 적용할 수 있는 부품 관리 프레임워크(Component-Control Framework)를 제공한다. 그 목적은 퓨즈 선정(Fuse Selection), 보호 협조(Protection Coordination), PDU 설계(PDU Design), 고전압 보호(High-Voltage Protection) 요구사항이 관리 가능하고 추적 가능하며 제조 및 정비가 가능한 실제 보호 하드웨어에 일관되게 반영되도록 하는 것이다.
