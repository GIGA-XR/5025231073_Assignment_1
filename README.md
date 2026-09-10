# XR Teardown — [XREAL One Pro]

**[5025231073] — [Bella Angeline Chong Puteri]** · [S1 Informatics / S1 AI Engineering] · Individual Assignment 1

|                          |                                                                    |
| ------------------------ | ------------------------------------------------------------------ |
| Subject                  |XREAL One Pro                                     |
| Publisher / manufacturer | XREAL                                                   |
| Release or major update  | Announced 4 Dec 2024 (San Francisco); US general availability sales began 1 Jul 2025                            |
| Platform(s)              | X1 Spatial Chip (Host-dependent via USB-C DP Alt Mode)   |
| How I examined it        | Official documentation and technical specs |
| Hands-on date(s)         | [when you actually put the headset on, or "documentation only"]    |

> **My claim in one sentence.** By relying on an external host device for power and compute, the XREAL One Pro succeeds as a lightweight wearable display, but falls short of being a self-contained AR computer.

---

## 1. Device class

The XREAL One Pro is optical see through (OST) smart glasses. It features built-in 3DoF head tracking powered by the custom X1 co-processor chip. It operates without an internal battery or standalone OS, running entirely via host devices over USB-C.

On Milgram's continuum, it sits squarely in Augmented Reality (AR). Unlike VR or camera-based video passthrough. you see the physical world directly through transparent optics with digital content overlaid on top. Because the base model tracks head rotation (3DoF) rather than full position (6DoF), it prioritizes screen stability over complex environment mapping, though 6DoF can be added through the optional XREAL Eye accessory. 

This hardware class trades away standalone computing and room-scale spatial tracking to keep the device lightweight and comfortable (~87g). It works well as a private, portable monitor precisely because it does not try to be a heavy, self contained AR computer. 

<p>
  <img src="https://github.com/user-attachments/assets/6cac5257-1d59-4e5a-8d15-b9b945234947" alt="Fig 1. XREAL One Pro hardware components" width="100%" />
  <br />
  <em>Fig 1. XREAL One Pro hardware components.</em>
</p>

<p>
  <img src="https://github.com/user-attachments/assets/1962afc3-6ec4-4e2e-a53c-82664c835574" alt="Fig 2. XREAL One Pro system architecture & data flow diagram" width="100%" />
  <br />
  <em>Fig 2. XREAL One Pro system architecture & data flow diagram.</em>
</p>


## 2. Input modality

**What the user does:** System navigation relies mainly on physical controls on the right temple arm, including the multifunction toggle for brightness and volume and display-mode switching between "Anchor" and "Follow". Spatial viewing also uses head orientation, while more complex interactions are handled by the connected host device, such as a mouse, keyboard, gamepad, or smartphone touchscreen. 

**Why this and not that:** The design prioritizes simple controls rather than making the glasses themselves responsible for direct spatial interaction. XREAL's own documentation shows that hand tracking is possible through the optional XREAL Eye, which uses a camera to track hand gestures and translate them into mouse/button signals. However, XREAL describes gesture control as experimental and notes that lightning, hand position, and visiblity of the fingers can affect recognition. 

Therefore, physical buttons provide a more predictable way to control the glasses, while hand tracking offers more natural spatial interaction at the cost of additional environmental requirements.  

**Where it fails:** The limitation is that physical buttons are well suited to display adjustments, but not to interacting with virtual objects. For example, changing the screen mode is straightforward, but manipulating a virtual object or cursor is less direct than pointing or pinching in space. The optional XREAL Eye addresses this limitation, but its gesture interaction depends on the camera being able to clearly see the user's hands. 

**What I would change:** I would keep the physical buttons for quick system controls but add a small touch-sensitive area on the temple for scrolling, swiping, and selecting. This would still keep the current controls simple but give users a more direct way to interact with spatial content.

<img width="1280" height="640" alt="button" src="https://github.com/user-attachments/assets/b608921d-b7b0-43c3-92d0-a3b8139df66d" />
[Fig 3. XREAL One Pro physical control layout on the right temple arm.]


## 3. Use of AI

| Where                | What it does                                                    | On-device or cloud | Cost it carries                                   | Source + the line I am relying on |
| -------------------- | --------------------------------------------------------------- | ------------------ | ------------------------------------------------- | --------------------------------- |
| Perception           | On-device AI depth estimation and real-time 2D-to-3D video conversion running on the X1 chip's NPU. (Optional XREAL Eye adds camera-based hand & 6DoF tracking.) |     On-device (X1 NPU)          | Additional processing/power demand. Added weight and cost when using XREAL Eye. | [https://www.xreal.com/blog/how-we-built-real-3d-en]  X1 includes a dedicated Neural Processing Unit (NPU) designed to run AI workloads efficiently on the glasses themselves |                  |                                                   | [link] — "[quote]"                |
| Rendering & delivery | Image stabilization and disortion correction |             On device (X1 Chip)       |    Processing overhead, silicon footprint                                               | [https://www.xreal.com/one-pro] X1 can insert frames to display content at up to 120 fps for ultra-smooth playback.  |


## 4. Impact

**Intended benefit:** A portable and private big-screen display. The official marketing frames this as up to a 171” (curved ultrawide up to 310”) virtual screen for travel, gaming, and productivity via a single USB-C cable without carrying a monitor. 

**Privacy, security, or ethics:** Base operation of the XREAL One Pro reduces one category of privacy risks as the glasses lack internal cameras for capturing surroundings. However, privacy concerns arise when using the optional XREAL Eye module, which adds a 12MP camera for quick POV photos and 1080p video triggered by the frame buttons without unlocking a phone. While the module features a visible privacy LED indicator light to alert bystanders when one is actively recording, some users may still feel uncomfortable around the device in public spaces. XREAL lessens this through physical modularity: the 1.35g camera can be detached completely in private spaces. While effective, this relies entirely on the wearer’s choice, meaning bystanders must trust the wearer’s etiquette or notice the small LED when the module is attached. 

**Accessibility / human factors:** Dual IPD sizing (57-66mm & 66-75mm) is marketed as covering roughly 95% of users, meaning certain adults with IPD measurements outside of this range suffer from optical misalignment and image blur. Children are excluded entirely by design, as XREAL’s official safety guidelines designate the device for users aged 16 and older. Prescription lens support requires a third-party partner service, adding cost and a separate ordering step.

## 5. What I take from this

The XREAL One Pro suggests that the next step in XR may not be toward more immersive headsets, but toward less intrusive ones: lightweight glasses that turn existing devices into spatial displays without requiring heavy cameras, controllers, or an isolated virtual environment. However, this simplicity comes with a clear trade-off. By avoiding the spatial sensing and interaction hardware required for richer spatial computing, the device remains exceptionally easy to wear, but remains fundamentally limited in how deeply it can understand and respond to the physical world around it. 

---

## References

1. **VR-Compare.** (2025). *XREAL One Pro Full Specifications & Hardware Database*. VR-Compare. https://vr-compare.com/headset/xrealonepro — accessed 9 Sep 2026.
2. **XREAL.** (2025). *Inside REAL 3D: How XREAL Built It and How the X1 Chip Paves the Way*. XREAL Official Blog. https://www.xreal.com/blog/inside-real-3d-x1-chip — accessed 8 Sep 2026. On-device NPU specification and 2D-to-3D depth processing pipeline.
3. **XREAL.** (2025). *XREAL One Series Official Hardware Specifications*. XREAL Tutorials. https://tutorials.xreal.com/docs/glasses/one-series/spec#xreal-one-pro — accessed 8 Sep 2026.
4. **XREAL.** (2025). *XREAL Eye Camera Module Specifications*. XREAL Tutorials. https://tutorials.xreal.com/docs/accessories/eye/spec/ — accessed 8 Sep 2026.
5. **XREAL.** (2025). *Gesture Control Guidelines & Operational Prerequisites*. XREAL Developer Documentation. https://tutorials.xreal.com/docs/glasses/one-series/gesture/before-you-begin/ — accessed 9 Sep 2026.

## Figure credits

- Fig. 1 — [XREAL One Pro hardware components.]
- Fig. 2 — [XREAL One Pro system architecture & data flow diagram.]
- Fig. 3 — [XREAL One Pro physical control layout on the right temple arm.]

## AI-assistance disclosure

**What I used, and for what.** I used Gemini to help with citation format, discuss technical concepts I found difficult to understand, and clarify some information from the device documentation. I used these discussions to support my understanding, but I independently checked the relevant information against the original sources and made the final decisions about what claims to include.

### What I disagreed with my AI assistant about

[One paragraph, and it is marked. Where did the tool tell you something you decided was wrong, shallow, or unsupported — and what did you do instead? Be specific: name the claim, name your reason. If you used no tools, write instead about a source you decided not to trust, and why.]
