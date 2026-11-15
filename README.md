# EasyStart

A FreeCAD macro that starts a new document the way you actually want it.

Instead of **File → New** followed by adding a Part, a Body, and a Spreadsheet
by hand, EasyStart does all of it and asks you for the file name in the same
dialog — then saves it, optionally creating a matching folder for the project.

![EasyStart icon](EasyStart.svg)

## What it does

- Creates a new document containing a **Part** (`App::Part`) with one **Body**
  (`PartDesign::Body`) and a **Spreadsheet**, and leaves the Body active.
- Optionally opens straight into a **new sketch** (`Create Sketch`).
- Asks for the **file name** and saves the document as `<name>.FCStd`.
- Optionally creates a **folder named after the project** under your save path
  (`Create Folder`).
- Remembers your **save path** between runs, and lets you change it from the
  same dialog (`Change Save Path`).

## Install

**Addon Manager** — once EasyStart is listed in the FreeCAD Addon Index, it
appears in **Tools → Addon Manager** and installs with one click.

**Manually** — copy `EasyStart.FCMacro` into your user macros directory:

| OS | Directory |
|---|---|
| Linux | `~/.local/share/FreeCAD/Macro/` |
| Windows | `%APPDATA%\FreeCAD\Macro\` |
| macOS | `~/Library/Application Support/FreeCAD/Macro/` |

Then restart FreeCAD and run it from **Macro → Macros…**. The easiest way to
find the directory is **Macro → Macros… → User macros location**.

## Use

1. Run the macro (**Macro → Macros… → EasyStart → Execute**).
2. Type a file name.
3. Optionally tick **Create Sketch** (open a new sketch immediately) or
   untick **Create Folder** (save the file directly in the save path rather
   than a folder named after it).
4. Pick one:
   - **Save** — saves as `<save path>/<name>/<name>.FCStd` (or
     `<save path>/<name>.FCStd` when *Create Folder* is off).
   - **Continue Without Saving** — keeps the new document in memory, unsaved.
   - **Cancel** — closes the new document and discards it.

Your checkbox choices are remembered for next time, as is your save path.

**Before you run it:** start from an empty FreeCAD session. EasyStart creates a
brand-new document; if you already have one open and unsaved, close it first.

## Compatibility

- FreeCAD 0.20 and newer. Qt bindings are resolved automatically
  (PySide6 → PySide2 → PySide), so it runs on both the Qt5 and Qt6 builds.
- No external dependencies — uses only what FreeCAD ships.

## Other macros in this repository

- **EasyAlias.FCMacro** — *not part of this addon.* A vendored copy of the
  community `Macro EasyAlias` by TheMarkster and rosta, published on the
  [FreeCAD wiki](https://wiki.freecad.org/Macro_EasyAlias). EasyStart is the
  only macro this package installs.

## License

MIT — see [LICENSE](LICENSE).
