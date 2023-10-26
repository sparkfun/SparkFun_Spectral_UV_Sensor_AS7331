---
icon: material/cog
---

## AS7331 Spectral UV Sensor

The AS7331 spectral UV sensor from ams measures UV radiation over three channels (UVA, UVB, and UVC). Each channel is isolated from the other and includes their own photodiode with a built-in filter to help with accuracy and interference from other channels.



The AS7331 has extensive configuration options to customize the sensor's responsiveness, sensitivity through adjusting the gain, clock speed, and conversion time, among others. These configuration options allow users to optimize the sensor for their application. For example, a high gain setting results in a more sensitive response from the sensor but a lower max detectable irradiance (in &micro;W/cm<sup>2</sup>) where a low gain has much less sensitivity but a much higher maximum detectable irradiance. For detailed information on the conversion equations and how all the available settings affect performance, refer to section 7.4 of the [datasheet](./assets/component_documentation/AS7331_DS001047_4-00.pdf) Note, these configurations apply across all three channels. It has four operating modes: Command (CMD), Continuous (CONT), Synchronized Start (SYNS), and Syncrhonized Start/End (SYND). The list below outlines the operating modes behaviors: 

* CMD Mode - Single measurement and conversion controlled by the I<sup>2</sup>C interface.
* CONT Mode - Continuous measurements and conversion on set intervals. 
* SYNS Mode - Synchronized start of measurements through the SYN pin.
* SYND Mode - Synchronized start and stop of measurements through the SYN pin.

 The sensor operates over I<sup>2</sup>C with a pin-configured I<sup>2</sup>C address supporting four separate addresses (the breakout board sets this to 0x74 by default). Refer to the [datasheet](./assets/component_documentation/AS7331_DS001047_4-00.pdf) for a complete overview of the AS7331.

## Qwiic and I<sup>2</sup>C Interfaces

Both boards include a pair of Qwiic connectors for the I<sup>2</sup>C interface (SDA, SCL, 3.3V, and GND) as well as a 0.1"-spaced plated through hole (PTH) header that includes the I<sup>2</sup>C interface as well as the SYNC and READY/INT pins.

## LEDs

These breakouts only have a red Power LED to indicate whenever the board is powered.

## Jumpers

??? note "Never modified a jumper before?"
	Check out our <a href="https://learn.sparkfun.com/tutorials/664">Jumper Pads and PCB Traces tutorial</a> for a quick introduction!
	<p align="center">
		<a href="https://learn.sparkfun.com/tutorials/664">
		<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/6/4/PCB_TraceCutLumenati.jpg" alt="Tutorial's thumbnail"><br>
        How to Work with Jumper Pads and PCB Traces</a>
	</p>

The boards have three solder jumpers labeled <b>PWR</b>, <b>A0</b>, and <b>A1</b>. The PWR jumper completes the power LED circuit. Open it to disable the Power LED to help reduce boards' current consumption. The A0 and A1 solder jumpers control the AS7331's I<sup>2</sup>C address. They default to tie both address pins to Ground to set the I<sup>2</sup>C address to <b>0x74</b>. The table below outlines the jumper positions for the four available I<sup>2</sup>C addresses:

<table>
	<tr>
		<th>A1</th>
		<th>A0</th>
		<th>Address</th>
	</tr>
	<tr>
		<td>GND</td>
		<td>GND</td>
		<td>0x74 (default)</td>
	</tr>
	<tr>
		<td>GND</td>
		<td>VDD</td>
		<td>0x75</td>
	</tr>
	<tr>
		<td>VDD</td>
		<td>GND</td>
		<td>0x76</td>
	</tr>
	<tr>
		<td>VDD</td>
		<td>VDD</td>
		<td>0x77</td>
	</tr>
</table>

## Board Dimensions

The board dimensions are illustrated in the drawing below; the listed measurements are in inches.

<figure markdown>
[![Board Dimensions](../assets/img/dimensions.png){ width="400" }](../assets/img/dimensions.png "Click to enlarge")
<figcaption markdown>
[Board dimensions (PDF)](../assets/board_files/dimensions.pdf) for the <Product Name>, in inches.
</figcaption>
</figure>


??? tip "Need more measurements?"
	For more information about the board's dimensions, users can download the [Eagle files](../assets/board_files/eagle_files.zip) for the board. These files can be opened in Eagle and additional measurements can be made with the dimensions tool.

	??? info ":octicons-download-16:{ .heart } Eagle - Free Download!"
		Eagle is a [CAD]("computer-aided design") program for electronics that is free to use for hobbyists and students. However, it does require an account registration to utilize the software.

		<center>
		[Download from<br>:autodesk-primary:{ .autodesk }](https://www.autodesk.com/products/eagle/free-download "Go to downloads page"){ .md-button .md-button--primary width="250px" }
		</center>
	
	??? info ":straight_ruler: Dimensions Tool"
		This video from Autodesk demonstrates how to utilize the dimensions tool in Eagle, to include additional measurements:

		<center>
		<div class="video">
		<iframe src="https://www.youtube.com/embed/dZLNd1FtNB8" title="EAGLE Dimension Tool" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
		</div>
		</center>