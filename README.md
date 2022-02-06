# STA-WORKSHOP TIMING OF LATCH and FLIPFLOP
To understand timing its important we have a indepth knowledge regarding internal structure of LATCH and FLIPFLOP.
The basic timing parameters setup and hold depends on its internal structure.We generally find other representation in book but the below diagram represents simplest form of latch and flip-flop.
![IMG_20220205_192232](https://user-images.githubusercontent.com/99008175/152646330-27d62f62-92fb-413c-a2ca-0a9f956552d0.jpg)
Basically setup time is time required for data to reach from Dpin to Q point in flop/latch.
similarly Hold is time required to off the transmission gate of flop.latch.
we know that flops and latches are available in different flavours,due to which internal inverters have different delays and hence setup and hold timings are different. 
STA __INPUTS__CHECKS__TIMMING ANALYSIS
![IMG_20220206_185852](https://user-images.githubusercontent.com/99008175/152683532-4fdaf796-de07-4792-9729-babc99b24dc4.jpg)
SDC
In sdc we have Clock definations,I/O Ports delays
![0](https://user-images.githubusercontent.com/99008175/152684769-bc40d7e4-d917-4e42-adb1-9f01bf0a1c44.jpg)


CPPR
When we do setup and hold analysis we know that PVT conditions effect the delay through elements and hence derates are applied,but extra pessimism should be avoided in commom path thus is CPPR(Common path pessimsim removal)
![IMG_20220206_183954](https://user-images.githubusercontent.com/99008175/152683127-3c72cf8e-d2d4-4e77-92b8-5234539ded01.jpg)

here we can observe cppr is 6.6ps timing difference before and after cppr enabling.
![0](https://user-images.githubusercontent.com/99008175/152683642-6c4cb64f-09c2-4966-bd02-61cb5ba5847b.jpg)
![0](https://user-images.githubusercontent.com/99008175/152683634-12dcd72f-e33d-44a1-b663-9cc9a851c5dc.jpg)

CLOCK GATING
Its important technique to avoid unwanted glitches.
![0](https://user-images.githubusercontent.com/99008175/152684887-eb0e8422-95f7-4b08-b826-68a4aa740ac2.jpg)
OT doesnt report the paths directly and hence i analysed DAT and AT individual pins
![0](https://user-images.githubusercontent.com/99008175/152685122-0606ed8b-97b0-4731-9284-63c44e9be02e.jpg)
![0](https://user-images.githubusercontent.com/99008175/152685202-9645fc17-d229-488c-b73e-4e50e8dc325b.jpg)

ECO
In ECO we do small changes like adding or deleting gates,nets or change pins connection.
![0](https://user-images.githubusercontent.com/99008175/152683908-06deb7dd-3298-4de4-b4b0-3854bdc2f27e.jpg)
After ECO insertion we can observe slack improves
![0](https://user-images.githubusercontent.com/99008175/152683924-df5a2d62-b07c-47f6-8d56-f795abd23dbb.jpg)
