# Contributing Guidelines

Thank you for your interest in contributing to the ENTS open-source ecosystem. This document outlines general contribution standards, code quality checks, and communication channels.

---

## Code of Conduct

All contributors and community participants are expected to adhere to the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/). We are committed to providing a welcoming, inclusive, and harassment-free environment for everyone.

---

## Communication Channels

Before embarking on significant architectural changes or large PRs, we strongly recommend opening an issue or starting a discussion on the [ENTS Zulip Chat](https://ents.zulipchat.com/). The `#development` channel is the primary forum for ongoing technical discussions.

---

## Pull Request Workflow

1. **Fork and Branch**:
   * Fork the relevant subsystem repository.
   * Create a feature branch with a descriptive name (for example, `feature/sdi12-multibus` or `fix/dirtviz-oauth-refresh`).
2. **Commit Standards**:
   * Write concise, conventional commit messages (for example, `fix(backend): correct timestamp parsing for UTC offsets` or `docs(firmware): update pinout diagram for rev2`).
   * Ensure commits are atomic and self-contained.
3. **Local Testing and Formatting**:
   * Run subsystem-specific formatting and test suites before pushing.

### Subsystem Verification Standards

* **DirtViz Web Platform**:
  * Run frontend unit tests: `cd frontend && npm test`
  * Run backend pytest suite: `cd backend && pytest`
  * Ensure Docker Compose dev stack builds cleanly: `docker compose build`
* **Bare Metal Firmware (STM32 HAL)**:
  * Check formatting with clang-format: `./format.sh`
  * Verify CI compilation flags: `CI=true ./ci.sh`
  * Run PlatformIO build: `pio run`
* **TockOS Kernel and Apps**:
  * Check Rust code formatting: `cargo fmt --check`
  * Verify kernel compilation for target board: `cd boards/wm1110dev && make`
  * Verify userspace apps in `ENTS-tock`: `CI=true ./ci.sh`

4. **Submitting PRs**:
   * Open a pull request against the `main` (or `master`) branch of the target repository.
   * Provide a clear description of the problem solved and link any related issues.
   * Ensure all automated GitHub Actions checks pass.

---

## Reporting Issues

* **Bugs**: If you discover a bug, open an issue in the specific repository where the bug occurs. Include reproduction steps, environment details (hardware revision, OS, compiler version), and serial logs or browser console errors.
* **Hardware Issues**: Issues relating to PCB schematics, BOM sourcing, or enclosure fit should be reported in [jlab-sensing/soil_power_sensor](https://github.com/jlab-sensing/soil_power_sensor) or [jlab-sensing/ENTS-enclosure](https://github.com/jlab-sensing/ENTS-enclosure).
* **System-Level & Documentation Issues**: Issues spanning multiple components or requests for the central documentation portal should be filed directly in [jlab-sensing/ENTS](https://github.com/jlab-sensing/ENTS/issues).
