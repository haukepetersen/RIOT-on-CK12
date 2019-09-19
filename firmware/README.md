# Analysis of the original vendor firmware

## Tools used

Tools used:
- nrfjlink (version: 10.3.0)
- JLinkExe (SEGGER J-Link Commander V6.50b)
- arm-none-eabi-objcopy ((GNU Tools for Arm Embedded Processors 8-2018-q4-major) 2.31.51.20181213)


## Offloading the firmware
The naive approach is simply to use `nrfjprog` to download the binary from an untouched device:
```
# make sure the device is connected
nrfjprog --readregs

# read ROM
nrfjprog --readcode FOO.hex

# convert hex file to binary
arm-none-eabi-objcopy -Iihex -Obinary FOO.hex FOO.bin
```

But of course it is not that easy: the original firmware is readback protected:
```
nrfjprog --readregs
ERROR: The operation attempted is unavailable due to readback protection in
ERROR: your device. Please use --recover to unlock the device.
```

Simply using that `--recover` option is out of the questions, this would delete the original firmware - and thus would not be beneficial to our cause...

So we need to find another way in :-)

## Trying to offload firmware using OpenOCD (bypassing the readback protection)

https://www.pentestpartners.com/security-blog/nrf51822-code-readout-protection-bypass-a-how-to/


--> No success to circumwent the readback so far, seems we need to find a way to write the UICR.APPROTECT register without deleting anything else...
