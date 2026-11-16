# Publications and Research

The open-source hardware, firmware, and cloud infrastructure powering ENTS have been developed through iterative academic research and peer-reviewed in top embedded sensing venues.

---

## Peer-Reviewed Publications

### 1. ENTS: Experiences in Co-Designed Environmental Sensing (SenSys '26)

* **Authors**: John Madden, Stephen Taylor, Laura Jaliff, Aaron Wu, Alec Levy, Jack Lin, Ahmed Falah, Tyler Potyondy, Josiah Hester, George Wells, Yaman Sangar, Pat Pannuto, and Colleen Josephson
* **Venue**: *Proceedings of the 24th ACM Conference on Embedded Networked Sensor Systems (SenSys '26)*
* **DOI**: [https://doi.org/10.1145/3774906.3802780](https://doi.org/10.1145/3774906.3802780)

#### Abstract
Wireless sensor networks (WSNs) hold tremendous promise for environmental monitoring, precision agriculture, and ecological science. However, deployments frequently fail due to hardware unreliability, steep configuration barriers for non-technical domain scientists, and brittle data pipelines. This paper presents the evolution and deployment lessons of ENTS (Environmental NeTworked Sensing), an end-to-end WSN platform co-designed over three years alongside domain scientists in agroecology and biology. We detail our architectural principles across low-cost precision analog sensing, dual-radio firmware architectures, weatherproof 3D enclosure co-design, and cloud visualization. We evaluate multi-month field deployments monitoring soil microbial fuel cells, cactus energy harvesting, and marshland hydrology, sharing actionable design guidelines for interdisciplinary sensing platforms.

#### BibTeX Citation

```bibtex
@inproceedings{madden2026ents,
  author    = {Madden, John and Taylor, Stephen and Jaliff, Laura and Wu, Aaron and Levy, Alec and Lin, Jack and Falah, Ahmed and Potyondy, Tyler and Hester, Josiah and Wells, George and Sangar, Yaman and Pannuto, Pat and Josephson, Colleen},
  title     = {ENTS: Experiences in Co-Designed Environmental Sensing},
  booktitle = {Proceedings of the 24th ACM Conference on Embedded Networked Sensor Systems (SenSys '26)},
  year      = {2026},
  doi       = {10.1145/3774906.3802780},
  publisher = {ACM}
}
```

---

### 2. Demo: Hardware to Unleash Novel Energy Sources for Outdoor Sensor Networks (SenSys '25)

* **Authors**: Alec Levy, John Madden, Mirella Pessoa de Melo, and Colleen Josephson
* **Venue**: *Proceedings of the 23rd ACM Conference on Embedded Networked Sensor Systems (SenSys '25)*, pp. 706–707
* **DOI**: [https://doi.org/10.1145/3715014.3724369](https://doi.org/10.1145/3715014.3724369)

#### Abstract
Deploying long-lived wireless sensor networks in outdoor environments is fundamentally challenged by power constraints. While conventional solar harvesting is widely deployed, novel energy sources such as bio-electrochemical energy from plants and soil microbes offer continuous, non-diurnal energy generation. This demonstration presents the ENTS sensing hardware platform operating directly on novel environmental energy sources, showcasing precision energy tracking, real-time power profiling, and live telemetry ingestion into the DirtViz cloud interface.

#### BibTeX Citation

```bibtex
@inproceedings{levy2025demo,
  author    = {Levy, Alec and Madden, John and Pessoa de Melo, Mirella and Josephson, Colleen},
  title     = {Demo: Hardware to unleash novel energy sources for outdoor sensor networks},
  booktitle = {Proceedings of the 23rd ACM Conference on Embedded Networked Sensor Systems (SenSys '25)},
  pages     = {706--707},
  year      = {2025},
  doi       = {10.1145/3715014.3724369},
  publisher = {ACM}
}
```

---

### 3. Hardware to Enable Large-Scale Deployment and Observation of Soil Microbial Fuel Cells (ENSsys '22)

* **Authors**: John Madden, Gabriel Marcano, Stephen Taylor, Pat Pannuto, and Colleen Josephson
* **Venue**: *Proceedings of the 20th ACM Conference on Embedded Networked Sensor Systems (SenSys / ENSsys '22)*, pp. 906–912
* **DOI**: [https://doi.org/10.1145/3560905.3568110](https://doi.org/10.1145/3560905.3568110)

#### Abstract
Soil microbial fuel cells (SMFCs) represent a promising zero-maintenance energy harvesting technology for remote environmental sensing. However, systematic ecological research into SMFC behavior requires dense, multi-point electrical and environmental monitoring that commercial instrumentation cannot economically provide. This paper introduces custom, open-source data logging hardware specifically engineered for large-scale observation of SMFCs. We present the circuit architecture enabling simultaneous microvolt and sub-microampere sampling alongside digital soil moisture and temperature telemetry, demonstrating robust operation in real-world agricultural testbeds.

#### BibTeX Citation

```bibtex
@inproceedings{madden2022hardware,
  author    = {Madden, John and Marcano, Gabriel and Taylor, Stephen and Pannuto, Pat and Josephson, Colleen},
  title     = {Hardware to Enable Large-Scale Deployment and Observation of Soil Microbial Fuel Cells},
  booktitle = {Proceedings of the 20th ACM Conference on Embedded Networked Sensor Systems (SenSys '22)},
  pages     = {906--912},
  year      = {2022},
  doi       = {10.1145/3560905.3568110},
  publisher = {ACM}
}
```

---

## Grant and Funding Acknowledgements

This research is supported in part by:

* **UC Santa Cruz Agricultural Experiment Station**: Funding provided by the State of California.
* **U.S. Department of Agriculture (USDA), National Institute of Food and Agriculture (NIFA)**: Hatch Act of 1887 funding (Accession number: `7010079`).

*The findings and conclusions in these publications have not been formally disseminated by the U.S. Department of Agriculture and should not be construed to represent any agency determination or policy.*
