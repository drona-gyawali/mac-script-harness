# macOS Script Tester

A dedicated CI test harness for validating native macOS build scripts targeting digital logic and formal verification tools (`eqntott`, `espresso`, `must`, and `Z3`).

This repository executes native builds on GitHub Actions hosted macOS runners (`macos-latest` / Apple Silicon `arm64`) to verify script compatibility, toolchain dependencies, and binary outputs without requiring a local Mac environment.

---

## 🛠 Tools Covered

| Tool | Script | Description | Primary Output |
| :--- | :--- | :--- | :--- |
| **eqntott** | `tools/scripts/build_eqntott_mac.sh` | Converts Boolean equations to truth tables | Mach-O 64-bit executable |
| **espresso** | `tools/scripts/build_espresso_mac.sh` | Two-level Boolean logic minimization | Mach-O 64-bit executable |
| **must** | `tools/scripts/build_must_mac.sh` | Minimal Unsatisfiable Subset (MUS) extraction tool | Mach-O 64-bit executable |
| **Z3** | `tools/scripts/build_z3_mac.sh` | High-performance SMT solver | Mach-O dynamic library (`libz3.dylib`) |

---

## 📁 Repository Structure

```text
.
├── .github/
│   └── workflows/
│       └── test.yml          # GitHub Actions workflow for macOS runners
└── tools/
    └── scripts/
        ├── build_eqntott_mac.sh
        ├── build_espresso_mac.sh
        ├── build_must_mac.sh
        └── build_z3_mac.sh