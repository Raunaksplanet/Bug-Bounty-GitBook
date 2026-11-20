---
description: SSL pinning bypass and traffic interception on iOS.
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

# 🔐 SSL Pinning and Traffic Interception

Most iOS apps can be proxied once the certificate is trusted on the device. Apps with pinning need a Frida or Objection bypass on top of that.

- [Bypass SSL pinning on iOS 15 and above without jailbreak](https://medium.com/@SecureWithMohit/ios-15-and-above-traffic-intercept-via-burp-proxy-without-jailbreak-e72a36fd36cd): Burp proxy on a non-jailbroken device.
- [Intercept Flutter app traffic on iOS and Android](https://infosecwriteups.com/hacking-flutter-apps-network-interception-technique-for-ios-and-android-applications-4f79d065fb29): Flutter needs a different approach from normal apps.
- [Intercept HTTPS traffic on iPhone with Burp Suite](https://www.youtube.com/watch?v=awdL6qVT3Cw): the basic proxy setup.
- [SSL pinning in iOS applications](https://medium.com/@rajauzairabdullah/ssl-pinning-in-ios-applications-2a5af4749200): explains pinning and the usual bypass approaches.
