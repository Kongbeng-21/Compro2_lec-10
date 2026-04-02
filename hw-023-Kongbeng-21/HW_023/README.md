# Interactive Data Visualization with Tkinter

## Objective
Create an interactive Python desktop application using `tkinter`. The application will load data from a provided CSV dataset, allow the user to control inputs via the graphical interface, and display a dynamically updating data visualization chart.

**The final application should support different dynamic chart outputs.**
Here are examples of what the visualizer should look like as settings are toggled:

**Line Chart:**
![App Screenshot Line](screenshot_line.png)

**Scatter Plot:**
![App Screenshot Scatter](screenshot_scatter.png)

**Bar Chart:**
![App Screenshot Bar](screenshot_bar.png)

## Requirements

### 1. GUI Components (Tkinter)
- The application must have a main window.
- It must include at least three control widgets (e.g., Dropdowns for Category, Region, and Chart Type) that dictate what data is being visualized.
- It must include a display area (a `Label` or `Canvas`) to show the resulting graph.

### 2. Data Processing
- The program must read data from the provided CSV file (`data.csv`). You are encouraged to use the `pandas` library or the built-in `csv` module.

### 3. Visualization & Interaction Flow
To ensure the matplotlib visualization is fully compatible and displays correctly inside tkinter, you **must strictly follow this workflow**:
1. **Interactive Trigger:** When the user changes a value in the GUI control widget, a callback function must be triggered.
2. **Generate Plot & Save Image:** Inside the callback function, filter the data and generate a plot (using `matplotlib`). **Do not embed the plot directly.** Instead, save the generated figure to an image file on the disk (e.g., `output_plot.png`).
3. **Load Image to Tkinter:** Read the newly saved image file and update the `tkinter` display area to show the fresh image.

### 4. Code Quality
- Code should be clean and follow Object-Oriented Programming (OOP) principles by encapsulating the UI state and logic inside a class (`InteractivePlotApp`).
- Always close the `matplotlib` figure (`plt.close()`) after generating and saving an image to prevent memory leaks!

---

## Starter Code
You can find the starter code structure inside `homework.py`. Use it as a foundation and modify the dummy data generation to read and plot from the attached `data.csv` file instead. 

**Running the basic app:**
```sh
python homework.py
```
