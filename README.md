# ee-cse371-lab-3-display-interface-solved
**TO GET THIS SOLUTION VISIT:** [EE-CSE371 Lab 3-Display Interface Solved](https://www.ankitcodinghub.com/product/ee-cse371-lab-3-display-interface-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;99236&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;EE-CSE371 Lab 3-Display Interface Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="section">
<div class="layoutArea">
<div class="column">
Display Interface

</div>
</div>
<div class="layoutArea">
<div class="column">
Lab Objectives

</div>
</div>
<div class="layoutArea">
<div class="column">
In this lab, we will learn how to display images from an FPGA. We will use the LabsLand DE1-SoC VGA video-out port to display images on a computer monitor.

Background Information

The DE1-SoC FPGA includes a video-out port with a VGA controller that can be connected to a standard VGA monitor. The VGA controller supports a screen resolution of 640 × 480. The image that is displayed by the VGA controller is derived from two sources: a pixel buffer, and a character buffer. Only the pixel buffer will be used in this exercise, hence we will not discuss the character buffer.

Pixel Buffer

The pixel buffer for the video-out port holds the data (color) for each pixel that is displayed by the VGA controller. The pixel buffer provides an image resolution of 640 × 480 pixels, with the coordinate 0,0 being at the top-left corner of the image.

Figure 1 (a) shows that each pixel color is represented as a 16-bit halfword, with five bits for the blue and red components, and six bits for green. As depicted in Figure 1 (b), pixels are addressed in the pixel buffer by using the combination of a base address and an (x, y) offset.

</div>
</div>
<div class="layoutArea">
<div class="column">
Figure 1: Pixel values and addresses.

</div>
</div>
<div class="layoutArea">
<div class="column">
1

</div>
</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="section">
<div class="layoutArea">
<div class="column">
You can create an image by writing color values into the pixel addresses as described above. A dedicated pixel buffer controller reads this pixel data from the memory and sends it to the VGA display. The controller reads the pixel data in sequential order, starting with the pixel data corresponding to the upper-left corner of the VGA screen and proceeding to read the whole buffer until it reaches the data for the lower-right corner. This process is then repeated, continuously. You can modify the pixel data at any time, by writing to the pixel addresses. Writes to the pixel buffer are automatically interleaved in the hardware with the read operations that are performed by the pixel buffer controller.

It is also possible to prepare a new image for the VGA display without changing the content of the pixel buffer, by using the concept of double-buffering. In this scheme two pixel buffers are involved, called the front and back buffers. You don’t need to worry about double-buffering for this lab.

Drawing

In this lab, you will learn how to implement a simple line-drawing algorithm in hardware.

Drawing a line on a screen requires coloring pixels between two points (x1, y1) and (x2, y2), such that the pixels represent the desired line as closely as possible. Consider the example in Figure 4, where we want to draw a line between points (1, 1) and (12, 5). The squares in the figure represent the location and size of pixels on the screen. As indicated in the figure, we cannot draw the line precisely—we can only draw a shape that is similar to the line by coloring the pixels that fall closest to the line’s ideal location on the screen.

</div>
</div>
<div class="layoutArea">
<div class="column">
We can use algebra to determine which pixels to color. This is done by using the end points and the slope of the line. The slope of our example line is 𝑠𝑙𝑜𝑝𝑒 = 𝑦2−𝑦1 = 4 . Starting at point

</div>
</div>
<div class="layoutArea">
<div class="column">
𝑥2−𝑥1 11

(1, 1) we move along the x axis and compute the y coordinate for the line as follows:

</div>
</div>
<div class="layoutArea">
<div class="column">
𝑦 = 𝑦1 + 𝑠𝑙𝑜𝑝𝑒 * (𝑥 − 𝑥1)

</div>
</div>
<div class="layoutArea">
<div class="column">
Figure 2: Drawing a line between points (1,1) and (12, 5).

</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="section">
<div class="layoutArea">
<div class="column">
Thus, for column 𝑥 = 2, the y location of the pixel is 1 + 4 (2 − 1) = 11

</div>
<div class="column">
15 . Since pixel locations 11

</div>
</div>
<div class="layoutArea">
<div class="column">
are defined by integer values we round the y coordinate to the nearest integer, and determine that in column 𝑥 = 2 we should color the pixel at 𝑦 = 1. For column 𝑥 = 3 we perform the

</div>
</div>
<div class="layoutArea">
<div class="column">
calculation 𝑦 = 1 + 4 (3 − 1) = 11

</div>
<div class="column">
19 , and round the result to 𝑦 = 2. Similarly, we perform 11

</div>
</div>
<div class="layoutArea">
<div class="column">
such computations for each column between x1 and x2.

The approach of moving along the x axis has drawbacks when a line is steep. A steep line spans more rows than it does columns, and hence has a slope with absolute value greater than 1. In this case, our calculations will not produce a smooth-looking line. Also, in the case of a vertical line we cannot use the slope to make a calculation. To address this problem, we can alter the algorithm to move along the y axis when a line is steep.

The algorithm described above is called Bresenham’s line algorithm. Pseudo-code for an implementation of this algorithm is given in Figure 3. The first 15 lines of the algorithm make the needed adjustments depending on whether or not the line is steep. Then, in lines 17 to 22 the algorithm increments the x variable one step at a time and computes the y value. The y value is incremented when needed to stay as close to the ideal location of the line as possible. Bresenham’s algorithm calculates an error variable to decide whether or not to increment the y value. The version of the algorithm shown in Figure 3 uses only integers to perform all calculations. To understand how this algorithm works, you can read about Bresenham’s algorithm in a textbook or by searching for it on the internet.

You may find a simple C version of Bersenham’s algorithm on this page:

http://members.chello.at/easyfilter/bresenham.html

This implementation differs slightly from the pseudo-code shown in Figure 3, but the results are the same.

</div>
</div>
<div class="layoutArea">
<div class="column">
3

</div>
</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="section">
<div class="layoutArea">
<div class="column">
1 2 3 4 5 6 7 8 9

<pre>10
11
12
13
14
15
16
17
18
19
21
22
23
24
25
26
</pre>
Task 1

</div>
</div>
<div class="layoutArea">
<div class="column">
draw line(x0, x1, y0, y1)

</div>
</div>
<div class="layoutArea">
<div class="column">
boolean is_steep = abs(y1 − y0) &gt; abs(x1 − x0) if is_steep then

swap(x0, y0)

swap(x1, y1) ifx0&gt;x1then

swap(x0, x1) swap(y0, y1)

int delta_x = x1 − x0

int delta_y = abs(y1 − y0)

int error = −(delta_x / 2)

inty=y0 ify0&lt;y1theny_step=1elsey_step=−1

forxfromx0tox1 if is_steep then

draw_pixel(y,x) else

draw_pixel(x,y) error = error + delta_y if error ≥ 0 then

y = y + y_step

error = error − delta_x

Figure 3: Pseudo-code for a line-drawing algorithm.

</div>
</div>
<div class="layoutArea">
<div class="column">
Your task for lab 3 is to implement Bresenham’s line algorithm in SystemVerilog and compile it onto labsLand FPGA to draw lines on a computer monitor. Some files have been uploaded to Canvas to make this easier.

Perform the following:

<ol>
<li>Download the “lab3template.zip” file from Canvas. This is a compressed folder containing a full Quartus project with some files that will help you work with the VGA output of the DE1 board.</li>
<li>Observe that the project contains three SystemVerilog files:</li>
</ol>
a. VGA_framebuffer.sv, a driver for the VGA port of the board. You don’t need to edit or

understand this file, but you might notice it uses a very large framebuffer register,

</div>
</div>
<div class="layoutArea">
<div class="column">
4

</div>
</div>
</div>
</div>
<div class="page" title="Page 5">
<div class="section">
<div class="layoutArea">
<div class="column">
similar to what was described above. The ternary operator on the last line of this file

controls the colors of the lines you’ll be drawing.

<ol start="2">
<li>line_drawer.sv, a skeleton file for you to add your code to implement Bresenham’s
algorithm.
</li>
<li>DE1_SoC.sv, a top-level module which instantiates both of the above modules. This
should compile and function without any editing on your part, but you are free to do

whatever you want with it.
</li>
</ol>
3. Implement Bresenham’s line algorithm.

Some notes about the line_drawer.sv module:

<ol>
<li>The module takes inputs x0, y0, x1, y1 corresponding to the coordinate pairs (x0, y0)
and (x1, y1). Your task is to draw the line of pixels that best connects these coordinate

pairs.
</li>
<li>The module outputs x and y. These are the pixels being drawn by your algorithm.
These coordinates should change by at most one pixel each clock cycle.
</li>
<li>As indicated in the file, you’ll need to create some local registers to keep track of things. Notice that the example is declared as signed. This will be a two’s complement binary number, where the MSB is the sign bit. Keep in mind that you’ll be doing signed arithmetic during this lab. If you display numbers as unsigned in ModelSim, you might
end up very confused.
</li>
</ol>
Bresenham’s algorithm can get complicated. Ultimately, you’ll want to be able to draw a line between any two arbitrary points on the monitor, regardless of whether you’re drawing to the left or right, up or down, or whether the line is steep or gradual. Instead of doing this all at once, you’ll probably want to work in smaller steps.

The following are suggestions on how to approach this problem, but you can complete this task in whatever way makes the most sense to you.

<ol>
<li>Assume x0 = x1 or y0 = y1 and use the line_drawer.sv file to draw perfectly straight lines</li>
<li>Assume that (x0, y0) will be (0,0) and x1 = y1. That is, design an algorithm that only draws
perfectly diagonal lines from the origin
</li>
<li>Modify your algorithm to draw perfectly diagonal lines from any arbitrary starting point</li>
<li>Modify your algorithm to handle lines with gradual slopes, such as a line from (0,0) to
(100, 20)
</li>
</ol>
Demonstrate that your line algorithm can generate a line between any two coordinates on the monitor. To enable the VGA display, select “VGA” for “User interface” on LabsLand.

</div>
</div>
<div class="layoutArea">
<div class="column">
5

</div>
</div>
</div>
</div>
<div class="page" title="Page 6">
<div class="section">
<div class="layoutArea">
<div class="column">
Task 2

Modify the DE1_SoC.sv file to implement the following:

<ol>
<li>Use your line algorithm to draw a line on the monitor and animate it to move around the
screen.
</li>
<li>Implement a reset that, when activated, clears the screen by drawing every pixel to be
black. You’ll probably need to modify the arguments being passed to the VGA_framebuffer module to choose between drawing black or white.
</li>
</ol>
Demonstrate that you are able to animate an object moving around the screen and that your reset feature clears the monitor.

Lab Demonstration and Submission Requirements

<ul>
<li>● &nbsp;While working on the lab, on Padlet, write about a problem you had in the lab and the fix to it, and share a tip or trick you learned. You can also share an aha moment that you discovered while working on the lab. Avoid duplicating comments made by your classmates. NO videos for this Padlet task, please use textual comments. The link to the Padlet can be found in the corresponding Canvas assignment. Please note that the grace period does not apply to this portion of the lab.</li>
<li>● &nbsp;Record a demo video for each of the tasks in this lab. The length of each video is expected to be 2-3 minutes. You will need to demonstrate the soundness of your design by executing the design on the FPGA. You do not need to include Modelsim simulations in your demo for this lab. You only need to demonstrate the functionality of your system. Your demo video must be a screen recording created from software like ActivePresenter or Zoom. Please refer to the grading rubric on Canvas. Please note that the grace period does not apply to this portion of the lab.</li>
<li>● &nbsp;Write a Lab Report, as framed by the Lab Report Outline document on Canvas. Comment your code. Follow commenting guidelines as discussed in the Commenting Code document on Canvas. Please include the results of simulation in your lab report. Submit your lab report as a pdf file and all of your SystemVerilog files on Canvas. Please refer to the grading rubric on Canvas. As the grace period applies to the lab report and code assignment, you may submit it up to 2-days late without receiving a late penalty.</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
6

</div>
</div>
</div>
</div>
