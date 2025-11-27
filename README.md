# The-Eigen-Valley
Eigen Valley: A Linear Algebra Ecosystem

"Mathematics is the DNA of Nature."

Eigen Valley is a procedural 3D landscape generated entirely through mathematical functions and Linear Algebra concepts. It visualizes how abstract vector operations—like dot products, cross products, and gradient descent—can sculpt a living, breathing ecosystem.

Overview

This project treats the computer screen not as a canvas for pixels, but as a Vector Space ($\mathbb{R}^3$).

Instead of manually modeling mountains or rivers, we defined mathematical rules (axioms). The terrain, the river, and the weather are all emergent properties of these linear operators acting upon a grid of random vectors.

Mathematical Foundation

This project is a visual calculator for the following Linear Algebra concepts:

1. Vector Fields (Terrain Generation)

The terrain is not random noise; it is a Vector Field.

Concept: We assign a random "Gradient Vector" ($\vec{g}$) to grid corners.

Application: The height of any point on the ground is calculated using the Dot Product between the distance vector and the gradient vector.


$$h(x,y) = \vec{d} \cdot \vec{g} = ||\vec{d}|| \cdot ||\vec{g}|| \cos(\theta)$$

Visual Result: Smooth, continuous rolling hills instead of jagged randomness.

2. The Cross Product (Surface Normals)

To light the terrain correctly, the engine needs to know which way the ground faces.

Concept: The Normal Vector ($\vec{n}$) is orthogonal to the surface.

Application: We calculate this by taking the Cross Product of two tangent vectors ($\vec{t}_x, \vec{t}_z$) derived from the slope.


$$\vec{n} = \vec{t}_z \times \vec{t}_x$$

Visual Feature: Toggle "Show Normals" in the UI to see pink arrows representing these vectors in real-time.

3. The Null Space (The River)

The river is a mathematical "Kernel."

Concept: The Null Space is the set of vectors that map to zero.

Application: We defined a non-linear path function $P(z)$. Any terrain vector $\vec{v}$ that falls within the domain of this path is forced to a height of 0.

Visual Result: A riverbed that cuts through mountains, forcing the terrain function to "collapse" into the water level.

4. Gradient Descent (Eigen-Rain)

The weather system creates a visualization of machine learning optimization.

Concept: Gradient Descent finds the local minimum of a function.

Application: Each raindrop calculates the gradient (slope) of the terrain $\nabla h$ at its current position and moves in the opposite direction.


$$\vec{p}_{new} = \vec{p}_{old} - \alpha \nabla h$$

Visual Result: Glowing particles that flow like water, finding the most efficient path down the mountain to the river.

User Manual & Controls

The simulation includes an interactive HUD to manipulate the matrix parameters in real-time.

| Control | Function | Math Concept |
| :--- | :--- | :--- |
| **Grid Scale** | Changes the frequency of the noise. | Input Vector Scaling |
| **Amplitude** | Stretches the mountains vertically. | Scalar Multiplication |
| **River Width** | Widens the river path. | Null Space Domain Expansion |
| **Water Level** | Raises/Lowers the sea plane. | Subspace Intersection |
| **Show Normals** | Displays pink arrows on terrain. | Cross Product Visualization |
| **Eigen-Rain** | Activates the particle system. | Gradient Descent / Optimization |

Technology Stack

Engine: Three.js (WebGL rendering pipeline)

Language: JavaScript (ES6 Modules)

Math: Custom implementation of Perlin Noise and Gradient Kernels.

How to Run

### Option 1: Local Execution

Clone this repository.

git clone [https://github.com/JaideepBiswas2003/eigen-valley.git](https://github.com/JaideepBiswas2003/eigen-valley.git)


Navigate to the folder.

Open Eigen-Valley.html in your web browser.

Note: If textures fail to load due to CORS policies, run a local server:

python -m http.server
# Then visit http://localhost:8000

### Option 2: Manual Setup

If you just want to run the code quickly on your laptop without installing Git:

1.  **Copy the Code:** Open the `index.html` file in this repository, click "Raw", and copy all the text.
2.  **Open a Text Editor:**
    * **Windows:** Open *Notepad*.
    * **Mac:** Open *TextEdit* (Important: Go to **Format** > **Make Plain Text** first).
    * Or Use *VS Code*.
3.  **Save the File:**
    * Paste the code into the editor.
    * Save the file anywhere on your computer.
    * **Filename:** `index.html`
    * **Save as type:** Select **"All Files"** (if on Windows) to ensure it doesn't save as `index.html.txt`.
4.  **Run:** Go to the folder where you saved it and **double-click** `index.html`. It will launch the simulation in your default web browser.

> **Note:** If you see a blank screen, your browser's security settings might be blocking the 3D graphics engine. If this happens, please use **Option 1 (Local Execution)** to run a simple local server.

Authors

Sayali Kadam (25m1110)

Jaideep Biswas (25m1114)

Created for the EE 635 Linear Algebra Course Art Project.
