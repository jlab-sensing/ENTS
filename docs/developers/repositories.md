# Repository Directory and Source Map

This document catalogues all repositories in the ENTS ecosystem, detailing their primary languages, roles within the platform, and direct links to their canonical Markdown documentation.

---

## Documentation Strategy and Future Roadmap

The links below currently point directly to canonical Markdown files (`README.md`, `docs/`) maintained in each repository. As subsystem repositories configure automated API documentation pipelines, these links will transition to hosted **Sphinx** or **Doxygen** sites without altering the structure of this portal.

---

## 1. Core Ecosystem Repositories

| Subsystem | Repository | Primary Language | Canonical Documentation Link | Future Docs Roadmap |
| :--- | :--- | :--- | :--- | :--- |
| **Web Visualization** | [jlab-sensing/DirtViz](https://github.com/jlab-sensing/DirtViz) | JavaScript / React | [DirtViz Development Guide](https://github.com/jlab-sensing/DirtViz/blob/main/docs/development.md) | Sphinx/OpenAPI docs |
| **Backend API** | [jlab-sensing/DirtViz](https://github.com/jlab-sensing/DirtViz) | Python / Flask | [Backend Architecture README](https://github.com/jlab-sensing/DirtViz/blob/main/backend/README.md) | REST API reference |
| **Firmware: Production Bare Metal** | [jlab-sensing/soil-power-sensor-firmware](https://github.com/jlab-sensing/soil-power-sensor-firmware) | C / PlatformIO | [Firmware Developer Guide](https://github.com/jlab-sensing/soil-power-sensor-firmware/blob/main/README.md) | Hosted Doxygen site |
| **Firmware: Calibration Specs** | [jlab-sensing/soil-power-sensor-firmware](https://github.com/jlab-sensing/soil-power-sensor-firmware) | Markdown | [Sensor Measurements Spec](https://github.com/jlab-sensing/soil-power-sensor-firmware/blob/main/docs/sensor_measurements.md) | Sphinx Tech Note |
| **Firmware: TockOS Kernel (Future)** | [jlab-sensing/tock](https://github.com/jlab-sensing/tock) | Rust | [wm1110dev Board Documentation](https://github.com/jlab-sensing/tock/blob/master/boards/wm1110dev/README.md) | Rustdoc / Tock Book |
| **Firmware: TockOS Apps (Future)** | [jlab-sensing/ENTS-tock](https://github.com/jlab-sensing/ENTS-tock) | C | [ENTS-tock Userspace README](https://github.com/jlab-sensing/ENTS-tock/blob/main/README.md) | Tock Userspace Guide |
| **Firmware: TockOS Runtime (Future)** | [jlab-sensing/libtock-c](https://github.com/jlab-sensing/libtock-c) | C | [libtock-c README](https://github.com/jlab-sensing/libtock-c/blob/master/README.md) | libtock-c C API Docs |
| **Firmware: TockOS Tooling (Future)** | [jlab-sensing/tockloader](https://github.com/jlab-sensing/tockloader) | Python | [tockloader README](https://github.com/jlab-sensing/tockloader/blob/master/README.md) | CLI Manual |
| **Hardware PCB Design** | [jlab-sensing/soil_power_sensor](https://github.com/jlab-sensing/soil_power_sensor) | EagleCAD | [Hardware README and Assembly](https://github.com/jlab-sensing/soil_power_sensor/blob/main/README.md) | Interactive BOM / Schematics |
| **Enclosures** | [jlab-sensing/ENTS-enclosure](https://github.com/jlab-sensing/ENTS-enclosure) | CAD / STL | [Enclosure README](https://github.com/jlab-sensing/ENTS-enclosure/blob/main/README.md) | 3D Printing & Assembly Guides |

---

## 2. Derivative Projects

Derivative projects build upon core ENTS infrastructure to solve domain-specific challenges:

### NodeFlow
* **Repository**: [jlab-sensing/NodeFlow](https://github.com/jlab-sensing/NodeFlow)
* **Primary Language**: JavaScript / Python
* **Description**: An automated, low-cost irrigation control platform derived directly from DirtViz. NodeFlow uses soil moisture telemetry collected by ENTS sensing nodes to make real-time irrigation decisions and control physical water valves.
* **API Consumer Example**: NodeFlow serves as the primary reference implementation demonstrating how external services authenticate with the DirtViz REST API, fetch time-series sensor data, and execute closed-loop automation.
* **Documentation**: [NodeFlow README](https://github.com/jlab-sensing/NodeFlow/blob/main/README.md)

---

## 3. Related Projects and Tools (Unsupported)

The following repositories are provided as-is for reference, experimental exploration, and community tooling. They are not actively supported or maintained by the core ENTS engineering team:

* **irrigation-demo** ([jlab-sensing/irrigation-demo](https://github.com/jlab-sensing/irrigation-demo)): Standalone Python scripts demonstrating early irrigation control scripts that query the DirtViz API. Provided as a code sample for educational and prototyping purposes.
* **dirtviz-slack-bot** ([jlab-sensing/dirtviz-slack-bot](https://github.com/jlab-sensing/dirtviz-slack-bot)): A lightweight Python Slack bot utility that queries the DirtViz API and posts current cell telemetry into designated Slack channels for team monitoring.
