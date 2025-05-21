---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 🎹 CLI Commands & Shortcuts

| Category               | Command                                                                                                                                        | Description                            |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------- |
| **Emulator Commands**  | `emulator -list-avds`                                                                                                                          | List available Android Virtual Devices |
|                        | `emulator -avd New-Pixel_4 -writable-system -no-snapshot`                                                                                      | Start emulator with writable system    |
|                        | `emulator -avd Pixel_3a_Root -writable-system -no-snapshot -port 5560`                                                                         | Start emulator on specific port        |
| **MOBSF**              | `docker run -it --rm -p 8000:8000 -p 1337:1337 -e MOBSF_ANALYZER_IDENTIFIER=emulator-5554 opensecurity/mobile-security-framework-mobsf:latest` | Start MOBSF container                  |
| **ADB Commands**       | `adb shell pm list packages -3`                                                                                                                | List 3rd party packages                |
|                        | `adb shell getprop ro.product.cpu.abi`                                                                                                         | Get device CPU architecture            |
|                        | `adb push frida-server /data/local/tmp/`                                                                                                       | Push file to device                    |
|                        | `adb -s emulator-5560 push C:\Users\HP\Downloads\frida-server /data/local/tmp`                                                                 | Push to specific emulator              |
|                        | `adb shell "chmod +x /data/local/tmp/frida-server"`                                                                                            | Make frida-server executable           |
|                        | `adb shell "/data/local/tmp/frida-server &"`                                                                                                   | Start frida-server in background       |
| **Frida Commands**     | `frida-ps -Uia`                                                                                                                                | List running apps on USB device        |
|                        | `frida -U -f com.target.app --no-pause -l ssl-pinning-bypass.js`                                                                               | Inject script into app                 |
|                        | `frida --codeshare dzonerzy/fridantiroot -f <package-name> -U`                                                                                 | Use anti-root detection script         |
|                        | `frida --codeshare masbog/frida-android-unpinning-ssl -f <package-name> -U`                                                                    | Use SSL unpinning script               |
| **Objection Commands** | `objection-connect`                                                                                                                            | Connect to device                      |
|                        | `objection-patch <my.apk>`                                                                                                                     | Patch APK for objection                |
|                        | `objection -g <package name> explore`                                                                                                          | Explore app with objection             |
|                        | `android root disable`                                                                                                                         | Disable root detection                 |
|                        | `android sslpinning disable`                                                                                                                   | Disable SSL pinning                    |
|                        | `android hooking watch class <package-name>.UserMainActivity`                                                                                  | Watch class methods                    |
|                        | `android hooking list classes`                                                                                                                 | List all classes                       |

***

## Drozer Commands

| Command                                                                    | Description                                           | Example / Notes                                                                                                             |
| -------------------------------------------------------------------------- | ----------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `help`                                                                     | Show help menu with commands                          | `help`                                                                                                                      |
| `list`                                                                     | List all available modules                            | `list`                                                                                                                      |
| `run <module>`                                                             | Run a specific module                                 | `run app.package.list`                                                                                                      |
| `run app.package.list`                                                     | List installed packages                               | `run app.package.list`                                                                                                      |
| `run app.package.attacksurface -a <package>`                               | Show attack surface (exported components)             | `run app.package.attacksurface -a com.example.app`                                                                          |
| `run app.package.info -a <package>`                                        | Show detailed info about a package                    | `run app.package.info -a com.example.app`                                                                                   |
| `run app.activity.info -a <package>`                                       | List activities of an app                             | `run app.activity.info -a com.example.app`                                                                                  |
| `run app.provider.info -a <package>`                                       | List content providers                                | `run app.provider.info -a com.example.app`                                                                                  |
| `run app.service.info -a <package>`                                        | List services                                         | `run app.service.info -a com.example.app`                                                                                   |
| `run app.broadcast.info -a <package>`                                      | List broadcast receivers                              | `run app.broadcast.info -a com.example.app`                                                                                 |
| `run app.activity.start -a <package> -n <activity>`                        | Start a specific activity                             | `run app.activity.start -a com.example.app -n MainActivity`                                                                 |
| `run scanner.provider.injection -a <package>`                              | Check for SQL injection in content providers          | `run scanner.provider.injection -a com.example.app`                                                                         |
| `run scanner.provider.access -a <package>`                                 | Check for content provider access issues              | `run scanner.provider.access -a com.example.app`                                                                            |
| `run scanner.misc.debuggable -a <package>`                                 | Check if app is debuggable                            | `run scanner.misc.debuggable -a com.example.app`                                                                            |
| `run scanner.misc.exportedcomponents -a <package>`                         | Check for exported components                         | `run scanner.misc.exportedcomponents -a com.example.app`                                                                    |
| `run scanner.permissions.findleaks -a <package>`                           | Find permission leaks                                 | `run scanner.permissions.findleaks -a com.example.app`                                                                      |
| `run exploit.reinvokeactivity -a <package> -n <activity>`                  | Exploit activity re-invocation                        | `run exploit.reinvokeactivity -a com.example.app -n MainActivity`                                                           |
| `run exploit.debug`                                                        | Exploit debugging features                            | `run exploit.debug`                                                                                                         |
| `run exploit.serial -a <package>`                                          | Check for serial number leaks                         | `run exploit.serial -a com.example.app`                                                                                     |
| `run shell`                                                                | Get a shell on the device                             | `run shell`                                                                                                                 |
| `run shell pm list packages`                                               | List all packages via shell                           | `run shell pm list packages`                                                                                                |
| `run shell dumpsys package <package>`                                      | Get package dump information                          | `run shell dumpsys package com.example.app`                                                                                 |
| `run file.list -p /path/`                                                  | List files in a directory                             | `run file.list -p /data/data/com.example.app/`                                                                              |
| `run file.download -p <path>`                                              | Download file from device                             | `run file.download -p /data/data/com.example.app/databases/db.sqlite`                                                       |
| `run app.package.dump -a <package>`                                        | Dump manifest & app details                           | `run app.package.dump -a com.example.app`                                                                                   |
| `run scanner.activity.launcher -a <package>`                               | Check for launcher activities                         | `run scanner.activity.launcher -a com.example.app`                                                                          |
| `run scanner.broadcast.receiver -a <package>`                              | Scan for vulnerable broadcast receivers               | `run scanner.broadcast.receiver -a com.example.app`                                                                         |
| `run scanner.service.exported -a <package>`                                | Detect exported services                              | `run scanner.service.exported -a com.example.app`                                                                           |
| `run scanner.file.find -f <filename>`                                      | Find files matching filename                          | `run scanner.file.find -f "*.db"`                                                                                           |
| `run scanner.file.find -p <path>`                                          | Search files recursively under path                   | `run scanner.file.find -p /sdcard/`                                                                                         |
| `run scanner.intent.receiver -a <package>`                                 | Test intent receivers for possible hijacking          | `run scanner.intent.receiver -a com.example.app`                                                                            |
| `run scanner.intent.sender -a <package>`                                   | Test sending intents to apps                          | `run scanner.intent.sender -a com.example.app`                                                                              |
| `run exploit.activity.intent -a <package> -n <activity>`                   | Exploit vulnerable activity intents                   | `run exploit.activity.intent -a com.example.app -n MainActivity`                                                            |
| `run exploit.provider.injection -a <package>`                              | Exploit content provider SQL injection                | `run exploit.provider.injection -a com.example.app`                                                                         |
| `run exploit.provider.insert -a <package>`                                 | Insert malicious data into content provider           | `run exploit.provider.insert -a com.example.app`                                                                            |
| `run exploit.provider.delete -a <package>`                                 | Delete data via content provider                      | `run exploit.provider.delete -a com.example.app`                                                                            |
| `run exploit.provider.update -a <package>`                                 | Update data via content provider                      | `run exploit.provider.update -a com.example.app`                                                                            |
| `run exploit.provider.query -a <package>`                                  | Query data via content provider                       | `run exploit.provider.query -a com.example.app`                                                                             |
| `run scanner.credentials.find`                                             | Find exposed credentials on device                    | `run scanner.credentials.find`                                                                                              |
| `run scanner.storage.find`                                                 | Find sensitive files in storage                       | `run scanner.storage.find`                                                                                                  |
| `run scanner.intent.injection`                                             | Detect intent injection vulnerabilities               | `run scanner.intent.injection`                                                                                              |
| `run exploit.sharedprefs.read -a <package> -p <path>`                      | Read shared preferences file                          | `run exploit.sharedprefs.read -a com.example.app -p /data/data/com.example.app/shared_prefs/config.xml`                     |
| `run exploit.sharedprefs.write -a <package> -p <path> -k <key> -v <value>` | Modify shared preferences                             | `run exploit.sharedprefs.write -a com.example.app -p /data/data/com.example.app/shared_prefs/config.xml -k isAdmin -v true` |
| `run scanner.webview.loadurl`                                              | Test if app loads arbitrary URLs in WebView           | `run scanner.webview.loadurl`                                                                                               |
| `run scanner.webview.javascript`                                           | Detect vulnerable WebView JavaScript interfaces       | `run scanner.webview.javascript`                                                                                            |
| `run exploit.ssl.trustmanager`                                             | Test SSL trust manager bypass                         | `run exploit.ssl.trustmanager`                                                                                              |
| `run scanner.permission.injection`                                         | Check for permission escalation opportunities         | `run scanner.permission.injection`                                                                                          |
| `run exploit.permission.escalation`                                        | Try permission escalation                             | `run exploit.permission.escalation`                                                                                         |
| `run scanner.database.leak -a <package>`                                   | Detect database leaks                                 | `run scanner.database.leak -a com.example.app`                                                                              |
| `run scanner.crypto.insecure -a <package>`                                 | Detect insecure crypto usage                          | `run scanner.crypto.insecure -a com.example.app`                                                                            |
| `run scanner.network.manifest`                                             | Check for insecure network configurations in manifest | `run scanner.network.manifest -a com.example.app`                                                                           |
| `run scanner.misc.nativecode`                                              | Check for native code usage that may be vulnerable    | `run scanner.misc.nativecode -a com.example.app`                                                                            |
| `run scanner.misc.screenshots`                                             | Detect if app allows screenshots                      | `run scanner.misc.screenshots -a com.example.app`                                                                           |
| `run exploit.binding.command`                                              | Try to execute system commands via exported bindings  | `run exploit.binding.command -a com.example.app`                                                                            |
