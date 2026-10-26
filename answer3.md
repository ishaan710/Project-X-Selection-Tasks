# Problem 3 - Simulation vs Practical Development

## My choice

I would use both: simulate first, then build a prototype, then improve the design using both results. We have limited time and money. Only simulation is risky because the real plane can behave differently. Only building is costly because every crash costs money. So simulation removes bad ideas cheaply, and the prototype checks what the computer does not know.

## Comparison

| | Simulation-led | Prototype-led |
|---|---|---|
| Cost | very low once the software is ready (XFLR5 and OpenVSP are free) | higher, because foam, motor, battery and servos cost money and crashes add to it |
| Time | fast, results in minutes | slow, because of building and flying |
| Accuracy | depends on the model and the inputs; wrong inputs give wrong answers | real physics, so most true |
| Iteration speed | very fast, change a number and run again | slow, must rebuild |
| Failure detection | finds design mistakes like bad balance or low lift, but not build problems | finds real problems like weak joints, vibration, radio trouble |
| Performance | estimated | measured |

## Workflow

1. Write requirements: payload, wingspan, flight time, budget.
2. Do rough sizing by hand: weight, wing area, wing loading, thrust needed.
3. Choose the airfoil using XFLR5 polars.
4. Simulate the whole aircraft and check lift, drag, static margin and trim.
5. Choose motor, propeller and battery using a calculator like eCalc and check thrust against drag.
6. Build a cheap foam prototype.
7. Ground tests: weigh it, find the CG, check control directions, measure motor thrust and current.
8. Flight tests: short flights first, and record the results.
9. Compare real results with the simulation.
10. Fix the model and the design, and repeat from step 4.
11. Build the final version and test it.

## Three things to simulate

1. Airfoil and wing lift and drag (CL, CD, stall angle), because many airfoils can be compared for free.
2. Static margin and CG position, because it is safer to find a bad CG on the computer than by crashing.
3. Thrust needed versus thrust available, so I know if the motor and battery are enough before buying them.

## Three things to check physically

1. Real weight and real CG, because glue, wires and paint add weight that the model forgets.
2. Motor, ESC and battery behaviour: actual current, temperature, thrust and flight time.
3. Control and structure: servo play, control surface movement, wing strength, vibration and radio range.

## Validation

I compare the simulation with real tests: stall speed, takeoff distance, glide angle and battery use. If the difference is small (say below 10 to 15 percent) the model is good enough. If it is big, I look for the reason (wrong weight, wrong drag, wrong airfoil data) and fix the model. I can also test the software on a known plane first, like a ready trainer kit, to see if it gives believable results.

## Plane that cannot take off in simulation

I would check these in order:
- Thrust is less than drag at low speed. Fix: bigger motor or propeller, or less weight.
- Weight is too high or wing area too small (wing loading too high). Fix: reduce weight or increase area.
- Not enough lift at takeoff speed (low CLmax or wrong wing incidence). Fix: better airfoil, flaps, more incidence.
- CG too far forward so the plane cannot rotate. Fix: move the battery back.
- Elevator too small or its direction is reversed. Fix: bigger elevator or correct the sign.
- Wrong units or inputs (cm and m, g and kg). Fix: check all inputs.
- Propeller does not match the motor. Fix: match them.

A good first step is to plot thrust and drag against speed. If thrust is below drag at all speeds, the plane can never reach takeoff speed.

## Bonus: four-week plan

| Week | Work | Backup |
|---|---|---|
| 1 | Requirements, sizing, airfoil study, XFLR5 model, order parts | If parts are late, build the airframe first with spare parts |
| 2 | Finish simulation, build prototype, install electronics | If simulation fails, use hand calculations and a proven design |
| 3 | Ground tests, first flights, collect data | If it crashes, use spare foam and parts (keep 20% extra budget) |
| 4 | Fix problems, compare simulation with tests, write report | Keep 2 days free at the end for repairs and documentation |

Other backups: carry a spare propeller and battery, keep weather in mind for test days, and give each task to one person.
