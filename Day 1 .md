**Name : Aditya Narayanan Raghavan**

**Grade : 8^th^ grade**

**School : National Public School, Rajajinagar, Bangalore**

**\*All pictures in the below document are taken from the digital chip
design course**

Level 3 :-

Arduino Board -- Made up of many components.

![Envistia Mall Arduino UNO R3 Microcontroller
Board](media/image1.jpeg){width="2.6770833333333335in"
height="2.6770833333333335in"}

Photo Credit -
https://www.ubuy.co.in/product/3V6KZCHAG-arduino-uno-r3-compatible-atmega328p-ch340-usb-microcontroller-board

Below diagram of processor --

![A computer screen shot of a computer Description automatically
generated](media/image2.png){width="4.44003280839895in"
height="2.516641513560805in"}

Typical requirements for making Arduino board are above.

Zoom in to the main Integrated Circuit --

![A drawing of a square with a square in the middle Description
automatically generated with medium
confidence](media/image3.png){width="2.9852701224846894in"
height="2.7371062992125985in"}

Photo Credits -
<https://electronics.stackexchange.com/questions/394554/soldering-0-4mm-pitch-qfn-48-chip>

The chip sits at the centre of the package (In the middle of the QFN-48
package)

Wire bonds connected to the chip are able to transfer all the signal
coming from the outside world to the integers of the chip.

![A computer screen shot of a computer chip Description automatically
generated](media/image4.png){width="4.095384951881015in"
height="2.6742957130358707in"}

Many parts in a chip --

1.  Pads -- Through pads you can send the signal inside the chip and
    vice versa

2.  Core -- The core is where all the digital logic sits. The AND Gate,
    OR Gate etc are found in the core

3.  Die -- Size of the entire chip

![A computer chip with many wires Description automatically
generated](media/image5.png){width="4.147049431321085in"
height="2.392386264216973in"}

Foundry -- A factory where chips get manufactured.

IP -- Intellectual Property.

Reason why the Foundry IPs are called like that as they need
intelligence to be made.

The RISCV SOC and the SPI are macros.

They are called macros as they are put digital logic.

To manufacture chips, there needs to be communication with Foundry.

RISC-V Architecture

If you have a C Program and you need it to run on a computer, then you
need to pass it through hardware to make it binary to get the required
output.

Another interface is required to be present between the flow and the
RISC-V architecture that is the hardware description language.

You need to implement this RISC -- V specifications using some RTL Ex :
Picorv32 cpu core

This rtl implements these specifications of the architecture to make the
layout.

Software applications to Hardware.

The application software first enters into the system software which
then converts the application into a binary language.

The majors system softwares are the OS, Compiler and the Assembler.

OS -- Handles IO Operations, Allocates memory and does the low level
system functions. The other function is to make sure that it turns into
a binary language.

Compiler -- Converts the program code into a set of instructions

The compiler turns it into a set of instructions which is dependent on
the hardware

Then the job of the assembler is to make the instructions into a binary
language.

Then the hardware receives the code and does the function specified.

Ex : Stopwatch --

The functions, which is written in a specific language, is put into a
compiler, and if the hardware is a RISCV, then the output of the
compiler will be a set of RISCV instructions, which then enter the chip
layout to perform the functions

![A screenshot of a computer screen Description automatically
generated](media/image6.png){width="4.355306211723534in"
height="2.144359142607174in"}

Input and Output of Compiler

Instructions act as an abstract interface between the C and the
Hardware.

The hardware only understands the HDL, so if you give it a set of 1s and
0s, it understands it needs to do something with that.

The instructions are put into the assembler which turn it into a binary
language.

SoC design and OpenLANE --

RTL to GDSII Flow --

Synthesis, Clock Tree Synthesis, Floor/Power Planning, Routing,
Placement, Sign Off.

Synthesis -- Converts RTL to a circuit out of components from the
standard cell library.

The standard cells have regular layouts.

![A diagram of a circuit board Description automatically generated with
medium confidence](media/image7.png){width="3.5734153543307086in"
height="2.3961679790026245in"}

Chip Floor Planning -- Partition the chip die between system building
blocks and then the I/O pads will be placed.

Macro Floor Planning -- The macro dimensions are defined, The rows and
routing tracks are defined

Power Planning -- Has power pads, power straps and power rings.

Placement -- We place the Gate-2 steopsLevel Netlist cells on the
floorplan rows, aligned with the site.

2 steps -- Global and Detailed

Global placement tries to find the optimal placement for all the cells.
Such positions are not correct, so they may overlap

Detailed Placement are minimally altered to be legal

CTS -- Clock distribution network.

To deliver the clock to all sequential elements.

With minimum skew

Usually a tree.

Synthesized to level of clock.

Certain structures are used, such as H , X Tree etc

Route --

![](media/image8.png){width="4.163001968503937in"
height="1.7706353893263342in"}

To implement the interconnect using available metal layers

The local layers are all aluminium.

OpenLANE ASIC Flow --

![A diagram of a software flow Description automatically
generated](media/image9.png){width="4.104438976377953in"
height="2.3273337707786528in"}

Starts with RTL Synthesis

Can be used to generate a report

Based on this we can make a best strategy to continue

OpenLANE has design exploration Uitility

Then the physical implementation

PnR (Place and Route) --

Floor and Power planning

End decoupling Capacitors and Tap cells insertion

Placement : Global and Deatailed

Next step in process in Yosys --

Verification must be performed.

Modification of netlist

Used to confirm that what we ended up with was not what we started with.

Fake ant. Diodes insertion script --

When a metal wire segment is made, it can act as antenna.

Preventive approach -- Add fake antenna diode, run antenna checker and
if the checker reports violation, replace it with a real one.

Static Timing Analysis -- Involves RC Extraction from routed layout.

Then physical verification.

Open Source EDA Tools --

SKY130_D1_SK3 - Get familiar to open-source EDA tools

Screenshot of the virtual Ubuntu box running the open source EDA tools

![](media/image10.jpeg){width="4.583333333333333in"
height="2.735985345581802in"}

Screenshots of some of the files and directory structure of the open
source EDA tool.

![](media/image11.jpeg){width="3.5436198600174977in"
height="1.9916666666666667in"}

![](media/image12.jpeg){width="3.316666666666667in"
height="1.8659470691163604in"}

Screenshot on opening OpenLANE

![](media/image13.jpeg){width="4.6in" height="2.5853980752405947in"}

Design preparation steps - screenshots

![](media/image14.jpeg){width="4.641666666666667in"
height="2.610358705161855in"}

![](media/image15.jpeg){width="4.8in" height="2.466353893263342in"}

![](media/image16.jpeg){width="5.60119094488189in"
height="2.5430555555555556in"}

Once the preparation is completed successfully, the runs directory with
the current date is created as shown in the screenshot below.

![](media/image17.jpeg){width="4.607142388451444in"
height="2.589411636045494in"}

![](media/image18.jpeg){width="4.483333333333333in"
height="2.5198261154855643in"}

Output of the run_synthesis command

![](media/image19.jpeg){width="4.821428258967629in"
height="2.709850174978128in"}

Steps to Characterize Synthesis Results

After synthesis calculate flip-flop ratio as below.

Flip flop ratio = no of DFFs / No of cells \* 100

= 1613/14876\*100 = 10.84%

![](media/image20.jpeg){width="4.6852887139107615in"
height="2.6333333333333333in"}
