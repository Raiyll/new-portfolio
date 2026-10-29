# DESIGN.md - macOS Workstation Portfolio (Ahmad Rafi Fadhilah MacBook Pro)

## Identity & Concept
- **Product / Owner**: Ahmad Rafi Fadhilah (Full-Stack Developer at PT Tri Nindya Utama, Kab. Tangerang, Banten)
- **Visual Metaphor**: **macOS Workstation ("Ahmad Rafi's MacBook Pro")**, featuring an interactive MacBook Lock Screen / Login landing view (like opening a MacBook lid) that unlocks into a full macOS desktop with Menu Bar, Stage Manager / Draggable Windows, Finder, Preview.app (Resume), Activity Monitor, zsh Terminal, and Mail.app.
- **Design Read**: Interactive macOS Laptop Lock Screen and Desktop OS portfolio for technical recruiters and engineering managers, in a warm macOS workstation style, dial `ENERGY 3 / RHYTHM 3 / MOTION 2`.

## Three Dials
- **ENERGY: 3 (Bold)** - Opens with an interactive MacBook Login / Lock Screen showing live Tangerang time, portrait avatar, and one-click Touch ID / Enter login that transitions into the active macOS desktop.
- **RHYTHM: 3 (Varied)** - Every macOS application window uses a distinct layout tailored to its data:
  1. `Lock Screen Landing`: Centered MacBook account login screen with customizable wallpaper (`Starry`, `Foto Default`, `Warm Dusk`, or user-uploaded custom photo via `Pilih Foto` / `--lock-wallpaper-image`), an interactive starlight/firefly particle canvas with pause control, an interactive cat companion (`Mochi`) perched on the login card whose eyes track the cursor and ears twitch when typing, large time/date readout, Touch ID unlock prompt, and quick session actions.
  2. `About This Mac & Career (Experience.app)`: Asymmetric hardware/bio overview paired with a structured career timeline (PT Tri Nindya Utama - BKKBN AMS, SMKN 4 Tangerang, Samsung Innovation Campus Stage 1 & Stage 2 certifications).
  3. `Finder (/Users/ahmadrafi/Projects)`: Master-detail and category-filtered repository explorer covering all 6 projects (AMS Inspektorat BKKBN, Jamu!, LootHub, Esemkabooks C#, Esemka Store Android POS, ESP32 IoT Alarm).
  4. `Preview.app (Resume_Ahmad_Rafi_Fadhilah.pdf)`: Structured document sheet with competition awards (1st UNIPI, 2nd LKS ITSS Kota, 2nd Storytelling) and printable CV readout.
  5. `Activity Monitor (Stack & Processes)`: Searchable process table of frameworks, languages, databases, and IoT/desktop tools.
  6. `Terminal.app (zsh) & Mail.app`: Interactive macOS command-line shell alongside a two-pane email and social endpoint client.
- **MOTION: 2 (Balanced)** - Smooth Lock Screen unlock transition, interactive Lock Screen particle canvas and cat companion with an explicit user Pause/Play toggle (`#lock-motion-btn`, R-19), window minimize/zoom/focus transitions, and optional free-drag window movement on desktop. Respects `prefers-reduced-motion: reduce` and automatically stops Lock Screen `requestAnimationFrame` when unlocked.

## Color System (2 Core + 1 Deliberate Accent, Dual Theme, WCAG AA)
- **Dark Theme ("Space Black MacBook" - Default)**:
  - Surface Base: `#0c0e12` (Desktop wallpaper canvas) / `#161920` (Window surface) / `#1f242d` (Titlebar & elevated controls)
  - Text Hierarchy: `#f5f2eb` (Primary text, contrast 16.1:1) / `#b7b0a6` (Secondary text, contrast 8.3:1)
  - Deliberate Accent: `#e07a5f` (Warm Terracotta Copper, contrast 4.6:1 on dark surface, `#111317` dark ink on primary buttons at 7.1:1)
- **Light Theme ("Silver Birch MacBook")**:
  - Surface Base: `#e6dfd3` (Desktop canvas) / `#fcfaf5` (Window surface) / `#ede6da` (Titlebar & elevated controls)
  - Text Hierarchy: `#1d1612` (Primary text, contrast 15.2:1) / `#52453c` (Secondary text, contrast 7.5:1)
  - Deliberate Accent: `#a64122` (Deep Terracotta, contrast 5.7:1 on light surface, `#ffffff` ink on primary buttons)
- **Glassmorphism Dose Cap (R-10)**: `backdrop-filter: blur()` is restricted strictly to 2 chrome elements (`.mac-menubar` and `.mac-dock`); all windows, cards, and modals use solid opaque surfaces.

## Typography
- **UI & Document Copy**: `Plus Jakarta Sans` - clean humanist geometric sans for macOS menu chrome, Finder views, and resume paragraphs.
- **Terminal & System Metadata**: `JetBrains Mono` - used strictly for `zsh` terminal commands, process PIDs, and file paths.

## One-Line Reasons for Major Decisions (R-31)
- **Why this color palette?**: Combines macOS Space Black and Silver surface hierarchy with Ahmad Rafi's signature warm terracotta accent while meeting WCAG AA contrast in both themes.
- **Why this layout?**: Starting with a MacBook Lock Screen landing page before entering the multi-window macOS desktop fulfills the laptop wake-up metaphor while keeping every resume section organized by native Mac app.
- **Why this typography?**: `Plus Jakarta Sans` mirrors macOS interface clarity for dense career descriptions, while `JetBrains Mono` isolates executable `zsh` commands and system identifiers.
- **Why this spacing?**: Uses `16px` Stage Manager window gaps on desktop and compact `12px-16px` mobile spacing with `88px` bottom padding reserved for the macOS Dock.
- **Why use application windows instead of uniform cards?**: Each window represents a functional macOS utility (Experience Timeline, Finder Projects, Preview Resume, Activity Monitor, zsh Terminal, Mail) with real Close, Minimize, and Zoom controls.
- **Why these icons?**: RemixIcon glyphs are paired with explicit labels to represent macOS utilities (Apple menu, Finder folder, Preview document, CPU monitor, Terminal, Mail, Touch ID).
- **Why this motion?**: Short `180ms-240ms` transitions provide responsive feedback when unlocking the MacBook, switching Stage Manager workspaces, or dragging windows.
