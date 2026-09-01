# cAiGED

## Multimodal Edge-AI Guitar Chord Verification System

**cAiGED** is a custom embedded Edge-AI platform designed to investigate whether an embedded system can combine **visual and acoustic information** to determine whether a guitar chord is being played correctly.

The project combines embedded AI, computer vision, audio processing and high-speed PCB design around a custom hardware platform based on the **STM32N657X0H3Q**.

**Core technologies**

- STM32N6 / STM32N657X0H3Q
- Arm Cortex-M55
- ST Neural-ART NPU
- MIPI CSI-2
- Computer vision
- Audio AI
- Multimodal inference
- External high-speed memory
- XSPI
- USB
- Gigabit Ethernet
- microSD
- OLED
- High-speed PCB design
- VFBGA-264 BGA layout
- Signal and power integrity

> **Project status:** Hardware architecture / MB1940 analysis

---

## Project Objective

The objective of cAiGED is to design and build a **custom embedded Edge-AI system capable of verifying guitar chord performance using two independent sensing modalities**.

The system observes both:

1. **What the guitarist is physically doing** through a camera.
2. **What the guitar actually sounds like** through a microphone.

The central research question is:

> **Can an embedded AI system combine visual and acoustic information to determine whether a guitar is being played correctly?**

The initial application is based on the **CAGED guitar system**:

**C → A → G → E → D**

The long-term concept is an embedded guitar tutor that can present or expect a chord, observe the guitarist's fingering, analyse the resulting sound, compare the two sources of information and provide immediate feedback.

The project is therefore not intended to be simply an image-based guitar chord classifier.

The objective is to investigate whether **physical fingering and acoustic output can be combined on an embedded device to verify a musical performance**.

---

## Why cAiGED?

I have a long-standing interest in both **playing guitar and designing PCBs**.

cAiGED is where those two interests meet: the guitar provides the real-world multimodal problem, while the need to solve that problem drives the design of a technically demanding embedded system and custom PCB.

The result is a project that combines something I enjoy doing creatively with something I work on professionally: **guitar playing and electronics/PCB design in the same system**.

---

## System Concept

The fundamental concept is to process the visual and acoustic information independently before combining their outputs.

```mermaid
flowchart LR
    G[Guitarist] --> C[Camera]
    G --> M[Microphone]

    C --> VP[Visual Processing]
    VP --> VI[Visual AI]

    M --> AP[Audio Processing]
    AP --> AI[Audio AI]

    VI --> F[Multimodal Fusion]
    AI --> F

    F --> D[Chord Verification]
    D --> O[OLED Feedback]