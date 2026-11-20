---
description: Jailbreak detection, biometrics and anti-debugging bypasses.
layout:
  width: default
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
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# 🛡️ Jailbreak Detection and Bypasses

These protections are common on banking and payment apps. Read the detection code first, then patch or hook the check instead of guessing.

- [Bypass debugger detection in native libraries with IDA Pro](https://medium.com/@shubhamsonani/how-to-bypass-debugger-detection-in-android-ios-native-libraries-using-ida-pro-3e289c2127d6): covers both Android and iOS.
- [iOS biometrics bypass writeup](https://medium.com/@pandurangisuprit/no-finger-no-problem-ios-biometrics-bypassed-bug-bounty-win-f17bf619a089): a bug bounty case where Face ID and Touch ID checks were skipped.
- [Jailbreak detection bypass in iOS](https://medium.com/@rajauzairabdullah/everything-you-need-to-know-about-ios-jailbreak-detection-bypass-6a1183177797): how detection works and how to get around it.
