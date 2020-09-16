# Upgrade-Tasmota
Project description:
Upgrade Tasmota 6.5.0.11 to lastest (Tasmota 8.5.0.1) by Theo Arends
There are multiple ways to upgrade your Tasmota. For my project, my sensor node has a ADS1115, BME280,SHT3X, PZEM016, and A NodeMCU ESP8266.

I used Gitpod to work on the Tasmota Development file.
before you start, you need to create your own Gitpod account, you also can log in Gitpod with your github account, which was what I did.
   Step 1. go to the tasmota development web site: https://github.com/arendst/Tasmota   (thank Arends)
   Step 2. follow this link. (https://tasmota.github.io/docs/Gitpod/)
            Copy and paste   gitpod.io/#  before   https://github.com/arendst/Tasmot, which makes   gitpod.io/#https://github.com/arendst/Tasmot
           (this step will create a workshop for Gitpod)
   Step 3. Scroll to the bottom of /tasmota folder, find  platformio.ini  file and open it.
   Step 4. find 
           ; *** Tasmota build variant selection
[build_envs]
default_envs =
; *** Uncomment by deleting ";" in the line(s) below to select version(s)
;                tasmota
;                tasmota-ircustom
;                tasmota-minimal
;                tasmota-lite
;                tasmota-knx
;                tasmota-sensors
;                tasmota-display
;                tasmota-zbbridge
........
delete ';' to uncomment tasmota
which will make it 
; *** Uncomment by deleting ";" in the line(s) below to select version(s)
                tasmota           (this line)
;                tasmota-ircustom
;                tasmota-minimal
;                tasmota-lite
;                tasmota-knx
;                tasmota-sensors
;                tasmota-display
;                tasmota-zbbridge
........

step 5. go to Ternimal pane (the bottom of gitpod), and run:  platformio run -e tasmota
Step 6. in folder   /Tasmota/build_output/firmware/tasmota.bin, right click your mouse, and download tasmota.bin

--UPGRADE SECTION---
step 7. Go to you tasmota address and upgrade it with tasmota-minimal.bin
        you can find the OTA address here: http://ota.tasmota.com/tasmota/release/
Step 8. click up start upgrade.
Step 9. when upgrade finishes, in Upgrade by file upload, click choose file and upload your tasmota.bin built in gitpod.
Step 10. Start upgrade.

(if your upgrade file is bigger than 500K, you always need to upgrade to tasmota-minimal.bin first to free some space of your ESP8266 to proceed.
Or you will fail up upgrade)



Other ways to build your own tasmota.bin
1. use Atom software to build your binary file.
2. then use NodeMCU Pyflasher to flash your board. (select: 115200, Dual Output(DOUT), yes, wipes all data)
