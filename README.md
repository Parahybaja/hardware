# Hardware v2

<p align="center">
    <img src="renders/UECU-layout.PNG" alt="UECU layout" height="350">
    <img src="renders/UECU_3D-1.png" alt="UECU 3D 1" height="350">
    <img src="renders/UECU_3D-2.png" alt="UECU 3D 2" height="350">
    <img src="renders/UECU_3D-3.png" alt="UECU 3D 3" height="350">
</p>

<p align="center">
    <img src="renders/module-layout.PNG" alt="module layout" height="350">
    <img src="renders/module_3D-1.png" alt="module 3D 1" height="350">
    <img src="renders/module_3D-2.png" alt="module 3D 2" height="350">
    <img src="renders/module_3D-3.png" alt="module 3D 3" height="350">
</p>

## UECU

Universal Electronics Control Unit

## Module

The Accelaration and Velocity test module

### Signal Cleaning

A signal cleaning stage was employed in the digital inputs of each sensor with the aim of eliminating electromagnetic interference in the data transmission line. For this purpose, a passive low-pass filter with a cutoff frequency of 1GHz was implemented.

To achieve the desired cutoff frequency, based on a resistor of *2.2k* ohms, chosen to maintain the optimal current for the optocoupler's LED, the following calculations were made:

$$
F_c = \frac{1}{{2 \pi R C}}
$$

$$
C = \frac{1}{{F_c \cdot 2 \pi R}}
$$

$$
C = \frac{1}{{1 \text{GHz} \cdot 2 \pi \cdot 2.2k}}
$$

$$
C \approx 72 \text{pF}
$$
