# Open questions: CarCast / iCarCast

The docs alone can't answer these. Most would need the release binaries (IPA/APK) or a packet capture.

1. **How does an App Store / TestFlight app pass CarPlay accessory authentication** without an MFi auth chip? Software emulation, a licensed certificate, or something else? (ARCHITECTURE W8)
2. **What exactly did TestFlight builds 1-4 write to saved Wi-Fi profiles** (wrong security type, wrong or empty password)? What does build 6's "check the network first" actually check? (UG:267-280)
3. **What's the remote-touch transport?** Bluetooth HID pointer, an iAP2 HID descriptor, or something else? Why is Zoom specifically required rather than AssistiveTouch? (UG:121-131)
4. **How is a receiver authorized for remote touch?** Is "Allow" bound to a cryptographic device identity, or only to the `CarCast-XXXX` name? Can a spoofed name inherit the authorization?
5. **Where does the persistent device identity live** (Keychain, iCloud Keychain)? What is it: a UUID, a key pair, a MAC-like ID? (docs/ios.md:37)
6. **What does the Browser screen expose?** Port, protocol, authentication, and whether it listens only while active. (UG:156-157)
7. **Does the receiver validate AirPlay-push URLs** before fetching them? (UG:141-142)
8. **Which is right about Personal Hotspot,** `docs/releases.md:54` or the user guide? Presumably the guide, since it's newer and repeats the point consistently.
9. **What does CarCast Launcher's Accessibility service do** beyond the one tap? What does it collect, and how does it "announce the phone" (mDNS service type)? (UG:224-228)
10. **Release binaries weren't examined.** They live on GitHub Releases (`ios-ipad-1.0-15`, `ios-ipad-legacy-1.0-15`, `launcher-1.0-beta.1`, `android-0.3.27`), not in the git tree. Analyzing them is the next step if a code-level map is wanted.
