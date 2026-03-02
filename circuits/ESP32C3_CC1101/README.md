## creating the code
open a new devcontainer as a new codespace on github
after setting up the devcontainer, install platformio

`pip3 install -U platformio`

compile the code with 
`platformio run -e esp32c3_cc1101` 

## Flashing the code
<pre>esptool --port COM7 --chip esp32c3 --baud 921600 --before default-reset --after hard-reset write-flash -z --flash-mode dout --flash-size detect 0x0 bootloader.bin 0x8000 partitions.bin 0x10000 firmware.bin</pre>