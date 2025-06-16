# ENGR 102 Lab Topic 2 (individual)

## Activities
This lab consists of three individual activities. Please submit the following files to Gradescope. Check out the [Frequently Asked Questions](#frequently-asked_questions) below. **Please include the individual header in your ~.py files.**

1. [Using Variables](#using-variables)
2. [More Linear Interpolation](#more-linear-interpolation)
3. [Python Code Soup](#python-code-soup)

## Using Variables
Convert your program from Lab: Topic 1 Activity #2 (Print Math) to a new program named `using_variables.py` that produces identical output. However, for all of the calculations, you are to instead create variables for all values that are either constants or are values that might vary in the calculation.

Recall the following example from Lab Topic 1:</br>
New code:	
```python
# Calculate/print area of rectangle of length 5 in and height 3 in
print("Area of rectangle is", 5 * 3, "in^2")
```

New output:	
```
Area of rectangle is 15 in^2
```

Now we know about variables and assignments statements, so let’s modify the code as follows:</br>
Newer code:	
```python
# Calculate/print area of rectangle of length 5 in and height 3 in
length = 5 # inches
height = 3 # inches
area = length * height  # in^2
print("Area of rectangle is", area, "in^2")  
```

Newer output:	
```
Area of rectangle is 15 in^2
```

Please note the following:
1.	You should pick **good** names for your variables.  
2.	You do not have to perform the entire computation in one line; you can use multiple lines to perform the computation if you want.
3.	It is OK to introduce variables to hold values that are not a “final” value. For example, if you were computing the area of a circle, you might store the radius in one variable, then the radius squared in another variable, and then later multiply that by pi to compute the area.

Produce output for the following calculations:
1.	The **Reynolds Number (Re)** is an important dimensionless quantity in fluid mechanics that is used to predict flow patterns in different fluid flow situations. It is the ratio of inertial forces to viscous forces given by the equation<br/>
$$\text{Re}=\frac{uL}{ν}$$<br/>
Calculate the Reynolds number for a fluid with velocity ($$u$$) 9 m/s, kinematic viscosity ($$ν$$) 0.0015 m^2/s, and a characteristic linear dimension ($$L$$) of 0.875 m.
2.	Calculate the wavelength of x-rays scattering from a crystal lattice with a distance between crystal layers of 0.029 nm, scattering angle of 35 degrees, and first order diffraction. **Bragg’s Law** describes the scattering of waves from a crystal using the equation<br/>
$$nλ=2d\sin⁡θ$$<br/>
The standard unit of wavelength in the SI system is nanometers (nm).
3.	The **Arps equation** is a mathematical model to forecast future production rates of oil and gas wells. Use the equation below to calculate the production rate of a well after 10 days, if it had an initial production rate ($$q_i$$) of 100 barrels/day, an initial decline rate ($$D_i$$) of 2/day, and a hyperbolic constant ($$b$$) of 0.8.<br/>
$$q(t)=\frac{q_i}{(1+bD_i t)^{(1⁄b)}}$$
4.	The **Tsiolkovsky rocket equation** describes the motion of a device that can apply acceleration to itself by expelling part of its mass with high velocity. The equation relates the change of vehicle velocity to the exhaust velocity ($$v_e$$) and initial ($$m_0$$) and final ($$m_f$$) masses of the vehicle as<br/>
$$Δv=v_e\ln⁡\left( \frac{m_0}{m_f} \right)$$<br/>
Calculate the change of velocity of a fighter jet for an initial mass of 11000 kg, final mass of 8300 kg, and exhaust velocity of 2029 m/s.

Example output:
```
Reynolds number is 5250.0
Wavelength is 0.03326743330836067 nm
Production rate is 2.8969356500320727 barrels/day
Change of velocity is 571.4470689735155 m/s
```


## More Linear Interpolation
description

## Python Code Soup
description

## Frequently Asked Questions



Based upon Dr. Keyser’s Original<br/>
Revised Summer 2025 SNR
