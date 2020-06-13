# Bandgap Reference Circuit
The aim of this project is to design a Bandgap Reference Circuit which generates a constant,stable reference voltage independent to temperature variations.In any System on Chip(SoC) the need for reference voltage is imminent.In almost all the analog IP blocks like Analog to Digital Converters,Low Dropout Voltage Regulators etc require this Voltage.
# Installation steps for LTSpiceXVII Tool
The Design and Simulations of this Bandgap Reference Circuit are done using LTSpiceXVII Tool.The detailed steps for the installation of LTSpiceXVII tool are given below.

1.Click [here](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) to download the LTSpiceXVII Tool.

2.Click on `Download for Windows 7, 8 and 10` to get the `.exe` file for installation.

![download LTSPICE](https://user-images.githubusercontent.com/26677041/84537595-b02ada80-ad0d-11ea-93f8-31fd166bb32b.PNG)

3.In the `Downloads` section `LTspiceXVII.exe` is present.Use this file to install LTSpiceXVII tool on computer.

# Simulation Setup
The steps for Bandgap Reference circuit SPICE simulations are given below.
* 1.Open the LTSpiceXVII tool and Clik on `File` in the tool bar.

     ![File](https://user-images.githubusercontent.com/26677041/84565859-fb82ce80-ad89-11ea-90b9-cf9ab1d03a54.PNG)

* 2.Click on `Open` and select the BGR.asc file.

     ![open](https://user-images.githubusercontent.com/26677041/84565860-fcb3fb80-ad89-11ea-83f6-1eb66e21e05d.png)

* 3.The Schematic of the Bandgap Reference circuit will be opened.

  ![SChematic1](https://user-images.githubusercontent.com/26677041/84565863-fde52880-ad89-11ea-8ed6-d200b7935026.png)

* 4.In the menu bar, click on `Simulate` and select `Edit Simulation Cmd`.

   ![simulate](https://user-images.githubusercontent.com/26677041/84565993-2f122880-ad8b-11ea-93e7-f58376179007.png)

* 5.A transient analysis window is displayed.
* 6.Enter the values for `Stop Time`, `Time to start saving data` and `Maximum time step`.

  ![transient analysis](https://user-images.githubusercontent.com/26677041/84565999-31748280-ad8b-11ea-842a-2a163d9b1618.PNG)

* 7.A SPICE script of that transient analysis is obtained.Place it near the Schematic.

  ![trans](https://user-images.githubusercontent.com/26677041/84565998-30dbec00-ad8b-11ea-8e08-1e461fde2a8a.png)

* 8.To do simulation at various temperatures,a SPICE directive is to be used which is present at the last of tool bar with symbol `.op`.

  ![SPICE directive](https://user-images.githubusercontent.com/26677041/84565996-30435580-ad8b-11ea-8048-7045b1463295.png)

* 9.Write the command `.temp -40 -30 -10 20 40 50 80 110` in the SPICE directive and place it near the schematic.

  ![spice_direc](https://user-images.githubusercontent.com/26677041/84565997-30435580-ad8b-11ea-8a71-6572a6db36e2.PNG)

* 10.In the menu bar,select `Simulate` and and click on `Run`.

![run](https://user-images.githubusercontent.com/26677041/84566126-6a612700-ad8c-11ea-9e03-8af9b4391ada.png)

* 12.The waveforms at different temperatures are obtained.

![output waveform](https://user-images.githubusercontent.com/26677041/84566125-69c89080-ad8c-11ea-9dee-af15fa68dada.png)

# Contact Information
* PREETHAM M N R M.Tech VLSI System Design, NIT Warangal mnrpreetham1596@gmail.com
* KUNAL GHOSH Director, VSD Corp.Pvt.Ltd. kunalpghosh@gmail.com
* PHILIPP GÜHRING Software Architect at LibreSilicon Association pg@futureware.at
* Dr.GAVRAV TRIVEDI Co-Principal Investigator,EICT Academy,
  and Associate Professor,EEE Department,IIT Guwahati trivedi@iitg.ac.in
