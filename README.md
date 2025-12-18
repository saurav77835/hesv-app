# Handwritten Equation Solver and Visualizer

A web-based application that allows users to draw mathematical equations by hand and instantly solve and visualize them. The application uses machine learning to detect handwritten equations and provides real-time graphical visualization of the solutions.

## Features

### Polynomial Equation Solver
- Draw polynomial equations on an interactive canvas
- Automatic detection of handwritten polynomial equations using ML
- Real-time equation solving and visualization
- Support for equations with variable `x`
- Interactive graphing powered by Desmos
- Input validation and error handling

### Linear Equation Solver
- Solve systems of 2D and 3D linear equations
- Support for 2 or 3 simultaneous equations
- Variables: x, y, and z
- Real-time equation validation
- Visual representation of solutions on a 3D graph
- Handwritten equation detection via drawing canvas

## Live Demo

- **Polynomial Solver**: [https://saurav77835.github.io/hesv-app](https://saurav77835.github.io/hesv-app)
- **Linear Solver**: [https://saurav77835.github.io/hesv-app/linear](https://saurav77835.github.io/hesv-app/linear)

## Screenshots

### Polynomial Equation Interface
![Polynomial UI](./images/UI-Poly.png)

### Linear Equation Interface
![Linear UI](./images/UI-Linear.png)

## Technology Stack

### Frontend
- **HTML5/CSS3** - Core structure and styling
- **Vanilla JavaScript** - Application logic
- **jQuery 1.10.1** - DOM manipulation
- **DrawerJs** - Interactive canvas drawing functionality
- **Desmos API** - Mathematical graphing and visualization
- **Font Awesome 6.0** - Icons

### Backend API
The application connects to a backend API hosted at `https://hesv-api.onrender.com` which handles:
- Handwritten equation detection using machine learning
- Polynomial equation solving
- Linear equation system solving (2D and 3D)

## Project Structure

```
hesv-app/
├── index.html              # Polynomial equation solver page
├── linear.html             # Linear equation solver page
├── css/
│   ├── linear.css         # Styles for linear solver
│   ├── poly.css           # Styles for polynomial solver
│   └── tooltip.css        # Tooltip styling
├── js/
│   ├── linear.js          # Linear equation logic
│   └── poly.js            # Polynomial equation logic
├── dist/                   # DrawerJs library files
├── images/                 # UI screenshots and assets
└── README.md
```

## Usage

### Polynomial Equations

1. **Draw the Equation**
   - Use the canvas to draw your polynomial equation
   - Click the "Send" button to detect the handwritten equation
   - The detected equation will appear in the input field

2. **Manual Entry**
   - Type your equation directly in the input field
   - Format: `ax^n + bx^(n-1) + ... + c = 0`
   - Example: `x^2 + 2x + 1 = 0`

3. **Solve**
   - Click the "Solve" button
   - View solutions displayed below the equation
   - See the equation graphed on the Desmos calculator

4. **Clear**
   - Use the "Clear" button to reset the canvas

### Linear Equations

1. **Input Equations**
   - Draw equations on the canvas or type them manually
   - Support for 2-3 simultaneous equations
   - Variables: x, y, z
   - Format: `ax + by + cz = d`

2. **Validation**
   - Real-time validation ensures proper equation format
   - Equations must contain exactly one equals sign
   - Invalid characters are detected automatically

3. **Solve System**
   - Click "Solve" when 2 or more valid equations are entered
   - Solutions for x, y, and z are displayed
   - Visual representation on the 3D graph

## API Endpoints

The application uses the following backend endpoints:

### Polynomial Solver
- **Detection**: `POST /equations/get-polynomial-equation`
- **Solving**: `POST /equations/solve-polynomial-equation`

### Linear Solver
- **Detection**: `POST /equations/get-linear-equation`
- **2D Solving**: `POST /equations/solve-2d-linear-equation`
- **3D Solving**: `POST /equations/solve-3d-linear-equation`

## Development

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for CDN resources and API calls)

### Running Locally

1. Clone the repository:
```bash
git clone https://github.com/saurav77835/hesv-app.git
cd hesv-app
```

2. Serve the files using any local web server:
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js http-server
npx http-server

# Using PHP
php -S localhost:8000
```

3. Open your browser and navigate to:
   - Polynomial solver: `http://localhost:8000/index.html`
   - Linear solver: `http://localhost:8000/linear.html`

## Input Validation

### Polynomial Equations
- Allowed characters: `x`, `X`, `+`, `-`, `.`, `=`, `^`, digits
- Must contain exactly one equals sign
- No repeating special characters

### Linear Equations
- Allowed characters: `x`, `y`, `z`, `X`, `Y`, `Z`, `+`, `-`, `.`, `=`, digits
- Must contain exactly one equals sign
- No repeating special characters
- Each equation must be valid before solving

## Features in Detail

### Drawing Canvas
- Pencil tool for drawing equations
- Eraser tool for corrections
- Responsive canvas that adapts to window size
- Black on white for optimal ML detection

### Equation Detection
- ML-powered handwriting recognition
- Converts drawn equations to text format
- Provides debug logs for transparency

### Real-time Graphing
- Powered by Desmos Graphing Calculator
- Interactive visualization
- Supports 2D and 3D plotting
- Automatic graph updates as equations change

### Error Handling
- Client-side validation
- Server-side error messages
- Warning messages for edge cases
- Clear user feedback

## Browser Compatibility

- Chrome (recommended)
- Firefox
- Safari
- Edge
- Opera

## License

This project is part of a Major Project and is available for educational purposes.

## Acknowledgments

- [DrawerJs](http://camanjs.com/examples/#drawer) - Canvas drawing library
- [Desmos](https://www.desmos.com/) - Graphing calculator API
- [Font Awesome](https://fontawesome.com/) - Icon library
- Backend ML model for equation detection
