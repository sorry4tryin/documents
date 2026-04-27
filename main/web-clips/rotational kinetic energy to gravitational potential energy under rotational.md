---
source: https://chatgpt.com/g/g-p-69e1264882c0819187abed1fac171342-ap-physics/c/69f00dc5-368c-83ea-a740-ed14f96977ea
created: 2026-04-27
description: everything covering the outline on the topics regarding uploading the worksheets from class
tags:
  - chatgpt/conversation
---
# 6.1 Rotational Kinetic Energy

## Core concept
Rotational kinetic energy is the energy stored in an object due to its rotation about an axis. It is not fundamentally different from linear kinetic energy; instead, it is the rotational analog where mass distribution replaces simple mass. The key idea is that not all parts of a rotating object move at the same speed—points farther from the axis move faster, contributing disproportionately more energy.

The system is governed by the moment of inertia, which encodes how mass is distributed relative to the axis of rotation. This makes rotational energy highly geometry-dependent rather than purely mass-dependent.

---

## Core formulas

Rotational kinetic energy:  
$K_{rot} = \frac{1}{2} I \omega^2$

Total kinetic energy (translation + rotation):  
$K_{tot} = \frac{1}{2}mv^2 + \frac{1}{2}I\omega^2$

These expressions show that systems can simultaneously store energy in linear motion and rotational motion.

---

## Key relationships

Linear-to-rotational connection:  
$v = \omega r$

Moment of inertia examples:  
- Solid sphere: $I = \frac{2}{5}mr^2$  
- Hoop: $I = mr^2$

Parallel axis theorem:  
$I' = I_{cm} + md^2$

This theorem shows that shifting the axis increases rotational inertia, even if the object itself does not change.

---

## Problem structure patterns

Rotational energy problems typically require identifying angular velocity from graphs or converting linear motion into rotational motion using constraints like rolling without slipping. In systems like satellites or isolated rotating objects, energy distribution changes but total energy remains conserved if no external work is done.

Off-center rotation problems consistently involve the parallel axis theorem, where energy increases due to increased inertia even at constant angular speed.

---

# 6.2 Torque and Rotational Work

## Core concept
Torque represents the effectiveness of a force in producing rotation. It is not simply a rotational force but a measure of how force produces angular displacement about an axis. Work in rotational systems depends on how torque acts over angular displacement rather than linear distance.

This unit connects force interactions directly to changes in rotational energy through work-energy relationships.

---

## Core formulas

Rotational work:  
$W = \tau \Delta \theta$

Work-energy theorem:  
$W = \Delta K_{rot} = \frac{1}{2}I(\omega^2 - \omega_0^2)$

Rotational dynamics:  
$\alpha = \frac{\tau}{I}$

---

## Graph interpretation

The area under a torque vs angular displacement graph represents work done. This is analogous to force vs displacement in linear systems. Similarly, torque applied over time relates to angular impulse and momentum change.

---

## Key insights

Torque only depends on the perpendicular component of force relative to the axis of rotation. Forces acting through the axis produce no torque. This makes torque fundamentally a geometric interaction between force and position.

Work in rotational systems is path-dependent, meaning the total angular displacement matters, not just initial and final states. This contrasts with energy, which depends only on state.

---

## Common problem types

Pulley systems involve tension differences producing net torque. Friction on rotating surfaces produces constant torque opposing motion. Scaling torque changes angular acceleration linearly but angular displacement quadratically over time, making energy transfer nonlinear.

---

# 6.3 Angular Momentum and Impulse

## Core concept
Angular momentum is the rotational analog of linear momentum. It represents the quantity of rotational motion an object has and resists changes when no external torque is applied.

Unlike energy, angular momentum is conserved in isolated systems even when internal forces redistribute motion.

---

## Core formulas

Rigid body angular momentum:  
$L = I\omega$

Point particle angular momentum:  
$L = rmv\sin\theta$

Angular impulse:  
$\Delta L = \tau \Delta t = I\Delta \omega$

---

## Graph relationships

The area under a torque vs time graph represents angular impulse, which equals the change in angular momentum. The slope of angular momentum vs time represents net torque acting on the system.

---

## Structural insights

Only the perpendicular component of velocity contributes to angular momentum due to the sine term. This creates directional dependence, meaning motion aligned with the radius produces no rotational effect.

Angular momentum acts as a memory of rotational motion, persisting unless an external torque modifies it.

---

## Common problems

Collisions involving rods and pucks require analyzing perpendicular distance from pivot points. Systems involving jumping or tangential motion maximize angular momentum because the sine term equals one. Objects moving directly toward or away from a pivot contribute zero angular momentum.

---

# 6.4 Conservation of Angular Momentum

## Core concept
Angular momentum is conserved in a system when there is no net external torque. Internal forces may redistribute angular momentum between components, but they cannot change the total value.

This principle governs all isolated rotational systems.

---

## Core equations

$L_{system} = \text{constant when } \tau_{ext} = 0$

For rigid systems:  
$I\omega = \text{constant}$

---

## Physical interpretation

If a system’s moment of inertia increases, angular velocity must decrease to preserve angular momentum. If inertia decreases, angular velocity increases. This is a geometric redistribution of motion constrained by conservation laws.

Internal torques cancel due to Newton’s third law, meaning they cannot affect total angular momentum.

---

## Problem archetypes

Ice skaters pulling arms inward increase angular velocity. Objects sticking together during rotation conserve angular momentum but redistribute inertia. Mass moving outward decreases angular speed due to increased rotational resistance.

---

# 6.6 Motion of Orbiting Satellites

## Core concept
Orbital motion is continuous free fall under gravity, constrained by angular momentum conservation. Satellites are not “held up” in orbit—they are constantly falling while missing the Earth due to tangential velocity.

---

## Core formulas

Orbital velocity:  
$v = \sqrt{\frac{GM}{r}}$

Gravitational potential energy:  
$U_g = -\frac{GMm}{r}$

Escape velocity:  
$v_{esc} = \sqrt{\frac{2GM}{r}}$

---

## Circular orbits

In circular motion:
- velocity is constant
- kinetic energy is constant
- potential energy is constant
- total energy is constant
- angular momentum is constant

The system is in a steady-state energy configuration.

---

## Elliptical orbits

In elliptical motion:
- kinetic energy changes with distance
- potential energy changes with distance
- total mechanical energy remains constant
- angular momentum remains constant

Energy shifts between kinetic and potential forms as radius changes.

---

## Structural insights

Gravity exerts no torque about the center of orbit because it always points radially inward. This means it cannot change angular momentum, only redistribute energy along the orbit.

Escape velocity represents the threshold where total mechanical energy reaches zero, transitioning from bound to unbound motion.

---

## Common problem patterns

Satellite burns increase mechanical energy without changing angular momentum immediately. Speed differences between periapsis and apoapsis arise from energy conservation. Orbital radius changes directly affect velocity due to inverse square dependence.

---

# Unified System Insight

Across all sections, the same structure repeats:

- Energy describes system state magnitude  
- Torque describes how energy is transferred into rotation  
- Angular momentum describes conserved rotational motion  
- Gravity constrains motion without directly changing angular momentum  

At the deepest level, rotational physics is not about motion itself but about constraints acting on distributed mass systems under conservation laws.