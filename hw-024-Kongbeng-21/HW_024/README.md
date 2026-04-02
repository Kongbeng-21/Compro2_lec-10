# HW_024: Pygame Reaction Game with Matplotlib Dashboard

## Objective
Create an interactive Python desktop application using `pygame`. The window should be split into two halves:
1. **Left Side (Game Area):** A reaction game that displays a random character/letter on the screen. The user must press the exact key on their keyboard corresponding to that letter. 
2. **Right Side (Dashboard):** A dynamically updating `matplotlib` bar chart showing the user's current "Hits", "Misses", and "Total" attempts.

**The final requested application should look similar to the following screenshot:**
![App Screenshot](screenshot.png)

## Requirements

### 1. Pygame Window Structure
- The application must use `pygame` for the main loop and rendering.
- Set the window size to something wide (e.g., `800x400`) to accommodate both the game area and the chart side-by-side.

### 2. Game Logic
- Display a random uppercase letter in the left half of the screen.
- Listen for `pygame.KEYDOWN` events.
- If the pressed key matches the displayed letter: increment `Hits`.
- If the pressed key does not match: increment `Misses`.
- In either case, increment `Total` and generate a new random letter.

### 3. Matplotlib Integration (The Visualization)
Just like the previous Tkinter homework, you **must not** attempt to render matplotlib natively into the display framework. Instead, use the file-saving approach:
1. **Interactive Trigger:** Whenever the `Hits` or `Misses` stats change, trigger a plot update.
2. **Generate Plot & Save Image:** Generate a bar chart using `matplotlib` containing three bars (Hits, Misses, Total). Save the generated figure to an image file on the disk (e.g., `stats_plot.png`). **Remember to `plt.close()`!**
3. **Load Image to Pygame:** Load the newly saved image file using `pygame.image.load()` and `blit()` it to the exact right half of your game screen (e.g. at x=400).

### 4. Code Quality
- Clean code architecture following Object-Oriented Programming (OOP) is highly recommended.
- Limit unnecessary plot generations! Since generating plots takes a microscopic moment, only regenerate and overwrite `stats_plot.png` when the user actually presses a key, not wildly on every single Pygame frame (`while` loop tick). 

---

## Starter Code
You can find the structural starter code inside `homework.py`. Modify it to implement the data-tracking and plotting logic.

**Running the basic app:**
```sh
python homework.py
```
