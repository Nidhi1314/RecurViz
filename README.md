# 🧠 RecursoVis: Tower of Hanoi Simulation

**Visualizing Recursion: A Dynamic Learning Tool for Computer Science Students**

---

## 💡 Project Overview

This project is an **interactive, web-based simulation** of the classic Tower of Hanoi puzzle. Built using **HTML5 Canvas** and **Vanilla JavaScript**, the tool provides a tangible and intuitive way for students to understand and visualize the often-abstract concept of **recursive algorithms**. By animating the process step-by-step, we aim to bridge the gap between theoretical understanding and practical application of recursion.

---

## 🎯 The Problem & Our Solution

### The Problem

Studies show that a significant percentage of Computer Science students struggle to grasp **recursive algorithms**. Traditional teaching methods often rely on static diagrams and text, which fail to make the **abstract nature of recursion** clear. This difficulty ultimately leads to poor performance in algorithms courses.

### Our Solution

We provide an interactive, cross-platform solution to this problem:

* **Interactive Visualization:** A web-based animation of the Tower of Hanoi puzzle using **HTML5 Canvas**.
* **Real-Time Animation:** Smooth JavaScript animations show the execution of the recursive algorithm, making the process explicitly clear.
* **User Control:** An intuitive web interface allows students to **explore the simulation at their own pace**.
* **Concept Visualization:** Visual demonstration of the recursive logic, including the **state of the pegs** and each disk movement.

---

## ✨ Features & Technical Foundations

### Technical Foundations

| Component | Technology / Language | Purpose |
| :--- | :--- | :--- |
| **Programming Language** | Vanilla JavaScript | Client-side interactivity and animation control. |
| **Graphics API** | HTML5 Canvas | Rendering 2D graphics, disk animations, and visual effects. |
| **Styling Framework** | Tailwind CSS | Responsive design and modern user interface components. |
| **Data Structures** | JavaScript Arrays/Objects | Representing pegs and managing disk positions. |

### Interactive Learning & Visual Cues

* **User Controls:** Intuitive web interface with buttons, sliders, and potentially keyboard inputs for simulation control.
* **Animated Moves:** Disks move smoothly between pegs using `requestAnimationFrame` and CSS transitions for optimal performance.
* **Clarity:** Each disk is rendered as a distinct colored shape.

---

## ⚙️ How the Algorithm is Visualized

The simulation vividly demonstrates the core recursive steps to move $n$ disks from a source peg (**S**) to a destination peg (**D**) using an auxiliary peg (**A**):

1.  Move $n-1$ disks from **S** to **A**, using **D** as auxiliary.
2.  Move the remaining largest disk (disk $n$) from **S** to **D**.
3.  Move $n-1$ disks from **A** to **D**, using **S** as auxiliary.

By showing the process in real-time, the visualization helps students internalize abstract concepts like the **call stack, backtracking, and the divide-and-conquer strategy**.

---

## 🚀 Impact & Broader Relevance

Beyond improving recursion comprehension, this project demonstrates valuable principles in several areas:

* **Web Development & Graphics:** Practical application of HTML5 Canvas rendering, JavaScript animations, and responsive design.
* **Algorithm Visualization:** Essential practice for debugging and optimizing complex algorithms in fields like AI and robotics.
* **Recursion:** Reinforces a foundational concept used in data structures, compiler design, and functional programming.

