### Device Basics

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>adb devices</code></td><td>Lists connected devices</td></tr><tr class="even"><td><code>adb devices -l</code></td><td>Lists connected devices and kind</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>adb root</code></td><td>Restarts adbd with root permissions</td></tr><tr class="odd"><td><code>adb start-server</code></td><td>Starts the adb server</td></tr><tr class="even"><td><code>adb kill-server</code></td><td>Kills the adb server</td></tr><tr class="odd"><td><code>adb remount</code></td><td>Remounts file system with read/write access</td></tr><tr class="even"><td><code>adb reboot</code></td><td>Reboots the device</td></tr><tr class="odd"><td><code>adb reboot bootloader</code></td><td>Reboots the device into fastboot</td></tr><tr class="even"><td><code>adb disable-verity</code></td><td>Reboots the device into fastboot</td></tr></tbody></table>

`wait-for-device` can be specified after `adb` to ensure that the command will run once the device is connected.

`-s` can be used to send the commands to a specific device when multiple are connected.

#### Examples

    $ adb wait-for-device devices
     List of devices attached
     somedevice-1234 device
     someotherdevice-1234 device

    $ adb -s somedevice-1234 root

### Logcat

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>adb logcat</code></td><td>Starts printing log messages to stdout</td></tr><tr class="even"><td><code>adb logcat -g</code></td><td>Displays current log buffer sizes</td></tr><tr class="odd"><td><code>adb logcat -G &lt;size&gt;</code></td><td>Sets the buffer size (K or M)</td></tr><tr class="even"><td><code>adb logcat -c</code></td><td>Clears the log buffers</td></tr><tr class="odd"><td><code>adb logcat *:V</code></td><td>Enables ALL log messages (verbose)</td></tr><tr class="even"><td><code>adb logcat -f &lt;filename&gt;</code></td><td>Dumps to specified file</td></tr></tbody></table>

#### Examples

    $ adb logcat -G 16M
    $ adb logcat *:V > output.log

### File Management

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>adb push &lt;local&gt; &lt;remote&gt;</code></td><td>Copies the local to the device at remote</td></tr><tr class="even"><td><code>adb pull &lt;remote&gt; &lt;local&gt;</code></td><td>Copies the remote from the device to local</td></tr></tbody></table>

#### Examples

    $ echo "This is a test" > test.txt
    $ adb push  test.txt /sdcard/test.txt
    $ adb pull /sdcard/test.txt pulledTest.txt

### Remote Shell

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>adb shell &lt;command&gt;</code></td><td>Runs the specified command on device (most unix commands work here)</td></tr><tr class="even"><td><code>adb shell wm size</code></td><td>Displays the current screen resolution</td></tr><tr class="odd"><td><code>adb shell wm size WxH</code></td><td>Sets the resolution to WxH</td></tr><tr class="even"><td><code>adb shell pm list packages</code></td><td>Lists all installed packages</td></tr><tr class="odd"><td><code>adb shell pm list packages -3</code></td><td>Lists all installed 3rd-party packages</td></tr><tr class="even"><td><code>adb shell monkey -p app.package.name</code></td><td>Starts the specified package</td></tr></tbody></table>
