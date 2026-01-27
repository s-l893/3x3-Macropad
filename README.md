
# 3x3 Macropad with QMK

A custom DIY 3x3 macropad built with a Pro Micro microcontroller running QMK firmware.

## Hardware

- **Microcontroller**: Pro Micro (ATmega32U4)
- **Layout**: 3x3 ortholinear grid (9 keys)
- **Firmware**: QMK (Quantum Mechanical Keyboard)
- **Switches**: Epomaker Wisteria
- **PCB**: Custom designed

## Features

- Fully programmable keys via QMK
- Custom macros and key combinations
- USB connectivity
- Low-latency input
- Open-source firmware
- Automatic keyboard.json file Windows BATCH replacement script
- HTML-based front-end serving as a keyboard.json file creator

## Firmware Setup

### Prerequisites

- QMK MSYS (Windows) or QMK CLI (Mac/Linux)
- Git
- Pro Micro with bootloader

### Installation

1. **Clone QMK firmware repository**
```bash
   git clone --recurse-submodules https://github.com/qmk/qmk_firmware.git
   cd qmk_firmware
```

2. **Set up QMK**
```bash
   qmk setup
```

3. **Copy this keyboard to QMK**
   
   Copy the `macropad_v2` folder to `keyboards/macropad_v2/` in your QMK installation

### Compiling and Flashing

1. **Compile the firmware**
```bash
   qmk compile -kb macropad_v2 -km default
```

2. **Flash to Pro Micro**
```bash
   qmk flash -kb macropad_v2 -km default
```

3. **Enter bootloader mode**
   - Short RST to GND twice quickly on your Pro Micro
   - You have ~8 seconds to flash once in bootloader mode

### Windows BATCH Script

   - Using the HTML front end by simply opening the file with your browser of choice, create your macropad configuration and download the file to your downloads folder
   - BATCH script will automatically replace the file in your QMK macropad firmware
    
### Customizing Your Layout

Edit the keymap file at `keyboards/macropad_v2/keymaps/default/keymap.c` to customize your key functions.

After making changes, reflash using:
```bash
qmk flash -kb macropad_v2 -km default
```

## Default Keymap

The default keymap sends numbers 1-9:
```
┌───┬───┬───┐
│ 1 │ 2 │ 3 │
├───┼───┼───┤
│ 4 │ 5 │ 6 │
├───┼───┼───┤
│ 7 │ 8 │ 9 │
└───┴───┴───┘
```

## Pin Configuration

[Add your specific pin configuration here based on your PCB design]

Example:
```
Row Pins: D1, D0, D4
Col Pins: C6, D7, E6
Diode Direction: COL2ROW
```

## Customization Ideas

- **Media controls**: Volume up/down, play/pause, next/previous track
- **Application shortcuts**: Open programs, switch windows
- **Text macros**: Email signatures, code snippets, common phrases
- **Gaming**: Skill shortcuts, inventory management
- **Streaming**: Scene switching, mute/unmute, start/stop recording

## Troubleshooting

### Keys not registering
- Check your wiring connections
- Verify pin assignments in `info.json` or `keyboard.json` match your PCB
- Test individual switches with a multimeter

### Flash not working
- Ensure Pro Micro is in bootloader mode (double-tap reset)
- Check USB cable connection
- Verify QMK dependencies are installed: `qmk setup`

### LUFA compilation errors
- Update submodules: `git submodule update --init --recursive`
- Or run: `make git-submodule`

## Contributing

Feel free to submit issues or pull requests if you have improvements or find bugs!

## Resources

- [QMK Documentation](https://docs.qmk.fm/)
- [QMK Configurator](https://config.qmk.fm/)
- [Pro Micro Pinout](https://learn.sparkfun.com/tutorials/pro-micro--fio-v3-hookup-guide)
- [QMK Keycodes Reference](https://docs.qmk.fm/keycodes)

## License

This project is open source. 

## Acknowledgments

- QMK Firmware team
- DIY keyboard community
