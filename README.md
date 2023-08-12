# PCB

## ECU REAR

To create the board using KiCad, the first step involved creating a new folder within the GitHub directory named "ECU_Rear."
Inside this folder, I copied the necessary footprints, 3D models, and symbols. It's important to ensure that everything is written in the standard KiCad format.

### Board Calculations:

Following that, the necessary calculations were performed to assign values to the components of the circuits.

#### Sensor RPM:

The first calculation was for the RPM sensor, considering that the motor has a maximum of 4000 RPM. It was necessary to multiply by 2, as we want the theoretical maximum value, and then multiply by 2 again, since the RPM signal has 2 peaks per revolution.

4000RPM * 2 = 8000RPM. 

The next step would be to convert RPM to Hertz.

F(Hz) = RPM/60.

Substituting the values, we arrive at the result of 133.33Hz. However, since the motor has 2 peaks per revolution, it's necessary to multiply this value by 2.

F(Hz) = 266.66

In order to achieve this frequency, it was necessary to determine the equivalent values of the resistor (R) and capacitor (C) through the low-pass filter. Using the formula:

Fc = 1/2πRC

Where Fc is the desired cutoff frequency.

Finding the values for Fc = 266.66Hz, R = 59K, and C = 10nF.

#### Sensor Velocidade:

To convert speed from km/h to Hertz, you need to know the linear speed = 60 km/h, the diameter of the wheel = 400 mm, and the number of pulses per revolution = 3. The formula used is:

Frequency (Hz) = (Linear Speed) / (2 * π * Radius) * (Number of Pulses per Revolution)
 
It was necessary to convert 60 km/h to m/s. 

Velocity (m/s) = Velocity (km/h) * (1000 m / 3600 s)

Therefore, the velocity in m/s is: 16.67 m/s.

Afterwards, it was necessary to convert 400mm to meters, resulting in the value of 0.4m. Now that the results are in the correct units of measurement, you just need to substitute them into the frequency formula.

F(Hz) = 79,57Hz.

After using the low-pass filter formula, we found the values of Fc = 79.57Hz, R = 200K, and C = 10nF.

#### Fuel Sensor: 

In the case of the fuel system, the low-pass filter is used to remove electromagnetic interference. We use a default value of 10MHz as the desired cutoff frequency (Fc).

We directly substituted the values into the low-pass filter formula and found the values of Fc = 10kHz, R = 1.5k, and C = 10nF.

