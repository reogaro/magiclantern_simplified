# ptpcam

Host tool for communicating with connected cameras via USB-PTP.

## Usage

```bash
USAGE: ptpcam [OPTION]

Options:
  --bus=BUS-NUMBER             USB bus number
  --dev=DEV-NUMBER             USB assigned device number
  -r, --reset                  Reset the device
  -l, --list-devices           List all PTP devices
  -i, --info                   Show device info
  -o, --list-operations        List supported operations
  -p, --list-properties        List all PTP device properties
  -s, --show-property=NUMBER   Display property details
  --set-property=NUMBER        Set property value (--val required)
  --set=PROP-NAME              Set property by name
  --val=VALUE                  Property value
  --show-all-properties        Show all properties values
  --show-unknown-properties    Show unknown properties values
  -L, --list-files             List files on device
  --chdk                       Connect to Magic Lantern / CHDK interactive console
```

## Dependencies

To build `ptpcam`, you need `libusb-1.0` and `pkg-config` installed on your system. 

On Ubuntu/Debian:
```bash
sudo apt-get install libusb-1.0-0-dev pkg-config
```

On macOS (Homebrew):
```bash
brew install libusb pkg-config
```

On Windows (MSYS2/MinGW64):

For Windows: install MSYS2 and use "MSYS2 MinGW 64-bit" for compiling:

```bash
pacman -S mingw-w64-x86_64-libusb mingw-w64-x86_64-pkgconf mingw-w64-x86_64-gcc make
```

Windows users will need to use Zadig (or similar tools) to replace the camera's default driver with the WinUSB driver.

## Build

Simply run:
```bash
make
```

## Changelog
- **2026-07 Refactor:** Fully transitioned to native `libusb-1.0`, modernized for 64-bit portability, fixed pointer arithmetic bugs, and resolved compilation warnings.
- **g3gg0:** Modified for MagicLantern GDB stubs.
- **nanomad:** Minor build fixes.
