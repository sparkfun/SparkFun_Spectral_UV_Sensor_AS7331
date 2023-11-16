---
icon: material/book-open-page-variant
---

The SparkFun Spectral UV Sensor - AS7331 (Qwiic) and Mini Spectral UV Sensor - AS7331 (Qwiic) feature the AS7331 UV sensor from ams OSRAM<sup>&copy;</sup> which measures UV radiation on three channels: UVA (320-400nm), UVB (280-320nm), and UVC (200-280nm). Each channel on the AS7331 has an individual photodiode with built-in interference filters to ensure high sensitivity and accuracy across all three channels. The AS7331 communicates over I<sup>2</sup>C so naturally we put it on a standard (1"x1") and Mini (1"x0.5") Qwiic breakouts to integrate into our [Qwiic Connect System](https://www.sparkfun.com/qwiic).

<section class="grid cards col-2"markdown>

-	<a href="https://www.sparkfun.com/products/23517">
	**SparkFun Spectral UV Sensor - AS7331 (Qwiic)**<br>
	**SKU:** SEN-23517

	---

	<figure markdown>
	![https://cdn.sparkfun.com/r/600-600/assets/parts/2/3/8/0/8/23517-Spectral-UV-Sensor_Feature.jpg](https://cdn.sparkfun.com/r/600-600/assets/parts/2/3/8/0/8/23517-Spectral-UV-Sensor_Feature.jpg)
	</figure>
	</a>

	<center>
    [Purchase from SparkFun :fontawesome-solid-cart-plus:{ .heart }](https://www.sparkfun.com/products/23517){ .md-button .md-button--primary }
    </center>

-	<a href="https://www.sparkfun.com/products/23518">
	**SparkFun Mini Spectral UV Sensor - AS7331 (Qwiic)**<br>
	**SKU:** SEN-23518

	---

	<figure markdown>
	![https://cdn.sparkfun.com/r/600-600/assets/parts/2/3/8/0/9/23518-Spectral-UV-Sensor-Mini_Feature.jpg](https://cdn.sparkfun.com/r/600-600/assets/parts/2/3/8/0/9/23518-Spectral-UV-Sensor-Mini_Feature.jpg)
	</figure></a>

	<center>
	[Purchase from SparkFun :fontawesome-solid-cart-plus:{ .heart }](https://www.sparkfun.com/products/23518){ .md-button .md-button--primary }
	</center>

</section>

This guide goes over the AS7331 UV sensor and other hardware on these Qwiic breakouts, how to assemble them into a circuit and how to use them with the SparkFun AS7331 Arduino library.

## Required Materials

In order to follow along with this guide, you'll need the following materials. You'll need a microcontroller to connect the breakouts to. The development boards listed below come with Qwiic connectors for easy connection using the Qwiic system:

<div class="grid cards" markdown>

-   <a href="https://www.sparkfun.com/products/19177">

    <figure markdown>
    ![SparkFun IoT RedBoard - ESP32 Development Board](https://cdn.sparkfun.com//assets/parts/1/8/8/0/0/ESP32_03.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/19177">
    **SparkFun IoT RedBoard - ESP32 Development Board**<br>
    DEV-20168
    </a>

-   <a href="https://www.sparkfun.com/products/18158">
    
    <figure markdown>
    ![SparkFun RedBoard Plus](https://cdn.sparkfun.com//assets/parts/1/7/4/8/7/18158-SparkFun_RedBoard_Plus-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/18158">
    **SparkFun RedBoard Plus**<br>
    DEV-18158
    </a>

-   <a href="https://www.sparkfun.com/products/15574">
    
    <figure markdown>
    ![SparkFun Thing Plus - Artemis](https://cdn.sparkfun.com//assets/parts/1/4/1/7/0/15574-SparkFun_Thing_Plus_-_Artemis-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/15574">
    **SparkFun Thing Plus - Artemis**<br>
    DEV-18158
    </a>

-   <a href="https://www.sparkfun.com/products/20168">

    <figure markdown>
    ![SparkFun Qwiic Pocket Development Board - ESP32-C6](https://cdn.sparkfun.com//assets/parts/2/3/0/8/6/22925_QwiicPocket_Feature1.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/22925">
    **SparkFun Qwiic Pocket Development Board - ESP32-C6**<br>
    DEV-22925
    </a>
</div>

If your chosen microcontroller is not already Qwiic-enabled, you can add that functionality with one or more of the following items:

<div class="grid cards" markdown>

-   <a href="https://www.sparkfun.com/products/15081">

    <figure markdown>
    ![SparkFun Qwiic Cable Kit](https://cdn.sparkfun.com//assets/parts/1/3/4/3/1/15081-_01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/15081">
    **SparkFun Qwiic Cable Kit**<br>
    KIT-15081
    </a>

-   <a href="https://www.sparkfun.com/products/14495">
    
    <figure markdown>
    ![SparkFun Qwiic Adapter](https://cdn.sparkfun.com//assets/parts/1/2/5/5/1/14495-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/14495">
    **SparkFun Qwiic Adapter**<br>
    DEV-14495
    </a>

-   <a href="https://www.sparkfun.com/products/14352">
    
    <figure markdown>
    ![SparkFun Qwiic Shield for Arduino](https://cdn.sparkfun.com//assets/parts/1/2/3/4/3/14352-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/14352">
    **SparkFun Qwiic Shield for Arduino**<br>
    DEV-14352
    </a>

-   <a href="https://www.sparkfun.com/products/16790">

    <figure markdown>
    ![SparkFun Qwiic Shield for Thing Plus](https://cdn.sparkfun.com//assets/parts/1/5/6/9/7/16790-SparkFun_Qwiic_Shield_for_Thing_Plus-05.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/16790">
    **SparkFun Qwiic Shield for Thing Plus**<br>
    DEV-16790
    </a>
</div>

You will also need at least one Qwiic cable to connect your breakout to your microcontroller:

<div class="grid cards" markdown>

-   <a href="https://www.sparkfun.com/products/17259">

    <figure markdown>
    ![Flexible Qwiic Cable - 100mm)](https://cdn.sparkfun.com//assets/parts/1/6/2/4/6/17259-Flexible_Qwiic_Cable_-_100mm-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/17259">
    **Flexible Qwiic Cable - 100mm**<br>
    PRT-17259
    </a>

-   <a href="https://www.sparkfun.com/products/17260">
    
    <figure markdown>
    ![Qwiic Cable - 50mm](https://cdn.sparkfun.com//assets/parts/1/6/2/4/7/17260-Flexible_Qwiic_Cable_-_50mm-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/17260">
    **Flexible Qwiic Cable - 50mm**<br>
    PRT-17260
    </a>

-   <a href="https://www.sparkfun.com/products/17257">
    
    <figure markdown>
    ![Flexible Qwiic Cable - 500mm](https://cdn.sparkfun.com//assets/parts/1/6/2/4/4/17257-Flexible_Qwiic_Cable_-_500mm-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/17257">
    **Flexible Qwiic Cable - 500mm**<br>
    PRT-17257
    </a>

-   <a href="https://www.sparkfun.com/products/17261">

    <figure markdown>
    ![Flexible Qwiic Cable - Female Jumper (4-pin)](https://cdn.sparkfun.com//assets/parts/1/6/2/4/8/17261-Flexible_Qwiic_Cable_-_Female_Jumper__4-pin_-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/17261">**Flexible Qwiic Cable - Female Jumper (4-pin)**<br>
    CAB-17261
    </a>
</div>

## Optional Materials

If you prefer a soldered connection or want to modify the solder jumpers on these Qwiic breakouts you you may need some of the products listed below:

<div class="grid cards" markdown align="center">

-   <a href="https://www.sparkfun.com/products/116">

    <figure markdown>
    ![Break Away Headers - Straight)](https://cdn.sparkfun.com//assets/parts/1/0/6/00116-02-L.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/116">
    **Break Away Headers - Straight**<br>
    PRT-00116
    </a>

-   <a href="https://www.sparkfun.com/products/14681">
    
    <figure markdown>
    ![SparkFun Beginner Tool Kit](https://cdn.sparkfun.com//assets/parts/1/2/8/8/3/14681-SparkFun_Beginner_Tool_Kit.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/14681">
    **SparkFun Beginner Tool Kit**<br>
    TOL-14681
    </a>

-   <a href="https://www.sparkfun.com/products/9200">
    
    <figure markdown>
    ![Hobby Knife](https://cdn.sparkfun.com//assets/parts/2/6/4/6/09200-Hobby_Knife-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/9200">
    **Hobby Knife**<br>
    TOL-09200
    </a>

-   <a href="https://www.sparkfun.com/products/14579">

    <figure markdown>
    ![Chip Quik No-Clean Flux Pen - 10mL](https://cdn.sparkfun.com//assets/parts/1/2/7/2/5/14579-Chip_Quik_No-Clean_Flux_Pen_-_10mL-01.jpg)
    </figure>
    </a>
    ---
    <a href="https://www.sparkfun.com/products/14579">**Chip Quik No-Clean Flux Pen - 10mL**<br>
    CAB-14579
    </a>
</div>

## Suggested Reading

We designed this board for integration into SparkFun's Qwiic connect system.  Click on the banner below to learn more about the [SparkFun Qwiic Connect System](https://www.sparkfun.com/qwiic).

<div style="text-align: center">
<table>
  <tr>
   <td>
   <div style="text-align: center"><a href="https://www.sparkfun.com/qwiic"><img src="./assets/img/Qwiic-registered-updated.png" alt="Qwiic Connect System" title="Click to learn more about the Qwiic Connect System!"></a></div>
   </td>
  </tr>
  <tr>
    <td><div style="text-align: center"><i><a href="https://www.sparkfun.com/qwiic">Qwiic Connect System</a></i></div></td>
  </tr>
</table>
</div>

Before getting started with this Hookup Guide, you may want to read through the tutorials below if you are not familiar with the concepts covered in them or want a refresher. If you are using either of the Qwiic Shields linked above, we recommend reading through their respective Hookup Guides before continuing with this tutorial:

<div class="grid cards hide col-4" markdown align="center">

-   <a href="https://learn.sparkfun.com/tutorials/8">
    <figure markdown>
    ![Serial Communication](https://cdn.sparkfun.com/c/264-148/assets/7/d/f/9/9/50d24be7ce395f1f6c000000.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/8">**Serial Communication**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/82">
    <figure markdown>
    ![I2C](https://cdn.sparkfun.com/c/178-100/assets/learn_tutorials/8/2/I2C-Block-Diagram.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/82">**I2C**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/62">
    <figure markdown>
    ![Logic Levels](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/2/Input_Output_Logic_Level_Tolerances_tutorial_tile.png)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/62">**Logic Levels**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/61">
    <figure markdown>
    ![Installing Arduino IDE](https://cdn.sparkfun.com/c/178-100/assets/learn_tutorials/6/1/arduinoThumb.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/61">**Installing Arduino IDE**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/15">
    <figure markdown>
    ![Installing an Arduino Library](https://cdn.sparkfun.com/c/178-100/assets/b/e/4/b/2/50f04b99ce395fd95e000001.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/15">**Installing an Arduino Library**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/112">
    <figure markdown>
    ![Serial Terminal Basics](https://cdn.sparkfun.com/c/178-100/assets/learn_tutorials/1/1/2/terminalThumb.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/112">**Serial Terminal Basics**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/664">
    <figure markdown>
    ![How to Work with Jumper Pads and PCB Traces](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/6/4/PCB_TraceCutLumenati.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/664">**How to Work with Jumper Pads and PCB Traces**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/684">
    <figure markdown>
    ![Qwiic Shield for Arduino & Photon Hookup Guide](https://cdn.sparkfun.com/c/178-100/assets/learn_tutorials/6/8/4/Qwic_Shield_Hookup_Guide-05.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/684">**Qwiic Shield for Arduino & Photon Hookup Guide**
    </a>

-   <a href="https://learn.sparkfun.com/tutorials/1107">
    <figure markdown>
    ![Qwiic Shield for Thing Plus Hookup Guide](https://cdn.sparkfun.com/c/178-100/assets/learn_tutorials/1/1/0/7/16138-SparkFun_Qwiic_Shield_for_Thing_Plus-01_Thumb.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/1107">**Qwiic Shield for Thing Plus Hookup Guide**
    </a>
</div>