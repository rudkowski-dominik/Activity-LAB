# Open questions: CarCast / iCarCast

The docs alone can't answer these. Most would need the release binaries (IPA/APK) or a packet capture. Items marked **Partly answered** were narrowed by the user's screenshots (IMG_2138-IMG_2148).

1. **How does an App Store / TestFlight app pass CarPlay accessory authentication** without an MFi auth chip? Software emulation, a licensed certificate, or something else? (W8.) The publisher being VMLite Corporation (IMG_2144) suggests an existing accessory vendor, but that's unverified.
2. **What exactly did TestFlight builds 1-4 write to saved Wi-Fi profiles** (wrong security type, wrong or empty password)? What does build 6's "check the network first" actually check? (UG:267-280)
3. **What's the remote-touch transport?** Bluetooth HID pointer, an iAP2 HID descriptor, or something else? Why is Zoom specifically required rather than AssistiveTouch? (UG:121-131; the "AirPlay control" toggle, IMG_2138)
4. **How is a receiver authorized for remote touch?** Is "Allow" bound to a cryptographic device identity, or only to the `CarCast-XXXX` name? Can a spoofed name inherit the authorization?
5. **Partly answered.** What the persistent device identity is: a **MAC-format, locally administered Device ID** (IMG_2142). Still open: where it's stored (Keychain?), and how the `CarCast-XXXX` suffix is derived, since it doesn't match the Device ID's last bytes.
6. **Partly answered.** The Browser screen is HTTPS on :8081 plus WebSocket on :8888, configurable (IMG_2140). Still open: is there any auth or token, is the certificate self-signed, does it listen only while the mode is on, and does the WebSocket accept input (touches) or only send frames?
7. **Does the receiver validate AirPlay-push URLs** before fetching them? (UG:141-142)
8. **Partly answered.** Personal Hotspot: the vendor's own texts disagree (W3). Still open: does build 17 actually try a hotspot-based This iPhone path when there's no Wi-Fi, as the home screen suggests (IMG_2143)? Testable on-device: turn Wi-Fi off, turn the hotspot on, tap This iPhone, and note the result.
9. **What does CarCast Launcher's Accessibility service do** beyond the one tap? What does it collect, and how does it "announce the phone" (mDNS service type)? (UG:224-228)
10. **Why is the iPhone's "Screen" reported as 1920 × 1014** with "Fit this screen" (IMG_2142)? It's not the native panel size; is it a scaled canvas?
11. **Why does build 16 require iOS 17+ for This iPhone and Connect** (IMG_2145)? It likely depends on an iOS 17 networking or CarPlay API, which would hint at how the loopback works.
12. **Release binaries weren't examined.** They live on GitHub Releases (`ios-ipad-1.0-15`, `ios-ipad-legacy-1.0-15`, `launcher-1.0-beta.1`, `android-0.3.27`), not in the git tree. Analyzing them is the next step if a code-level map is wanted.
