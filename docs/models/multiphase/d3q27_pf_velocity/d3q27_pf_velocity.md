

## Description
d3q27_pf_velocity

## Details
[Model description files](Model description) files for this model:
[Dynamics.c](https://github.com/llaniewski/TCLB/blob/(HEAD detached at 55c8268)/src/d3q27_pf_velocity/Dynamics.c.Rt)
[Dynamics.R](https://github.com/llaniewski/TCLB/blob/(HEAD detached at 55c8268)/src/d3q27_pf_velocity/Dynamics.R)

### [Zonal Settings](Settings)

| Name | Comment |
| --- | --- |
|`PhaseField`|Initial PhaseField distribution|
|`VelocityX`|inlet/outlet/init velocity|
|`VelocityY`|inlet/outlet/init velocity|
|`VelocityZ`|inlet/outlet/init velocity|
|`Pressure`|inlet/outlet/init density|
|`InterfacePositionInObj`|Weight of [trackPosition] in objective|
|`RTISpikeInObj`|Weight of [SpikeTracker ] in objective|
|`RTIBubbleInObj`|Weight of [BubbleTracker] in objective|
|`RTISaddleInObj`|Weight of [SaddleTracker] in objective|
|`PressureLossInObj`|Weight of [pressure loss] in objective|
|`OutletFluxInObj`|Weight of [pressure loss] in objective|
|`InletFluxInObj`|Weight of [pressure loss] in objective|
|`TotalDensityInObj`|Weight of [Mass conservation check] in objective|


### [Global Settings](Settings)

| Name | Derived | Comment |
| --- | --- | --- |
|`Density_h`||High density|
|`Density_l`||Low  density|
|`PhaseField_h`||PhaseField in Liquid|
|`PhaseField_l`||PhaseField gas|
|`IntWidth`||Anti-diffusivity coeff|
|`omega_phi`|1.0/(3*M+0.5)|one over relaxation time (phase field)|
|`M`||Mobility|
|`sigma`||surface tension|
|`RTI_Characteristic_Length`||Use for RTI instability|
|`Radius`||Diffuse Sphere Radius|
|`CenterX`||Diffuse sphere center_x|
|`CenterY`||Diffuse sphere center_y|
|`CenterZ`||Diffuse sphere center_z|
|`BubbleType`||droplet or bubble?!|
|`tau_l`|(3*Viscosity_l)|relaxation time (low density fluid)|
|`tau_h`|(3*Viscosity_h)|relaxation time (high density fluid)|
|`Viscosity_l`||kinematic viscosity|
|`Viscosity_h`||kinematic viscosity|
|`GravitationX`||applied (rho)*GravitationX|
|`GravitationY`||applied (rho)*GravitationY|
|`GravitationZ`||applied (rho)*GravitationZ|
|`BuoyancyX`||applied (rho-rho_h)*BuoyancyX|
|`BuoyancyY`||applied (rho-rho_h)*BuoyancyY|
|`BuoyancyZ`||applied (rho-rho_h)*BuoyancyZ|
|`Threshold`||Parameters threshold|

### [Exported Quantities](Quantities) (VTK, etc)

| Name | [Unit](Units) | Comment |
| --- | --- | --- |
|`PhaseField`|`1`|PhaseField|
|`U`|`m/s`|U|
|`P`|`Pa`|P|

#### [Exported Global Integrals](Globals) (CSV, etc)

| Name | [Unit](Units) | Comment |
| --- | --- | --- |
|`InterfacePosition`|`1`|trackPosition|
|`RTISpike`|`1`|SpikeTracker |
|`RTIBubble`|`1`|BubbleTracker|
|`RTISaddle`|`1`|SaddleTracker|
|`PressureLoss`|`1mPa`|pressure loss|
|`OutletFlux`|`1m2/s`|pressure loss|
|`InletFlux`|`1m2/s`|pressure loss|
|`TotalDensity`|`1kg/m3`|Mass conservation check|
|`Objective`|`1`|Objective function|

### [Node Types](Node-Types)

| Group | Types |
| --- | --- |
|ADDITIONALS|Centerline, Spiketrack, Saddletrack, Bubbletrack, SymmetricXY_W, SymmetricXY_E|
|BOUNDARY|Wall, Solid, WVelocity, WPressure, WPressureL, EPressure, EVelocity, MovingWall_N, MovingWall_S|
|COLLISION|BGK, MRT|
|DESIGNSPACE|DesignSpace|
|NONE|None|
|OBJECTIVE|Inlet, Outlet|
|SETTINGZONE|DefaultZone|

### [Solved fields](Fields)

| Name | Access pattern | Comment |
| --- | --- | --- |
|`g0`|![stencil](/images/st_b1p0p0p0p0p0p0.png)|g0|
|`g1`|![stencil](/images/st_b1n1p0p0n1p0p0.png)|g1|
|`g2`|![stencil](/images/st_b1p1p0p0p1p0p0.png)|g2|
|`g3`|![stencil](/images/st_b1p0n1p0p0n1p0.png)|g3|
|`g4`|![stencil](/images/st_b1p0p1p0p0p1p0.png)|g4|
|`g5`|![stencil](/images/st_b1p0p0n1p0p0n1.png)|g5|
|`g6`|![stencil](/images/st_b1p0p0p1p0p0p1.png)|g6|
|`g7`|![stencil](/images/st_b1n1n1n1n1n1n1.png)|g7|
|`g8`|![stencil](/images/st_b1p1n1n1p1n1n1.png)|g8|
|`g9`|![stencil](/images/st_b1n1p1n1n1p1n1.png)|g9|
|`g10`|![stencil](/images/st_b1p1p1n1p1p1n1.png)|g10|
|`g11`|![stencil](/images/st_b1n1n1p1n1n1p1.png)|g11|
|`g12`|![stencil](/images/st_b1p1n1p1p1n1p1.png)|g12|
|`g13`|![stencil](/images/st_b1n1p1p1n1p1p1.png)|g13|
|`g14`|![stencil](/images/st_b1p1p1p1p1p1p1.png)|g14|
|`g15`|![stencil](/images/st_b1n1n1p0n1n1p0.png)|g15|
|`g16`|![stencil](/images/st_b1p1n1p0p1n1p0.png)|g16|
|`g17`|![stencil](/images/st_b1n1p1p0n1p1p0.png)|g17|
|`g18`|![stencil](/images/st_b1p1p1p0p1p1p0.png)|g18|
|`g19`|![stencil](/images/st_b1n1p0n1n1p0n1.png)|g19|
|`g20`|![stencil](/images/st_b1p1p0n1p1p0n1.png)|g20|
|`g21`|![stencil](/images/st_b1n1p0p1n1p0p1.png)|g21|
|`g22`|![stencil](/images/st_b1p1p0p1p1p0p1.png)|g22|
|`g23`|![stencil](/images/st_b1p0n1n1p0n1n1.png)|g23|
|`g24`|![stencil](/images/st_b1p0p1n1p0p1n1.png)|g24|
|`g25`|![stencil](/images/st_b1p0n1p1p0n1p1.png)|g25|
|`g26`|![stencil](/images/st_b1p0p1p1p0p1p1.png)|g26|
|`h0`|![stencil](/images/st_b1p0p0p0p0p0p0.png)|h0|
|`h1`|![stencil](/images/st_b1n1p0p0n1p0p0.png)|h1|
|`h2`|![stencil](/images/st_b1p1p0p0p1p0p0.png)|h2|
|`h3`|![stencil](/images/st_b1p0n1p0p0n1p0.png)|h3|
|`h4`|![stencil](/images/st_b1p0p1p0p0p1p0.png)|h4|
|`h5`|![stencil](/images/st_b1p0p0n1p0p0n1.png)|h5|
|`h6`|![stencil](/images/st_b1p0p0p1p0p0p1.png)|h6|
|`h7`|![stencil](/images/st_b1n1n1n1n1n1n1.png)|h7|
|`h8`|![stencil](/images/st_b1p1n1n1p1n1n1.png)|h8|
|`h9`|![stencil](/images/st_b1n1p1n1n1p1n1.png)|h9|
|`h10`|![stencil](/images/st_b1p1p1n1p1p1n1.png)|h10|
|`h11`|![stencil](/images/st_b1n1n1p1n1n1p1.png)|h11|
|`h12`|![stencil](/images/st_b1p1n1p1p1n1p1.png)|h12|
|`h13`|![stencil](/images/st_b1n1p1p1n1p1p1.png)|h13|
|`h14`|![stencil](/images/st_b1p1p1p1p1p1p1.png)|h14|
|`U`|![stencil](/images/st_b1p0p0p0p0p0p0.png)|U|
|`V`|![stencil](/images/st_b1p0p0p0p0p0p0.png)|V|
|`W`|![stencil](/images/st_b1p0p0p0p0p0p0.png)|W|
|`PhaseF`|![stencil](/images/st_b1n1n1n1p1p1p1.png)|PhaseF|

### [Densities - default accessors](Densities)

| Name | [Field](Fields) | Pulling field from | Comment |
| --- | --- | --- | --- |
|`g0`|g0|![stencil](/images/st_b1p0p0p0p0p0p0.png)|g0|
|`g1`|g1|![stencil](/images/st_b1p1p0p0p1p0p0.png)|g1|
|`g2`|g2|![stencil](/images/st_b1n1p0p0n1p0p0.png)|g2|
|`g3`|g3|![stencil](/images/st_b1p0p1p0p0p1p0.png)|g3|
|`g4`|g4|![stencil](/images/st_b1p0n1p0p0n1p0.png)|g4|
|`g5`|g5|![stencil](/images/st_b1p0p0p1p0p0p1.png)|g5|
|`g6`|g6|![stencil](/images/st_b1p0p0n1p0p0n1.png)|g6|
|`g7`|g7|![stencil](/images/st_b1p1p1p1p1p1p1.png)|g7|
|`g8`|g8|![stencil](/images/st_b1n1p1p1n1p1p1.png)|g8|
|`g9`|g9|![stencil](/images/st_b1p1n1p1p1n1p1.png)|g9|
|`g10`|g10|![stencil](/images/st_b1n1n1p1n1n1p1.png)|g10|
|`g11`|g11|![stencil](/images/st_b1p1p1n1p1p1n1.png)|g11|
|`g12`|g12|![stencil](/images/st_b1n1p1n1n1p1n1.png)|g12|
|`g13`|g13|![stencil](/images/st_b1p1n1n1p1n1n1.png)|g13|
|`g14`|g14|![stencil](/images/st_b1n1n1n1n1n1n1.png)|g14|
|`g15`|g15|![stencil](/images/st_b1p1p1p0p1p1p0.png)|g15|
|`g16`|g16|![stencil](/images/st_b1n1p1p0n1p1p0.png)|g16|
|`g17`|g17|![stencil](/images/st_b1p1n1p0p1n1p0.png)|g17|
|`g18`|g18|![stencil](/images/st_b1n1n1p0n1n1p0.png)|g18|
|`g19`|g19|![stencil](/images/st_b1p1p0p1p1p0p1.png)|g19|
|`g20`|g20|![stencil](/images/st_b1n1p0p1n1p0p1.png)|g20|
|`g21`|g21|![stencil](/images/st_b1p1p0n1p1p0n1.png)|g21|
|`g22`|g22|![stencil](/images/st_b1n1p0n1n1p0n1.png)|g22|
|`g23`|g23|![stencil](/images/st_b1p0p1p1p0p1p1.png)|g23|
|`g24`|g24|![stencil](/images/st_b1p0n1p1p0n1p1.png)|g24|
|`g25`|g25|![stencil](/images/st_b1p0p1n1p0p1n1.png)|g25|
|`g26`|g26|![stencil](/images/st_b1p0n1n1p0n1n1.png)|g26|
|`h0`|h0|![stencil](/images/st_b1p0p0p0p0p0p0.png)|h0|
|`h1`|h1|![stencil](/images/st_b1p1p0p0p1p0p0.png)|h1|
|`h2`|h2|![stencil](/images/st_b1n1p0p0n1p0p0.png)|h2|
|`h3`|h3|![stencil](/images/st_b1p0p1p0p0p1p0.png)|h3|
|`h4`|h4|![stencil](/images/st_b1p0n1p0p0n1p0.png)|h4|
|`h5`|h5|![stencil](/images/st_b1p0p0p1p0p0p1.png)|h5|
|`h6`|h6|![stencil](/images/st_b1p0p0n1p0p0n1.png)|h6|
|`h7`|h7|![stencil](/images/st_b1p1p1p1p1p1p1.png)|h7|
|`h8`|h8|![stencil](/images/st_b1n1p1p1n1p1p1.png)|h8|
|`h9`|h9|![stencil](/images/st_b1p1n1p1p1n1p1.png)|h9|
|`h10`|h10|![stencil](/images/st_b1n1n1p1n1n1p1.png)|h10|
|`h11`|h11|![stencil](/images/st_b1p1p1n1p1p1n1.png)|h11|
|`h12`|h12|![stencil](/images/st_b1n1p1n1n1p1n1.png)|h12|
|`h13`|h13|![stencil](/images/st_b1p1n1n1p1n1n1.png)|h13|
|`h14`|h14|![stencil](/images/st_b1n1n1n1n1n1n1.png)|h14|
|`U`|U|![stencil](/images/st_b1p0p0p0p0p0p0.png)|U|
|`V`|V|![stencil](/images/st_b1p0p0p0p0p0p0.png)|V|
|`W`|W|![stencil](/images/st_b1p0p0p0p0p0p0.png)|W|

### [Action stages](Stages)

| Name | Main procedure | Preloaded densities | Pushed fields |
| --- | --- | --- | --- |
|PhaseInit|Init|_none_|PhaseF|
|BaseInit|Init_distributions|_none_|g0, g1, g2, g3, g4, g5, g6, g7, g8, g9, g10, g11, g12, g13, g14, g15, g16, g17, g18, g19, g20, g21, g22, g23, g24, g25, g26, h0, h1, h2, h3, h4, h5, h6, h7, h8, h9, h10, h11, h12, h13, h14, U, V, W|
|calcPhase|calcPhaseF|h0, h1, h2, h3, h4, h5, h6, h7, h8, h9, h10, h11, h12, h13, h14|PhaseF|
|BaseIter|Run|g0, g1, g2, g3, g4, g5, g6, g7, g8, g9, g10, g11, g12, g13, g14, g15, g16, g17, g18, g19, g20, g21, g22, g23, g24, g25, g26, h0, h1, h2, h3, h4, h5, h6, h7, h8, h9, h10, h11, h12, h13, h14, U, V, W|g0, g1, g2, g3, g4, g5, g6, g7, g8, g9, g10, g11, g12, g13, g14, g15, g16, g17, g18, g19, g20, g21, g22, g23, g24, g25, g26, h0, h1, h2, h3, h4, h5, h6, h7, h8, h9, h10, h11, h12, h13, h14, U, V, W|


### [Actions](Stages)

| Name | Stages |
| --- | --- |
|Iteration|BaseIter, calcPhase|
|Init|PhaseInit, BaseInit, calcPhase|

