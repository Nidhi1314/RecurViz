# 🔄 RecurViz - Interactive Recursion Visualizer

**Master recursive algorithms through real-time visualization and live code execution.**

Transform abstract recursive concepts into tangible visual experiences with synchronized code highlighting, adjustable animation speeds, and step-by-step execution tracking across 5 classic algorithms.

---

## 🌟 Description

RecurViz is an interactive web-based platform designed to demystify recursive algorithms for computer science students. With real-time canvas animations, synchronized C++ code highlighting, and intuitive controls, users can visualize how recursion works under the hood—from call stack mechanics to backtracking behavior—making complex concepts accessible and engaging.

---

## 📋 Table of Contents

- [Features](#features)
- [Algorithms Included](#algorithms-included)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Team](#team)

---

## ✨ Features

### 🎨 **Visual Animations**
- Real-time HTML5 Canvas rendering for algorithm execution
- Smooth transitions and color-coded states
- Responsive design adapting to all screen sizes

### 💻 **Live Code Highlighting**
- Synchronized C++ code display with syntax highlighting
- Active line highlighting during execution
- Easy-to-follow step-by-step code flow

### ⚙️ **Interactive Controls**
- Adjustable animation speed (Slow/Normal/Fast)
- Configurable problem parameters (board size, array size, etc.)
- Play, pause, reset, and step-through functionality

### 📊 **Statistics & Feedback**
- Real-time metrics (backtracks, comparisons, moves)
- Current action descriptions
- Solution count and performance tracking

### 🌙 **Modern Dark UI**
- Eye-friendly dark theme
- Smooth hover animations
- Professional gradient effects
- Tailwind CSS-powered responsive layout

---

## 🧩 Algorithms Included

### 1. **N-Queens Problem**
Visualize backtracking as queens are placed on an N×N chessboard with constraint checking.

### 2. **Tower of Hanoi**
Watch disks move recursively between three pegs following the classic puzzle rules.

### 3. **Binary Search**
See how divide-and-conquer recursively halves the search space to find a target element.

### 4. **Flood Fill**
Experience the paint bucket algorithm spreading through connected regions on a pixel grid.

### 5. **Merge Sort**
Observe recursive array splitting and the merging process that creates a sorted list.

### 6. **Depth First Search (DFS)**
Follow graph traversal as recursion explores nodes depth-first with backtracking visualization.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5** | Structure and Canvas API for rendering |
| **CSS3** | Styling with custom animations |
| **Tailwind CSS** | Utility-first responsive design framework |
| **JavaScript (ES6+)** | Algorithm logic, animation control, DOM manipulation |
| **Canvas API** | Real-time 2D graphics rendering |
| **Google Fonts (Inter)** | Modern typography |

**No external JavaScript libraries or frameworks required!** Pure vanilla JS for maximum performance and learning clarity.

---

## 📥 Installation

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Basic web server (optional, for local development)

### Steps

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/recurviz.git
cd recurviz
```

2. **Open in browser**
```bash
# Option 1: Direct file open
open index.html

# Option 2: Using Python's built-in server
python -m http.server 8000

# Option 3: Using Node.js http-server
npx http-server
```

3. **Access the application**
Navigate to `http://localhost:8000` (if using a local server) or simply open `index.html` directly.

---

## 🚀 Usage

### Getting Started

1. **Launch the application** by opening `index.html` in your browser
2. **Select an algorithm** from the landing page card grid
3. **Configure parameters** using the control panel:
   - Adjust problem size (board size, array length, etc.)
   - Set animation speed (Slow/Normal/Fast)
4. **Click "Start"** to begin visualization
5. **Watch the magic happen**:
   - Observe canvas animations
   - Follow highlighted code execution
   - Monitor real-time statistics
6. **Interact as needed**:
   - Pause/Resume execution
   - Reset to try different configurations
   - Step through for detailed analysis

### Example: N-Queens Problem
```javascript
// The visualizer shows this algorithm in action:
function solveNQueens(row) {
    if (row === n) return true; // Base case - all queens placed
    
    for (let col = 0; col < n; col++) {
        if (isSafe(row, col)) {
            board[row] = col;        // Place queen
            if (solveNQueens(row + 1)) return true; // Recurse
            board[row] = -1;         // Backtrack
        }
    }
    return false;
}
```

As the algorithm runs, you'll see:
- Queens being placed on the board
- Code lines highlighting in sync
- Backtracking when conflicts occur
- Statistics updating in real-time

---

## 📸 Screenshots

### Landing Page
![Landing Page](screenshots/landing-page.png)
*Modern card-based interface showcasing all available algorithms*

### N-Queens Visualizer
![N-Queens](screenshots/n-queens.png)
*Real-time board visualization with synchronized code highlighting*

### Binary Search
![Binary Search](screenshots/binary-search.png)
*Array visualization showing search space reduction*

### Merge Sort
![Merge Sort](screenshots/merge-sort.png)
*Multi-level visualization of recursive splitting and merging*

---

## 📁 Project Structure
```
recurviz/
│
├── index.html              # Landing page with algorithm cards
├── n-queen.html           # N-Queens Problem visualizer
├── tower_of_hanoi.html    # Tower of Hanoi visualizer
├── binary-search.html     # Binary Search visualizer
├── flood-fill.html        # Flood Fill visualizer
├── ms.html                # Merge Sort visualizer
├── dfs.html               # Depth First Search visualizer
│
├── assets/
│   ├── screenshots/       # Project screenshots
│   └── icons/            # Custom icons (if any)
│
├── README.md             # Project documentation
├── LICENSE               # License file
└── .gitignore           # Git ignore rules
```

### File Organization

- **index.html**: Main landing page with navigation cards
- **Algorithm files**: Individual HTML files for each visualization
  - Self-contained with embedded CSS and JavaScript
  - Consistent dark theme and UI patterns
  - Responsive canvas and control layouts

---

## 🔧 How It Works

### 1. **Canvas Rendering**
```javascript
function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    drawBoard();    // Render background/structure
    drawQueens();   // Render current state
}
```

### 2. **Async Animation Control**
```javascript
async function solveNQueens(row) {
    highlightLine('currentLine');
    await sleep(animationSpeed);  // Pause for visualization
    // Algorithm logic...
}
```

### 3. **Live Code Highlighting**
```javascript
function syntaxHighlight(text) {
    return text
        .replace(/\b(if|return|for)\b/g, '<span class="cpp-keyword">$1</span>')
        .replace(/\b(solveNQueens)\b/g, '<span class="cpp-function">$1</span>')
        // ... more regex patterns
}
```

### 4. **Responsive Design**
```javascript
function resizeCanvas() {
    canvas.width = container.clientWidth;
    canvas.height = Math.min(window.innerHeight * 0.7, 500);
    draw();
}
window.addEventListener('resize', resizeCanvas);
```

---

## 🎯 Key Implementation Details

### N-Queens Problem
- **Algorithm**: Backtracking with constraint satisfaction
- **Visualization**: Chessboard with queen placement
- **Key Function**: `isSafe(row, col)` checks column and diagonal conflicts
- **Stats Tracked**: Solutions found, backtracks, current row

### Tower of Hanoi
- **Algorithm**: Classic recursive divide-and-conquer
- **Visualization**: Three pegs with animated disk movements
- **Key Function**: `hanoi(n, source, dest, aux)` recursive moves
- **Stats Tracked**: Total moves, current step

### Binary Search
- **Algorithm**: Recursive search with array halving
- **Visualization**: Color-coded array with search range
- **Key Function**: `binarySearch(arr, target, low, high)`
- **Stats Tracked**: Comparisons, recursion depth

### Flood Fill
- **Algorithm**: 4-directional recursive spreading
- **Visualization**: Pixel grid with color propagation
- **Key Function**: `floodFill(x, y, targetColor, replaceColor)`
- **Stats Tracked**: Cells filled, recursion calls

### Merge Sort
- **Algorithm**: Divide-and-conquer sorting
- **Visualization**: Multi-level array representation
- **Key Function**: `mergeSort(arr, left, right)` and `merge()`
- **Stats Tracked**: Comparisons, swaps, merge operations

### Depth First Search
- **Algorithm**: Graph traversal via recursion
- **Visualization**: Nodes and edges with visit coloring
- **Key Function**: `dfs(node, visited)` recursive exploration
- **Stats Tracked**: Nodes visited, path length

---

## 🚀 Future Enhancements

### 📚 More Algorithms
- Quick Sort visualization
- Fibonacci sequence (memoization vs plain recursion)
- Tree traversals (Inorder, Preorder, Postorder)
- Maze solving algorithms
- Subset sum problem
- Permutations and combinations

### 🎓 Educational Features
- **Custom code input**: Let users visualize their own recursive functions
- **Quiz mode**: Test understanding after visualization
- **Comparison mode**: Show recursive vs iterative side-by-side
- **Voice explanations**: Audio walkthrough for accessibility
- **Export functionality**: Save animations as GIF/video

### 💻 Technical Improvements
- **WebGL rendering**: Better performance for complex visualizations
- **PWA support**: Offline functionality and app-like experience
- **Multi-language support**: Python, Java, JavaScript code examples
- **User accounts**: Save progress and custom configurations
- **Complexity analyzer**: Show time/space complexity in real-time

### 🎨 UI/UX Enhancements
- **Theme customization**: Light mode, high contrast options
- **Mobile gestures**: Swipe controls for touch devices
- **Keyboard shortcuts**: Power user navigation
- **Collaborative features**: Share visualizations with classrooms

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Reporting Bugs
- Use GitHub Issues to report bugs
- Include browser version and steps to reproduce
- Screenshots are helpful!

### Suggesting Features
- Open a feature request issue
- Describe the use case and expected behavior
- Explain why it would benefit users

### Code Contributions
1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes with clear commit messages
4. Test thoroughly across browsers
5. Submit a pull request with description

### Coding Standards
- Use meaningful variable names
- Comment complex logic
- Follow existing code style (2-space indentation)
- Ensure responsive design principles
- Test on Chrome, Firefox, and Safari

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```
MIT License

Copyright (c) 2024 RecurViz Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files...
```

---

## 👥 Team

**Computer Graphics Project - [Your University Name]**

| Name | Role | Contact |
|------|------|---------|
| [Your Name] | Lead Developer | [email/github] |
| [Team Member 2] | Algorithm Implementation | [email/github] |
| [Team Member 3] | UI/UX Design | [email/github] |
| [Team Member 4] | Documentation | [email/github] |

---

## 🙏 Acknowledgments

- **Inspiration**: Visualgo.net, Algorithm Visualizer
- **Resources**: MDN Web Docs, "Introduction to Algorithms" by CLRS
- **Tools**: Tailwind CSS, Google Fonts, Canvas API
- **Community**: Stack Overflow, GitHub discussions

---

## 📞 Contact & Links

- **GitHub Repository**: [github.com/yourusername/recurviz](https://github.com/yourusername/recurviz)
- **Live Demo**: [recurviz.netlify.app](https://recurviz.netlify.app) *(if deployed)*
- **Documentation**: [Wiki](https://github.com/yourusername/recurviz/wiki)
- **Report Issues**: [Issue Tracker](https://github.com/yourusername/recurviz/issues)

---

## ⭐ Star This Repository

If RecurViz helped you understand recursion better, please give it a star! ⭐

---

<div align="center">

**Made with ❤️ for Computer Science Students**

*"Recursion: See Recursion"*

</div>
```

---

## 📝 2-3 Line Descriptions (Various Styles)

### **Technical & Concise**
```
RecurViz is an interactive web platform that visualizes recursive algorithms in real-time with synchronized code highlighting. Built with HTML5 Canvas and vanilla JavaScript, it transforms abstract recursive concepts into tangible visual experiences across 5 classic algorithms.
```

### **Student-Focused**
```
Stop struggling with recursion! RecurViz provides step-by-step visual animations of recursive algorithms with live code tracking, adjustable speeds, and real-time statistics—making call stacks, backtracking, and base cases finally click for computer science students.
```

### **Feature-Driven**
```
RecurViz combines HTML5 Canvas animations, syntax-highlighted code execution, and interactive controls to visualize N-Queens, Tower of Hanoi, Binary Search, Flood Fill, Merge Sort, and DFS algorithms—all in a modern dark-themed interface with responsive design.
```

### **Problem-Solution Format**
```
70% of CS students struggle with recursion. RecurViz solves this with real-time algorithm visualization, synchronized code highlighting, and step-by-step execution tracking across 6 recursive algorithms—transforming abstract concepts into clear visual understanding.
```

### **Marketing Style**
```
Master recursion the visual way! RecurViz brings algorithms to life with smooth canvas animations, live code tracking, and intuitive controls. Watch backtracking happen, see call stacks build, and finally understand how recursion works—one frame at a time.
