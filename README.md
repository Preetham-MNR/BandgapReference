# Bandgap Reference Circuit
This Project is about generating a constant,stable reference voltage independent to temperature variations.
# Simulation Setup
First LTSpiceXVII tool is to be installed.The steps for SPICE simulation are given below.
 1.Open the LTSpiceXVII tool and Clik on `File` in the tool bar.
* 2.Click on `Open` and select the BGR.asc file.
* 3.The Schematic of the Bandgap Reference circuit will be opened.
* 4.In the menu bar, click on `Simulate` and select `Edit Simulation Cmd`.
* 5.A transient analysis window is displayed.
* 6.Enter the values for `Stop Time`, `Time to start saving data` and `Maximum time step`.
* 7.A SPICE script of that transient analysis is obtained.Place it near the Schematic.
* 8.To do simulation at various temperatures,a SPICE directive is to be used which is present at the last of tool bar.
* 9.Write the command `.temp -40 -30 -10 20 40 50 80 110` in the SPICE directive and place it near the schematic.
* 10.In the menu bar,select `Simulate` and and click on `Run`.
* 11.A probe appears in the schematic window.Touch the probe on the wire at the Vref label on the schematic.
* 12.The waveforms at different temperatures are obtained.
# Contact Information
* PREETHAM M N R M.Tech VLSI System Design, NIT Warangal mnrpreetham1596@gmail.com
* KUNAL GHOSH Director, VSD Corp.Pvt.Ltd. kunalpghosh@gmail.com
* PHILIPP GÜHRING Software Architect at LibreSilicon Association pg@futureware.at
* Dr.GAVRAV TRIVEDI Co-Principal Investigator,EICT Academy,
  and Associate Professor,EEE Department,IIT Guwahati trivedi@iitg.ac.in
