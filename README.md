# ENTS: Environmental NeTworked Sensing

A living open-source platform for real-world wireless sensor networks.

Co-designed with domain scientists, ENTS provides an end-to-end open-source hardware, firmware, and software ecosystem for building environmental sensor networks that are low-cost, extensible, and field-ready.

---

## Central Documentation Portal

The primary documentation for the ENTS ecosystem is published at:

**[https://jlab-sensing.github.io/ENTS/](https://jlab-sensing.github.io/ENTS/)**

The documentation portal is organized into two primary user pathways:

* **[User Guide](https://jlab-sensing.github.io/ENTS/users/)**: End-to-end deployment instructions, DirtViz dashboard operations, board power and wiring, and on-device WiFi captive portal configuration.
* **[Developer Hub](https://jlab-sensing.github.io/ENTS/developers/)**: System architecture, end-to-end dataflow, and repository directory linking all source code across the ecosystem.
* **[Project Roadmap](https://jlab-sensing.github.io/ENTS/roadmap/)**: The evolutionary path from current production firmware (Bare Metal STM32 HAL) to the next-generation modular architecture (TockOS).

---

## Quick Repository Links

| Subsystem | Repository | Description |
| :--- | :--- | :--- |
| **Web Platform** | [jlab-sensing/DirtViz](https://github.com/jlab-sensing/DirtViz) | Flask API, time-series storage, and React web dashboard |
| **Firmware (Production)** | [jlab-sensing/soil-power-sensor-firmware](https://github.com/jlab-sensing/soil-power-sensor-firmware) | C firmware on STM32 HAL for Wio-E5 and ESP32 co-processor |
| **Firmware (Roadmap Kernel)** | [jlab-sensing/tock](https://github.com/jlab-sensing/tock) | TockOS microkernel port for ENTS board target (`wm1110dev`) |
| **Firmware (Roadmap Apps)** | [jlab-sensing/ENTS-tock](https://github.com/jlab-sensing/ENTS-tock) | Isolated userspace sensing applications running on TockOS |
| **Hardware** | [jlab-sensing/soil_power_sensor](https://github.com/jlab-sensing/soil_power_sensor) | EagleCAD PCB schematics, bill of materials, and assembly QA |
| **Enclosures** | [jlab-sensing/ENTS-enclosure](https://github.com/jlab-sensing/ENTS-enclosure) | Weatherproof 3D printable outdoor enclosure models |
| **Derivative (API Example)** | [jlab-sensing/NodeFlow](https://github.com/jlab-sensing/NodeFlow) | Automated irrigation system consuming the DirtViz REST API |

---

## Peer-Reviewed Publications

1. **ENTS: Experiences in Co-Designed Environmental Sensing**  
   John Madden, Stephen Taylor, Laura Jaliff, Aaron Wu, Alec Levy, Jack Lin, Ahmed Falah, Tyler Potyondy, Josiah Hester, George Wells, Yaman Sangar, Pat Pannuto, and Colleen Josephson.  
   *ACM SenSys '26*. [https://doi.org/10.1145/3774906.3802780](https://doi.org/10.1145/3774906.3802780)

2. **Demo: Hardware to Unleash Novel Energy Sources for Outdoor Sensor Networks**  
   Alec Levy, John Madden, Mirella Pessoa de Melo, and Colleen Josephson.  
   *ACM SenSys '25*, pp. 706–707. [https://doi.org/10.1145/3715014.3724369](https://doi.org/10.1145/3715014.3724369)

3. **Hardware to Enable Large-Scale Deployment and Observation of Soil Microbial Fuel Cells**  
   John Madden, Gabriel Marcano, Stephen Taylor, Pat Pannuto, and Colleen Josephson.  
   *ACM SenSys / ENSsys '22*, pp. 906–912. [https://doi.org/10.1145/3560905.3568110](https://doi.org/10.1145/3560905.3568110)

---

## Community and Contributions

* **Discussion**: Join the conversation on the [ENTS Zulip Chat](https://ents.zulipchat.com/).
* **Sponsorship**: We gratefully acknowledge Zulip for sponsoring free hosting for our open-source and academic community.
* **Contact**: Inquiries can be directed via Zulip or to `ents-group@ucsc.edu`.

---

## Funding Acknowledgements

This project and open-source ecosystem are supported in part by:

* **National Science Foundation (NSF)**: Pathways to Enable Open-Source Ecosystems (POSE) program.
* **UC Santa Cruz Agricultural Experiment Station**: Funding provided by the state of California.
* **U.S. Department of Agriculture (USDA), National Institute of Food and Agriculture (NIFA)**: Hatch Act of 1887 funding (Accession number: 7010079).
