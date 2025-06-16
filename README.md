# ENGR 102 Lab Topic 2 (individual)

## Activities
This lab consists of three individual activities. Please submit the following files to Gradescope. Check out the [Frequently Asked Questions](#frequently-asked-questions) below. **Please include the individual header in your ~.py files.**

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
In the team lab, your team put together a program that interpolated between two position values based on the time values when each positon was observed. This was a one-dimensional (1D) interpolation, since you were interpolating only a single value, the distance traveled by the ISS. You are now going to extend that program to one that will linearly interpolate between two points in 3D. Let’s say we are tracking the change of a satellite’s position with time. So, at time t0 the position is (x0, y0, z0) and at time t2 the position is (x2, y2, z2). What is the position (x1, y1, z1) at some time t1 between t0 and t2?

Refer again to the Linear Interpolation material associated with the team lab (posted on Canvas). That material describes the development of the equation representing linear interpolation of a dependent variable y versus an independent variable x. For the current problem, what varies linearly with what? What are the dependent variable(s)?  What are the independent variable(s)?

Let’s assume that each of the position variables (x, y, z) varies linearly with time (t). Therefore, time (t) is the independent variable in each case. This means we can perform linear interpolation three separate times to get what we need. This can be done in three steps: 1) linearly interpolate between (t0, x0) and (t2, x2) for t1 with x1 as the result; 2) repeat for (t0, y0) and (t2, y2) for t1 with y1 as the result; 3) repeat for (t0, z0) and (t2, z2) for t1 with z1 as the result. The result will be (x1, y1, z1) associated with time t1.

<ol>
<li>Write a program named <code>more_linear_interpolation.py</code> that will take two observed 3D positions at two points in time, and then will calculate the 3D position at a third point in time. Let’s consider only times between the two observed times. You should output the x, y, and z values for that position on separate lines. Begin by identifying the variables you will use, the names for those variables, and the computations that should occur for those variables. Then, write a program that will output the 3D position of the interpolated point on 3 separate lines.

For this initial program, use the following data values:
- At time 12 seconds, observed position was (8, 6, 7) meters
- At time 85 seconds, observed position was (-5, 30, 9) meters
- You want to find the position at time 30 seconds

Example output:
```
At time 30.0 seconds:
x1 = 4.794520547945206 m
y1 = 11.917808219178081 m
z1 = 7.493150684931507 m
```
</li>
<li>Now, add to your file <code>more_linear_interpolation.py</code> from above. Modify your program in the following ways:
<ul>
    <li>When printing the position, follow the output by a line of dashes (“<code>-----------------------</code>”).</li>
    <li>Instead of just computing the interpolation at one point and printing the result, you will now compute it at 5 points. You may copy and paste the portion of your code that is needed to recompute interpolation 5 times. </li>
    <li>Create variables for the <strong>starting</strong> time of interpolation, and the <strong>ending</strong> time of interpolation. Display the results from interpolating at 5 points, <strong>evenly spaced</strong> from the beginning time to the ending time, inclusive.</li>
    <li>Interpolate, starting at time 30 seconds and ending at time 60 seconds, printing the result each time. The line of dashes will separate each computation. (<strong>Note:</strong> later we will see how we can do this more efficiently, without copying-and-pasting code, but for now, copy-and-paste your code.)</li>
</ul>

Example output (first two times only):
```
At time 30.0 seconds:
x1 = 4.794520547945206 m
y1 = 11.917808219178081 m
z1 = 7.493150684931507 m
-----------------------
At time 37.5 seconds:
x2 = 3.4589041095890414 m
y2 = 14.383561643835616 m
z2 = 7.698630136986301 m
```
</li>
</ol>

## Python Code Soup
Create a program named `python_code_soup.py` consisting of **only** the following lines of code to produce the output shown below. You may put these lines of code in any order, and can re-use the lines as much as you want. There is more than one way to achieve the result – try to see if you can obtain the output using fewer lines of code. **Hint**: you can only print `z` to the screen, so you have to build the value of `z` that you want using the other statements, then print `z`.

```python
x = 1
y = 10
z = 0
x = y
x += 1
y += x
y *= x
z += x
z += y
print(z)
```
You may also use blank lines and `#` style comments in your code (including the header), **everything else will be marked as “not allowed”**

For example, say that you wanted to print the number `1` to the screen. The following lines would do the trick:
```python
z = 0
x = 1
z += x
print(z)
```

Your program should print out the following, when run:
```
1
29
102
100000000000000
8675
```
Note: The fourth line is 10<sup>14</sup>


## Frequently Asked Questions
1. **Do I have to add comments to my code?** YES! Comments are how you communicate to your future self and to others. It also helps us follow your thinking process and makes it easier to grade and give feedback. Plus, you'll lose points on assignments if you don't comment your code!
2. **Can I use stuff we haven't learned yet?** Yes and no. If you understand how to use concepts we haven't covered yet (loops, etc) and can do so correctly, feel free to use them on the labs, unless stated otherwise. However, if you're pulling code snippets from somewhere and don't fully understand what you're doing, it's better not to. All of the lab assignments are written so that you only need concepts we have covered so far in class. If you're struggling to figure out how to do a problem, ask during class for help. *Also, if you use concepts we haven't covered yet on a team assignment, make sure EVERYONE on your team understands it.*
3. **Activity 2 part 2, what points do I use for linear interpolation?** Use the same points that you did in part 1. Actually, START with your code from part 1 and add/modify for part 2!
4. **Activity 3 Gradescope says I didn't use only the given lines of code. What did I do wrong?** Look at the failed testcase and look at the feedback. It should have `not allowed: <line of code>`, that's the line that you need to remove. It's okay to have blank lines, `#` style comments, or extra spaces, but make sure you remove any triple quote strings or lines not present in the template.

Have a question you don't see here? Email your instructor!


Based upon Dr. Keyser’s Original<br/>
Revised Summer 2025 SNR
