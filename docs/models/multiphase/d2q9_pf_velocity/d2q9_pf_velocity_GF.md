

## Description
d2q9_pf_velocity_GF

## Details
[Model description files](Model description) files for this model:
[Dynamics.c](https://github.com/llaniewski/TCLB/blob/(HEAD detached at 71dd0de)/src/d2q9_pf_velocity_GF/Dynamics.c.Rt)
[Dynamics.R](https://github.com/llaniewski/TCLB/blob/(HEAD detached at 71dd0de)/src/d2q9_pf_velocity_GF/Dynamics.R)

### [Zonal Settings](Settings)

| Name | Comment |
| --- | --- |
|`PhaseField`|Initial PhaseField distribution|
|`VelocityX`|inlet/outlet/init velocity|
|`VelocityY`|inlet/outlet/init velocity|
|`Pressure`|inlet/outlet/init density|
|`PressureLossInObj`|Weight of [pressure loss] in objective|
|`OutletFluxInObj`|Weight of [pressure loss] in objective|
|`InletFluxInObj`|Weight of [pressure loss] in objective|
|`TotalDensityInObj`|Weight of [Mass conservation check] in objective|
|`RTIBubbleInObj`|Weight of [Bubble Tracker] in objective|
|`RTISpikeInObj`|Weight of [Spike Tracker] in objective|


### [Global Settings](Settings)

| Name | Derived | Comment |
| --- | --- | --- |
|`Period`||Number of cells per cos wave|
|`Perturbation`||Size of wave perturbation, Perturbation Period|
|`MidPoint`||height of RTI centerline|
|`Radius`||Radius of diffuse interface circle|
|`CenterX`||Circle center x-coord|
|`CenterY`||Circle Center y-coord|
|`BubbleType`||Drop/bubble|
|`Density_h`||High density|
|`Density_l`||Low  density|
|`PhaseField_h`||PhaseField in Liquid|
|`PhaseField_l`||PhaseField gas|
|`W`||Anti-diffusivity coeff|
|`omega_phi`|1.0/(3*M+0.5)|one over relaxation time (phase field)|
|`M`||Mobility|
|`sigma`||surface tension|
|`tau_l`|(3*Viscosity_l)|relaxation time (low density fluid)|
|`tau_h`|(3*Viscosity_h)|relaxation time (high density fluid)|
|`Viscosity_l`||kinematic viscosity|
|`Viscosity_h`||kinematic viscosity|
|`GravitationX`||applied (rho)*GravitationX|
|`GravitationY`||applied (rho)*GravitationY|
|`BuoyancyX`||applied (rho-rho_h)*BuoyancyX|
|`BuoyancyY`||applied (rho-rho_h)*BuoyancyY|
|`Threshold`||Parameters threshold|

### [Exported Quantities](Quantities) (VTK, etc)

| Name | [Unit](Units) | Comment |
| --- | --- | --- |
|`Rho`|`kg/m3`|Rho|
|`PhaseField`|`1`|PhaseField|
|`U`|`m/s`|U|
|`P`|`Pa`|P|

#### [Exported Global Integrals](Globals) (CSV, etc)

| Name | [Unit](Units) | Comment |
| --- | --- | --- |
|`PressureLoss`|`1mPa`|pressure loss|
|`OutletFlux`|`1m2/s`|pressure loss|
|`InletFlux`|`1m2/s`|pressure loss|
|`TotalDensity`|`1kg/m3`|Mass conservation check|
|`RTIBubble`|`1`|Bubble Tracker|
|`RTISpike`|`1`|Spike Tracker|
|`Objective`|`1`|Objective function|

### [Node Types](Node-Types)

| Group | Types |
| --- | --- |
|ADDITIONALS|SpikeTrack, BubbleTrack|
|BOUNDARY|Wall, Solid, WVelocity, WPressure, WPressureL, EPressure, EVelocity, MovingWall_N, MovingWall_S, Symmetry_N, Symmetry_S|
|COLLISION|BGK, MRT|
|DESIGNSPACE|DesignSpace|
|NONE|None|
|SETTINGZONE|DefaultZone|

### [Solved fields](Fields)

| Name | Access pattern | Comment |
| --- | --- | --- |
|`g[0]`|![stencil](/images/st_a1p0p0p0p0p0p0.png)|g[0]|
|`g[1]`|![stencil](/images/st_a1n1p0p0n1p0p0.png)|g[1]|
|`g[2]`|![stencil](/images/st_a1p0n1p0p0n1p0.png)|g[2]|
|`g[3]`|![stencil](/images/st_a1p1p0p0p1p0p0.png)|g[3]|
|`g[4]`|![stencil](/images/st_a1p0p1p0p0p1p0.png)|g[4]|
|`g[5]`|![stencil](/images/st_a1n1n1p0n1n1p0.png)|g[5]|
|`g[6]`|![stencil](/images/st_a1p1n1p0p1n1p0.png)|g[6]|
|`g[7]`|![stencil](/images/st_a1p1p1p0p1p1p0.png)|g[7]|
|`g[8]`|![stencil](/images/st_a1n1p1p0n1p1p0.png)|g[8]|
|`h[0]`|![stencil](/images/st_a1p0p0p0p0p0p0.png)|h[0]|
|`h[1]`|![stencil](/images/st_a1n1p0p0n1p0p0.png)|h[1]|
|`h[2]`|![stencil](/images/st_a1p0n1p0p0n1p0.png)|h[2]|
|`h[3]`|![stencil](/images/st_a1p1p0p0p1p0p0.png)|h[3]|
|`h[4]`|![stencil](/images/st_a1p0p1p0p0p1p0.png)|h[4]|
|`h[5]`|![stencil](/images/st_a1n1n1p0n1n1p0.png)|h[5]|
|`h[6]`|![stencil](/images/st_a1p1n1p0p1n1p0.png)|h[6]|
|`h[7]`|![stencil](/images/st_a1p1p1p0p1p1p0.png)|h[7]|
|`h[8]`|![stencil](/images/st_a1n1p1p0n1p1p0.png)|h[8]|
|`U`|![stencil](/images/st_a1p0p0p0p0p0p0.png)|U|
|`V`|![stencil](/images/st_a1p0p0p0p0p0p0.png)|V|
|`PhaseF`|![stencil](/images/st_a1n1n1p0p1p1p0.png)|PhaseF|

### [Densities - default accessors](Densities)

| Name | [Field](Fields) | Pulling field from | Comment |
| --- | --- | --- | --- |
|`g[0]`|g[0]|![stencil](/images/st_a1p0p0p0p0p0p0.png)|g[0]|
|`g[1]`|g[1]|![stencil](/images/st_a1p1p0p0p1p0p0.png)|g[1]|
|`g[2]`|g[2]|![stencil](/images/st_a1p0p1p0p0p1p0.png)|g[2]|
|`g[3]`|g[3]|![stencil](/images/st_a1n1p0p0n1p0p0.png)|g[3]|
|`g[4]`|g[4]|![stencil](/images/st_a1p0n1p0p0n1p0.png)|g[4]|
|`g[5]`|g[5]|![stencil](/images/st_a1p1p1p0p1p1p0.png)|g[5]|
|`g[6]`|g[6]|![stencil](/images/st_a1n1p1p0n1p1p0.png)|g[6]|
|`g[7]`|g[7]|![stencil](/images/st_a1n1n1p0n1n1p0.png)|g[7]|
|`g[8]`|g[8]|![stencil](/images/st_a1p1n1p0p1n1p0.png)|g[8]|
|`h[0]`|h[0]|![stencil](/images/st_a1p0p0p0p0p0p0.png)|h[0]|
|`h[1]`|h[1]|![stencil](/images/st_a1p1p0p0p1p0p0.png)|h[1]|
|`h[2]`|h[2]|![stencil](/images/st_a1p0p1p0p0p1p0.png)|h[2]|
|`h[3]`|h[3]|![stencil](/images/st_a1n1p0p0n1p0p0.png)|h[3]|
|`h[4]`|h[4]|![stencil](/images/st_a1p0n1p0p0n1p0.png)|h[4]|
|`h[5]`|h[5]|![stencil](/images/st_a1p1p1p0p1p1p0.png)|h[5]|
|`h[6]`|h[6]|![stencil](/images/st_a1n1p1p0n1p1p0.png)|h[6]|
|`h[7]`|h[7]|![stencil](/images/st_a1n1n1p0n1n1p0.png)|h[7]|
|`h[8]`|h[8]|![stencil](/images/st_a1p1n1p0p1n1p0.png)|h[8]|
|`U`|U|![stencil](/images/st_a1p0p0p0p0p0p0.png)|U|
|`V`|V|![stencil](/images/st_a1p0p0p0p0p0p0.png)|V|

### [Action stages](Stages)

| Name | Main procedure | Preloaded densities | Pushed fields |
| --- | --- | --- | --- |
|PhaseInit|Init|_none_|PhaseF|
|BaseInit|Init_distributions|_none_|g[0], g[1], g[2], g[3], g[4], g[5], g[6], g[7], g[8], h[0], h[1], h[2], h[3], h[4], h[5], h[6], h[7], h[8], U, V|
|calcPhase|calcPhaseF|h[0], h[1], h[2], h[3], h[4], h[5], h[6], h[7], h[8]|PhaseF|
|BaseIter|Run|g[0], g[1], g[2], g[3], g[4], g[5], g[6], g[7], g[8], h[0], h[1], h[2], h[3], h[4], h[5], h[6], h[7], h[8], U, V|g[0], g[1], g[2], g[3], g[4], g[5], g[6], g[7], g[8], h[0], h[1], h[2], h[3], h[4], h[5], h[6], h[7], h[8], U, V|


### [Actions](Stages)

| Name | Stages |
| --- | --- |
|Iteration|BaseIter, calcPhase|
|Init|PhaseInit, BaseInit|

