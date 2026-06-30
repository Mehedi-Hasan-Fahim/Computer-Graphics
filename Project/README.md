```markdown
# 🎡 Interactive Village Fair

An OpenGL graphics project featuring a fully interactive village fair scene with a rotating Ferris wheel, animated environment, day/night cycle, and shop interactions.

![OpenGL](https://img.shields.io/badge/OpenGL-2D_Graphics-blue)
![C++](https://img.shields.io/badge/C++-GLUT-green)
![Platform](https://img.shields.io/badge/Platform-Windows-orange)

---

## 📸 Features

- **🎡 Animated Ferris Wheel** — Continuously rotating wheel with 4 colored gondolas, passengers, rim lights, and cross bars
- **🌅 Day/Night Cycle** — Toggle between day mode (sun, blue sky, white clouds) and night mode (moon, stars, dark overlay)
- **☁️ Animated Clouds** — 5 clouds drifting across the sky with seamless wrapping
- **🧑 Interactive Character** — Move a detailed character around the scene using arrow keys
- **🛒 Shop Interactions** — Visit two shops and purchase items:
  - **Left Stall** — Fruit Shop (apple, orange, guava, lemon)
  - **Right Stall** — Balloon Shop (pink, blue, yellow balloons)
- **🎒 Inventory System** — Purchased items visually appear on the character (balloon in hand or fruit basket)
- **🌳 Environment Details** — Trees, grass blades, textured pathway, layered ground

---

## 🎮 Controls

| Key | Action |
|-----|--------|
| `↑` `↓` `←` `→` | Move character |
| `D` | Enable Day mode |
| `N` | Enable Night mode |
| `Y` | Buy item from shop (Yes) |
| `N` | Decline purchase (No) — *when shop prompt is active* |

> **Note:** Walk your character near a shop to trigger the buy prompt, then press `Y` to purchase or `N` to decline.

---

## 🏗️ Project Structure

```
├── main.cpp          // Single-file OpenGL application
└── README.md
```

All drawing logic, animation, input handling, and interaction are contained in a single well-commented source file organized into clear sections:

| Section | Description |
|---------|-------------|
| Global Configuration | Mode flags, animation speeds, positions, inventory state |
| Primitive Helpers | `drawFilledCircle()`, `drawCircleOutline()`, `drawArch()` |
| Sky & Atmosphere | Gradient sky, clouds, sun/moon, stars |
| Ground & Nature | Layered ground, grass blades, trees, pathway |
| Characters | Detailed player character (`drawUser()`), generic humans (`drawHuman()`) |
| Shops | Fruit shop (left), Balloon shop (right) with keepers & items |
| Ferris Wheel | Rim, lights, cross bars, gondolas with counter-rotation |
| Interaction | Proximity-based shop prompts, inventory toggles |
| Input & Loop | Keyboard handler, timer callback, display loop |

---

## 🔧 Dependencies & Setup

### Prerequisites

- **Windows OS** (uses `windows.h`)
- **OpenGL** (typically pre-installed on Windows)
- **GLUT Library** (OpenGL Utility Toolkit)

### Installing GLUT

1. Download GLUT from the [OpenGL GLUT repository](https://www.opengl.org/resources/libraries/glut/)
2. Place these files in your compiler's include/lib directories:
   - `glut.h` → `C:\Program Files\...\include\GL\`
   - `glut32.lib` → `C:\Program Files\...\lib\`
   - `glut32.dll` → `C:\Windows\System32\`

### Compiling

**With MinGW/GCC:**
```bash
gcc main.cpp -o village_fair.exe -lopengl32 -lglut32 -lglu32
```

**With Visual Studio:**
1. Create a new C++ Console Project
2. Add `main.cpp` to the project
3. Link additional dependencies: `opengl32.lib`, `glut32.lib`, `glu32.lib`
4. Build & Run

**With Code::Blocks:**
1. New Project → Console Application → C++
2. Go to *Project → Build Options → Linker settings*
3. Add: `opengl32`, `glut32`, `glu32`
4. Build & Run

---

## 🧩 Technical Highlights

### Gradient Sky
Vertex-by-vertex color interpolation using `GL_QUADS` to create smooth sky gradients.

### Cloud Animation
Clouds use a continuous offset (`cloudOffset`) with modular wrapping to create infinite scrolling.

### Ferris Wheel Gondola Counter-Rotation
```
glRotatef(wheelAngle, 0, 0, 1);       // Rotate entire wheel
  glTranslatef(gondolaX, gondolaY, 0); // Move to gondola position
    glRotatef(-wheelAngle, 0, 0, 1);   // Counter-rotate so gondola stays upright
      drawGondolaBox(i);
```

### Night Overlay
Semi-transparent dark layer using `GL_BLEND` with alpha blending:
```c
glEnable(GL_BLEND);
glBlendFunc(GL_SRC_ALPHA, GL_ONE_MINUS_SRC_ALPHA);
glColor4f(0.0f, 0.0f, 0.1f, 0.4f); // 40% opaque
```

### Proximity-Based Interaction
Shop prompts trigger when the character's position falls within a defined radius of a shop center.

---

## 📄 License

This project is for educational purposes as part of a Computer Graphics course.

---

## 🙏 Acknowledgements

- OpenGL documentation and references
- GLUT library for window management and input handling
```
