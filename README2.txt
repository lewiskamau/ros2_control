
This repository enables you run create a custom node for Hardware Interface.

You can use 1. Actuator Interface
            2. Sensor Interface
            3. System interface.

             ACTUATOR INTERFACE
Actuator Interface: An actuator interface is a hardware interface that allows a system to control actuators.
Actuators are devices responsible for converting electrical signals into physical action.
This interface typically includes methods for sending commands to the actuators, such as activating or deactivating them, setting their position or speed, etc.

Example usage: In a robotic arm system, the actuator interface would be used to control the motors responsible for moving the arm.
           namespace ros2_control_demo_example_6
{
class RRBotModularJoint : public hardware_interface::ActuatorInterface
{
public:
  RCLCPP_SHARED_PTR_DEFINITIONS(RRBotModularJoint);

              SENSOR INTERFACE
Sensor Interface: A sensor interface is a hardware interface that allows a system to receive data from sensors.
Sensors are devices that detect physical properties and convert them into electrical signals.
The sensor interface typically includes methods for reading sensor data, configuring sensor parameters, and handling sensor events
           
            namespace ros2_control_demo_example_5
            {
            class ExternalRRBotForceTorqueSensorHardware : public hardware_interface::SensorInterface
            {
            public:
            RCLCPP_SHARED_PTR_DEFINITIONS(ExternalRRBotForceTorqueSensorHardware);

              SYSTEM INTERFACE
System Interface: A system interface is a hardware interface that facilitates communication between different components or systems within a larger system.
This interface abstracts the interactions between subsystems, allowing them to exchange data and commands seamlessly.

ie 
            namespace ros2_control_demo_example_2
            {
            class DiffBotSystemHardware : public hardware_interface::SystemInterface
            {
            public:
            RCLCPP_SHARED_PTR_DEFINITIONS(DiffBotSystemHardware);

To create your own custom HardwareInterface :
    A. Go to ros2_control/hardware_interface/include
/hardware_interface/
    B. Choose the interface you want to use.
    C. Create your custom node that inherits from any of the 3 Nodes.
    D. The parent node should guide you on creating your custom node.