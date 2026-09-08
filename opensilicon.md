---
layout: default
title: OpenSilicon
permalink: /opensilicon/
---

# OpenSilicon

**Open-source semiconductor fabrication.**

OpenSilicon is an attempt to make practical semiconductor fabrication more accessible to hobbyists, educators, researchers, and small organizations.

## Progress

**Overall:** `██████░░░░` **In development**

| Area | Status |
| --- | --- |
| Spin coating | **Complete** |
| Optical lithography | **Active** |
| X-Y-Z stage | **Active** |
| OPU control electronics | **Active** |
| Metrology | **In development** |
| Process development | **In development** |

## Current work

The current lithography work is building on the work of **Edwin En-Te Hwu and Anja Boisen** in [*Hacking CD/DVD/Blu-ray for Biosensing*](https://doi.org/10.1021/acssensors.8b00340), *ACS Sensors* 3(7), 1222–1232 (2018). Their paper describes the construction and control of several commercial optical pickup units (OPUs), including a KEM 410 unit, and provides supporting controller-circuit designs. The authors describe Blu-ray OPUs as using a 405 nm laser and a high-NA objective, with the optical system capable of approximately 250 nm full-width-at-half-maximum spot size under the conditions discussed in the review.

I have purchased a **KEM410CCA**, which is related to but not identical to the KEM410A/KEM410 unit discussed in the paper. I am adapting the published approach rather than assuming the pinout and electrical behavior are identical, and am reverse engineering the OPU alongside the controller design.

The starting point for the controller is a rough adaptation of the KEM410 circuit shown in the paper's Supporting Information. The working circuit reference is available here rather than embedded directly in the page:

[**KEM410 controller circuit — kem410.png**](/images/kem410.png)

The paper's Supporting Information contains the triple-wavelength OPU controller circuit designs, and the paper acknowledges **Chung-Hsiang Cheng** and **Christian Werner** for the OPU driving-circuit design. A 2022 correction to the paper subsequently added a citation to the original source of the circuit diagrams, *Hacking the PHR-803T Home Page* by Diyouware.

The immediate goal is to establish reliable control of the OPU's laser, photodiode/PDIC signals, and voice-coil actuators, then integrate the optical head into a controlled lithography system. The research literature also demonstrates the suitability of Blu-ray optical heads for low-cost laser lithography, including the work of Rothenbach and Gupta on using a Blu-ray optical head assembly for high-resolution laser lithography.

Alongside the optical work, I am developing the **X-Y-Z motion stage** that will position the substrate relative to the optical head. The eventual system needs the optical head, motion system, exposure control, and process chemistry to behave as one instrument rather than as separate experiments.

## Latest OpenSilicon posts

{% assign os_posts = site.posts | where: "project", "opensilicon" | sort: 'date' | reverse %}
{% if os_posts.size > 0 %}
{% for post in os_posts limit:10 %}
**{{ post.date | date: "%Y-%m-%d" }}** — [{{ post.title }}]({{ post.url | relative_url }})  
{% endfor %}
{% else %}
No OpenSilicon posts yet.
{% endif %}

## Links

- [OpenSilicon GitHub](https://github.com/RParkerE/OpenSilicon)
- [Project roadmap](#roadmap)
- [GitHub Discussions](https://github.com/RParkerE/OpenSilicon/discussions)

## Roadmap

The roadmap will remain deliberately lightweight and will evolve as the system moves from individual components toward an integrated fabrication tool.

### Spin coater — Complete

- [x] Spin-coating hardware
- [x] Initial operation and testing

### Lithography — Active

- [ ] KEM410CCA controller and pin characterization
- [ ] Laser control and power characterization
- [ ] OPU focus / tracking / tilt characterization
- [ ] Optical alignment
- [ ] Exposure characterization
- [ ] Resist/process characterization
- [ ] First repeatable lithography test structures

The lithography approach is informed by the Blu-ray OPU literature, particularly the 405 nm optical architecture described by Hwu and Boisen and the earlier demonstration of low-cost laser lithography using a Blu-ray optical head by Rothenbach and Gupta.

### X-Y-Z stage — Active

- [ ] Mechanical design
- [ ] X/Y motion
- [ ] Z/focus positioning
- [ ] Position feedback
- [ ] Software control
- [ ] Integrate motion with exposure

### Metrology — In development

- [ ] Optical inspection workflow
- [ ] Calibration structures
- [ ] Measurement and repeatability testing
- [ ] Integrate Fourier ptychography / optical metrology

## References

1. Hwu, E. E.-T.; Boisen, A. **Hacking CD/DVD/Blu-ray for Biosensing.** *ACS Sensors* **2018**, *3* (7), 1222–1232. [doi:10.1021/acssensors.8b00340](https://doi.org/10.1021/acssensors.8b00340). The paper's Supporting Information includes triple-wavelength OPU controller circuit designs.

2. Hwu, E. E.-T.; Boisen, A. **Correction to Hacking CD/DVD/Blu-ray for Biosensing.** *ACS Sensors* **2022**, *7*, 2492. [doi:10.1021/acssensors.2c01529](https://doi.org/10.1021/acssensors.2c01529). The correction adds a citation to the original source of the circuit diagrams and corrects values in the original article's table.

3. Rothenbach, C. A.; Gupta, M. C. **High Resolution, Low Cost Laser Lithography Using a Blu-ray Optical Head Assembly.** *Optics & Laser Technology* **2012**, *50*, 900–904. [doi:10.1016/j.optlaseng.2011.12.004](https://doi.org/10.1016/j.optlaseng.2011.12.004).

Circuit-design acknowledgement: Hwu and Boisen thank **Chung-Hsiang Cheng** and **Christian Werner** for the OPU driving-circuit design. The 2022 correction identifies *Hacking the PHR-803T Home Page* (Diyouware) as the original source for the circuit diagrams.

