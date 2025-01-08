# st
This is Pete Hinchley's fork of st (simple terminal): https://st.suckless.org

## Changes
It is based on version 0.9 of st with the following patches:
- scrollback (with mouse support + reflow): https://st.suckless.org/patches/scrollback/
- alpha transparency: https://st.suckless.org/patches/alpha/
- change alpha: https://st.suckless.org/patches/changealpha/
- right click to paste selection: https://st.suckless.org/patches/rightclickpaste/
- character height offsets: https://st.suckless.org/patches/charoffsets/

It also includes the following personal customisations:
- Fira Code font with a default size of 14px.
- Catppuccin colour theme (macchiato): https://github.com/catppuccin/

## Shortcuts
Action           | Key Combination
---              | ---
Copy             | `ctrl`  + `shift` + `c`
Paste            | `ctrl`  + `shift` + `v`
Paste Selected   | `ctrl`  + `shift` + `y`
Zoom In          | `ctrl`  + `shift` + `PageUp`
Zoom Out         | `ctrl`  + `shift` + `PageDown`
Reset Zoom       | `ctrl`  + `shift` + `Home`
Scroll Up        | `shift` + `PageUp`
Scroll Down      | `shift` + `PageDown`
Increase Opacity | `alt`   + `BracketLeft`
Decrease Opacity | `alt`   + `BracketRight`
Reset Opacity    | `alt`   + `BraceRight`

## Build
To build and install st:

```
git clone https://github.com/hinchley/st.git
cd st
./build.sh
```

## Update Procedure
To create this fork, the relevant patches were downloaded, and each was applied using the following command from the root of the repository:

```
patch --merge -i <patch name>.diff
```

Failed changes were then manually remediated. A failure is marked by >>>> or <<<< within the target file. The tailored changes were then saved into the patches folder using the following command:

```
git diff > ./patches/<xx-name>.patch
```

Where xx is an incremental index that defines the sequence in which the patches must be applied.

The changes can be applied to a fresh pull of the st repo by running:

```
git apply ./patches/*
```
