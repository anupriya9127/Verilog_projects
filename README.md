Digital Clock
The Digital_Clock module is a Verilog implementation of a digital clock with alarm functionality. It keeps track of seconds, minutes, and hours, and generates an alarm signal when the current time matches the specified alarm time.

Inputs
Clk_1sec: Clock input with a frequency of 1 Hz.
reset: Active high reset signal.
alarm_hour: 6-bit input representing the alarm hour.
alarm_minute: 8-bit input representing the alarm minute.
alarm_second: 8-bit input representing the alarm second.
Outputs
seconds: 6-bit output representing the current seconds.
minutes: 6-bit output representing the current minutes.
hours: 5-bit output representing the current hours.
alarm: Output signal indicating whether the current time matches the alarm time. It is high (1) when the alarm is active and low (0) otherwise.
Internal Variables
seconds: 6-bit register storing the current seconds.
minutes: 6-bit register storing the current minutes.
hours: 5-bit register storing the current hours.
alarm_hour: 6-bit register storing the alarm hour.
alarm_minute: 8-bit register storing the alarm minute.
alarm_second: 8-bit register storing the alarm second.
alarm: Register storing the alarm status.
Functionality
The clock operates based on the Clk_1sec signal. On each positive edge of Clk_1sec, the clock updates the time by incrementing the seconds and checking for rollovers. When the seconds reach 60, they reset to 0, and the minutes are incremented. Similarly, when the minutes reach 60, they reset to 0, and the hours are incremented. When the hours reach 24, they reset to 0, completing a full day cycle.

The reset signal is used to reset the time. When reset is asserted (1), the seconds, minutes, and hours are all set to 0.

The alarm functionality compares the current time (seconds, minutes, and hours) with the specified alarm time (alarm_hour, alarm_minute, and alarm_second). If they match, the alarm output is set to 1, indicating that the alarm is active. Otherwise, alarm is set to 0.

Make sure to provide the necessary input signals (Clk_1sec, reset, alarm_hour, alarm_minute, and alarm_second) and observe the outputs (seconds, minutes, hours, and alarm) to utilize the digital clock module effectively.
