# Constrained Device Application (Connected Devices)

## Lab Module 09

Be sure to implement all the PIOT-CDA-\* issues (requirements) listed at [PIOT-INF-09-001 - Lab Module 09](https://github.com/orgs/programming-the-iot/projects/1#column-10488503).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do?

In module 9, I choose CDA as CoAP async client. The implementation allows the CDA to talk to my GDA CoAP server using five operations: discover available resources, GET data from the server, PUT/POST sensor data to the server, DELETE data, and OBSERVE a resource.

How does your implementation work?

The core component is AsyncCoapClientConnector, which wraps the aiocoap Python library. Because the rest of the app runs on regular threads, the connector runs its own background asyncio event loop and uses asyncio.run_coroutine_threadsafe() to safely bridge the two worlds. Each operation, GET, PUT, POST, DELETE, and OBSERVE, follows the same pattern: a public method builds the target resource path and schedules an async coroutine, the coroutine constructs and sends the CoAP message, and a response callback decodes the JSON payload and passes the  
data to the rest of the app. OBSERVE keeps a persistent subscription open, streaming updates from the server in a loop until explicitly cancelled.

### Code Repository and Branch

NOTE: Be sure to include the branch (e.g. https://github.com/programming-the-iot/python-components/tree/alpha001).

URL: https://github.com/TELE6530-spring2026-WEICHENG/cda-python-components/tree/lab9

### UML Design Diagram(s)

NOTE: Include one or more UML designs representing your solution. It's expected each
diagram you provide will look similar to, but not the same as, its counterpart in the
book [Programming the IoT](https://learning.oreilly.com/library/view/programming-the-internet/9781492081401/).

![Class UML diagram](docs/UML/CDA9.png)

### Unit Tests Executed

NOTE: TA's will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- test_ConfigUtilDefault
- test_ConfigUtilCustom
- test_SystemCpuUtilTask
- test_SystemMemUtilTask
- test_ActuatorData
- test_SensorData
- test_SystemPerformanceData
- test_HumiditySensorSimTask
- test_PressureSensorSimTask
- test_TemperatureSensorSimTask
- test_HumidifierActuatorSimTask
- test_HvacActuatorSimTask

### Integration Tests Executed

NOTE: TA's will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- test_ConstrainedDeviceApp
- test_SystemPerformanceManager
- test_SensorAdapterManager
- test_ActuatorAdapterManager
- test_DeviceDataManagerNoComms
- test_SenseHatEmulatorQuickTest
- test_HumidityEmulatorTask
- test_PressureEmulatorTask
- test_TemperatureEmulatorTask
- test_HumidifierEmulatorTask
- test_HvacEmulatorTask
- test_LedDisplayEmulatorTask
- test_SensorEmulatorManager
- test_ActuatorEmulatorManager
- test_SystemPerformanceManager
- test_DataIntegrationTest

---

- testConnectAndDisconnect() in test_MqttClientConnector
- testConnectAndCDAManagementStatusPubSub() in test_MqttClientConnector
- testActuatorCmdPubSub() in test_MqttClientConnector
- Publish and subscribe integration test - using two terminal

---

- test_CoapAsyncClientConnectorTest - testConnectAndDiscover(), testGetActuatorCommandCon(), testGetActuatorCommandNon(), testPutSensorMessageCon(), testPutSensorMessageNon(), testPostSensorMessageCon(), testPostSensorMessageNon(), testActuatorCommandObserve()

EOF.
