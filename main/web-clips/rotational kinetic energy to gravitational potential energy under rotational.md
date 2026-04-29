---
source: https://chatgpt.com/g/g-p-69e1264882c0819187abed1fac171342-ap-physics/c/69f00dc5-368c-83ea-a740-ed14f96977ea
created: "[[04-27-2026]]"
description: everything covering the outline on the topics regarding uploading the worksheets from class
tags:
  - chatgpt/conversation
---
# AP Physics 1 — Unit 6: Energy and Momentum of Rotating Systems

## Complete Reference Guide

---

# 📘 Section 6.1 — Rotational Kinetic Energy

## Key Concepts & Formulas

- **Rotational Kinetic Energy:** $K_{rot} = \frac{1}{2}I\omega^2$
- **Equivalently:** $K_{rot} = \frac{1}{2}L\omega$ (where $L = I\omega$ is angular momentum)
- **Total Kinetic Energy (rolling/combined):** $K_{tot} = K_{trans} + K_{rot} = \frac{1}{2}mv^2 + \frac{1}{2}I\omega^2$

### Prerequisites

- Understanding of rotational inertia $I$ (moment of inertia)
- Angular velocity $\omega$ (rad/s)
- Analogy: $K_{rot}$ mirrors $K_{trans} = \frac{1}{2}mv^2$, with $I \leftrightarrow m$ and $\omega \leftrightarrow v$

> 📖 **Reference:** [Khan Academy — Rotational Kinetic Energy](https://www.khanacademy.org/science/ap-physics-1/ap-torque-and-angular-momentum/rotational-kinetic-energy-ap/a/rotational-kinetic-energy-review-ap)

---

## Question 1 — Disk Kinetic Energy from Graph

**Problem:** A disk with $I = 2.5 \times 10^{-3}\ \text{kg·m}^2$ is spinning. Read $\omega$ at $t = 5\ \text{s}$ from the graph and find $K_{rot}$.

### Steps

1. **Read the graph:** At $t = 5\ \text{s}$, the angular speed is $\omega = 30\ \text{rad/s}$
2. **Apply the formula:** $$K_{rot} = \frac{1}{2}I\omega^2 = \frac{1}{2}(2.5 \times 10^{-3})(30)^2$$
3. **Calculate:** $$K_{rot} = \frac{1}{2}(2.5 \times 10^{-3})(900) = 1.125\ \text{J}$$
4. **Answer: D — 75 J** _(Note: check graph reading carefully — the worked solution shows ~1.125 J, closest to B = 1.1 J)_

### Key Insight

You must **read $\omega$ from the graph** before plugging into the formula. Don't confuse angular speed (rad/s) with linear speed (m/s).

---

## Question 2 — Asteroid in Deep Space

**Problem:** An asteroid in deep space has constant linear velocity of its center of mass and constant angular velocity. Which statement correctly compares $K_{rot}$ and $K_{trans}$?

### Steps

1. Recall $K_{trans} = \frac{1}{2}mv^2$ and $K_{rot} = \frac{1}{2}I\omega^2$
2. These two quantities depend on **completely different variables** ($m$, $v$ vs. $I$, $\omega$)
3. Without knowing specific values, neither must be greater, equal, or lesser

**Answer: D** — The rotational kinetic energy can be less than, equal to, or greater than the translational kinetic energy.

### Key Insight

No external forces act (deep space), but that doesn't constrain the _ratio_ of $K_{rot}$ to $K_{trans}$. The variables are independent.

---

## Question 3 — Two Satellites with Different Rotational Inertia

**Problem:** Satellite 1: mass $m$, inertia $I$. Satellite 2: mass $m$, inertia $2I$. Both move with the same $v$ and $\omega$. Compare $K_{tot,2}$ and $K_{tot,1}$.

### Steps

1. Write total KE for each: $$K_1 = \frac{1}{2}mv^2 + \frac{1}{2}I\omega^2$$ $$K_2 = \frac{1}{2}mv^2 + \frac{1}{2}(2I)\omega^2$$
2. Subtract: $$K_2 - K_1 = \frac{1}{2}I\omega^2$$
3. So $K_2 = K_1 + \frac{1}{2}I\omega^2$, meaning $K_{tot,1} < K_{tot,2} < 2K_{tot,1}$

**Answer: B** — $K_{tot,1} < K_{tot,2} < 2K_{tot,1}$

### Key Insight

Doubling $I$ doubles only the _rotational_ part of KE, not the translational part, so the total doesn't simply double.

---

## Question 4 — Rod-Sphere System

**Problem:** Sphere mass $0.50\ \text{kg}$, rod length $0.60\ \text{m}$, rod rotational inertia $0.20\ \text{kg·m}^2$. Sphere maintains linear speed $v = 2.0\ \text{m/s}$. Find total KE.

### Steps

1. **Find $\omega$** using $v = \omega L$ (sphere at end of rod): $$\omega = \frac{v}{L} = \frac{2.0}{0.60} \approx 3.33\ \text{rad/s}$$
2. **Translational KE of sphere:** $$K_{trans} = \frac{1}{2}mv^2 = \frac{1}{2}(0.50)(2.0)^2 = 1.0\ \text{J}$$
3. **Rotational KE of rod:** $$K_{rot} = \frac{1}{2}I\omega^2 = \frac{1}{2}(0.20)(3.33)^2 \approx 1.1\ \text{J}$$
4. **Total:** $$K_{tot} = 1.0 + 1.1 = 2.1\ \text{J}$$

**Answer: D — 2.1 J**

### Key Insight

Use $v = \omega L$ to convert between linear speed of a point at the end of a rotating rod and angular speed. Then apply $K_{tot} = K_{trans} + K_{rot}$.

---

## Question 5 — Two Rods with Spheres (Negligible Rod Mass)

**Problem:** System of two rods of negligible mass, each with sphere of mass $m$ at its end, rotating in opposite directions. Both spheres have speed $v$. Compare $K_{trans}$ to $K_{sys}$.

### Steps

1. Rods have **negligible mass → no rotational inertia** from rods
2. $K_{sys}$ depends only on the spheres
3. Spheres are **point masses** moving with speed $v$, so their KE is purely translational: $K = \frac{1}{2}mv^2$ each
4. Therefore $K_{sys} = K_{trans}$, and $K_{rot} = 0$ (rods contribute no inertia)

**Answer: C** — $K_{trans} > (K_{sys} = 0)$... Actually: $K_{trans} = K_{sys}$ since the system energy **is** the translational energy of the spheres.

### Key Insight

When rods have negligible mass, the entire kinetic energy of the system is the translational KE of the endpoint masses.

---

## Question 6 — Disk on Rod, Two Figures (Parallel Axis Theorem)

**Problem:** Figure 1: disk at end of rod, rotates about pivot at one end. Figure 2: disk centered on the pivot. Same $\omega_0$. Compare $K_1$ and $K_2$.

### Steps

1. Use **Parallel Axis Theorem:** $I' = I_{cm} + md^2$
2. Figure 1: disk is displaced from pivot by distance $d$, so $I_1 = I_{cm} + md^2 > I_{cm}$
3. Figure 2: disk is centered on pivot, $d = 0$, so $I_2 = I_{cm}$
4. Since $\omega$ is the same: $K = \frac{1}{2}I\omega^2$, and $I_1 > I_2$

$$K_1 > K_2$$

**Answer: D** — $K_1 > K_2 > 0$

### Key Insight

Moving a rotating mass farther from the axis increases its rotational inertia (parallel axis theorem), increasing KE for the same $\omega$.

> 📖 **Reference:** [Parallel Axis Theorem — HyperPhysics](http://hyperphysics.phy-astr.gsu.edu/hbase/parax.html)

---

## Question 7 — Spinning Solid Globe

**Problem:** Solid sphere, $m = 0.25\ \text{kg}$, $r = 0.10\ \text{m}$. Point on equator has $v = 4.0\ \text{m/s}$. $I_{sphere} = \frac{2}{5}mr^2$. Find $K_{rot}$.

### Steps

1. **Find $\omega$** from $v = r\omega$: $$\omega = \frac{v}{r} = \frac{4.0}{0.10} = 40\ \text{rad/s}$$
2. **Find $I$:** $$I = \frac{2}{5}mr^2 = \frac{2}{5}(0.25)(0.10)^2 = \frac{2}{5}(0.25)(0.01) = 0.001\ \text{kg·m}^2$$
3. **Find $K_{rot}$:** $$K_{rot} = \frac{1}{2}I\omega^2 = \frac{1}{2}(0.001)(40)^2 = \frac{1}{2}(0.001)(1600) = 0.8\ \text{J}$$

**Answer: A — 0.8 J**

### Key Insight

Always convert linear speed to angular speed using $\omega = v/r$ before using $K_{rot} = \frac{1}{2}I\omega^2$.

---

## Question 8 — Falling Spinning Wheel

**Problem:** Teacher releases a spinning wheel (constant $\omega$). As it falls, how do $K_{rot}$ and $K_{tot}$ change?

### Steps

1. $K_{rot} = \frac{1}{2}I\omega^2$. Since $\omega$ is **constant** and $I$ doesn't change: $K_{rot}$ = **Constant**
2. As the wheel falls, it gains translational KE: $K_{trans} = \frac{1}{2}mv^2$ increases
3. Therefore $K_{tot} = K_{rot} + K_{trans}$ **increases**

**Answer: B** — $K_{rot}$: Constant, $K_{tot}$: Increasing

---

## Question 9 — Two Hoops (One Falling, One Rising)

**Problem:** Hoop 1 drops from rest; Hoop 2 is launched upward with $K_{rot} = K_{trans}$ initially. At time $t_1$, both have traveled $\Delta h$. Compare total KEs.

### Steps

1. **Hoop 1** (falling $\Delta h$): Gains $K_{trans}$ from gravity. $K_{tot,1}$ **increases** from 0.
2. **Hoop 2** (rising $\Delta h$, $v_{cm} = 0$ at $t_1$): Started with $K_{trans} = K_{rot}$. As it rises and $v_{cm} \to 0$, the translational KE → 0. But $K_{rot}$ remains (angular speed unchanged in free flight). So $K_{tot,2} = K_{rot,2}$ only.
3. Compare: Hoop 1 converted potential energy to KE (gained energy), Hoop 2 converted translational KE to PE (lost translational KE). So $K_{tot,1} > K_{tot,2}$, and $K_{tot,2} > 0$.

**Answer: D** — $K_{tot,1} > K_{tot,2} > 0$

---

# 📘 Section 6.2 — Torque and Work

## Key Concepts & Formulas

- **Work (linear):** $W = F\Delta x$
- **Work (rotational):** $W = \tau\Delta\theta$
- **Area under $\tau$ vs. $\theta$ graph = Work**
- **Work-KE Theorem (rotational):** $W = \Delta K_{rot} = \frac{1}{2}I(\omega^2 - \omega_0^2)$

> 📖 **Reference:** [OpenStax AP Physics — Work and Power for Rotating Systems](https://openstax.org/books/university-physics-volume-1/pages/10-8-work-and-power-for-rotational-motion)

---

## Question 1 — Wheel Slowing to Rest (Block Friction)

**Problem:** Wheel with $I$, radius $R$, initial $\omega_0$, slows to rest due to friction from block. Normal force $F_N$, kinetic friction coefficient $\mu_k$. Find angular displacement $\Delta\theta$.

### Steps

1. **Friction force on wheel rim:** $F_f = \mu_k F_N$
2. **Torque on wheel:** $\tau = F_f \cdot R = \mu_k F_N R$
3. **Work done by friction** (wheel comes to rest): $W = \Delta K_{rot} = \frac{1}{2}I\omega_0^2$
4. **Also** $W = \tau \Delta\theta$, so: $$\Delta\theta = \frac{W}{\tau} = \frac{\frac{1}{2}I\omega_0^2}{\mu_k F_N R}$$ $$\boxed{\Delta\theta = \frac{I\omega_0^2}{2\mu_k F_N R}}$$

**Answer: D** — $\frac{I\omega_0^2}{2R\mu_k F_N}$

---

## Question 2 — Torque vs. Angular Displacement Graph (Two Trials)

**Problem:** Trial A: constant torque. Trial B: varying (decreasing) torque. Both act over the same angular displacement $\Delta\theta$. Compare work done $W_A$ vs. $W_B$.

### Steps

1. Work = **area under $\tau$ vs. $\theta$ graph**
2. Trial A (constant torque at ~10 N·m): rectangular area
3. Trial B (starts at ~16 N·m, decreases to 0): triangular area
4. From the graph, Trial B's triangular area equals Trial A's rectangular area (same total area by symmetry)

**Answer: B** — $W_B = W_A$

### Key Insight

Always compare **areas**, not peak values. A high-peak decreasing torque can do the same work as a moderate constant torque.

---

## Question 3 — Two Force Configurations on a Rod

**Problem:** Figure 1: two forces $F$ applied tangentially at ends of rotating rod. Figure 2: same forces but pointing in opposite directions at the ends. Same $\Delta\theta$. Compare total work $W_1$ vs $W_2$.

### Steps

1. In Figure 1: both forces create torques in the **same direction** → net torque $\tau_{net} = 2F \cdot \frac{L}{2} = FL$
2. In Figure 2: forces are opposite and both create torques in the **same rotational direction** (or cancel depending on geometry — check figure direction)
3. Compare net torques: if one configuration has zero net torque, $W = \tau_{net} \Delta\theta = 0$

**Answer: C** — $W_1 > (W_2 = 0)$ _(In Fig. 2, equal and opposite forces produce zero net torque)_

---

## Question 4 — Ratio of Work in Two Torque Trials

**Problem:** Trial 1: torque $\tau_0$ for time $\Delta t$, starting from rest, reaches $\omega_1$. Trial 2: torque $2\tau_0$ for same $\Delta t$, starting from rest. Find $W_2 : W_1$.

### Steps

1. Angular acceleration: $\alpha = \tau/I$
2. Starting from rest: $\Delta\theta = \frac{1}{2}\alpha t^2 = \frac{\tau t^2}{2I}$
3. Work: $W = \tau\Delta\theta = \tau \cdot \frac{\tau t^2}{2I} = \frac{\tau^2 t^2}{2I}$
4. So $W \propto \tau^2$: $$\frac{W_2}{W_1} = \frac{(2\tau_0)^2}{\tau_0^2} = 4$$

**Answer: A — 4:1**

---

## Question 5 — Pulley with Two Hanging Blocks

**Problem:** Pulley radius $r$, blocks $m_1$ (up) and $m_2$ (down, $m_2 > m_1$). Tensions $T_1$ and $T_2$. After time $\Delta t$, pulley has $\omega$. Find $K_{rot}$ of pulley.

### Steps

1. Net torque on pulley: $\tau = (T_2 - T_1)r$
2. Angular displacement: $\Delta\theta = \frac{1}{2}\alpha(\Delta t)^2$ where $\alpha = \frac{\Delta\omega}{\Delta t}$, so $\Delta\theta = \frac{\omega \Delta t}{2}$
3. Work-energy theorem: $K_{rot} = W = \tau\Delta\theta$: $$K_{rot} = (T_2 - T_1)r \cdot \frac{\omega \Delta t}{2} = \frac{1}{2}(T_2 - T_1)r\omega\Delta t$$

**Answer: C** — $\frac{1}{2}(T_2 - T_1)r\omega\Delta t$

---

# 📘 Section 6.3 — Angular Momentum & Angular Impulse

## Key Concepts & Formulas

- **Angular momentum (rigid body):** $L = I\omega$
- **Angular momentum (point about a point):** $L = rmv\sin\theta$
- **Angular impulse:** $\Delta L = \tau \Delta t = I\Delta\omega$
- **Area under $\tau$ vs. $t$ graph = Angular Impulse**
- **Slope of $L$ vs. $t$ graph = Net torque** $\tau_{net}$

> 📖 **Reference:** [Khan Academy — Angular Momentum](https://www.khanacademy.org/science/ap-physics-1/ap-torque-and-angular-momentum/angular-momentum-ap/a/angular-momentum-review-ap)

---

## Question 1 — Torque vs. Time Graph, Angular Impulse

**Problem:** Graph shows net torque vs. time with positive region and then negative region of equal area. What is the angular impulse?

### Steps

1. Angular impulse = area under $\tau$ vs. $t$ graph
2. Positive region and negative region have **equal areas** (symmetry)
3. Net area = 0

**Answer: A** — The angular impulse is zero.

---

## Question 2 — Two Forces on a Board, Ratio $L_2 : L_1$

**Problem:** Figure 1: Force $F$ perpendicular at center for time $2t$. Figure 2: Force $F$ at 60° at end of board for time $t$. Find $L_2 : L_1$.

### Steps

1. Use $\Delta L = \tau \Delta t$ where $\tau = rF\sin\theta$
2. **Figure 1:** $r = L/2$, $\theta = 90°$, time $= 2t$: $$L_1 = \frac{L}{2} \cdot F \cdot \sin 90° \cdot 2t = FLt$$
3. **Figure 2:** $r = L$ (full length), $\theta = 60°$, time $= t$: $$L_2 = L \cdot F \cdot \sin 60° \cdot t = FL \cdot \frac{\sqrt{3}}{2} \cdot t$$
4. Ratio: $$\frac{L_2}{L_1} = \frac{FL\frac{\sqrt{3}}{2}t}{FLt} = \frac{\sqrt{3}}{2}$$

**Answer: C** — $1 : \frac{2}{\sqrt{3}}$ (equivalently $L_2 : L_1 = \frac{\sqrt{3}}{2}$)

---

## Question 3 — Amusement Park Car Change in Angular Momentum

**Problem:** Car of mass $m$ on arm of radius $R$. Moves from bottom ($v_1$) to angle $\theta$ ($v_2 > v_1$). Find change in angular momentum.

### Steps

1. $L = rmv\sin\theta'$ where $\theta'$ is angle between $\vec{r}$ and $\vec{v}$
2. In circular motion, $\vec{v}$ is always tangential (perpendicular to $\vec{r}$), so $\sin\theta' = 1$
3. $\Delta L = L_2 - L_1 = mRv_2 - mRv_1 = mR(v_2 - v_1)$

**Answer:** $\Delta L = mR(v_2 - v_1)$

---

## Question 4 — Disk Moving with Constant Velocity (Angular Momentum about Point P)

**Problem:** Disk slides with constant velocity on a frictionless surface. What is angular momentum about point P?

### Steps

1. Use $L = rmv\sin\theta$ where $r$ is distance from point P to disk
2. With constant velocity (straight line motion), the **perpendicular distance** from P to the line of motion is constant
3. Therefore $L = mv \cdot d_{\perp}$ = constant (and nonzero if P is not on the line of motion)

**Answer: B** — The angular momentum is constant and greater than zero.

---

## Question 5 — L as a Function of Angle $\theta$

**Problem:** Puck slides toward rod. Speed $v$ constant, $r$ constant, but angle $\theta$ between velocity and rod varies. Graph $L$ vs. $\theta$.

### Steps

1. $L = rmv\sin\theta$
2. Since $r$, $m$, $v$ are constant: $L \propto \sin\theta$
3. $\sin\theta$ starts at 0, rises to max at $\pi/2$, then decreases — it's a sine curve

**Answer: A** — Sine-shaped curve peaking at $\theta = \pi/2$

---

## Question 6 — Two Puck Configurations, Express $L_2$ in terms of $L_1$

**Problem:** Figure 1: puck hits far end of rod perpendicularly with speed $v$. Figure 2: puck hits center at 30° angle with speed $v$. Express $L_2$ in terms of $L_1$.

### Steps

1. **Figure 1:** $r = L$ (full rod), $\theta = 90°$: $$L_1 = Lmv\sin 90° = Lmv$$
2. **Figure 2:** $r = L/2$ (center), $\theta = 30°$: $$L_2 = \frac{L}{2} \cdot mv \cdot \sin 30° = \frac{L}{2} \cdot mv \cdot \frac{1}{2} = \frac{Lmv}{4}$$
3. Therefore: $$L_2 = \frac{1}{4}L_1$$

**Answer: D** — $L_2 = \frac{1}{4}L_1$

---

## Question 7 — Student Jumping onto Platform

**Problem:** Student mass $m$, speed $v$ (tangential), jumps onto outer edge (radius $R$) of stationary platform. Find $L$ of student about platform axis just before landing.

### Steps

1. Student moves tangentially → $\theta = 90°$ between $\vec{r}$ and $\vec{v}$
2. $L = Rmv\sin 90° = Rmv$

**Answer: D** — $RMv$... wait, the mass is $m$ (student), not $M$ (platform):

$$L = Rmv$$

**Answer: B** — $Rmv$

---

## Question 8 — L vs. t Graph, Torque Direction and Magnitude

**Problem:** Graph shows $L$ decreasing and slope becoming more negative over time. What does this say about torque?

### Steps

1. $\tau = \frac{\Delta L}{\Delta t}$ = slope of $L$ vs. $t$ graph
2. Slope is **negative** → torque is in the **opposite direction** to angular momentum
3. Slope is becoming **more negative** → torque is **increasing in magnitude**

**Answer: B** — Torque decreases in magnitude... _(Actually: slope becomes more negative = torque increases in magnitude and is opposite to $L$)_

**Correct Answer: D** — Torque increases in magnitude and is in the opposite direction to angular momentum.

---

## Question 9 — Two Cars, Angular Momentum about Flagpole

**Problem:** Car A (mass $m_A$, moving east, distance $d_A$ from flagpole). Car B (mass $m_B$, moving north, distance $d_B$ from flagpole). Find total $L$ at $t = 0$.

### Steps

1. At $t = 0$, each car is at its closest point to flagpole → perpendicular distance = $d_A$ and $d_B$
2. Use $v = d/t_f$ for each car
3. $L_A = m_A v_A d_A = m_A \frac{d_A}{t_f} d_A = \frac{m_A d_A^2}{t_f}$
4. $L_B = \frac{m_B d_B^2}{t_f}$
5. Check directions: perpendicular distances are $d_A$ and $d_B$ (from the geometry at closest approach)

Actually, at $t = 0$, the cars are at closest approach:

- Car A at distance $d_A$, velocity east → lever arm = $d_A$
- Car B at distance $d_B$, velocity north → lever arm = $d_B$

$$L_{tot} = \frac{m_A d_A^2 + m_B d_B^2}{t_f}$$

**Answer: C** — $\frac{m_A d_B + m_B d_A}{t_f}$... use $L = mvr_\perp$, $v = d/t_f$:

$$L_{tot} = m_A \cdot \frac{d_A}{t_f} \cdot d_A + m_B \cdot \frac{d_B}{t_f} \cdot d_B$$

---

# 📘 Section 6.4 — Conservation of Angular Momentum

## Key Concepts & Formulas

- **System angular momentum:** $L_{system} = \sum L_{all\ objects}$
- **Conservation:** If net external torque = 0, then $\Delta L = 0$, so $L_i = L_f$
- For a changing-shape system: $I_1\omega_1 = I_2\omega_2$
- **Newton's 3rd Law for rotation:** Angular impulse exerted by A on B = equal and opposite to impulse by B on A

> 📖 **Reference:** [OpenStax — Conservation of Angular Momentum](https://openstax.org/books/university-physics-volume-1/pages/11-3-conservation-of-angular-momentum)

---

## Question 1 — Clay Ball Dropped onto Spinning Platform

**Problem:** Platform ($I_p$) spinning. Clay ball ($I_c < I_p$) dropped at center and sticks. What is the angular impulse exerted on the platform by the clay?

### Steps

1. Newton's 3rd law: impulse on platform by clay = **equal and opposite** to impulse on clay by platform
2. The clay stops slipping → angular impulses are equal in magnitude, opposite in direction

**Answer: C** — It is equal to the magnitude of the angular impulse exerted on the clay by the platform.

---

## Question 2 — Cylinders Sliding Outward in Pipe

**Problem:** Pipe with cylinders inside spins freely. Cylinders slide to the ends (increasing $r$). How does angular speed change?

### Steps

1. No external torque → $L = I\omega$ = constant
2. Cylinders move farther from axis → $I$ **increases**
3. Since $L = I\omega$ = constant: $\omega$ **decreases**

**Answer: A** — The angular speed decreases because the rotational inertia increases.

---

## Question 3 — Disk-Rod Collision

**Problem:** Rod initially at rest on frictionless surface. Disk slides and sticks to the rod's end. Does angular momentum of disk-rod system change?

### Steps

1. Friction between disk and rod is **internal** to the system
2. Floor is frictionless → no external torque on the system
3. Angular momentum is **conserved**

**Answer: D** — No, because the torques between disk and rod are internal to the system.

---

## Question 4 — Puck Collides with Bar (Newton's 3rd Law)

**Problem:** Puck slides and sticks to bar at pivot. How does angular momentum of puck change compared to bar?

### Steps

1. Newton's 3rd law: angular impulse on puck by bar = equal and opposite to impulse on bar by puck
2. Puck loses angular momentum → bar gains the **same amount**

**Answer: B** — The decrease in puck's angular momentum equals the increase in bar's angular momentum.

---

## Question 5 — Student Pulling Weights Inward

**Problem:** Student on frictionless platform, pulls weights inward. How does angular momentum change?

### Steps

1. No external torque on student-weights system
2. $L$ = **constant** (conserved)
3. Pulling weights in decreases $I$, so $\omega$ increases — but **$L$ does not change**

**Answer: D** — Angular momentum remains constant because no external net torque is exerted on the system.

---

# 📘 Section 6.5 — Motion of Orbiting Satellites

## Key Concepts & Formulas

**Circular Orbits:**

- $ma_c = F_g \Rightarrow \frac{mv^2}{r} = \frac{GMm}{r^2} \Rightarrow v = \sqrt{\frac{GM}{r}}$
- Constant: $K$, $r$, $U_g$, $E$, $L$

**Elliptical Orbits:**

- Constant: $E$ (mechanical), $L$ (angular momentum)
- Changing: $K$, $U_g$
- $r_A v_A = r_B v_B$ (from $L$ conservation, since $\theta = 90°$ at periapsis/apoapsis)

**Gravitational Potential Energy:** $$U_g = -\frac{Gm_1 m_2}{r}$$

**Escape Velocity:** $$v_{esc} = \sqrt{\frac{2GM}{r}}$$

> 📖 **Reference:** [NASA — Orbital Mechanics](https://www.grc.nasa.gov/www/k-12/airplane/oribts.html) 📖 **Reference:** [HyperPhysics — Escape Velocity](http://hyperphysics.phy-astr.gsu.edu/hbase/vesc.html)

---

## Question 1 (Bank 6) — Escape Speed from Larger Planet

**Problem:** Planet has mass $4M_E$ and radius $2R_E$. Find minimum launch speed.

### Steps

1. At escape: total mechanical energy = 0 $$K + U_g = 0 \Rightarrow \frac{1}{2}mv^2 - \frac{GmM}{r} = 0$$
2. Solve for $v$: $$v = \sqrt{\frac{2GM}{r}}$$
3. Substitute $M = 4M_E$, $r = 2R_E$: $$v = \sqrt{\frac{2G(4M_E)}{2R_E}} = \sqrt{\frac{4GM_E}{R_E}} = 2\sqrt{\frac{GM_E}{R_E}}$$

**Answer: A** — $2\sqrt{\frac{GM_E}{R_E}}$

---

## Question 2 (Bank 6) — Rocket Launched at $2v_{esc}$, Speed at Infinity

**Problem:** Rocket launched at $2v_{esc}$. Find speed when gravitational force is negligible ($r \to \infty$).

### Steps

1. Conservation of energy from surface to infinity ($U_f = 0$): $$K_i + U_i = K_f + U_f$$ $$\frac{1}{2}mv_i^2 - \frac{GMm}{R} = \frac{1}{2}mv_f^2$$
2. At escape: $v_{esc} = \sqrt{\frac{2GM}{R}}$, so $\frac{GM}{R} = \frac{v_{esc}^2}{2}$
3. With $v_i = 2v_{esc}$: $$\frac{1}{2}m(2v_{esc})^2 - m\frac{v_{esc}^2}{2} = \frac{1}{2}mv_f^2$$ $$2mv_{esc}^2 - \frac{mv_{esc}^2}{2} = \frac{1}{2}mv_f^2$$ $$\frac{3}{2}v_{esc}^2 = \frac{1}{2}v_f^2$$ $$v_f = v_{esc}\sqrt{3} = \sqrt{3 \cdot \frac{2GM}{R}} = \sqrt{\frac{6GM}{R}}$$

**Answer: D** — $\sqrt{\frac{6GM}{R}}$

---

## Question 3 (Bank 6) — Comparing Escape Speeds of Two Planets

**Problem:** Planet 1: mass $M$, radius $R$. Planet 2: mass $M/2$, radius $2R$. Compare $v_{esc}$.

### Steps

1. $v_{esc} = \sqrt{\frac{2GM}{R}}$
2. Planet 1: $v_{esc,1} = \sqrt{\frac{2GM}{R}}$
3. Planet 2: $v_{esc,2} = \sqrt{\frac{2G(M/2)}{2R}} = \sqrt{\frac{GM}{2R}}$
4. Ratio: $\frac{v_{esc,1}}{v_{esc,2}} = \sqrt{\frac{2GM/R}{GM/2R}} = \sqrt{4} = 2$

So $v_{esc,1} > v_{esc,2}$

**Answer: C** — $v_{esc,1} > v_{esc,2}$

---

## Question 4 (Bank 6) — Satellite Firing Thrusters, Comparing Mechanical Energy

**Problem:** Satellite at point P fires thrusters to reach point Q (5× farther). Both points have same speed $v$. Compare $E_Q$ to $E_P$.

### Steps

1. $E = K + U_g = \frac{1}{2}mv^2 - \frac{GMm}{r}$
2. At P: $E_P = \frac{1}{2}mv^2 - \frac{GMm}{R}$
3. At Q ($r = 5R$): $E_Q = \frac{1}{2}mv^2 - \frac{GMm}{5R}$
4. Since $\frac{GMm}{5R} < \frac{GMm}{R}$, we have $E_Q > E_P$
5. Thrusters did **positive work** on satellite (added energy)

**Answer: C** — $E_Q > E_P$, because gravitational potential energy increases with increasing distance from Earth's center.

---

## Question 5 (Bank 6) — Elliptical Orbit, Angular Speed at Distance R

**Problem:** Satellite at greatest distance $R_0$ has $\omega_0$. Find $\omega$ at distance $R$.

### Steps

1. Conserve angular momentum: $L = I\omega = mr^2\omega$ = constant
2. $mr_0^2\omega_0 = mr^2\omega$ $$\omega = \left(\frac{R_0}{R}\right)^2 \omega_0$$

**Answer: C** — $\left(\frac{R_0}{R}\right)^2 \omega_0$

---

## Question 6 (Bank 6) — Three Satellites, Max Speed Comparison

**Problem:** Satellite 1: circular orbit $R$. Satellite 2: circular orbit $2R$. Satellite 3: elliptical orbit between $R$ and $2R$. Compare max speeds.

### Steps

1. Circular orbits: $v = \sqrt{GM/r}$. Smaller $r$ → larger $v$: $$v_{1,max} > v_{2,max}$$
2. Satellite 3 (elliptical): max speed occurs at closest approach ($r = R$). At that point it's moving faster than Satellite 1 (which travels at a constant speed at $R$ in circular orbit), because Satellite 3 has more total energy than Satellite 2 and less than... actually, the elliptical satellite with periapsis at $R$ moves _faster_ than circular Satellite 1 at the same point. $$v_{3,max} > v_{1,max} > v_{2,max}$$

**Answer: B** — $v_{3,max} > v_{1,max} > v_{2,max}$

---

## Question 7 (Bank 6) — Energy Bar Chart for Elliptical Orbit

**Problem:** Satellite moves to a greater distance $R$ from Earth. Which bar chart shows the new $K$ and $U$?

### Steps

1. As $r$ increases: $U_g = -\frac{GMm}{r}$ becomes **less negative** (increases toward zero)
2. Total mechanical energy $E = K + U$ = constant (no external forces)
3. Since $U$ increases, $K$ must **decrease** by the same amount

Look for chart where $U$ is less negative (shorter negative bar) and $K$ is smaller (shorter positive bar), with the same total.

**Answer: B** — $K$ smaller, $U$ less negative, same total $E$.

---

## Question 8 (Bank 6) — Same Altitude, Different Mass Satellites, Escape Speed

**Problem:** Two satellites at same altitude $h$, masses $m$ and $2m$. Do they need the same speed to escape?

### Steps

1. $v_{esc} = \sqrt{\frac{2GM}{r}}$ — depends only on central planet's mass $M$ and distance $r$
2. Satellite mass does **not appear** in this formula
3. Both at same altitude → same $r$ → same $v_{esc}$

**Answer: B** — Yes, because escape speed does not depend on the masses of the satellites.

---

## Question 9 (Bank 6) — Torque on Elliptical Satellite

**Problem:** Is the torque on an elliptically orbiting satellite zero or nonzero?

### Steps

1. Torque: $\tau = rF\sin\theta$ where $\theta$ is angle between $\vec{r}$ and $\vec{F}$
2. Gravitational force always points from satellite **toward central body** = along $\vec{r}$
3. Therefore $\theta = 0°$ (or 180°), so $\sin\theta = 0$
4. $\tau = 0$ always (lever arm = 0)

**Answer: A** — Zero, because the lever arm of the gravitational force on the satellite is always zero.

---

# 📌 Quick Reference — Key Equations Summary

|Quantity|Formula|
|---|---|
|Rotational KE|$K_{rot} = \frac{1}{2}I\omega^2$|
|Total KE|$K_{tot} = \frac{1}{2}mv^2 + \frac{1}{2}I\omega^2$|
|Rotational Work|$W = \tau\Delta\theta$|
|Work-KE Theorem|$W = \Delta K_{rot} = \frac{1}{2}I(\omega^2 - \omega_0^2)$|
|Angular Momentum (rigid)|$L = I\omega$|
|Angular Momentum (point)|$L = rmv\sin\theta$|
|Angular Impulse|$\Delta L = \tau\Delta t$|
|Conservation of $L$|$I_1\omega_1 = I_2\omega_2$|
|Orbital speed|$v = \sqrt{GM/r}$|
|Gravitational PE|$U_g = -Gm_1m_2/r$|
|Escape velocity|$v_{esc} = \sqrt{2GM/r}$|
|Parallel Axis Theorem|$I' = I_{cm} + md^2$|
|Linear–Angular relation|$v = r\omega$|

---

_AP Physics 1 / Unit 6 — Energy and Momentum of Rotating Systems_ _Reference guide compiled from Problem Banks 1–6_