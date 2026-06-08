<div align="center">

# ⚒️ fleet-midi-symusic

> *C++ high-performance MIDI manipulation for batch processing*

[![CI](https://img.shields.io/github/actions/workflow/status/SuperInstance/fleet-midi-symusic/ci.yml?style=flat-square&logo=github&label=CI)](https://github.com/SuperInstance/fleet-midi-symusic/actions)
[![npm](https://img.shields.io/badge/npm-%40superinstance%2Fmidi--symusic-cb3837?style=flat-square&logo=npm)](https://www.npmjs.com/package/@superinstance/midi-symusic)
[![Docker](https://img.shields.io/badge/docker-ghcr-2496ed?style=flat-square&logo=docker)](https://github.com/SuperInstance/fleet-midi-symusic/pkgs/container/fleet-midi-symusic)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](http://makeapullrequest.com)

---

Wraps the symusic C++ library for MIDI transformation at scale. Operates hundreds of times faster than pure Python — essential for processing terabytes of fleet session data without bottlenecks.

---

## 📦 Installation

```bash
# npm
npm install @superinstance/midi-symusic

# Docker
docker pull ghcr.io/superinstance/fleet-midi-symusic:latest

# Clone
git clone https://github.com/SuperInstance/fleet-midi-symusic.git
```

## 🚀 Quick Start

```bash
# Python bindings:
from lib.midi_ops import transpose_midi, merge_tracks

# Transpose all MIDI in a fleet session
transpose_midi("agent_output.mid", 2)  # Up 2 semitones

# For C++ backend, build with CMake:
# mkdir build && cd build && cmake .. && make
```

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│   C++ Core                    Python Bindings        │
│   ┌──────────┐    ┌──────────┐    ┌──────────┐       │
│   │ MIDI     │───▶│ PyBind11 │───▶│ fleet   │       │
│   │ Engine   │    │ Wrapper  │    │ bridge  │       │
│   └──────────┘    └──────────┘    └──────────┘       │
│                                                     │
│   100× faster than pure Python MIDI parsing          │
│   Ideal for batch fleet session processing           │
│   200k+ MIDI files? This handles it.                 │
└─────────────────────────────────────────────────────┘
```

## 📡 API

### Python API (via symusic bindings)
```python
from symusic import Score, Note
score = Score("agent_output.mid")
```

### C++ API (direct)
See `include/symusic/` for the full C++ header surface.

## 🧪 Beta Tested

Part of the [SuperInstance MIDI Fleet](https://github.com/SuperInstance/construct-coordination/blob/main/FLEET_MIDI.md). Every push verified via CI — zeroshot tests ensure zero-config operation out of the box.

## 🤝 Related

- [fleet-bridge](https://github.com/SuperInstance/fleet-bridge) — I2I bottle transport
- [construct-coordination](https://github.com/SuperInstance/construct-coordination) — Fleet catalog

---

<div align="center">
<sub>Built with ⚒️ for the SuperInstance fleet • <a href="https://github.com/SuperInstance">github.com/SuperInstance</a></sub>
</div>
