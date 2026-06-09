# Huawei Air Transfer Technology

> Transfer files between nearby computers using nothing but a hand gesture.


## What is this?

Huawei Air Transfer Technology (HATT) is an open-source, cross-platform file transfer tool that makes moving files between computers feel like physically carrying an object.

- **Grab** a file on one machine by closing your fist in front of the webcam
- **Walk** to another machine on the same network
- **Drop** it by opening your palm — the file appears instantly

No cables. No USB drives. No cloud uploads. No manual pairing dialogs. Just gesture and go.







## Features

- Hand gesture recognition via webcam (no special hardware needed)
- Automatic device discovery on local Wi-Fi — devices find each other instantly
- Encrypted file transfer over your local network (AES-GCM)
- Floating overlay UI that shows which file you are currently "carrying"
- Works on **Windows**, **Linux**, and **macOS**
- Fully offline — nothing leaves your local network
- Open source under the MIT license



## How it works

```
[Webcam] → [MediaPipe gesture detection]
                    ↓
             Fist detected = GRAB active file
                    ↓
          [Zeroconf device discovery]
                    ↓
          Select nearby target device
                    ↓
      Open palm detected = SEND via TCP socket
                    ↓
        [AES-GCM encrypted transfer]
                    ↓
         File appears on target machine
```

---

## Requirements

- Python 3.10 or higher
- A working webcam
- Both devices connected to the same Wi-Fi or LAN network
- Windows 10+, Ubuntu 20.04+, or macOS 12+

---

## Installation

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/huawei-air-transfer.git
cd huawei-air-transfer

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the app(mac & linux users can use python3 ...)
python src/main.py 
```

That is all. The app will open in your system tray and start listening for nearby devices automatically.

---

## Usage

1. Make sure both machines are running the app and on the same network
2. On the **sending machine**: hold a file open or select it, then close your fist in front of the webcam and hold for half a second
3. A floating badge will appear showing the file you are carrying
4. On the **receiving machine**: open your palm in front of the webcam
5. A notification will ask you to accept or decline the incoming file
6. Accept — the file is saved to your Downloads folder

---

## Tech stack

| Component | Technology |
|---|---|
| Gesture detection | MediaPipe Hands + OpenCV |
| Device discovery | Zeroconf (mDNS / DNS-SD) |
| File transfer | asyncio TCP sockets |
| Encryption | cryptography library (AES-GCM) |
| Desktop UI | PySide6 |
| Packaging | PyInstaller |

---

## Project structure

```
huawei-air-transfer/
├── src/
│   ├── gesture/        # Webcam input and gesture classification
│   ├── network/        # Device discovery and file transfer
│   ├── ui/             # Overlay window and system tray
│   └── main.py         # Entry point
├── tests/              # Unit tests
├── docs/               # Architecture notes
├── requirements.txt
├── CONTRIBUTING.md
└── README.md
```


## Contributing

We welcome contributions from the community.

**How to contribute:**

1. Fork this repository
2. Create a branch: `feature/your-feature-name` or `fix/your-bug-name`
3. Make your changes and write tests where relevant
4. Open a pull request against the `main` branch
5. One of the maintainers will review it

**Branch rules:**
- `main` is protected — no direct pushes allowed
- All changes must come in through a pull request
- PRs require approval from at least one of the three maintainers before merging
- Only the maintainers can merge into `main`

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guidelines.

---

## Maintainers

This project is maintained by three CS students at Dushanbe Innovation Institute.
Aminjon, Fadl  & islamibragimov


---

## Security

All file transfers happen over your local network only. Nothing is sent to any external server. Transfers are encrypted end-to-end using AES-GCM. The first time two devices connect, you confirm the pairing manually — after that it is remembered.

If you discover a security issue, please open a private issue or email us directly rather than posting it publicly.

---

## License

MIT License — see [LICENSE](LICENSE) for details.

You are free to use, copy, modify, and distribute this software for any purpose. Attribution appreciated but not required.

---

*Built at Dushanbe Innovation Institute · 2026*
