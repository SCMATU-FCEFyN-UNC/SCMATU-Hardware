# SCMATU-Hardware
Hardware design for the thesis project "SCMATU," developed to excite and measure PZT ultrasonic transducers for automatic resonance frequency determination. The system provides a controlled sinusoidal excitation stage (±10 V), voltage and current sensing circuitry, and signal conditioning to enable accurate phase measurement between voltage and current during frequency sweeps.

---

## Repository Initialization

To obtain this repository locally, use the following commands:

### 1. Initialize Local Repository

```bash
cd your_local_directory
git init
```

### 2. Mark Directory as Safe (If Required)

Some environments may require explicitly marking the repository as safe.

- Bash (Git Bash, WSL, macOS Terminal, Linux):

```bash
git config --global --add safe.directory "$(pwd)"
```

- PowerShell:

```powershell
git config --global --add safe.directory "%cd%"
```

### 3. Add Remote Repository and Pull Branches

```bash
git remote add origin https://github.com/SCMATU-FCEFyN-UNC/SCMATU-Hardware.git
git pull origin main
```

> KiCad v7.0 or later is recommended to open the project files.

---

## 📄 Documentation

- [Schematic](docs/Complete_Schematic.pdf)
- [Hardware Requirements Specification](docs/requirements.md)

---

# License

This project is licensed under the MIT License.

See the [LICENSE](LICENSE) file for full license text.