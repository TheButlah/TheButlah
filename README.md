# Hi, I'm Ryan 👋

I'm a Rust developer, passionate about building realtime systems. I do a lot of open
source VR development, especially for full-body motion tracking in games like VRChat.

I also like to dance and go bouldering.

## Hire Me 🔥
**I'm actively seeking job opportunities** - I will build you something awesome, in exchange
for money. It's a win win :) You can contact me at [rjbutler.main@gmail.com].

If you would like to support my open source projects, you can fund me at [ko-fi].


## Current Projects
<details>
<summary> Click to expand </summary>

### SlimeVR

SlimeVR is an open source organization for full-body motion capture in VR. It uses IMUs
and a forward kinematics model to allow social VR users to have legs in games like
VRChat. I am a core contributor in the org, and the primary author of several
components of the ecosystem.

The four main things I work on under this umbrella, are located in the [SlimeVR-Rust]
monorepo or in [SolarXR]. 

#### [Firmware]
I develop bare metal embedded rust on the ESP32C3 and NRF52840 microcontrollers, which
takes IMU sensor data, does sensor fusion, and sends that data over WiFi or BLE. I use
async/await and [`embassy`] for concurrency without the need for an RTOS[^1].

This firmware has been really fun to work on and is what I spend most of my time on
right now.

If that sounds exciting to you, open a PR or [support my work] so I can buy
more hardware :)

#### [Overlay]
I also am the primary author of an OpenVR overlay for SlimeVR, which renders a simple 3D
view in VR of the pose of the user. This has been critical in debugging SlimeVR, and
allows power users to tweak their settings in real time.

I also created [`ovr_overlay`], which allows rust code to access the C++ based OpenVR
API. Prior to this work, only fairly out of date and unmaintained bindings to the C API
existed. I used [`autocxx`] to easily write FFI for the C++ code.

#### [Skeletal Model]
I created an experimental skeletal model that can solve the user's pose. The goal is to
be more general purpose than the current (trigger warning) Java based model that the
official server uses, with several new features like arbitrary positional constraints,
adjusting mounting calibration without a full reset, and supporting languages other than
Java, via FFI.

Unfortuantely, a lot of the skeletal model is still feature incomplete. If you are
interested in helping me build this, reach out to me on the [SlimeVR discord].

#### [SolarXR Protocol]
I maintain and co-authored the SolarXR protocol, which is a Websocket and Flatbuffer
based networking protocol that allows applications (like the [GUI] and [overlay]) to
work with the SlimeVR server.

After we adopted the protocol, it allowed the team to break the gui code into
its own app and adopt technologies like `tauri`, `typescript`, and `react`, with
clearer separation of concerns, less code, and prettier UI/UX.

</details>

## Tech I think is cool
|     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
| <img src="https://www.rust-lang.org/logos/rust-logo-128x128.png" height="25" /> | Rust | <img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Neovim-mark.svg" height="25" /> | Neovim | <img src="https://blog.bazel.build/images/bazel-icon.svg" height="25" /> | Bazel | <img src="https://buck2.build/img/logo.svg" height="25" /> | Buck2 |
| <img src="https://upload.wikimedia.org/wikipedia/commons/1/1f/WebAssembly_Logo.svg" height="25" /> | WebAssembly | <img src="https://raw.githubusercontent.com/bevyengine/bevy/main/assets/branding/icon.svg" height="25" /> | Bevy | <img src="https://raw.githubusercontent.com/gpuweb/gpuweb/main/logo/webgpu-notext.svg" height="25" /> | WebGPU | | |


[ko-fi]: https://ko-fi.com/thebutlah
[support my work]: https://ko-fi.com/thebutlah
[overlay]: https://github.com/SlimeVR/SlimeVR-Rust/tree/main/overlay
[`ovr_overlay`]: https://github.com/TheButlah/ovr_overlay
[`autocxx`]: https://github.com/google/autocxx
[firmware]: https://github.com/SlimeVR/SlimeVR-Rust/tree/main/firmware
[SlimeVR discord]: https://discord.gg/SlimeVR
[SolarXR Protocol]: https://github.com/SlimeVR/SolarXR-Protocol
[SolarXR]: https://github.com/SlimeVR/SolarXR-Protocol
[SlimeVR-Rust]: https://github.com/SlimeVR/SlimeVR-Rust
[skeletal model]: https://github.com/SlimeVR/SlimeVR-Rust/tree/main/skeletal_model/rust
[GUI]: https://github.com/SlimeVR/SlimeVR-Server/tree/main/gui
[`embassy`]: https://embassy.dev
[rjbutler.main@gmail.com]: mailto:rjbutler.main@gmail.com

[^1]: Real time operating system
