# Bandgap Reference Circuit
The aim of this project is to design a Bandgap Reference Circuit which generates a constant,stable reference voltage independent to temperature variations.In any System on Chip(SoC) the need for reference voltage is imminent.In almost all the analog IP blocks like Analog to Digital Converters,Low Dropout Voltage Regulators etc require this Voltage.
# Ngspice
Ngspice is a mixed-level/mixed-signal electronic circuit simulator.
## Installation steps on Ubuntu
1.Open the teminal 
 
2.Type `sudo apt-get update -y` command in the teminal.
 
3.Now type `sudo apt-get install -y ngspice` command in the command, Ngspice will be installed on ubuntu.
## Simulation steps
 1.Git clone this repository in the ubuntu system.
 
 2.Go to `BandgapReference -> Ngspice` folder.
 
 3.Open terminal in `Ngspice` folder.
 
 4.Type `ngspice Vref,PTATandCTAT.net` and hit `enter`.
 
**Waveform for Vreference,PTAT and CTAT vs Temperature (from -40C to 125C) at resistive load of 100M ohms**

![Vref,PTATandCTAT](https://user-images.githubusercontent.com/26677041/85393621-f03e5880-b56a-11ea-93be-9b1cb5838dde.png)

 6.Type `ngspice VrefvsTemp.net` and hit `enter`.
 
 **Waveform for Vreference vs Temperature (from -40C to 125C) at resistive load of 100M ohms**

 ![VrefvsTemp](https://user-images.githubusercontent.com/26677041/85393623-f0d6ef00-b56a-11ea-9367-85140c6d0265.png)
  
 8.Type `ngspice VrefvsVdd.net` and hit `enter`.
 
 **Waveform for Vreference vs Vdd (from 2v to 4v) at resistive load of 100M ohms**
 
 ![VrefvsVdd](https://user-images.githubusercontent.com/26677041/85393624-f0d6ef00-b56a-11ea-850e-b8dbd2467024.png)
 
 14.Type `ngspice transientanalysis.net` and hit `enter`.
 
 **Waveform for Vreference vs time (from 0 to 100us) at load capacitance of 50pF at 27C temperature**
 
 ![transientanalysis](https://user-images.githubusercontent.com/26677041/85393626-f16f8580-b56a-11ea-87b9-c556fa067723.png)
 
  12.Type `ngspice temperaturecoefficient.net` and hit `enter`.
 
 **Waveform for Temperature Coefficient  vs temperature (from -40C to 125C) at load resistance of 100M ohms**
 
 ![temperaturecoefficient](https://user-images.githubusercontent.com/26677041/85393614-eddbfe80-b56a-11ea-819c-2f2b7dd8c4d6.png)
 
 10.Type `ngspice Voltagecoefficient.net` and hit `enter`.
 
  **Waveform for Voltage Coefficient  vs temperature (from -40C to 125C) at load resistance of 100M ohms**
 
 ![voltagecoefficient](https://user-images.githubusercontent.com/26677041/85393619-efa5c200-b56a-11ea-8206-0ee7005f8be3.png)

# LTSpiceXVII 
LTspice is a SPICE-based analog electronic circuit simulator computer software, produced by semiconductor manufacturer Analog Devices.
## Installation on Windows & Mac
1.Click [here](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) to download the LTSpiceXVII Tool.

2.Click on `Download for Windows 7, 8 and 10` to get the file for installation on windows.

3.Click on `Download for Mac 10.9+` to get the file for installation on Mac.

![download LTSPICE](https://user-images.githubusercontent.com/26677041/84537595-b02ada80-ad0d-11ea-93f8-31fd166bb32b.PNG)

3.In the `Downloads` section `LTspiceXVII.exe` is present.Use this file to install LTSpiceXVII tool on computer.
## Installation on Ubuntu
1.Open the terminal.

2.Type `sudo apt-get install wine` command in the terminal.

3.Then type `wget http://ltspice.linear-tech.com/software/LTspiceIV.exe` command in the terminal.

4.Finally type `wine LTspiceIV.exe` command which will install LTSpice in the ubuntu system. 

# Simulation Steps
The SPICE simulation steps for Current mirror based Bandgap Reference circuit are given below.
* 1.Download the `BGR_currentmirror` folder from this repository.
* 2.Open the LTSpiceXVII tool and Clik on `File` in the tool bar.

     ![File](https://user-images.githubusercontent.com/26677041/84565859-fb82ce80-ad89-11ea-90b9-cf9ab1d03a54.PNG)

* 3.Click on `Open` and select the BGR_currentmirror.asc file.

     ![open](https://user-images.githubusercontent.com/26677041/84565860-fcb3fb80-ad89-11ea-83f6-1eb66e21e05d.png)

* 4.The Schematic of the Bandgap Reference circuit will be opened.

![Schematic1](https://user-images.githubusercontent.com/26677041/85134054-83207f80-b259-11ea-9524-ae8c7bb1db99.PNG)
    
* 5.In the menu bar, click on `Simulate` and select `Edit Simulation Cmd`.

   ![simulate](https://user-images.githubusercontent.com/26677041/84565993-2f122880-ad8b-11ea-93e7-f58376179007.png)

* 6.An `Edit Simulation Command` window will be displayed.Select `DC sweep`.
* 7.Under 1st Source, enter `Name of 1st source to sweep` as *temp*, `Type of sweep` as *linear* , `Start value` as *-40*, `Stop Value` as *140*, `Increment` as *20* .

  ![dc sweep](https://user-images.githubusercontent.com/26677041/84700868-94277300-af71-11ea-9874-732eb74f3bba.PNG)

* 7.A SPICE script of that DC sweep analysis is obtained.Place it near the Schematic and save the Schematic.

  ![dcsweep1](https://user-images.githubusercontent.com/26677041/84700874-9558a000-af71-11ea-8e03-2c473aecebc8.PNG)

* 8.In the menu bar,select `Simulate` and and click on `Run`.

  ![run](https://user-images.githubusercontent.com/26677041/84566126-6a612700-ad8c-11ea-9e03-8af9b4391ada.png)

* 9.A waveform window appears.Now click on `Vref` wire on the schematic.The waveform corresponding to variation of Reference voltage w.r.t temperature is obtained.

To see the PTAT nature w.r.t temperature,measure the voltage across the `R1` resistor.This is done by placing the probe on one side of resistor, left click on the mouse and drag and place the probe on other side of resistor.

To see the CTAT nature w.r.t temperatre, click on the wire above `Q5` transistor.

The final waveform will be as shown in the Figure below.

  ![Vref,PTATandCTAT](https://user-images.githubusercontent.com/26677041/85134057-83b91600-b259-11ea-97fd-03ba694bb6af.png)

* 10.To get the variation of Reference voltage with power supply,Repeat the `Steps 5 & 6`.

* 11.Under 1st Source, enter `Name of 1st source to sweep` as *V1*, `Type of sweep` as *linear* , `Start value` as *2*, `Stop Value` as *4*, `Increment` as *0.2* .

* 12.Again repeat `steps 7 & 8`,A waveform window appears.Now click on `Vref` wire on Schematic. The waveform corresponding to varistion of reference voltgae w.r.t power supply is obatined.
The wavefrom will be as shown below.

  ![VrefvsVdd](https://user-images.githubusercontent.com/26677041/85134062-84ea4300-b259-11ea-9f55-33c27609a8ca.png)
  
The SPICE simulation steps for OpAmp based Bandgap Reference circuit  are given below.
* 1.Open the LTSpiceXVII tool and Clik on `File` in the tool bar.

* 2.Click on `Open` and select the BGR.asc file.

* 3.The Schematic of the Bandgap Reference circuit will be opened.

  ![SChematic1](https://user-images.githubusercontent.com/26677041/84565863-fde52880-ad89-11ea-8ed6-d200b7935026.png)

* 4.In the menu bar, click on `Simulate` and select `Edit Simulation Cmd`.

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
