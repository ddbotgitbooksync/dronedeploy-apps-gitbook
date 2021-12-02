# Sample Flight Log

This is our latest specification for flight logs. Our support for any other version of flight logs are depricated. If you received a flight log from customer that is not upto this specification, we recommend that you notify users with some messaging that an older version of flight log was used.

## Download our sample flight log

iOS - {% file src="../../.gitbook/assets/example\_plan\_2020-11-13-011622-444.log" caption="Example Flight Log - iOS" %}
Android - {% file src="../../.gitbook/assets/61a803f01591990426bf20fb_2021-12-01-232345-164_2021-12-01-232611-939" caption="Example Flight Log - Android" %}


## File Name Convention

`587936ec02c50e25fa9cf365_2017-01-13-202254-159_2017-01-13-202714-779.log`

Plan ID: 587936ec02c50e25fa9cf365  
Start Time Stamp: 2017-01-13-202254-159 \(yyyy-MM-dd-hhmmss-SSS\)  
End Time Stamp: 2017-01-13-202714-779 \(yyyy-MM-dd-hhmmss-SSS\)

## Header

```text
#DroneDeploy    2.1.0
#Flight Recorder
Session ID    587936ec02c50e25fa9cf365
Session Start    01/13/2017 20:22:54
#Device
Device Model    iPhone
Device User Interface Idiom    iPhone    0
Device Operating System    iOS    10.2
Device SSID    
#Aircraft
Aircraft Model    Phantom 4 Pro
Aircraft Name    dd
Aircraft Firmware    01.02.0304
#Aircraft Battery
Full Charge Volume (mAh)    5974
Remaining Life (%)    0
Discharges    1
#Components
Battery Cells Number    4
Battery Serial Number    0DQADB703108WN
Battery Firmware    02.00.07.26
Flight Controller Serial Number    07JDDAK001012B
Flight Controller Firmware    03.02.15.14
Gimbal Firmware    01.50.12.84
Remote Control Serial Number    0CKL1A02L8
Remote Control Firmware    01.03.00.00+
Camera Serial Number    0BDDDBE00100V3
```

## Main Body

```text
Date/Time (UTC)    Elapsed Time (sec)    Info    Device Latitude (Degrees)    Device Longitude (Degrees)    Device Location Last Updated (ms)    Aircraft Battery Power (%)    Aircraft Battery Charge (mAh)    Aircraft Battery Current (mA)    Aircraft Battery Voltage (mV)    Aircraft Battery Temperature (Fahrenheit)    Aircraft Battery Last Updated (ms)    Aircraft Battery Cell 1 Voltage    Aircraft Battery Cell 2 Voltage    Aircraft Battery Cell 3 Voltage    Aircraft Battery Cell 4 Voltage    Aircraft Battery Cell Voltage Last Updated (ms)    Aircraft Latitude (Degrees)    Aircraft Longitude (Degrees)    Aircraft Speed (mph)    Aircraft Barometric Altitude (ft)    Aircraft Heading (Degrees)    Aircraft Vel - X (mph)    Aircraft Vel - Y (mph)    Aircraft Vel - Z (mph)    Aircraft Pitch (Degrees)    Aircraft Roll (Degrees)    Aircraft Satellites    Aircraft Motors On    Aircraft Flying    Aircraft Flight Mode    Aircraft Flight Mode Value    Aircraft IMU Preheating    Aircraft Ultrasonic On    Aircraft Ultrasonic Altitude (ft)    Aircraft Vision On    Aircraft GPS Signal    Aircraft GPS Signal Value    Aircraft No-fly    Aircraft No-fly Value    Aircraft No-fly Latitude (Degrees)    Aircraft No-fly Longitude (Degrees)    Aircraft No-fly Radius (ft)    Home Latitude (Degrees)    Home Longitude (Degrees)    Aircraft Smart Go-home Flight Time Remaining (sec)    Aircraft Smart Go-home Flight Return Time (sec)    Aircraft Smart Go-home Landing Time (sec)    Aircraft Smart Go-home Return Power (%)    Aircraft Smart Go-home Landing Power (%)    Aircraft Smart Go-home Radius (ft)    Aircraft Smart Go-home Requesting    Aircraft System State Last Updated (ms)    Gimbal Pitch (Degrees)    Gimbal Roll (Degrees)    Gimbal Yaw (Degrees)    Gimbal Mode    Gimbal Mode Value    Gimbal Pitch at Stop    Gimbal Roll at Stop    Gimbal Yaw at Stop    Gimbal Status Last Updated (ms)    Landing Gear is Movable    Landing Gear Status    Landing Gear Status Value    Landing Gear Mode    Landing Gear Mode Value    Landing Gear Last Updated (ms)    RC State    RC State Value    RC Left Horizontal    RC Left Vertical    RC Right Horizontal    RC Right Vertical    RC Left Wheel    RC Right Wheel    RC Landing Gear    RC Landing Gear Value    RC Go Home    RC Record     RC Shutter    RC Playback    RC Pause    RC Custom 1    RC Custom 2    RC State Last Updated (ms)    RC Battery (%)    RC Battery State Last Updated (ms)    RC Sattelites    RC Horizontal Accuaracy (ft)    RC Latitude (Degrees)    RC Longitude (Degrees)    RC GSP Data is Valid    RC GPS State Last Updated (ms)    RC Signal 1    RC Signal 2    RC Signal Last Updated (ms)    LB Signal 1    LB Signal 2    LB Signal Last Updated (ms)    Aircraft Camera Mode    Aircraft Camera Mode Value    Aircraft Camera Overheated    Aircraft Camera Sensor Error    Aircraft Camera Recording    Aircraft Camera Raw Capture    Aircraft Camera Interval Capture    Aircraft Camera Burst Capture    Aircraft Camera Single Capture    Aircraft Camera Storing Photo    Aircraft Camera State Last Updated (ms)    Aircraft Camera SD Card Exists    Aircraft Camera SD Card Remaining (%)    Aircraft Camera SD Card State Last Updated (ms)    Aircraft Camera Changeable Lens Supported    Aircraft Camera Lens Installed    Aircraft Camera Lens Type    Aircraft Camera Lens Type Value    Aircraft Camera Lens AF Enabled    Aircraft Camera Lens Focus Mode    Aircraft Camera Lens Focus Mode Value    Aircraft Camera Lens Focus Status    Aircraft Camera Lens Focus Status Value    Aircraft Camera Lens MF Assistant    Aircraft Camera Lens AF Assistant    Aircraft Camera Lens Assistant Working    Aircraft Camera Lens State Last Updated (ms)    Device > Aircraft Distance - XY (ft)
01/13/2017 20:22:54    0.169    Mission did take off    37.77178839318247    -122.407485069821    121    0    0    0    0    0    No Data    4099    4100    4096    4098    30    37.77181960628966    -122.4074304459029    0    0    33.1    0    0    0    -1.4    -1.7    19    1    0    TakeOff    41    0    1    0.328084    0    Very Strong    5    Flying Normally    0    -180    -180    0    37.77181913575728    -122.4074251897526    0    0    0    0    0    0    0    68    0    0    33.90000152587891    Yaw Follow    2    0    0    0    68    0    Unknown    0    Unknown    3    No Data    3    2    0    0    0    0    0    0    No Present    0    0    0    0    0    0    0    0    68    0    No Data    0    0    0    0    0    No Data    100    100    155    N/A    N/A    No Data    Shoot Photo    0    0    0    0    0    0    0    0    0    67    1    68.5107    67    0    1    AF    0    1    Auto    1    Idle    0    0    0    0    67    19.454875566298
01/13/2017 20:22:54    0.268        37.77178839318247    -122.407485069821    220    0    0    0    0    0    No Data    4099    4100    4096    4098    95    37.77181960569202    -122.4074304584804    0    0    33.1    0    0    0    -1.3    -1.7    19    1    0    TakeOff    41    0    1    0.328084    0    Very Strong    5    Flying Normally    0    -180    -180    0    37.77181913575728    -122.4074251897526    0    0    0    0    0    0    0    65    0    0    33.79999923706055    Yaw Follow    2    0    0    0    65    0    Unknown    0    Unknown    3    No Data    3    2    0    0    0    0    0    0    No Present    0    0    0    0    0    0    0    0    65    0    No Data    0    0    0    0    0    No Data    100    100    254    N/A    N/A    No Data    Shoot Photo    0    0    0    0    0    0    0    0    0    65    1    68.5107    65    0    1    AF    0    1    Auto    1    Idle    0    0    0    0    167    19.45179792084206
01/13/2017 20:22:54    0.368        37.77178839318247    -122.407485069821    320    0    0    0    0    0    No Data    4099    4100    4096    4098    15    37.77181959836646    -122.407430459737    0    0    33.1    0    0    0    -1.3    -1.7    19    1    0    TakeOff    41    0    1    0.328084    0    Very Strong    5    Flying Normally    0    -180    -180    0    37.77181913575728    -122.4074251897526    0    0    0    0    0    0    0    63    0    0    33.79999923706055    Yaw Follow    2    0    0    0    62    0    Unknown    0    Unknown    3    No Data    3    2    0    0    0    0    0    0    No Present    0    0    0    0    0    0    0    0    62    0    No Data    0    0    0    0    0    No Data    100    100    354    N/A    N/A    No Data    Shoot Photo    0    0    0    0    0    0    0    0    0    61    1    68.5107    61    0    1    AF    0    1    Auto    1    Idle    0    0    0    0    61    19.44994456286924
```

## [Footer](https://github.com/dronedeploy/ios/pull/1355/files)

If no footer information is present in the flight log, it implies that the app crashed or closed mid flight. We recommend to have a check if footer is available in the flight log.

```text
#Flight Recorder Session End
Date/Time (UTC)    01/13/2017 20:27:14
Elapsed Time (sec)    260.618
```

## Changes coming in November 2020 for iOS

### Header

Adding **User ID** and **Organization ID** to the Header under **\#Flight Recorder**.

Adding **Platform** to the Header under **\#Device**.

```text
#DroneDeploy    4.24.0
#Flight Recorder
User ID    587936ec02c50e25fa9cf363
Organization ID    587936ec02c50e25fa9cf36a
Session ID    587936ec02c50e25fa9cf365
Session Start    01/13/2017 20:22:54
#Device
Platform    iOS
Device Model    iPhone
Device User Interface Idiom    iPhone    0
Device Operating System    iOS    10.2
Device SSID    
#Aircraft
Aircraft Model    Phantom 4 Pro
Aircraft Name    dd
Aircraft Firmware    01.02.0304
#Aircraft Battery
Full Charge Volume (mAh)    5974
Remaining Life (%)    0
Discharges    1
#Components
Battery Cells Number    4
Battery Serial Number    0DQADB703108WN
Battery Firmware    02.00.07.26
Flight Controller Serial Number    07JDDAK001012B
Flight Controller Firmware    03.02.15.14
Gimbal Firmware    01.50.12.84
Remote Control Serial Number    0CKL1A02L8
Remote Control Firmware    01.03.00.00+
Camera Serial Number    0BDDDBE00100V3
```

### Main Body

The **Info** column has changed from a **-** separated list of strings to a JSON Array of values.  Existing events will be JSON Objects of format:

```text
{"message": "existing text"}
```

Newly added events denoting the start of a plan during flight:

```text
{"planId":"5f921be8d09c4ce169e71697","templateId":"5eb9f71600fd224435a9cbe2","projectId":"5e5da0be976932beb266c15f"}
```

Full example:

```text
Date/Time (UTC)	Elapsed Time (sec)	Info	Device Latitude (Degrees)	Device Longitude (Degrees)	Device Location Last Updated (ms)	Aircraft Battery Power (%)	Aircraft Battery Charge (mAh)	Aircraft Battery Current (mA)	Aircraft Battery Voltage (mV)	Aircraft Battery Temperature (Fahrenheit)	Aircraft Battery Last Updated (ms)	Aircraft Battery Cell 1 Voltage	Aircraft Battery Cell 2 Voltage	Aircraft Battery Cell 3 Voltage	Aircraft Battery Cell 4 Voltage	Aircraft Battery Cell Voltage Last Updated (ms)	Aircraft Latitude (Degrees)	Aircraft Longitude (Degrees)	Aircraft Speed (mph)	Aircraft Barometric Altitude (ft)	Aircraft Heading (Degrees)	Aircraft Vel - X (mph)	Aircraft Vel - Y (mph)	Aircraft Vel - Z (mph)	Aircraft Pitch (Degrees)	Aircraft Roll (Degrees)	Aircraft Satellites	Aircraft Motors On	Aircraft Flying	Aircraft Flight Mode	Aircraft Flight Mode Value	Aircraft IMU Preheating	Aircraft Ultrasonic On	Aircraft Ultrasonic Altitude (ft)	Aircraft Vision On	Aircraft GPS Signal	Aircraft GPS Signal Value	Aircraft No-fly	Aircraft No-fly Value	Aircraft No-fly Latitude (Degrees)	Aircraft No-fly Longitude (Degrees)	Aircraft No-fly Radius (ft)	Home Latitude (Degrees)	Home Longitude (Degrees)	Aircraft Smart Go-home Flight Time Remaining (sec)	Aircraft Smart Go-home Flight Return Time (sec)	Aircraft Smart Go-home Landing Time (sec)	Aircraft Smart Go-home Return Power (%)	Aircraft Smart Go-home Landing Power (%)	Aircraft Smart Go-home Radius (ft)	Aircraft Smart Go-home Countdown (sec)	Aircraft Smart Go-home Requesting	Aircraft System State Last Updated (ms)	Gimbal Pitch (Degrees)	Gimbal Roll (Degrees)	Gimbal Yaw (Degrees)	Gimbal Mode	Gimbal Mode Value	Gimbal Pitch at Stop	Gimbal Roll at Stop	Gimbal Yaw at Stop	Gimbal Status Last Updated (ms)	Landing Gear is Movable	Landing Gear Status	Landing Gear Status Value	Landing Gear Mode	Landing Gear Mode Value	Landing Gear Last Updated (ms)	RC State	RC State Value	RC Left Horizontal	RC Left Vertical	RC Right Horizontal	RC Right Vertical	RC Left Wheel	RC Right Wheel	RC Landing Gear	RC Landing Gear Value	RC Go Home	RC Record	RC Shutter	RC Playback	RC Pause	RC Custom 1	RC Custom 2	RC State Last Updated (ms)	RC Battery (%)	RC Battery State Last Updated (ms)	RC Sattelites	RC Horizontal Accuaracy (ft)	RC Latitude (Degrees)	RC Longitude (Degrees)	RC GSP Data is Valid	RC GPS State Last Updated (ms)	RC Signal 1	RC Signal 2	RC Signal Last Updated (ms)	LB Signal 1	LB Signal 2	LB Signal Last Updated (ms)	Aircraft Camera Mode	Aircraft Camera Mode Value	Aircraft Camera Overheated	Aircraft Camera Sensor Error	Aircraft Camera Recording	Aircraft Camera Raw Capture	Aircraft Camera Interval Capture	Aircraft Camera Burst Capture	Aircraft Camera Single Capture	Aircraft Camera Storing Photo	Aircraft Camera State Last Updated (ms)	Aircraft Camera SD Card Exists	Aircraft Camera SD Card Remaining (%)	Aircraft Camera SD Card State Last Updated (ms)	Aircraft Camera Changeable Lens Supported	Aircraft Camera Lens Installed	Aircraft Camera Lens Type	Aircraft Camera Lens AF Enabled	Aircraft Camera Lens Focus Mode	Aircraft Camera Lens Focus Mode Value	Aircraft Camera Lens Focus Status	Aircraft Camera Lens Focus Status Value	Aircraft Camera Lens MF Assistant	Aircraft Camera Lens AF Assistant	Aircraft Camera Lens Assistant Working	Aircraft Camera Lens State Last Updated (ms)	Compass Index	Compass Sensor Value	Compass State	Compass State Last Updated (ms)	Compass Calibration State	Compass Calibration Last Updated (ms)	Device > Aircraft Distance - XY (ft)
10/22/2020 23:55:45	17.658	[{"message":"Mission did take off"},{"planId":"5f921be8d09c4ce169e71697","templateId":"5eb9f71600fd224435a9cbe2","projectId":"5e5da0be976932beb266c15f"}]	0.0	0.0	17657.18698501587	56	1	1	25	73.4	1.7139911651611328	0	0	0	0	17657.204151153564	37.771846	-122.407436	22.369418519393044	9.84252	27.0	22.369418519393044	0.0	0.0	0.0	0.0	10	1	1	flight mode	14	0	1	0.0	1	Very Strong	5	Fly Zone Unknown	255	0.0	0.0	0	37.771846	-122.407436	100	100	90	40	10	32.8084	0	0	2.0508766174316406	0.0	0.0	0.0	Free	0	0	0	0	17657.357215881348	0	Unknown	0	Unknown	3	17657.395124435425	3	2	0	0	0	0	0	0	No Present	0	0	0	0	0	0	0	0	1.67083740234375	100	1.6300678253173828	1	0.0	0.0	0.0	1	1.9240379333496094	0	0	17657.42826461792	0	0	17657.430171966553	Shoot Photo	0	0	0	0	0	0	0	0	0	17657.458782196045	0	0.0	17657.4809551239	0	0	Unknown	0	Manual	0	Idle	0	0	0	0	17657.523155212402	0	27.0	2	2.2039413452148438	255	17657.526969909668	3902877.547784845
10/22/2020 23:55:45	18.108		0.0	0.0	18106.89377784729	56	1	1	25	73.4	424.285888671875	0	0	0	0	18106.901168823242	37.771846	-122.407436	22.369418519393044	13.12336	27.0	22.369418519393044	0.0	0.0	0.0	0.0	10	1	1	flight mode	14	0	1	0.0	1	Very Strong	5	Fly Zone Unknown	255	0.0	0.0	0	37.771846	-122.407436	100	100	90	40	10	32.8084	0	0	424.5409965515137	-90.0	0.0	0.0	Free	0	1	1	1	449.73206520080566	0	Unknown	0	Unknown	3	18107.0339679718	3	2	0	0	0	0	0	0	No Present	0	0	0	0	0	0	0	0	424.17097091674805	100	424.1318702697754	1	0.0	0.0	0.0	1	424.4379997253418	0	0	18107.048988342285	0	0	18107.06329345703	Shoot Photo	0	0	0	0	0	0	0	0	0	449.97286796569824	1	100.0	449.91207122802734	0	0	Unknown	0	Manual	0	Idle	0	0	0	0	18107.108116149902	0	27.0	2	424.6678352355957	255	18107.11097717285	3902877.547784845
10/22/2020 23:55:45	18.328		0.0	0.0	18326.38907432556	56	1	1	25	73.4	218.86491775512695	0	0	0	0	18326.406002044678	37.771846	-122.407436	22.369418519393044	16.4042	27.0	22.369418519393044	0.0	0.0	0.0	0.0	10	1	1	flight mode	14	0	1	0.0	1	Very Strong	5	Fly Zone Unknown	255	0.0	0.0	0	37.771846	-122.407436	100	100	90	40	10	32.8084	0	0	219.22802925109863	-90.0	0.0	0.0	Free	0	1	1	1	669.1479682922363	0	Unknown	0	Unknown	3	18326.44295692444	3	2	0	0	0	0	0	0	No Present	0	0	0	0	0	0	0	0	218.19281578063965	100	218.08910369873047	1	0.0	0.0	0.0	1	218.8699245452881	0	0	18326.449155807495	0	0	18326.45010948181	Shoot Photo	0	0	0	0	0	0	0	0	0	669.3549156188965	1	100.0	669.2900657653809	0	0	Unknown	0	Manual	0	Idle	0	0	0	0	18326.488971710205	0	27.0	2	219.21706199645996	255	18326.495885849	3902877.547784845
```

## Changes coming in December 2021 for Android

### Main Body

The **Info** column has changed from a **-** separated list of strings to a JSON Array of values.  Existing events will be JSON Objects of format:

```text
{"message": "existing text"}
```

Newly added events denoting the start of a plan during flight:

```text
{"planId":"61a803f01591990426bf20fb","projectId":"61295629473ddb6a32682273","templateId":"61a7eaff6b9bb32cf735b4eb"}
```

Full example:

```text
Date/Time (GMT)	Elapsed Time (sec)	Info	Aircraft Battery Power (%)	Aircraft Battery Charge (mAh)	Aircraft Battery Current (mA)	Aircraft Battery Voltage (mV)	Aircraft Battery Temperature (Fahrenheit)	Aircraft Battery Last Updated (ms)	Aircraft Battery Cell 1 Voltage (mV)	Aircraft Battery Cell 2 Voltage (mV)	Aircraft Battery Cell 3 Voltage (mV)	Aircraft Battery Cell 4 Voltage (mV)	Aircraft Latitude (Degrees)	Aircraft Longitude (Degrees)	Aircraft Barometric Altitude (ft)	Aircraft Heading (Degrees)	Aircraft Pitch (Degrees)	Aircraft Roll (Degrees)	Aircraft Satellites	Aircraft Motors On	Aircraft Flying	Aircraft Flight Mode	Aircraft Flight Mode Value	Aircraft IMU Preheating	Aircraft Ultrasonic On	Aircraft Ultrasonic Altitude (ft)	Aircraft Vision On	Aircraft GPS Signal	Aircraft GPS Signal Value	Aircraft No-Fly	Aircraft No-Fly Value	Aircraft No-fly Latitude (Degrees)	Aircraft No-fly Longitude (Degrees)	Aircraft No-fly Radius (ft)	Home Latitude (Degrees)	Home Longitude (Degrees)	Aircraft Smart Go-home Flight Time Remaining (sec)	Aircraft Smart Go-home Flight Return Time (sec)	Aircraft Smart Go-home Landing Time (sec)	Aircraft Smart Go-home Return Power (%)	Aircraft Smart Go-home Landing Power (%)	Aircraft Smart Go-home Radius (ft)	Aircraft Smart Go-home Countdown (sec)	Aircraft Smart Go-home State	Aircraft System State Last Updated (ms)	Gimbal Pitch (Degrees)	Gimbal Roll (Degrees)	Gimbal Yaw (Degrees)	Gimbal Mode	Gimbal Mode Value	Gimbal Pitch at Stop	Gimbal Roll at Stop	Gimbal Yaw at Stop	Gimbal State Last Updated (ms)	Landing Gear is Movable	Landing Gear Status	Landing Gear Status Value	Landing Gear Mode	Landing Gear Mode Value	RC State	RC State Value	RC Left Horizontal	RC Left Vertical	RC Right Horizontal	RC Right Vertical	RC Left Wheel	RC Right Wheel	RC Landing Gear	RC Landing Gear Value	RC Go Home	RC Record	RC Shutter	RC Playback	RC Pause	RC Custom 1	RC Custom 2	RC State Last Updated (ms)	RC Battery (%)	RC Satellites	RC Horizontal Accuracy (ft)	RC Latitude (Degrees)	RC Longitude (Degrees)	RC GPS Last Updated (ms)	RC Signal 1 (%)	RC Signal 2 (%)	RC Signal Last Updated (ms)	LB Signal 1 (%)	LB Signal 2 (%)	LB Signal Last Updated (ms)	Aircraft Camera Mode	Aircraft Camera Mode Value	Aircraft Camera Overheated	Aircraft Camera Sensor Error	Aircraft Camera Recording	Aircraft Camera Raw Capture	Aircraft Camera Interval Capture	Aircraft Camera Burst Capture	Aircraft Camera Single Capture	Aircraft Camera Storing Photo	Aircraft Camera SD Card Exists	Aircraft Camera SD Card Remaining (%)	Aircraft Camera Lens Installed	Aircraft Camera Lens Type	Aircraft Camera Lens Type Value	Aircraft Camera Lens AF Enabled	Aircraft Camera Lens Focus Mode	Aircraft Camera Lens Focus Mode Value	Aircraft Camera Lens Focus Status	Aircraft Camera Lens Focus Status Value	Aircraft Camera Lens MF Assistant	Aircraft Camera Lens AF Assistant	Aircraft Camera Lens Assistant Working	Device > Aircraft Distance - XY (ft)	Aircraft Vel - X (mph)	Aircraft Vel - Y (mph)	Aircraft Vel - Z (mph)	Aircraft Speed (mph)
12/01/2021 23:23:46	1.819	[{"message":"Mission did take off"},{"planId":"61a803f01591990426bf20fb","projectId":"61295629473ddb6a32682273","templateId":"61a7eaff6b9bb32cf735b4eb"}]	66	2412	-1310	15970	38.8	18					32.96138223962492	-97.2765785293478	2.952756	112.7	0.0	0.0	15.0	1	1	TakeOff	11	0	1	3.28084	0	Very strong	5	null	0	0.0	0.0	0.0	32.961381393923666	-97.2765761254795	0	0	0	0	N/A	5063.883	0	IDLE	101	0.0	0.0	17.1	YawFollowMode	2	0	0	0	100	0	Unknown	0	Unknown	3	null	0	0	0	0	0	0	0	Not present	254	0	0	0	0	0	0	0	0	0	0	0.0	0.0	0.0	0	0	0	0	0	0	0	null	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	N/A	0	N/A	0	0	0	0	0.0	0.0	0.0	-0.89477676	0.0
```