# XR Teardown — [XREAL One Pro]

**[5025231073] — [Bella Angeline Chong Puteri]** · [S1 Informatics / S1 AI Engineering] · Individual Assignment 1

|                          |                                                                    |
| ------------------------ | ------------------------------------------------------------------ |
| Subject                  |XREAL One Pro                                     |
| Publisher / manufacturer | XREAL                                                   |
| Release or major update  | Announced 4 Dec 2024 (San Francisco); US general availability sales began 1 Jul 2025                            |
| Platform(s)              | [e.g. Meta Quest 3, Pico 4 Ultra, visionOS, WebXR, Android XR]     |
| How I examined it        | [Hands-on on a lab Quest 3 / documentation and spec sheets / both] |
| Hands-on date(s)         | [when you actually put the headset on, or "documentation only"]    |

> **My claim in one sentence.** By relying on an external host device for power and compute, the XREAL One Pro succeeds as a lightweight wearable display, but falls short of being a self-contained AR computer.

---

## 1. Device class

[Which hardware class does it target? Name it precisely — degrees of freedom, standalone or tethered, opaque or passthrough, colour or monochrome, controllers shipped or not.]

[Where does it sit on the reality–virtuality continuum, and why there rather than one step either side?]

[What does that class make possible, and what does it rule out? If it depends on a capability our lab hardware lacks — eye tracking, depth-aware colour passthrough below Quest 3 / Pico 4 Ultra — say so and say what breaks without it.]

![Caption that makes a point, not "screenshot of the app"](assets/fig1.png)

> **One of your three figures must be your own** — a photo or capture of your own hands-on session on a lab headset, or your own measurement, with a visible date. Mark it clearly in the figure credits below.

## 2. Input modality

**What the user does:** System navigation relies mainly on physical controls on the right temple arm, including the multifunction toggle for brightness and volume and display-mode switching between "Anchor" and "Follow". Spatial viewing also uses head orientation, while more complex interactions are handled by the connected host device, such as a mouse, keyboard, gamepad, or smartphone touchscreen. 

**Why this and not that:** The design prioritizes simple controls rather than making the glasses themselves responsible for direct spatial interaction. XREAL's own documentation shows that hand tracking is possible through the optional XREAL Eye, which uses a camera to track hand gestures and translate them into mouse/button signals. However, XREAL describes gesture control as experimental and notes that lightning, hand position, and visiblity of the fingers can affect recognition. 

Therefore, physical buttons provide a more predictable way to control the glasses, while hand tracking offers more natural spatial interaction at the cost of additional environmental requirements.  

**Where it fails:** The limitation is that physical buttons are well suited to display adjustments, but not to interacting with virtual objects. For example, changing the screen mode is straightforward, but manipulating a virtual object or cursor is less direct than pointing or pinching in space. The optional XREAL Eye addresses this limitation, but its gesture interaction depends on the camera being able to clearly see the user's hands. 

**What I would change:** I would keep the physical buttons for quick system controls but add a small touch-sensitive area on the temple for scrolling, swiping, and selecting. For more advanced interaction, I would make hand tracking an optional input method rather than the only method. This would still keep the current controls simple but give users a more direct way to interact with spatial content.

![Caption](assets/fig2.png)

## 3. Use of AI

| Where                | What it does                                                    | On-device or cloud | Cost it carries                                   | Source + the line I am relying on |
| -------------------- | --------------------------------------------------------------- | ------------------ | ------------------------------------------------- | --------------------------------- |
| Perception           | 3DoF pose/head tracking via the X1 chip                    |      On Device              | Battery drain on host device, minor thermal output on temple arms | [https://docs.xreal.com/XREALDevices/XREAL%20Glasses] self-developed X1 chip, enabling direct connection with various devices while providing 3DoF tracking capabilities  |                  |                                                   | [link] — "[quote]"                |
| Rendering & delivery | Image stabilization and disortion correction |             On device (X1 Chip)       |    Processing overhead, silicon footprint                                               | [https://www.xreal.com/one-pro] X1 can insert frames to display content at up to 120 fps for ultra-smooth playback.  |

## 4. Impact

**Intended benefit:** A portable and private big-screen display. The official marketing frames this as up to a 171” (curved ultrawide up to 310”) virtual screen for travel, gaming, and productivity via a single USB-C cable without carrying a monitor. 

**Privacy, security, or ethics:** Base operation of the XREAL One Pro reduces one category of privacy risks as the glasses lack internal cameras for capturing surroundings. However, privacy concerns arise when using the optional XREAL Eye module, which adds a 12MP camera for quick POV photos and 1080p video triggered by the frame buttons without unlocking a phone. While the module features a visible privacy LED indicator light to alert bystanders when one is actively recording, some users may still feel uncomfortable around the device in public spaces. XREAL lessens this through physical modularity: the 1.35g camera can be detached completely in private spaces. While effective, this relies entirely on the wearer’s choice, meaning bystanders must trust the wearer’s etiquette or notice the small LED when the module is attached. 

**Accessibility / human factors:** Dual IPD sizing (57-66mm & 66-75mm) is marketed as covering roughly 95% of users, meaning certain adults with IPD measurements outside of this range suffer from optical misalignment and image blur. Children are excluded entirely by design, as XREAL’s official safety guidelines designate the device for users aged 16 and older. Prescription lens support requires a third-party partner service, adding cost and a separate ordering step.

## 5. What I take from this

[Two or three sentences. What does this teardown tell you about where XR design is heading — or where it is stuck? Do not summarise the sections above.]

---

## References

1. [Primary source — developer documentation, specification, technical paper, or your own measurement. At least one of these is required.]
2. [Author/Publisher. (Year). *Title*. URL — accessed DD Mon 2026]
3. [ ]
4. [ ]

## Figure credits

- Fig. 1 — [my own screenshot, Quest 3, 8 Sep 2026 / source and licence]
- Fig. 2 — [ ]
- Fig. 3 — [ ]

## AI-assistance disclosure

**What I used, and for what.** [Name the tools and the tasks — e.g. "Claude to tighten the prose in §2; all sources located and read by me." If you used none, write "None."]

### What I disagreed with my AI assistant about

[One paragraph, and it is marked. Where did the tool tell you something you decided was wrong, shallow, or unsupported — and what did you do instead? Be specific: name the claim, name your reason. If you used no tools, write instead about a source you decided not to trust, and why.]
