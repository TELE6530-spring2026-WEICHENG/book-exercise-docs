# Constrained Device Application (Connected Devices)

## Lab Module 01

Be sure to implement all the PIOT-CDA-\* issues (requirements) listed at [PIOT-INF-01-001 - Lab Module 01](https://github.com/orgs/programming-the-iot/projects/1#column-9974937).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do?
In order to make this project run, I create a virtual environment where all dependencies are install correctly and designate PYTHONPATH for Python interpreter, thereby executing the project successfully.

How does your implementation work?
I insert the correct PYTHONPATH for the project environment, which allows Python interpreter know where packages are located.

### Code Repository and Branch

NOTE: Be sure to include the branch (e.g. https://github.com/programming-the-iot/python-components/tree/alpha001).

URL: https://github.com/TELE6530-spring2026-WEICHENG/book-exercise-docs

### UML Design Diagram(s)

NOTE: Include one or more UML designs representing your solution. It's expected each
diagram you provide will look similar to, but not the same as, its counterpart in the
book [Programming the IoT](https://learning.oreilly.com/library/view/programming-the-internet/9781492081401/).

### Unit Tests Executed

NOTE: TA's will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- test_ConfigUtilDefault
  Verifies that the project can load the default config file (PiotConfig.props) successfully and the crucial properties and sections can be found. The credential test is skipped for now.

- test_ConfigUtilCustom
  It verifies that ConfigUtil can load a specified configuration file which is ValidTestConfig.props at this time, and and correctly access core configuration data.

### Integration Tests Executed

NOTE: TA's will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- test_ConstrainedDeviceApp
  At this moment, we just simply initiate ConstrainedDeviceApp class, making sure it runs as we expect.

EOF.
