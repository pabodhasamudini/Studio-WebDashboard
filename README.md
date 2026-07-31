# Studio-WebDashboard

SMART MOTORIZED STUDIO LIGHTING SYSTEM
Web-Based Control Dashboard | First Year Microcontroller Based Hardware Project
ForgeMinds - Group 33

1. PROJECT OVERVIEW
The Smart Motorized Studio Lighting System is an integrated hardware-software solution for smart studio lighting control. This web dashboard serves as the central control interface, enabling centralized management of DMX lighting, motorized positioning, and audio-reactive illumination via an ESP32 microcontroller.

2. SYSTEM CAPABILITIES

a) DMX Lighting Control
Controls two DMX512 compatible fixtures (12 channels total).
Channels per fixture: Dimmer, Red, Green, Blue, White, Speed/Strobe.
Operating Modes: Manual RGBW, Jump, Gradient, Pulse, and Sound Active.
Includes real time color preview scaled to dimmer intensity.

b) Motorized Positioning Control
Provides three axis movement for dynamic light positioning.
M.01 Pan, M.02 Tilt, M.03 Height.
Controls: Directional movement (Up/Down) and individual stop, with global Stop All.

c) Music-Reactive Module
Implements browser based audio analysis for beat synchronized lighting.
Input: Local audio file upload or live system audio capture.
Processing: Web Audio API with FFT analysis and adaptive beat detection.
Output: Automatic DMX triggering with configurable sensitivity, floor, and decay.

3. SYSTEM ARCHITECTURE
Web Dashboard (Client) -> Wi-Fi (HTTP) -> ESP32 Controller -> DMX Driver & Motor Drivers

Communication Interface:
GET /ping - Verifies connectivity.
GET /set?light={1|2}&d=&r=&g=&b=&w=&p=&s= - Transmits DMX values.
GET /m{id}{up|dn|st} - Controls motor movement.

4. OPERATING INSTRUCTIONS
1. Power the hardware rig and connect to the ESP32 access point.
2. Open index.html in a compatible browser (Chrome recommended).
3. Confirm IP (default: 192.168.4.1) and select Test Connection.
4. Operate lighting via sliders and positioning via motor controls.
5. For music mode, provide audio source, select target fixture, and enable.

5. TECHNICAL IMPLEMENTATION
Frontend: HTML5, CSS3, Vanilla JavaScript
Audio: Web Audio API (AnalyserNode)
Hardware: ESP32, RS485 DMX Interface, Motor Drivers
Deployment: Single-file application, no external dependencies.


