Potential & planned features for the Korva DSP+Amp board.
Status tags: V1 = ship with MVP · V1.5 = near-term post-launch · V2 = future expansion · CUT = not building

Hardware

4× RCA analog inputs V1 — Unbalanced analog inputs
USB-C port V1 — Firmware recovery; USB audio input deferred to V2
6 powered speaker outputs V1 — Any channel configurable as pre-out
2× line-level pre-outs V1 — Fixed, for external sub amps
TPA3255 × 3 Class D stage V1 — 4ch @ 75W + 2ch @ 150W sustained into 4Ω
ADAU1467 DSP V1 — Master signal graph, pre-compiled topology images
PCM3168A codec V1 — ADC + DAC on same chip
ESP32-S3-WROOM-1-N16R8 V1 — Wi-Fi, WebSocket, OTA, parameter marshaling
48V soft-start / inrush limit V1 — Rail protection on PSU input
Output short-circuit detection + mute V1 — Hardware-level
DC offset detection per output V1 — Auto-mute on fault
Per-chip over-temp foldback V1 — Graceful, no hard shutdown mid-listen
Relay / MOSFET speaker mute V1 — Triggered on fault
Clip indicator to ESP32 GPIO V1 — Drives UI meter clip hold
Fan header (×1) V1 — Optional, with tach input
12V wake input (trigger) V1 — HT integration
GPIO expansion header V1 — Documented for community builders
Debug headers + test points + boot pads V1 — Recovery & bring-up
Safety covers (standard) V1 — Over high-power section
Debug LED status codes V1 — Documented blink codes
6-layer PCB stackup V1 — Analog/digital ground separation
Per-PVDD decoupling V1 — 220µF electrolytic + 10µF ceramic per PVDD pin
Class-D output LC filter + EMI layout V1 — FCC Part 15 Class B
Domain-isolated supplies V1 — 48V → separate 3.3V / 1.8V / analog rails
Intentional board aesthetic V1 — Silkscreen & layout quality
OPA1612 op-amp input buffer V1 — Keep only if bring-up measurements justify
12V trigger output V2 — Daisy-chain multi-unit
S/PDIF digital input V2 — Community request (streamer/HTPC use)
TOSLINK digital input V2 — Community request (avoids extra D/A/D conversions)
FPC screen connector CUT — No screen SKU in V1
3.5mm stereo input CUT — Ground-loop & reliability risk, wrong customer


Software / UI

Wi-Fi AP on first boot V1 — SSID "Korva-XXXX", zero-install
Join home Wi-Fi (station mode) V1 — For subsequent sessions
WebSocket server on ESP32 V1 — Transport for all UI actions
Bundled static UI on flash V1 — <200KB, vanilla JS or Preact/Svelte
Cross-browser support V1 — iOS Safari, Android Chrome, desktop Chrome/Edge/Firefox
Signal-flow canvas (primary UI) V1 — 3 columns: Inputs / Speakers / Outputs
Right-side inspector drawer V1 — Contextual editing
Topology picker V1 — 3–4 fixed + free 8-channel custom
Speaker as first-class object V1 — Grouping of outputs by role
Full preset round-trip V1 — Device state readable; diff against file
4 named preset slots + JSON export V1 — On-device + file
A/B preset compare with diff table V1 — Live swap
Revert / Undo (per-parameter) V1 — History stack
HPF/LPF + slopes per channel V1 — LR12/LR24/BW12/BW24/BW48
6-band PEQ per channel V1 — Q, f, gain
Per-channel delay + distance display V1 — Auto unit conversion (ms/ft/in/cm/mm)
Per-channel polarity (large badge) V1 — High-contrast UI
Per-channel gain + mute V1 — Foundational
Global master volume / input select / mute V1 — Always visible
Measurement-mode bypass (one click) V1 — Disables all DSP for REW
Crossover editor w/ summed-response overlay V1 — Beats miniDSP/Hypex/DBX
Chain inspection ("what feeds this output?") V1 — Click output, see full chain
Bottom strip: 8 output meters + clip V1 — Always visible
Top bar: device / connection / preset / unsaved / master V1 — Always visible
Inline warnings (3 tiers) V1 — Control / speaker card / tray
OTA firmware update from browser V1 — With rollback
A/B firmware partitions + signed recovery V1 — No-brick guarantee
Factory reset (UI + HW button) V1 — Returns to first-boot state
Open-source firmware + UI on GitHub V1 — Day one
REW workflow integration V1 — Sweep-friendly
Filter import (REW .txt + generic biquad CSV) V1 — Kills Hypex's worst pain point
Progressive disclosure ("Show all parameters") V1 — No mode toggle
Per-channel limiter (user-reviewed thresholds) V1 — Placeholders in starter config
Auto-save working state V1 — No saving modal, never lose edits
Peak / clip hold, limiter-active chip V1 — Meter state
Polarity indicator as large badge V1 — Not a tiny checkbox
Master mute ON at first boot V1 — Hard safety
Channel labeling (role + output #) V1 — Role primary, number secondary
Confirm-before-unmute gate V1 — Explicit acknowledgement, not dismissible toast
Output-assignment conflict detection V1 — Live, in UI and firmware
Starter-configuration value labeling V1 — Placeholders visually marked until touched
Keyboard shortcuts V1 — E=EQ, D=Delay, G=Gain, 1–6 band select, undo/redo
Expandable side panels per channel V1 — Inspect deeper settings without leaving main view (community request)
Channel compare mode V1.5 — Overlay channels to see setting differences (community request)
All-pass / phase tuning V1.5 — Biquad primitive behind "show all parameters"
IR remote V1.5 — Deferred from V1
Customizable UI templates by role V2 — Modular layouts per use case (community request)
FIR filter authoring V2 — Deferred; Hypex doesn't have it either
Master/slave multi-unit chain V2 — V1 customer is one-box
BLE remote / phone-as-remote V2 — Browser UI already covers phone
USB-C audio input V2 — Hardware present, firmware deferred
Driver database + auto T/S populate CUT — Liability, maintenance, contradicts positioning
Community driver submissions CUT — Requires community that doesn't exist yet
Automatic tweeter HPF from lookup CUT — Contradicts "we don't know your drivers" stance
Listening profile / preference curve CUT — Confuses preference with protection
Visual custom-topology mapper UI CUT — Free 8-ch mode does the job
Raw ADAU1467 programming UI in browser CUT — 6–12 months of firmware
Native iOS/Android app CUT — Browser UI already runs on mobile
Cloud sync CUT — Not the product
Streaming (Roon / Spotify / AirPlay) CUT — Not the product


Guided Setup

First-run topology picker V1 — Visual cards, no jargon
Speaker role + output assignment V1 — Live conflict detection
Skip-safe guided setup V1 — Placeholders remain; master stays muted
Confirm-before-unmuting master V1 — Explicit gate, not a toast
<10 min plug-in → reviewable starter config V1 — Demo video promise
Expert path (canvas immediately available) V1 — Wizard never forced
Pre-authored starter configurations per topology V1 — Topology graph + placeholders
Optional manual driver entry V1 — Size/RMS/impedance → suggested limiter (user confirms)
Time-alignment position diagram V1 — Multi-unit conversion, user accepts/overrides
Optional Full Review summary V1 — Flags untouched placeholders & unassigned outputs
Guided-setup end summary V1 — Plain-language list, review-and-unmute gate inline


Reliability / Protection

A/B firmware partitions (ESP-IDF OTA) V1 — Hard safety
Signed read-only recovery image V1 — Third partition
Hardware factory reset button V1 — Can't be bricked from UI
Output short-circuit protection V1 — Hardware-level
DC offset detection → auto-mute V1 — Protects drivers
Per-chip thermal foldback V1 — Graceful, not hard shutdown
Pop/click suppression V1 — <20mV DC transient at speaker terminal
Inrush current limit on 48V rail V1 — Soft-start
Input overload indication + graceful limiting V1 — UI + behavior
Debug LED blink codes V1 — Documented in manual
Safety covers (standard) V1 — Ship them, don't option them
Documented fault table V1 — What each protection does, how to clear
Diagnostic log export from UI V1 — For support tickets
Persistent crash report to flash V1 — Recovery diagnostics
SN + firmware version in UI V1 — Top bar Device page
ESP32 watchdog V1 — Control hang must not kill audio


Power / Thermal

External 48V PSU + official pre-wired bundle V1 — Recommended path
Honest sustained multichannel power spec V1 — All 6 driven, 4Ω, 25°C
Per-chip + ambient temp monitoring V1 — Feeds foldback + UI
Thermal foldback (graceful) V1 — Reduce power, don't shut down
Signal-detect auto-standby V1 — Adjustable timeout
12V trigger wake input V1 — HT chain integration
Fan header (×1) + tach + UI readout V1 — Optional, documented
Real-time power headroom readout in UI V1 — Usage meter
Startup sequencing (no pop) V1 — DSP ready → unmute relay → audio
Configurable power allocation profiles V1.5 — Beyond the 2 V1 presets
12V trigger output V2 — Multi-unit chain


Tuning / Workflow

Measurement bypass (one click) V1 — Top-bar badge
Filter import (REW .txt + generic biquad CSV) V1 — No manual transcription
Sum-response overlay in XO editor V1 — Differentiator
Keyboard shortcuts for expert tuning V1 — Power-user credibility
A/B preset compare w/ live audio swap V1 — Live comparison
Per-band trim sliders in XO editor V1 — Not just handoff points
Warning on user-entered driver limit violations V1 — Only on data user provided
Persistent working state across disconnects V1 — Never lose edits
"What affects this output?" inspector V1 — Chain trace
Preset export as JSON + FW version + board ID V1 — Portable working files
Measurement-mode indicator badge V1 — So you don't forget it's on
Per-band RMS/peak limiters V1.5 — Community request (DSP/firmware level)
Multiband compressor V2 — Community request


Trust / Quality-of-Life

Published ASR-grade measurements at launch V1 — Product requirement
Public beta tester measurements (incl. negatives) V1 — Before pre-orders
Pre-wired official PSU bundle V1 — Recommended safe path
DIY PSU warning docs (realistic) V1 — For builders rolling their own
Transparent firmware release notes V1 — Trust multiplier
Public build log on diyAudio V1 — Weekly updates
Realistic support-response policy V1 — "Best effort 72h, Discord first"
Written warranty + product liability insurance V1 — Terms in writing
Demo video (<5 min, single take) V1 — Unbox → review → music
"What Korva does and does not know" documentation V1 — In manual, product page, UI


Community Suggestions
Features pulled from user comments, integrated above under their category:

Per-band RMS/peak limiters — V1.5
Multiband compressor — V2
S/PDIF digital input — V2
TOSLINK digital input — V2
Expandable side panels per channel — V1
Channel compare mode (overlay differences) — V1.5
Role-based UI templates / modular layouts — V2
Temp readings visible in UI — V1 (already planned)
