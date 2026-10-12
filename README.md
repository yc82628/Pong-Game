# Pong-Game

My first ever coding project: the classic two-player Pong, written in Python with the built-in
[`turtle`](https://docs.python.org/3/library/turtle.html) graphics module.

**▶ Play it in your browser:** [yc82628.github.io/pong.html](https://yc82628.github.io/pong.html)
(a JavaScript port with the same rules, plus a computer opponent so you can play alone)

## Run it

You only need Python 3. `turtle` comes with the standard Python installer, so there is nothing to `pip install`.

```bash
python main.py
```

On some Linux distributions Tkinter is a separate package (for example `sudo apt install python3-tk`).

## Controls

| Player | Up | Down |
|---|---|---|
| Player A (left) | `W` | `S` |
| Player B (right) | `↑` | `↓` |

Close the window to quit.

## How it works

Everything runs in one `while True` game loop in `main.py`:

- **Movement:** every frame the ball moves by `dx` and `dy` (2 units each).
- **Walls:** when the ball reaches the top or bottom edge (y = ±290), `dy` flips and it bounces.
- **Scoring:** if the ball passes a paddle (x = ±390), the other player gets a point and the ball
  restarts in the middle, heading the other way.
- **Paddles:** when the ball reaches a paddle's x position and is within 40 units of its centre,
  `dx` flips and it bounces back. Each key press moves a paddle 20 units.

## What I'd do differently now

Looking back at my first project:

- **Speed depends on the computer.** The loop runs as fast as the machine allows, so the ball is faster
  on a faster computer. I'd tie movement to elapsed time instead.
- **Paddles can leave the screen.** Nothing stops them at the top or bottom edge.
- **Same serve every time.** The ball always restarts at the same angle; a random angle would keep rallies interesting.
- **Repeated code.** Paddle A and B are copy-pasted; one `Paddle` class used twice would be cleaner.

More about the project on my portfolio: [yc82628.github.io/pong.html](https://yc82628.github.io/pong.html)
