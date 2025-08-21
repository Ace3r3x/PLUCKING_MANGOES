# Plucking Mangoes 🥭

A physics-based slingshot game where you help a boy collect mangoes by launching stones at a mango tree. Built with p5.js and Matter.js for realistic projectile physics and collision detection.

## Features ✨

- **Slingshot Mechanics**: Drag and release stone with mouse for realistic launching
- **12 Target Mangoes**: Multiple mangoes positioned throughout the tree at different heights
- **Physics Simulation**: Realistic stone trajectory and mango falling with gravity
- **Collision Detection**: Accurate hit detection between stone and mangoes
- **Reset Functionality**: Space bar resets stone position for multiple attempts
- **Interactive Gameplay**: Intuitive mouse controls for aiming and shooting

## Tech Stack 🛠️

- **p5.js** - Creative coding library for graphics and animation
- **p5.play.js** - Sprite management and collision detection
- **Matter.js** - 2D physics engine for realistic projectile motion
- **HTML5 Canvas** - Game rendering and mouse interaction
- **JavaScript ES6** - Game logic and physics simulation

## Gameplay 🎮

### Objective
Help the boy collect mangoes by using the slingshot to knock them down from the tree. Aim carefully and use physics to your advantage!

### How to Play
1. **Aim**: Position your mouse near the stone
2. **Drag**: Click and drag to pull back the slingshot
3. **Release**: Let go to launch the stone at the mangoes
4. **Reset**: Press SPACE bar to reset stone position for another shot
5. **Collect**: Watch mangoes fall when hit by the stone

### Strategy Tips
- Aim for mangoes at different heights to maximize collection
- Use the stone's arc trajectory to reach higher mangoes
- Reset and try different angles for hard-to-reach mangoes

## Controls 🕹️

- **Mouse Drag**: Aim and launch the stone
- **Mouse Release**: Fire the slingshot
- **SPACE BAR**: Reset stone position for next shot

## Project Structure 📁

\`\`\`
PLUCKING_MANGOES/
├── MatterJSBoilerPlate-master/
│   ├── sketch.js              # Main game logic and physics setup
│   ├── stone.js              # Slingshot stone class with physics
│   ├── mango.js              # Mango objects with collision detection
│   ├── tree.js               # Tree structure and positioning
│   ├── ground.js             # Ground physics body
│   ├── launcher.js           # Slingshot mechanism
│   ├── index.html            # HTML entry point
│   ├── boy.png               # Boy character sprite
│   ├── tree.png              # Mango tree background
│   ├── mango.png             # Individual mango sprites
│   ├── p5.js                 # p5.js core library
│   ├── p5.play.js           # p5.play physics objects
│   ├── matter.js            # Matter.js physics engine
│   └── style.css            # Game styling
└── README.md                # This file
\`\`\`

## Installation & Setup 🚀

### Prerequisites
- Modern web browser with HTML5 Canvas support
- Local web server (recommended for asset loading)

### Quick Start

1. **Clone the repository**
   \`\`\`bash
   git clone https://github.com/Ace3r3x/PLUCKING_MANGOES.git
   cd PLUCKING_MANGOES
   \`\`\`

2. **Run locally**
   \`\`\`bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js (if you have http-server installed)
   npx http-server
   
   # Navigate to MatterJSBoilerPlate-master folder
   cd MatterJSBoilerPlate-master
   \`\`\`

3. **Play the game**
   - Navigate to `http://localhost:8000/MatterJSBoilerPlate-master/`
   - Use mouse to aim and shoot stones at mangoes
   - Press SPACE to reset for multiple attempts

## Code Structure 🏗️

### Main Components

**Game Classes**:
- `Stone`: Slingshot projectile with physics body and launch mechanics
- `Mango`: Target objects with collision detection and falling physics
- `Tree`: Static background structure for mango positioning
- `Ground`: Physics boundary for stone and mango interactions
- `Launcher`: Slingshot mechanism for stone launching

### Physics Implementation

**Stone Physics**:
\`\`\`javascript
// Realistic projectile with proper mass and restitution
this.body = Bodies.circle(x, y, radius, {
    restitution: 0.8,    // Bouncy stone
    friction: 0.5,       // Ground friction
    density: 1.2         // Stone weight
});
\`\`\`

**Collision Detection**:
\`\`\`javascript
// Detect stone hitting mangoes
if (stone.body.position.x > mango.body.position.x - 50 && 
    stone.body.position.x < mango.body.position.x + 50) {
    // Mango falls when hit
    mango.body.isStatic = false;
}
\`\`\`

**Slingshot Mechanics**:
\`\`\`javascript
// Mouse drag for aiming and power
if (mouseIsPressed) {
    let force = {
        x: (mouseX - stone.body.position.x) * 0.005,
        y: (mouseY - stone.body.position.y) * 0.005
    };
    Matter.Body.applyForce(stone.body, stone.body.position, force);
}
\`\`\`

## Game Features 🎯

### Physics Simulation
- **Realistic Trajectory**: Stone follows proper parabolic arc
- **Gravity Effects**: Both stone and mangoes affected by gravity
- **Collision Response**: Mangoes fall naturally when struck
- **Bounce Physics**: Stone bounces off ground and obstacles

### Visual Elements
- **Character Sprite**: Boy character with slingshot
- **Tree Background**: Detailed mango tree with branches
- **Mango Sprites**: Individual mango graphics positioned on tree
- **Smooth Animation**: 60 FPS rendering for fluid gameplay

### Interactive Features
- **Mouse Controls**: Intuitive drag-and-release mechanics
- **Reset System**: Space bar for multiple attempts
- **Visual Feedback**: Clear indication of stone trajectory
- **Collision Effects**: Mangoes respond to stone impacts

## Educational Value 📚

### Physics Concepts
- **Projectile Motion**: Parabolic trajectory under gravity
- **Force and Acceleration**: Mouse drag translates to launch force
- **Collision Physics**: Momentum transfer between objects
- **Energy Conservation**: Kinetic and potential energy in motion

### Learning Outcomes
- Understanding of trajectory physics
- Hand-eye coordination development
- Strategic thinking and problem solving
- Interactive physics experimentation

## Future Enhancements 🔮

- **Scoring System**: Points for mangoes collected
- **Win Conditions**: Complete level objectives
- **Sound Effects**: Audio feedback for hits and collections
- **Multiple Levels**: Different tree layouts and challenges
- **Power-ups**: Special stones with different properties
- **Mango Counter**: Track collected vs remaining mangoes
- **Time Challenges**: Speed-based gameplay modes
- **Difficulty Levels**: Varying mango positions and stone physics

## Known Issues 🔧

- Missing mango5 display call in draw function
- No scoring or win condition implementation
- Basic visual styling could be enhanced
- No sound effects or audio feedback
- Limited to single stone type

## Educational Use 🎓

Perfect for:
- **Physics Education**: Demonstrating projectile motion
- **Game Development Learning**: Physics-based game mechanics
- **Interactive Learning**: Hands-on physics experimentation
- **Coding Workshops**: p5.js and Matter.js integration

## Contributing 🤝

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/game-enhancement`)
3. Commit your changes (`git commit -m 'Add game feature'`)
4. Push to the branch (`git push origin feature/game-enhancement`)
5. Open a Pull Request

## Repository Information 📋

- **Repository**: [Ace3r3x/PLUCKING_MANGOES](https://github.com/Ace3r3x/PLUCKING_MANGOES)
- **Created**: October 19, 2020
- **Language**: 100% JavaScript
- **Type**: Physics-Based Game

## License 📄

This project is open source and available under the MIT License.

---

**Aim, Shoot, Collect! 🥭🎯**
