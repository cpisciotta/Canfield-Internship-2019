# Canon EOS SL3 Available API Calls Version 1.0

---

## Meta
Date Created: July 26, 2019

---

## PLEASE NOTE
The URLs for each call were made on the MobileDebug WiFi network. The host name and port number in each API call url will vary depending on what WiFi network you are connected to.<br /><br />The following GET call will generate a list similar to the one below, containing all available API calls for that Canon camera model and API version: 
`http://HOSTNAME:PORT/ccapi`

---

## Table Of Contents

- [ ] Fixed Information<br />
	>[Device Information](#device-information)<br />
- [ ] Camera Status
	>[Storage Information](#storage-information)<br />
	>[Battery Information](#battery-information)<br />
	>[Lens Information](#lens-information	)<br />
	>[Temperature Information](#temperature-information)<br />
- [ ] Camera Settings<br />
	>[Copyright Information](#copyright-information)<br />
	>[Author Information](#author-information)<br />
	>[Ownername Information](#ownername-information)<br />
	>[[Nickname Information](#[nickname-information)<br />
	>[Date and Time Information](#date-and-time-information)<br />
	>[Card Format](#card-format)<br />
	>[Mute Setting](#mute-setting)<br />
	>[Auto Power Off](#auto-power-off)<br />
	>[Wifi Disconnect](#wifi-disconnect)<br />
	>[Wifi Settings](#wifi-settings)<br />
	>[Wifi Setting 1](#wifi-setting-1)<br />
	>[Wifi Setting 2](#wifi-setting-2)<br />
	>[Wifi Setting 3](#wifi-setting-3)<br />
- [ ] Image Operations<br />
	>[Contents](#contents)<br />
- [ ] Shooting Control<br />
	>[Automatic Shutter Button Control](#automatic-shutter-button-control)<br />
	>[Manual Shutter Button Control](#manual-shutter-button-control)<br />
	>[Movie Mode](#movie-mode)<br />
	>[Recording Button Control](#recording-button-control)<br />
	>[Drive Focus](#drive-focus)<br />
	>[Auto Focus](#auto-focus)<br />
- [ ] Shooting Settings<br />
	>[Parameter List](#parameter-list)<br />
	>[Shooting Mode](#shooting-mode)<br />
	>[AV Setting](#av-setting)<br />
	>[TV Setting](#tv-setting)<br />
	>[ISO Setting](#iso-setting)<br />
	>[Exposure Setting](#exposure-setting)<br />
	>[White Balance Setting](#white-balance-setting)<br />
	>[Auto Focus Operation Setting](#auto-focus-operation-setting)<br />
	>[Auto Focus Method Setting	](#auto-focus-method-setting	)<br />
	>[Still Image Quality Setting](#still-image-quality-setting)<br />
	>[Still Image Aspect Ratio Setting](#still-image-aspect-ratio-setting)<br />
	>[Flash Setting](#flash-setting)<br />
	>[Metering Setting](#metering-setting)<br />
	>[Drive Setting](#drive-setting)<br />
	>[Auto Exposure Bracket Setting](#auto-exposure-bracket-setting)<br />
	>[White Balance Shift Setting](#white-balance-shift-setting)<br />
	>[White Balance Bracket Setting](#white-balance-bracket-setting)<br />
	>[Color Space Setting](#color-space-setting)<br />
	>[Picture Style Setting](#picture-style-setting)<br />
	>[Auto Picture Style Setting](#auto-picture-style-setting)<br />
	>[Standard Picture Style Setting](#standard-picture-style-setting)<br />
	>[Portrait Picture Style Setting](#portrait-picture-style-setting)<br />
	>[Picture Style Setting](#picture-style-setting)<br />
	>[Fine Detail Picture Style Setting](#fine-detail-picture-style-setting)<br />
	>[Neutral Picture Style Setting](#neutral-picture-style-setting)<br />
	>[Faithful Picture Style Setting](#faithful-picture-style-setting)<br />
	>[Monochrome Picture Style Setting](#monochrome-picture-style-setting)<br />
	>[User Defined 1 Picture Style Setting](#user-defined-1-picture-style-setting)<br />
	>[User Defined 2 Picture Style Setting](#user-defined-2-picture-style-setting)<br />
	>[User Defined 3 Picture Style Setting](#user-defined-3-picture-style-setting)<br />
	>[User Defined 1 Base Picture Style Setting](#user-defined-1-base-picture-style-setting)<br />
	>[User Defined 2 Base Picture Style Setting](#user-defined-2-base-picture-style-setting)<br />
	>[User Defined 3 Base Picture Style Setting](#user-defined-3-base-picture-style-setting)<br />
	>[Movie Quality Setting](#movie-quality-setting)<br />
	>[Sound Recording Setting](#sound-recording-setting)<br />
	>[Sound Recording Level Setting](#sound-recording-level-setting)<br />
	>[Sound Recording Wind Filter Setting](#sound-recording-wind-filter-setting)<br />
	>[Sound Recording Attenuator Setting](#sound-recording-attenuator-setting)<br />
- [ ] Recording Information<br />
	>[Sound Recording Recordable Setting](#sound-recording-recordable-setting)<br />
- [ ] Live View<br />
	>[Live View](#live-view)<br />
	>[Flip](#flip)<br />
	>[Flip Detail](#flip-detail)<br />
	>[Scroll](#scroll)<br />
	>[Scroll Detail](#scroll-detail)<br />
	>[RTP](#rtp)<br />
	>[RTP Session Desc](#rtp-session-desc)<br />
	>[Angle Information](#angle-information)<br />
	>[Auto Focus Frame Position](#auto-focus-frame-position)<br />
- [ ] Camera Status<br />
	>[Polling](#polling)<br />
	>[Monitoring](#monitoring)		

---

### Device Information
>url	"http://192.168.1.106:8080/ccapi/ver100/deviceinformation"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Storage Information
>url	"http://192.168.1.106:8080/ccapi/ver100/devicestatus/storage"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Battery Information
>url	"http://192.168.1.106:8080/ccapi/ver100/devicestatus/battery"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Lens Information	
>url	"http://192.168.1.106:8080/ccapi/ver100/devicestatus/lens"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Temperature Information
>url	"http://192.168.1.106:8080/ccapi/ver100/devicestatus/temperature"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Copyright Information
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/registeredname/copyright"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Author Information
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/registeredname/author"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Ownername Information
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/registeredname/ownername"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Nickname Information
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/registeredname/nickname"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Date and Time Information
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/datetime"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Card Format	
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/cardformat"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Mute Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/beep"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Auto Power Off
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/autopoweroff"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Wifi Disconnect
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/wificonnection"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Wifi Settings
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/wifisetting"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Wifi Setting 1
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/wifisetting/set1"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Wifi Setting 2
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/wifisetting/set2"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Wifi Setting 3
>url	"http://192.168.1.106:8080/ccapi/ver100/functions/wifisetting/set3"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Contents
>url	"http://192.168.1.106:8080/ccapi/ver100/contents"<br />
>get	true<br />
>post	true<br />
>put	true<br />
>delete	true<br />

### Automatic Shutter Button Control
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/control/shutterbutton"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Manual Shutter Button Control
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/control/shutterbutton/manual"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Movie Mode
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/control/moviemode"<br />
>get	true<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Recording Button Control
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/control/recbutton"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Drive Focus
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/control/drivefocus"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Auto Focus
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/control/af"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Parameter List
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Shooting Mode
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/shootingmodedial"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### AV Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/av"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### TV Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/tv"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### ISO Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/iso"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Exposure Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/exposure"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### White Balance Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/wb"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Auto Focus Operation Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/afoperation"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Auto Focus Method Setting	
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/afmethod"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Still Image Quality Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/stillimagequality"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Still Image Aspect Ratio Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/stillimageaspectratio"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Flash Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/flash"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Metering Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/metering"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Drive Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/drive"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false

### Auto Exposure Bracket Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/aeb"<br />
>get	true<br />
>post	false
>put	true
>delete	false

### White Balance Shift Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/wbshift"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### White Balance Bracket Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/wbbracket"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Color Space Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/colorspace"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Auto Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/auto"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Standard Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/standard"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Portrait Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/portrait"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/landscape"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Fine Detail Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/finedetail"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Neutral Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/neutral"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Faithful Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/faithful"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### Monochrome Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/monochrome"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### User Defined 1 Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/userdef1"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### User Defined 2 Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/userdef2"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### User Defined 3 Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/userdef3"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	true<br />

### User Defined 1 Base Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/userdef1/basepicturestyle"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### User Defined 2 Base Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/userdef2/basepicturestyle"<br />
>get	true<br />
>post	false<br />
>put	true
>delete	false

### User Defined 3 Base Picture Style Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/picturestyle/userdef3/basepicturestyle"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Movie Quality Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/moviequality"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Sound Recording Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/soundrecording"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Sound Recording Level Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/soundrecording/level"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Sound Recording Wind Filter Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/settings/soundrecording/windfilter"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Sound Recording Attenuator Setting
>url "http://192.168.1.106:8080/ccapi/ver100/shooting/settings/soundrecording/attenuator"<br />
>get	true<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Sound Recording Recordable Setting
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/information/recordable"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Live View
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Flip
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/flip"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Flip Detail
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/flipdetail"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Scroll
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/scroll"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	true<br />

### Scroll Detail
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/scrolldetail"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	true<br />

### RTP
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/rtp"<br />
>get	true<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### RTP Session Desc
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/rtpsessiondesc"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	false<br />

### Angle Information
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/angleinformation"<br />
>get	false<br />
>post	true<br />
>put	false<br />
>delete	false<br />

### Auto Focus Frame Position
>url	"http://192.168.1.106:8080/ccapi/ver100/shooting/liveview/afframeposition"<br />
>get	false<br />
>post	false<br />
>put	true<br />
>delete	false<br />

### Polling
>url	"http://192.168.1.106:8080/ccapi/ver100/event/polling"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	true<br />

### Monitoring
>url	"http://192.168.1.106:8080/ccapi/ver100/event/monitoring"<br />
>get	true<br />
>post	false<br />
>put	false<br />
>delete	true<br />
