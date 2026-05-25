# Brutal Zip

**Ultra-fast ZIP creation, extraction, and encryption for Windows.**

Built from scratch in C# on .NET 8. No wrappers, no third-party compression libraries for the core ZIP engine — just a custom-forked libdeflate with multi-threading and streaming, tuned for modern hardware.

---

## Performance

Benchmarked against Star Wars Battlefront II (9.57 GB mixed content). All tools produce standard `.zip` files — same format, same rules, same compatibility.

### Compression

| Tool | Time | Speed |
|------|------|-------|
| **Brutal Zip** | **0:28** | **341 MB/s** |
| WinRAR | 1:57 | 82 MB/s |
| 7-Zip | 2:11 | 73 MB/s |
| Windows 11 | 3:58 | 40 MB/s |

### Decompression

| Tool | Time | Speed |
|------|------|-------|
| **Brutal Zip** | **0:06** | **1,595 MB/s** |
| WinRAR | 0:43 | 223 MB/s |
| 7-Zip | 0:56 | 171 MB/s |
| Windows 11 | 1:11 | 135 MB/s |

4x faster compression and 7-12x faster decompression than the industry standard tools — on the same open ZIP format.

---

## Features

### Archive Formats

| Format | Open | Create |
|--------|------|--------|
| ZIP | Yes | Yes |
| 7z | Yes | - |
| RAR 4/5 | Yes | - |
| TAR | Yes | Yes |
| TAR.GZ | Yes | Yes |
| TAR.ZST | Yes | Yes |

### Compression Methods
- **Deflate** — Default ZIP compression via custom-forked libdeflate
- **Zstandard (Zstd)** — Modern compression with dictionary training, levels 1-22
- **LZMA** — High-ratio compression
- **Store** — No compression

### Encryption
- AES-256 / AES-192 / AES-128 (WinZip compatible)
- ZipCrypto (legacy)
- Built-in multi-threaded password recovery (brute force + dictionary attacks)

### Split Archives
- Multi-part / split archive creation and extraction
- Configurable part sizes

### Self-Extracting Archives (SFX)
- Custom icons, banners, and gradient themes with live preview
- License agreement with acceptance requirement
- Post-extraction command execution
- UAC elevation support
- Macro-based extraction paths (`%TEMP%`, `%DESKTOP%`, `%APPDATA%`, etc.)

### Archive Repair & Forensics
- Interactive ZIP Map visualising the raw archive structure
- Per-entry diagnostics: signature validation, CRC verification, overlap detection
- Central Directory rebuild or salvage-to-new-archive repair modes
- Raw compressed data extraction

### Archive Comparison
- Side-by-side diff of two archives
- CSV and JSON export

### File Preview (In-App)
- **Images:** PNG, JPG, BMP, GIF, TIFF, ICO, WebP
- **Code:** C#, Java, Python, JavaScript, HTML, CSS, XML, JSON, YAML (syntax highlighted)
- **Documents:** PDF (via Chromium), plain text, Markdown, CSV
- **Media:** MP4, WebM, MOV, MP3, WAV, OGG, FLAC
- **Binary:** EXE/DLL signature detection, hex view

### Windows Explorer Integration
- **Preview Handler** — View archive contents in Explorer's preview pane without opening Brutal Zip
- **Context Menu** — 20+ right-click operations for compress, extract, test, repair, and more
- Per-user registration — no admin elevation required

### Scripting (BZS)
- Domain-specific language with 50+ commands for archive automation
- IDE with syntax highlighting, breakpoints, debugging, and auto-complete
- Visual block editor for drag-and-drop scripting
- AI script generation (Claude and OpenAI)

### UI
- Dark and light themes with automatic OS detection
- Ribbon toolbar with collapsible groups
- Command Palette (Ctrl+K)
- Real-time progress chart with speed history, ETA, and file throughput

---

## System Requirements

- **OS:** Windows 10 or Windows 11
- **Runtime:** .NET 8 Desktop Runtime (bundled with installer)
- **Architecture:** x64

---

## Installation

Download the latest installer from the [Releases](https://github.com/Limintel-PTY-LTD/Brutal-Zip-Release/releases) page.

The installer registers context menus, the preview handler, and file associations under your user account — no administrator privileges needed.

Auto-updates are built in and check on startup (configurable in Settings).

---

## License

Proprietary. Brutal Zip is freeware — free to use, no nag screens, no feature locks.

If you paid for it, you should get a refund.

---

## Author

**James Grice** — [Limintel Solutions](https://limintel.com/)

Built over 8 months of hand-crafted engineering.
