This is a specialized version of GRBL for our photonics lab automation purposes. For arduino mega 2560.

-- How to upload: --

0. install arduino ide and ch430 driver

1. select the right com port (arduino ide -> Tools -> Port -> ...)

2. select the right board (Tools -> Board -> mega 2560)

3. load pla-firmware\pla-firmware.ino into ide\*, and upload. IDE status bar should read "uploaded" on green background if successful.

4. (optional\*\*) reset config stored in eeprom: send `$RST=*` followed by a newline to com port via terminal

\*) do not install grbl as an arduino library. If it is alreagy installed as a library, uninstall, otherwise it will fail to compile.

\*\*) uploading the firmware does not wipe EEPROM data. GRBL stores a lot of settings in eeprom, such as max speeds, limit switch config, status reporting, and so on. These settings will persist through uploading. Sending `$RST=*` will reset them to defaults set in firmware code.

