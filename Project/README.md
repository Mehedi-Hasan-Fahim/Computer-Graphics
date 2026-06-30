# 🎡 Interactive Village Fair

An OpenGL graphics project featuring a fully interactive village fair scene with a rotating Ferris wheel, animated environment, day/night cycle, and shop interactions.

![OpenGL](https://img.shields.io/badge/OpenGL-2D_Graphics-blue)
![C++](https://img.shields.io/badge/C++-GLUT-green)
![Platform](https://img.shields.io/badge/Platform-Windows-orange)

---

## 📸 Features

* **🎡 Animated Ferris Wheel** — Continuously rotating wheel with 4 colored gondolas, passengers, rim lights, and cross bars.
* **🌅 Day/Night Cycle** — Toggle between day mode (sun, blue sky, white clouds) and night mode (moon, stars, dark overlay).
* **☁️ Animated Clouds** — 5 clouds drifting across the sky with seamless wrapping.
* **🧑 Interactive Character** — Move a detailed character around the scene using your keyboard arrow keys.
* **🛒 Shop Interactions** — Visit two shops and purchase items:
  * **Left Stall:** Fruit Shop (sells apples, oranges, guavas, and lemons).
  * **Right Stall:** Balloon Shop (sells pink, blue, and yellow balloons).
* **🎒 Inventory System** — Purchased items visually appear on the character (a balloon in hand or a fruit basket).
* **🌳 Environment Details** — Beautifully layered ground featuring trees, grass blades, and a textured pathway.

---

## 🎮 Controls

| Key | Action |
| :--- | :--- |
| `↑` `↓` `←` `→` | Move the player character |
| **`D`** | Enable **Day mode** |
| **`N`** | Enable **Night mode** |
| **`Y`** | **Buy item** from shop (Yes) |
| **`N`** | **Decline purchase** (No) — *when shop prompt is active* |

> 💡 **How to interact:** Walk your character near either of the shops to trigger the buy prompt. Then, press **`Y`** to purchase an item or **`N`** to decline.

---

## 🏗️ Project Structure

```text
├── main.cpp          // Single-file OpenGL application
└── README.md         // Documentation
