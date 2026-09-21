# Helicoid scattering patterns

:::{warning} Caveat

1. The _Ribbon_ code makes the same assumptions as that of the theory of large
   deflection of thin plates: _Straight lines normal to the midsurface in the
reference configuration remain straight and normal in the deformed current
configuration_. This imples **no warping** of the cross-sections. This
assumption will break down when the deflection is more than half of the
thickness.

2. The above is not an issue for isometric deformations, like cylinders and
   helical ribbons (Gauss curvature $\kappa_g = 0$), but helicoids ($\kappa_g <
0$) are non-isometric to a flat plate and straight normals will rotate and bend
when the deflection gets too large. Warping will occur for non-circular
cross-sections, but not for circular ones.
:::

:::{figure} images/3/fig-helicoid-saxs.svg
:label: fig-hcsaxs
:width: 100%
:align: center

SAXS/WAXS patterns for helicoids with different values of pitch $P$ at $L = 100$ nm and
$W = 10$ nm for 2ML CdSe NPLs. 
:::

We look at the effect of pitch on the SAXS patterns for helicoids in
[](#fig-hcsaxs). In contrast to helical ribbons, deformation of flat plates 
to helicoids is non-isometric. Going from a flat configuration to increasing
values of central line twist, $\kappa_g$ progressively becomes negative. 
The neutral surface stretches as the edges in the lengthwise direction become longer
while those in the widthwise direction remains same (this is the definition of
a helicoid). Every point on the surface is a saddle point. The length
difference between the stretched edges and the centerline (neutral axis) will
lead to tensile stress; at sufficiently high twist this would cause _secondary
torsional buckling_. Just visually from [](#fig-hcsaxs), it is most likely that
pitches lower than 120 nm would buckle. In terms of SAXS patterns, significant
differences from that of a flat plate appears only at high twists ($P < 120$ nm).

# Understanding shape transition

Let's try to understand pathways for transitions between flat plates, helical
ribbons, and helicoids. We will assume that the NPL dimensions remain same and
some external factors, e.g. ligand exchange, is responsible to changing the
curvatures of the NPL.

We begin with a helical ribbon whose centerline (assumed same as the neutral
axis), a helix is specified by two curvatures: (1) $l$, the curvature along the
length, and (2) $m$ the twist along the length. To describe the neutral
surface, we need a third curvature, $n$, but that is not important right now.
As it is more convenient to use the parameters radius $R$ and pitch $P$ instead of $l$
and $m$, we will avoid directly using the curvatures (internally _Ribbon_ uses
$l$ and $m$). The two sets of parameters are related thus:

\begin{equation}
R = \frac{l}{l^2+m^2} \qquad \text{and} \qquad P = \frac{2 \pi m}{l^2 + m^2}.
\end{equation}

In case of a flat configuration, the $l,m$ paramaterization is unambiguous; it
has no curvature and no twist. So $l = 0$ and $m=0$. But in case of
parametrization in terms of radius and pitch setting $l = 0, m=0$ leads to
undefined values.  In fact there are two cases for the RP parametrization: (1)
$R \rightarrow \infty, P \rightarrow 0$, and (2) $R \rightarrow 0, P
\rightarrow \infty$. If we imagine a right-handed helix with axis along the
positive $z$-direction starting from the $x-y$ plane, case (1) corresponds to a
line on the $x-y$ plane parallel to the $x$-axis and case (2) corresponds to a
line on the $y-z$ plane parallel to the $z$-axis.

:::{figure} images/3/fig-transitions.svg
:label: fig-transition
:width: 100%
:align: center

Neutral surface of a helical ribbon (a). Gradually increasing $R$ and reducing
$P$ (b) gets us to a flat configuration (c). Reducing $R$ encounters a limiting
case (f). The surface leaves the surface of the cylinder defined by the
centerline helix and remains tangent to it (e). Progessively reducing $R$ and 
increasing $P$ gets us to a helicoid (g) via intermediate shapes (f).
By increasing $P$ at $R=0$ we reach a flat state again (h). The if the surface
moves more than tangential we get complex intermediates (i, j). These will
eventually reach a twisted cylindrical state instead of a helicoid and finally
a straight cylinder instead of a flat surface.
:::

## Helical ribbon to a flat plate

Starting from a helical ribbon, we can (mentally) continously and isometrically
deform it by increasing $R$ and simultaneously decreasing $P$ while keeping the
contour length fixed all the way to obtain a flat configuration. No issues
here. The Gauss curvature remains zero in all cases.

## Helical ribbon to a helicoid

On the other hand, if we start reducing $R$ we encounter problems. As $R$
reduces, $P$ must be more than $P_{min}$ to prevent ovelap. $P_{min}$ will blow
up as $R \rightarrow W/2\pi$ as the helix angle $\psi \rightarrow \pi/2$ as 
$R \rightarrow W/2\pi$. Thus we cannot reduce $R$ lower than $W/2\pi$ at finite
$P$ while shape stays a helical ribbon. If we imagine a set of grid lines on
the neutral surface of the ribbon, all lines reamin on the surface of the
cylinder defined by the centerline helix. Mentally unwrapping the lines on the
cylinder to a flat surface will show that the lines perpendicular to the
centerline (along the width direction) _cannot_ stay on the surface of the
cylinder. As soon as they move away from the surface, the Gauss curvature
becomes non-zero. If these lines (which in turn define the surface) move
outward with respect to the cylinder surface we obtain transitional shape
characterized by a circle translating and rotating around a helix. Moving
inward is the same but with opposite curvature. Of they stay tangent
to the surface. The key point is that the singularity has in $P_{min}$ has been 
removed by the neutral surface moving away from the surface of the cylinder. In
the case of the grid lines are tangential to the cylinder surface, in the limit
$R \rightarrow 0$ we obtain a _helicoid_ at a finite value of $P$. The other
two cases may be considered to be twisted cylindrical surfaces.

## Helicoid to a flat plate

This is again without any issues as we have $R=0$ and the limit $P \rightarrow
\infty$ leads to a flat plate.

## Scattering patterns

:::{figure} images/3/fig-hr2flat-saxs.svg
:label: fig-hr2flat
:width: 100%
:align: center

SAXS/WAXS patterns for 2ML CdSe NPLs for different shapes during unrolling from
a helical ribbon to a flat plate.
:::

:::{figure} images/3/fig-hr2hc-saxs.svg
:label: fig-hr2hc
:width: 100%
:align: center

SAXS/WAXS patterns for 2ML CdSe NPLs for different shapes during transition from a
helical ribbon $\rightarrow$ helicoid $\rightarrow$ flat plate. For better
comparison between helicoid and a flat plate see [](#fig-hcsaxs). The case
$R=10, P=10.3$ is the limiting case for a helical ribbon shape. At these
parameter values it is essentially a cylinder. SAXS patterns for other cases,
e.g. where the edges are circular rather than linear as in
[](#fig-transition)(i,j) are more complicated and difficult to reason about.
:::

:::{warning}
We are dealing with static monodisperse shapes here. The _pathways_ being
talked about here may be far from physically realistic kinetic pathways.
:::
