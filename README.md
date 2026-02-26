# Snake_nn

## Project Overview
Snake_nn is a Python project that combines a playable Snake game with an evolutionary AI training loop. A population of neural networks controls parallel snakes, receives fitness scores based on survival and food collection, and evolves over generations through selection, crossover, and mutation.

The repository also includes a small custom neural-network library (`lib_nn`) used by the game simulation.

## Features
- Play classic Snake in single-player mode.
- Train a Snake-playing AI using a genetic algorithm.
- Run large-population simulations (default: 2000 agents).
- Persist the best-performing model to `best_nn_data.pkl`.
- Replay the best saved model from the in-game menu.
- Visualize average fitness over generations (periodic Matplotlib plot).

## Architecture / Structure
```text
Snake_nn/
├── SNAKE/
│   ├── Main.py        # Entry point and initial training configuration
│   ├── Menu.py        # Pygame menu: Single Player / Train AI / Best AI
│   ├── Game.py        # Core game loop, simulation, evolution, persistence
│   ├── Snake.py       # Snake movement, collisions, AI input features
│   └── Food.py        # Food entity
├── lib_nn/
│   ├── nn.py          # Neural network class + crossover/mutation utilities
│   └── matrix.py      # Matrix operations used by the NN implementation
└── best_nn_data.pkl   # Saved best model (created/updated during training)
```

## Build & Run Instructions
### 1) Prerequisites
- Python 3.9+
- `pip`

### 2) Install dependencies
From the repository root:

```bash
python3 -m pip install pygame pygame-menu matplotlib
```

### 3) Run the project
Because the code uses local imports from both `SNAKE` and `lib_nn`, launch from the repository root with:

```bash
PYTHONPATH=./SNAKE:. python3 SNAKE/Main.py
```

### 4) Use the menu
- **Single Player**: play manually.
- **Train AI**: start evolutionary training.
- **Best AI**: replay the currently saved best model.

## Testing
This project does not currently include an automated test suite.

For a quick validation pass:
- Start the app and verify the menu loads.
- Run **Single Player** to confirm game controls and collisions.
- Run **Train AI** briefly and confirm generations advance.
- Return to menu (`Esc`) and open **Best AI** to confirm model persistence.

## Project Context
This project is focused on learning and experimentation with:
- Neural-network inference in a game loop
- Evolutionary optimization (selection, crossover, mutation)
- Performance trade-offs in multi-agent simulation
- Model persistence using Python `pickle`

Training quality depends heavily on runtime and hardware. Long training sessions are typically needed before behavior becomes consistently strong.

## Screenshots
<img src="https://files.fm/thumb_show.php?i=m9tj2zqpc" alt="Snake_nn screenshot 1">
<br>
<img src="https://files.fm/thumb_show.php?i=q7aedxfez" alt="Snake_nn screenshot 2">
<br>
<img src="https://files.fm/thumb_show.php?i=pavmpqq56" alt="Snake_nn screenshot 3">
