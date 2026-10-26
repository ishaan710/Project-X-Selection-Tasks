# Problem 1 - Airfoil Selection

(Values are approximate for small RC wings at Re around 200,000 to 300,000. I will update them with my XFLR5 results.)

## Aircraft A (maximum payload, stable)

For a heavy plane I need a lot of lift at low speed, a soft stall, and easy balance.

Airfoils I looked at:

| | Clark Y | NACA 4412 | Selig S1223 |
|---|---|---|---|
| Thickness | about 11.7% | 12% | about 12% |
| Camber | about 3.5% (flat bottom) | 4% | about 8.7% |
| CLmax | about 1.3 to 1.5 | about 1.4 to 1.6 | 2.0 or more |
| Drag | low to medium | low to medium | high |
| L/D | good | good | medium |
| Stall | soft | fairly soft | can be sudden |
| Nose-down moment | small | medium | very large |
| Building | very easy | easy | hard |

I selected Clark Y. It gives enough lift and has low drag. The stall is gentle, which is good for a slow, heavy plane. Its pitching moment is small, so the tail does not have to work too hard. The flat bottom is also easy to build.

S1223 gives the most lift, but the drag is high and the nose-down moment is very large. So I would need a bigger tail, and that adds weight.

## Aircraft B (maneuverability)

For tricks like rolls and loops I need a wing that behaves the same upright and inverted.

| | NACA 0009 | NACA 0012 | NACA 2412 |
|---|---|---|---|
| Thickness | 9% | 12% | 12% |
| Camber | 0% | 0% | 2% |
| CLmax | about 1.0 to 1.2 | about 1.1 to 1.3 | about 1.4 |
| Drag | lowest | low | low |
| Zero lift angle | 0 deg | 0 deg | about -2 deg |
| Stall | sharp | medium | gentle |
| Inverted flight | same as upright | same as upright | worse |

I selected NACA 0012. It is symmetric, so inverted flight feels the same as normal flight. It gives zero lift at zero angle, so the response is easy to predict. It is thick enough to be strong and to fit a spar, but the drag is still low. NACA 0009 has less drag but it is weaker and stalls more suddenly.

## Comparing the two selected airfoils

| | Clark Y (A) | NACA 0012 (B) |
|---|---|---|
| Camber | about 3.5% | 0% |
| Thickness | 11.7% | 12% |
| CLmax | higher | lower |
| Best L/D | higher | lower |
| Stall | gentle | medium |
| Suited for | slow, heavy flight | aerobatics |

## Can one airfoil do both jobs?

Partly. A semi-symmetric airfoil like NACA 2412 can do light aerobatics and carry some load. But it gives less lift than Clark Y and works worse upside down than NACA 0012. So it is a compromise. If the two missions are very different, two different airfoils are better. One airfoil is fine if we want a simple and cheap design.

## Airfoil traits and whole-aircraft factors

Airfoil traits: camber, thickness, CLmax, stall behaviour, Cd, pitching moment, zero-lift angle.

Whole-aircraft factors: wing area and wing loading, aspect ratio, tail size and tail arm, CG position, motor power and propeller, control surface size, total weight.

Example: Aircraft B can have a good airfoil, but if the CG is too far back it will still be unstable. Aircraft A can have a good airfoil, but if the wing area is too small it cannot lift the payload.

## Bonus: XFLR5

Steps I will follow:
1. Load the airfoil .dat files in XFLR5.
2. Run XFoil direct analysis at Re = 200,000 and 300,000, angles -5 to 15 degrees.
3. Save plots of CL vs alpha, CD vs alpha, drag polar, and CL/CD vs alpha.

Plots go in the `plots` folder (to be added after I run it).
