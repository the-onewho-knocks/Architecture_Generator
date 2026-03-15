# Architecture Generator

Generate a real folder/file structure from tree-style architecture text.  
No dependencies — just Python 3.x standard library.

---

## Usage

### GUI Mode (default)
Opens a tkinter window with a text box and browse button.
```bash
python generator.py
```

### CLI Mode
Paste architecture text directly in the terminal.
```bash
python generator.py --cli
```

### File Mode
Read architecture from a `.txt` file.
```bash
python generator.py --file arch.txt
```

---

## Example

Given this architecture text (saved as `arch.txt`):

```
parttime-platform/
├── cmd/
│   └── main.go
├── internal/
│   ├── models/
│   │   └── user.go
│   └── services/
│       └── auth_service.go
├── go.mod
└── README.md
```

Run:
```bash
python generator.py --file arch.txt
```

It will ask for an output directory, then create:
```
parttime-platform/
├── cmd/
│   └── main.go
├── internal/
│   ├── models/
│   │   └── user.go
│   └── services/
│       └── auth_service.go
├── go.mod
└── README.md
```

---

## Features

- Supports standard tree format using `├──`, `└──`, `│` characters
- Works with plain indented text too
- Optionally saves a `create_structure.sh` bash script
- GUI has a folder browser for easy output directory selection

---

## Requirements

- Python 3.x
- `tkinter` (included with standard Python on Windows/macOS — for GUI mode only)

---

## Tips

- Folder names ending with `/` are treated as directories
- Names without a file extension are also treated as directories
- Output directory is created automatically if it doesn't exist
- Existing files are never overwritten
