# scrcpy

**scrcpy** (Screen Copy) is an open-source tool for displaying and controlling an Android device from a computer. It supports both USB and wireless connections, providing developers and enthusiasts with an efficient way to interact with their Android devices via a PC or laptop.

## Key Features

- **High performance:** scrcpy supports resolutions up to 1920x1080 at 60 frames per second. It utilizes hardware video encoding (H.264) for high performance and low latency.
- **Two-way interaction:** You can not only view the device screen but also control it using your mouse and keyboard.
- **No need for additional apps:** Scrcpy does not require any apps to be installed on the Android device. All necessary components run from the computer.
- **Cross-platform support:** scrcpy works on Windows, Linux, and macOS, making it a versatile tool for users across different operating systems.
- **Low latency:** scrcpy provides minimal latency when displaying the screen, making it ideal for real-time use, such as demonstrations or app testing.
- **Wireless connection support:** Scrcpy allows you to connect to your device over Wi-Fi, eliminating the need for a USB cable.

## Installation

### Linux

To install on Linux, follow these steps:

1. Update the package list:
    ```bash
    sudo apt update
    ```

2. Install the necessary dependencies:
    ```bash
    sudo apt install adb ffmpeg libsdl2-2.0-0 libavcodec-dev libavformat-dev libswscale-dev libx11-dev
    ```

3. Install scrcpy:
    ```bash
    sudo apt install scrcpy
    ```

### Windows

For Windows users, download the release from the [official GitHub page](https://github.com/Genymotion-device/scrcpy/releases).

1. Download the archive for Windows.
2. Extract the archive to a preferred location.
3. Run `scrcpy.exe`.

### macOS

To install on macOS, it's recommended to use [Homebrew](https://brew.sh/):

1. Install Homebrew if it's not already installed:
    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

2. Install scrcpy:
    ```bash
    brew install scrcpy
    ```

## Usage

To use scrcpy, connect your Android device to your computer via USB or Wi-Fi.

### USB Connection

1. Enable USB debugging on your Android device:
    - Go to "Settings" -> "About phone" and tap "Build number" multiple times to enable Developer options.
    - In the Developer options, enable "USB debugging."

2. Connect the device to your PC using a USB cable.

3. Run scrcpy:
    ```bash
    scrcpy
    ```

### Wireless Connection

To use scrcpy over Wi-Fi, follow these steps:

1. Connect your device to your PC via USB.
2. Get the device's IP address:
    ```bash
    adb shell ip route
    ```

3. Enable Wi-Fi mode for scrcpy:
    ```bash
    adb tcpip 5555
    ```

4. Disconnect the USB cable and connect over Wi-Fi:
    ```bash
    adb connect <ip_address>
    ```

5. Run scrcpy:
    ```bash
    scrcpy
    ```

## Additional Features

- **Screen recording:** scrcpy supports screen recording from your device. To start recording, use the `--record` flag:
    ```bash
    scrcpy --record file.mp4
    ```
- **Quality adjustments:** You can adjust the image quality and data rate using the `-b` flag for bitrate and `-m` for maximum resolution. For example:
    ```bash
    scrcpy -b 8M -m 1024
    ```
- **Audio support:** If your device supports audio, scrcpy can forward audio from your device to your computer. Use the `--audio` flag:
    ```bash
    scrcpy --audio
    ```

## Tips and Tricks

- **Keyboard control:** All standard keyboard events, such as key presses, work through scrcpy, allowing you to interact with your Android device as if you were using a keyboard and mouse.
- **Keyboard shortcuts:** Scrcpy supports several keyboard shortcuts, such as `Ctrl + c` for copying, `Ctrl + v` for pasting, and others.
- **Fullscreen mode:** To use the device screen in fullscreen mode, simply press `Ctrl + f`.

## License

scrcpy is distributed under the **Apache 2.0** license. You are free to use, modify, and distribute the software under the terms of the license.

## Contact the Developers

If you encounter any issues with scrcpy or have suggestions for improvement, please open an issue on the [GitHub repository](https://github.com/Genymotion-device/scrcpy).

## Conclusion

scrcpy is an incredibly powerful tool for interacting with Android devices from a computer. It is easy to use, highly performant, and supports both wired and wireless connections. If you regularly work with Android apps or want to demonstrate your device's content on a larger screen, scrcpy will become an indispensable tool in your workflow.
