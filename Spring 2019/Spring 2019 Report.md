# StaRS Filter Theory, Spring 2019
#### Barbara Oramah, Lainey Reed, Pablo Alonso Alguacil and Ronya Strom
##### 12th April, 2019 **[Update the date]**

**[Sidney: Hey team! I'll be commenting in these bolded square brackets.]**

**[Did you guys remove Felix's comments from your last submission? Please don't do that because I can't see if you properly address comments and resolve them.]**

**[Overall: Nice work! Please address my comments on grammar, past tense, figure labeling, and Python commenting for next time. Consider writing a walk-through of how influent passes through your apparatus.]**

### Abstract

Stacked Rapid Sand (StaRS) Filtration is the last stage in an AguaClara treatment plant. The filters are used to further reduce the turbidity of water to meet EPA standards of 0.3 NTU or less. As a whole, the StaRS subteam is working to develop a mathematical model to describe sand filtration. This semester, the StaRS Filter Theory team will be running experiments with the three newly constructed StaRS filters with varying sand grain sizes. This research will show the extent to which sand grain size has an effect **[effect?]** on filter performance.


### Table of Contents

- [Introduction](#Introduction)
- [Literature Review](#Literature-review)
- [Previous Works](#Previous-Works)
- [Bibliography](#Bibliography)
- [Experimental Apparatus](#Experimental-Apparatus)
- [Future Work](#Future-Work)
- [Manual](#Manual)
  - [Connecting Four Turbidimeters to ProCoDa](#Connecting-Four-Turbidimeters-to-ProCoDa)
- [Appendix](#Appendix)
  - [StaRS Filter Theory Experimental Python Documentation](#StaRS-Filter-Theory-Experimental-Python-Documentation)


### Introduction
Sand filtration has been used since ancient times. In AguaClara water treatment plants, a common type of sand filtration is used - rapid (gravity) sand filtration. This filtration method requires the use of a chemical coagulant, polyaluminum chloride (PACl **[We write PACl]**), to aggregate small particles (flocs) to increase the ease of particle filtration. This filter design has proven to reduce turbidity below 0.3 NTU, which meets the EPA standards. Experimentation performed on the model sand filter in the lab and the sand filters in the water treatment plants built in Honduras have proved the effectiveness of StaRS filters.

The goal of the StaRS Filter Theory sub-team is to develop a mathematical model describing the filter performance. To do so, the relevant filtration parameters must be determined through experimentation. These parameters can then be used to optimize filter performance for minimum effluent turbidity and maximum failure time. The filter parameters that have been investigated by previous sub-teams include coagulant dosage, influent flow rate, influent turbidity, backwash duration (e.g. the time needed for the system to clean itself between runs) and floc size. The Spring 2019 team will be  **[Try to use consistent past tense]** running experiments and analyzing the performance with the 3 new StaRS filters that were built by the previous team. Each of the filters contain a layer of sand, differing in their sand grain size.

Last semester, while focusing on fabricating three new filters, the team developed a hypothesis for how sand grain size affects filter performance. The team hypothesized that the filter with the largest sand grains would have the shortest failure time. This hypothesis has not changed within the Spring 2019 team. Failure time corresponds to the time taken for the filter performance efficiency to decrease drastically. The team expects that flocs will be deposited along the sand pores at the same rate in every filter because the rate of the influent stream will be held constant. However, the volume of the filter will be held constant, so when sand grain size increases, the number of sand grain pores in the filter decreases. Ultimately, this means that for a filter filled with larger sand grains, there will be fewer sand pores active at one time. This is demonstrated in Figure 1. This decrease in pore number may cause the active filtration zone to move through the filter faster, leading to a quicker failure time.


<p align="center">
<img src="https://github.com/AguaClara/stars_filter_theory/blob/master/Fall%202018/Images/sand.jpg?raw=true" heights=720 width=1260>
</p>

<p align="center">
<b>Figure 1 </b>: Demonstrates that when sand grain sizes are larger, there are fewer pores in the filter.
</p>


The results of these experiments could hold major significance for filtration methods of AguaClara and other water filtration plants. If it is discovered that sand grain size does impact filter performance, the team will be able to determine the sand grain size that maximizes failure time while maintaining the desired effluent turbidity. This parameter would need to be included in a mathematical model that accurately describes StaRS filters. Moreover, using the optimum size of sand in future filters would lead to a longer period between backwash cycles, saving the AguaClara plants both time and resources.


### Literature Review

The team conducted a thorough literature review to understand the existing research on sand filtration. The team especially looked into how these other experiments took into account different parameters, especially grain size, in their mathematical models.

Many models of filtration include reentrainment, the process by which precipitated aggregate materials get unstuck from pores due to shear force from water and move through the filter, eventually sticking elsewhere ([Przekop & Gradon, 2016](https://doi.org/10.1515/cpe-2016-0033), [Tien et al., 1979](https://doi.org/10.1002/aic.690250302), [Yao et al., 1971](https://doi.org/10.1021/es60058a005)). The team will not be taking into account reentrainment, and instead will be assuming that particles either permanently bind to sand particles or completely pass through the system. Once experimentation begins, the team will try see the impact of neglecting reentrainment in our calculations.

One of the team's goals in varying sand grain size is to understand how the grain size influences ripening time and failure time. Ripening time is the time taken for the filter to reach maximum particle removal efficiency. Failure time is the time it takes for the filter to fail, measured by a dramatic increase in effluent turbidity. Other studies have found that pore size has an effect on ripening time, with smaller pores on a filter leading to longer ripening times ([Przekop & Gradon, 2016](https://doi.org/10.1515/cpe-2016-0033)). This study made the case that physical properties within the filter can affect its efficiency. In this semester, the physical property that the team will investigate is sand grain size.

Investigations into grain sizes of glass beads have found that grain size has less of an effect compared to changes in coagulant doses ([Chuang & Li, 1997](https://doi.org/10.1016/S1383-5866(97)00048-8)). Larger doses of coagulant lead to a shorter ripening time, but also lead to an increased rate of pore clogging and to an increase in the shear force in unclogged pores. However, grain size can have effects depending on the coagulant and flocculant dosages. In this study, a flocculant, separate from the coagulant, was used to further increase flocculation. The researchers found that larger grains in addition to both flocculant and higher coagulant dosages reduced the rate of pore clogging. They hypothesized that it was because larger aggregates were able to pass through the pores between the larger glass beads. In the future, the team will be varying both coagulant dosage and grain size, as was done in this study. However, sand will be used as a filter material, as is used in AguaClara plants. Furthermore, AguaClara plants only use PaCl, a coagulant, not both a coagulant and a flocculant. The flocculant increased the extent to which the reduction in clogging was observed within the study. The team would expect to see greater clogging than what was seen in this study in the larger sand grains.

As the semester progresses and experiments begin, the team hopes to review more literature to aid with our research.

### Previous Works

Previous StaRS Filter Theory teams focused on combining information from sand bed research with the effects of microscopic level physics and macroscopic filter performance. A visual model of constrictions between the sand grains was developed by previous StaRS Filter Theory teams from the conclusions of several experimental runs. Once the constriction model was developed, the StaRS teams moved to varying coagulant dosage, which was hypothesized to affect filter performance.

The Fall 2017 team systematically varied coagulant dosages to determine its effect on filter performance. The team ran the set of experiments twice. The first set was done by gradually increasing PACl dosage, labeled ‘step up’. The second set was obtained by decreasing the PACl dosages, labeled ‘step down’. They concluded from these experiments that lower coagulant dosages prolonged failure time compared to higher dosages. They also found out that backwashing the filter between filter runs for 20 minutes allowed for more consistent results.

The Spring 2018 team focused primarily on changing the density of floc particles and varying coagulant dosages. Varying coagulant dosages affects the size of the floc particles that enter the filter. By measuring the different floc sizes, the team was able to deduce that the size of flocs did affect the performance of the filter. Large flocs, caused by higher coagulant dosages, proved to make the performance worse. Figure 2 shows the experimental apparatus most typically used by previous teams.

<p align="center">
<img src="https://github.com/AguaClara/stars_filter_theory/blob/master/Fall%202018/Images/Apparatus%20Design.jpg?raw=true" heights=720 width=1260>
</p>

<p align="center">
<b>Figure 2 </b>: The schematic for the Spring 2018 experimental filter apparatus in filter mode.
</p>


The main goal of the Fall 2018 Team was to construct the apparatus for future experimentation. The team focused on building three 1-layered sand filters, each of them connected to a turbidimeter that would measure the NTU units of the filtered water. The team was also focused on creating a detailed manual for future teams. The prior filter design used by different teams was the 2-layer filter.

The 2-layered sand filter was first used by the Fall 2013 team and the design had not been changed until Fall 2018. The height of the sand bed was 40 cm, but due to the fluidization of the sand bed, an additional 30% of the height was needed. Fluidization happens when water is pumped backwards through the system in the backwash cycle, which causes the sand to rise and allows the pores to unclog. The final height of the filter was 60 cm. The filter had one inlet stream that drove water into the filter through a downward rectangular orifice at the center of the column, and two outlets near the top and bottom of the filter column.

In contrast, the 1-layered filter that Fall 2018 started to build was designed to have a sand bed of 20 cm. Calculations deemed a 30 cm filter as satisfactory for the requirements of the backwash cycle. To be on the safe side, the final height of the filter was decided to be 40 cm. The sand that would be used for the filters was sieved to get different diameters that ranged from 18-25, 25-35, and 35-45 mesh sizes. Porosity tests were conducted to understand the material properties of the sand. The filter columns were PVC pipes with a diameter of 0.5 inches, and one inlet and one outlet, instead of two.

The findings of the previous StaRS teams are crucial for understanding filter performance as well as choosing which variables to test to develop efficient filters.

### Experimental Apparatus

<p align="center">
<img src="https://raw.githubusercontent.com/AguaClara/stars_filter_theory/master/Spring%202019/Apparatus%20Design%20Spring%202019.png" heights=720 width=1260>
</p>

<p align="center">
<b>Figure 3 </b>: The  first schematic for the Spring 2019 experimental filter apparatus.
</p>

The Spring 2019 team slightly altered the design from the Fall 2018 team.  Figure 2 shows the design that the Team from Fall 2018 had and Figure 3 shows the new design. The two pumps from the Fall 2018 apparatus, which were on the backwash line (light blue) and before the effluent turbidimeters (Fig. 2),**(Fig. 3)** were combined into one pump which is located on the exit line, labelled 13 on the diagram (Fig. 3)**(Fig. 4)**. The team opted to place the necessary pump after the effluent turbidimeters instead of before in order to prevent the pump from altering the turbidimeter readings from the effluent flow. By removing this pump, the team intended to improve the efficiency of the apparatus, and prevent pumps from essentially competing with each other. The pump that was at the water inlet was considered redundant and removed. Therefore, the only pump needed for the water flow in the apparatus is near the exit. This design change had been effective for initial tests with only water, but ended up being improved upon further.

<p align="center">
<img src="https://raw.githubusercontent.com/AguaClara/stars_filter_theory/master/Spring%202019/Backwash%20Apparatus%20Design.png?raw=true" heights=720 width=1260>
</p>

<p align="center">
<b>Figure 4</b>: The current schematic for the Spring 2019 backwash set-up
</p>

**[Nice graphics!]**

After setting up the apparatus, more changes were made. Figure 4 is the schematic while Figure 5 is an image of the current iteration of the apparatus for the Spring 2019 StaRS Filter Team. The solenoid valves that were placed after each filter were removed. The backwash line was attached directly to the inlet and the outlet lines, with a solenoid valve to control the direction of flow.

The apparatus depicted in Figure 4 was designed to work in the following way in the filtering state, labelled in green. The water entered the system through the water inlet (1) and mixed with the clay, which has been pumped in from the clay-water solution (3,4). The turbidity was then measured in the influent turbidimeter (5). The PACl was pumped in and mixed with the clay solution in the contact chamber (6,7).  As the water ran through the flocculator, flocs began to form before the water reached the filters (8). A check valve prevented backwards flow (C) and the solenoid valve D was open to allow the passage of water. The water split and flowed into each filter (10-1,10-2,10-3), through an inlet at the top of the sand bed (9-1,9-2,9-3) then out of the respective outlet (11-1,11-2,11-3). The closed solenoid valve B forced the water through the outlets. A pressure sensor was attached to the inlet and outlet of each filter column. The treated water, still in three streams then moved into the effluent turbidimeters (12-1,12-2,12-3), which combined into one stream that was then pumped out of the system (Exit).

During backwash, labelled in red, water flows from the water inlet (1) and through the now open solenoid B. It runs backwards through the three turbidimeters and filters, entering the filter column through the outlets (11-1,11-2,11-3). Solenoid D was closed during backwash, preventing water from moving into the flocculator and the clay and PACl stocks. Water exited the filters from above, by passing through the now open solenoid valve B, and through the exit. This design is also pictured in Figure 5.

<p align="center">
<img src="https://github.com/AguaClara/stars_filter_theory/blob/master/Spring%202019/Apparatus%20Set-Up.png?raw=true" heights=720 width=1260>
</p>

<p align="center">
<b>Figure 5</b>: The experiment set-up for the Spring 2019 StaRS Team.
</p>



### Future Work

The team is currently working towards preparing a system to add the clay into the apparatus to ensure a desirable influent turbidity. The team needs to create a mixing system to prevent the clay from settling down with a stirrer, and create a structure to support that addition, as the bench is full.

The StaRS Spring 2019 team will be filling the filters with the varying sand grain sizes as well as determining the proper coagulant dosage that the system will require when running experiments. The code for determining the coagulant concentration can be found in the appendix. Methods for the team's experiments will need to be drafted into a manual.

Finally, the team needs to finish editing the ProCoDa method file.

### Bibliography

Chuang, C.J., & Li, K.-Y. (1997). Effect of coagulant dosage and grain size on the performance of direct filtration. Separation and Purification Technology, 12(3), 229–241. Retrieved from: https://doi.org/10.1016/S1383-5866(97)00048-8

Przekop, R., & Gradoń, L. (2016). Dynamics of particle loading in deep-bed filter. Transport, deposition and reentrainment. Chemical and Process Engineering, 37(3), 405–417. Retrieved from: https://doi.org/10.1515/cpe-2016-0033

Kuan-Mu Yao, Mohammad T. Habibian, and Charles R. O'Melia (1971). Water and waste water filtration. Concepts and applications. ACS publications, 5 (11), 1105-1112. Retrieved from: https://doi.org/10.1021/es60058a005.


### Manual

##### Connecting Four Turbidimeters to ProCoDa

To account for the 3 StaRS Filter, The Spring 2019 team requires 4 Turbidimeters in the experimental apparatus. The ProCoDa control box has limited inputs and outputs. Therefore, the team utilized a feature of the MicroTOL 4 Turbidimeter. The team was able to connect all the four turbidimeters so they all can be measured from one input.

The steps to achieve this are the following:

1. Connect the blue wires of each turbidimeters to form a chain. One of the ends needs to connect to the com port on the computer.

2. Press the mode button on the turbidimeter to get to "CONFIG", push the enter button until "ADDRESS" selection comes up.

3. Assign each turbidimeter to a different address (different numbers) using the up and down arrow. Once the number is selected, press the mode button to go back to AUTO.

4. In ProCoDa, open up the edit rules window, go to set points. Set up four states for each respective turbidimeter ID, call these "Turbidimeter X ID" (X being the address). These are all constants and the value should be the address.

5. Create another constant, call it  "turbidity meter com" or something similar. It should be below the ID. Set the value to whatever com port the turbidimeter daisy chain is hooked up to. If you don't know, set it to 1 and continue, step 7 has a way to find out if it's correct.

6. Set up four more states for each turbidimeter, for the actual turbidity data. We called them "Filter 1 Turbidity" etc. They should each be a variable. The units are NTU. Click on the little folder and navigate to this location: "C:
\ProgramData\ProCoDa\Functions\HF turbidimeter" (or equivalent) and select "HF modbus rtu.vi" as the file. Now, under selected set points, click the corresponding turbidimeter ID, and the turbidity meter com variable from step 5.

(Note: these two states correspond to the two values in the "Required Set Points below" box and their order should be the same in the selected set points as they are in the required set points box. If they aren't, you can't move them, so delete them and recreate them in the proper order. Once they are correct, the green lights will come on)

7. If everything is done correctly, the green light should come up, and the number in the value box in the ProCoDa variable should be the same as the value for the NTU on the actual turbidimeter. If it's not and each one gives a value of -999, keep changing the com port number until it is. If they aren't all -999 and the values simply are wrong, make sure the address is the same as the ID.



### Appendix

##### StaRS Filter Theory Experimental Documentation
-------
###### Calculations for Headloss
```python

#importing aguaclara packages needed for calculations
import aguaclara
#pyschem contains useful functions for calculations
import aguaclara.core.physchem as pc
#units package helps us convert to useful untis
from aguaclara.core.units import unit_registry as u
#math packages
import numpy as np
from aide_design.play import*

#Constraints:
# Filter diameter = 1 inch
# Backwash Velocity = 11 mm/s
# Filter Column length = 20 cm (old filters were 40cm)
# Temperature = 20 degrees Celsius
# Pipe Roughness = 0
# KMinor (constant) = 1

#Solving for:
# Filter Area, Nu (Viscosity Kinematic), Velocity (during filtering), headloss
# Filter Area and Nu are needed for headloss calculation

#First the geometry of the pipes was defined. inletpipe_ID is the diameter of the pipe and filter_D is the diameter of the filter. With the diameter, the internal area of the pipe was obtained.

inletpipe_ID = 0.25 * u.inch
filter_D= 1 * u.inch
pipe_A=pc.area_circle(inletpipe_ID)

#Further characteristics of the experimentation. Backwash velocity was estimated to be 11 mm/s, and the regular velocity is just a fraction of the former. For comparison purposes, we are using a length of 100 cm. With the geometry that was defined above and the velocity it is possible to obtain the flow rate.

backwash_v=11 * u.mm / u.s
Length= 100 * u.cm
velocity = backwash_v/6
flow_rate=(velocity*filter_A).to(u.ml / u.sec)

#Using this help function we determined that this function returns total head loss, major and minor
help(pc.headloss)

#More variables are defined. The roughness of PVC pipes was stimated to be zero, the temperature used was 20 ºC and the coefficient for minor losses 1. A function was called to obtain the vicosity based on the temperature.

print(flow_rate)
temp=20 * u.degC

Nu=pc.viscosity_kinematic(temp)
PipeRough=0 * u.mm
KMinor= 1

#With all the variables that have been defined, it was possible to obtian the headloss.

head_loss=pc.headloss(flow_rate, inletpipe_ID, Length, Nu, PipeRough, KMinor)
print(head_loss)
#Headloss was negligible

```
###### Calculations for PaCl concentration

```python
#importing aguaclara packages needed for calculations
import aguaclara
#pyschem contains useful functions for calculations
import aguaclara.core.physchem as pc
#units package helps us convert to useful untis
from aguaclara.core.units import unit_registry as u
#math packages
import numpy as np
from aide_design.play import*

#stock concentration in the lab now, may change as new stock is created
stock_concentration=70.28 *u.g/u.l
#We went with 2 mg/L because that is what was in our ProCoDa
final_concentration=2 *u.mg/u.l
final_volume=1* u.l
#Volume_stock=Volume_Final*Concentration_Final/Concentation_stock
#We wanted units of microliters
stock_volume=(final_concentration*final_volume/stock_concentration).to(u.microl)
print(stock_volume)
#Volume is: 28.46 microliters
# Now we can calculate volume needed in the future if the stock concentration changes

```


**[Add comments to your code to explain what is going on.]**
