# Desktop Launcher

Flutter Desktop for Mac OS, Linux, Windows Launcher

## Getting Started

You can view how to setup this launcher on Youtube: [Run Flutter on Desktop Platform without Emulator](https://www.youtube.com/watch?v=QFD2r4C3fHs).

![Flutter Desktop Hot Reload](https://github.com/canewsin/flutter_desktop_launcher/blob/master/demo.gif)

How to setup for VSCode:
- Run   ```flutter doctor -v``` because your info has to match with below 
 - For Linux : 
```
[✓] Flutter (Channel stable, v1.2.1, on Linux, locale en_IN)
    • Flutter version 1.2.1 at /your/path/to/flutter
    • Framework revision 8661d8aecd (7 weeks ago) 2019-02-14 19:19:53 -0800
    • Engine revision 3757390fa4
    • Dart version 2.1.2 (build 2.1.2-dev.0.0 0a7dcf17eb)

```
 - For Mac OS : 
```
[✓] Flutter (Channel stable, v1.0, on Mac OS, locale en_IN)
```

 - For Windows 10 : 
```
[√] Flutter (Channel stable, v1.2.1, on Microsoft Windows [Version 10.0.17763.379], locale en-IN)
    • Flutter version 1.2.1 at C:\flutter\1.0.0
    • Framework revision 8661d8aecd (7 weeks ago), 2019-02-14 19:19:53 -0800
    • Engine revision 3757390fa4
    • Dart version 2.1.2 (build 2.1.2-dev.0.0 0a7dcf17eb)
```

# Download

- Windows 10  
   - [Debug](https://github.com/canewsin/flutter_desktop_launcher/raw/master/v1.2.1/flutter_desktop_windows_debug.zip)

- Linix/Debian  
   - [Release](https://github.com/canewsin/flutter_desktop_launcher/raw/master/v1.2.1/flutter_desktop_linux_release.zip)  
   - [Debug](https://github.com/canewsin/flutter_desktop_launcher/raw/master/v1.2.1/flutter_desktop_linux_debug.zip)
  
- Mac OS  
   - [Debug](https://github.com/canewsin/flutter_desktop_launcher/raw/master/v1.0.0/macos_launcher.zip)    

   Mac OS binary files not updated to Latest flutter version anybody can contribute and make pull request, Pull Request should include ``` flutter doctor -v ``` as above.
- Extract zip archive
- Copy `Flutter.app` (Mac) / `flutter_desktop + all files` (Linux)/ `flutter_desktop.exe + all files` (Windows) to your project, I had provided 2 folders so choose release version(without asserts and debug label) or debug version as required
- Modify your `main.dart` add target platform to `Fuchsia`

  ```dart
  import 'package:flutter/foundation.dart'

  show debugDefaultTargetPlatformOverride; // for desktop embedder

  void main() {
    debugDefaultTargetPlatformOverride = TargetPlatform.fuchsia; // for desktop embedder
    runApp(MyApp());
  }
  ```

- Build flutter bundle inside your project `flutter build bundle`
- Run `Flutter.app` or `./flutter_desktop` or `flutter_desktop.exe`
- *This will give a port insert it below config file.
- Open VS Code Cmd Pannel and search for `Debug: open launch.json`
- In VS Code create Launch Configuration:
  ```javascript
  {
    "version": "0.2.0",
    "configurations": [
      {
        "name": "Flutter Desktop",
        "request": "attach",
        "deviceId": "flutter-tester",
        "observatoryUri": "http://127.0.0.1:Your_Port_comes_here*/",
        "type": "dart"
      }
    ]
  }
  ```
- ` now ` Hot Reload  will work..

How to setup for Android Studio:
- [![Flutter Desktop on Android Studio](https://img.youtube.com/vi/imgl0GTopYM/0.jpg)](https://www.youtube.com/watch?v=imgl0GTopYM)
