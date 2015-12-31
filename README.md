###**Converting from Eagle to KiCad.**
*    [Quick Introduction Video](http://cosmosc.com/video/testtital.mp4)  
     *Recommended video player [Firefox 43+](https://www.mozilla.org/en-US/firefox/desktop/) with [VLC video player plugin](http://www.videolan.org/vlc/)*  


* The following 5 **ulp** (eagle user script file) and one **ulp** include file, work together or stand alone to convert **Eagle** *sch/pcb* version 6.xx*(7.xx maybe?)* file(s) and any version of Eagle lib(*lbr*) to **KiCad** *sch/pcb* and *lib/mod* files.  

* The Programs will do
	* Eagle mulit sheet sch to KiCad  mulit sheets.  
	* Global and local net labels for mulit sheets.*(This is a real nasty bit of hacking!*)  
	* Mulit part gate's.  
	* Build KiCad PCB modules and SCH libs from Eagle SCH.  
	* Make project director to store all the converted files.  
	* And basic error checking.  
	* Eagle 6.xx PCB files can be directly import to KiCad.  
	* Eagle *LBR's*(any version of Eagel libs or size ) can be converted to KiCad lib/mod using eagle-lbr2kicad-1.0.ulp see  
	* [Eagle Lib conversion]( https://github.com/lachlanA/eagle-to-kicad-libs) for more details.  
	* Converts Via's to Pads, which helps with KiCad's flood fill, when Via's have no connections.  
	* Documents fill's over SMD pad's on Eagle Layer 155,156  
	* Documents on layer's 150,152,153,154 of (Eagle) the unconnected Via's and tracks.  
	* The **[examples](https://github.com/lachlanA/eagle-to-kicad/tree/master/examples)** director contains a number of converted sch's/board's.  

* By using the following **ulp's**  a consistent link from the SCH to PCB is maintained so forward and backward net-list annotations work under KiCad!  

**WARNING KiCad via's and tracks don't retain NET information from Eagle when they are not connect to a PAD!,**** So KiCad flood fill will not connect to them !!! There is an option to convert and document on layer's 150,152,153,154 of (Eagle) the unconnected Via's and tracks which will make finding and fixing the problem much easier.**  


###Installing.
* Download the zip file, (*click on the button on the bottom right of this page*. **Download ZIP**) And unzip using your favorite zip program to your target directory *OR* if your prefer git:

			git clone https://github.com/lachlanA/eagle-to-kicad.git  

* **WARNING:**  The ULP's file-name will conflict with Eagles ULP's file-name's so  
  ***DO NOT install them in Eagle's ULP directory***.  

* There are 5 **ulp's** and one **ulp** include file have been hack together.  
***renumber-sheet.ulp*** ........................   stage 1: Add missing number(s) to parts Prefix's.  
***fix_via_hack.ulp*** ..............................   stage 2: Converts unconnected Via's to Pad's.  
***eagle6xx-sch-to-kicad-sch.ulp*** ....    stage 3: Build sch and project files, etc  
***exp-lbrs.ulp*** .......................................   stage 4: Extract libs from eagle SCH/PCB  
***eagle-lbr2kicad-1.0.ulp***....................  stage 5: Converts Eagle lbr to KiCad lib/mod  
***eagle_to_kicad_include.inc*** ..........  Include file used by the other 4 ULP's  
####HOW TO RUN THE ULP'S 
 
 **WARNING Always backup your Eagle SCH/PCB files before running this program!**  
 
* **1:** Start your Eagle program *(Make sure your using  version 6.xx of Eagle)*

* **2:** Open the eagle SCH/PCB  file you wish to convert. Make sure the eagle SCH and PCB file's are both, Correct and pass all ERC/DRC checks in Eagle.  

* **3:** Next Open the top left hand  **File menu** and select  **Run ULP**  

* **4:** A file requester window will open.  Using this, to select find or type the location of the ***renumber-sheet.ulp*** ULP you download from this website. We use this script to make sure all part prefix's are ending in a number  IE:   R0,  X1   etc. As KiCad will ask to renumber any prefix which dose not end in a number. *(It may do this any way, but don't worry it wont change any Prefix's which have already been numbered unless you tell it too!)*  Keeping prefix's consistent from SCH to PCB will allow net-list forward and back annotation to work in KiCad. Select **OK** *(this will run the scrip)*.  When this completes all references with out a number, should have a number appended to them. Note: This number will start from the largest reference number on the SCH/PCB.

* **5:** Next stage will run automatically, ***fix_via_hack.ulp*** This will check for free unconnected VIA'S and convert them to PADS,  this is very much a hack, as it change's the Eagle SCH/PCB files.  The changed files are saved in ***targetdir/modified_eagle_files/***  
There are 2 option's Document the VIA'S/PADS buy putting a ***>*** and net lable name on the VIA/PAD on **layer 51** for Ealge, and **Dwgs.User** for KiCad. Second option is to Not to convert the VIA's to PAD'S.  
The ulp hack adds pad's to the SCH file, at **X-Y 0.0** this may conflict with any net/part at this location, so please move the sch/PCB contents so, there is no parts/nets at this location before running the script.
You may getting warnings from Eagle about connecting net??? to a power plan net, just click OK, as this is normal for this script.

* **6:** Next stage will run automatically  
Set the option/location of the download ULP. And also Make sure you make/select a ***clean target directory*** where all the KiCad file's will be put. Select OK, And with luck you should have SCH part done.   The previous ULP will link automatically to ***exp-lbrs.ulp*** for the  next step: If you have selected extract the KiCad lib's from Eagle SCH/PCB *(The default).* This  ULP will build  Eagle lbr file,  *Note: this can be a very slow process,  and will  
leave the Eagle PCB editor window open when complete*. Just ignore this for the moment. If this complete OK, the previous ULP will link to ***eagle-lbr2kicad-1.0.ulp*** which will convert the Eagle lbr file to a KiCad lib/mod file's.  The ***eagle-lbr2kicad-1.0.ulp*** window window will open with quite a few options. Just select OK for the moment.  And if *Murphy's Law  is sound asleep* we should have the target directory with all the converted files, including KiCad project files. But with one exception, it will be missing KiCad PCB file.

* **7:** For this, we need to Open KiCad's **pcbnew** program directly,  at the command prompt.
 *If you make the mistake of not opening **pcbnew** directly, and instead chose to run it from KiCad's **pcbnew**  menu. You will have no option for importing the Eagle 6 PCB file!*  Click on **File->Open** in **pcbnew** an window will pop-up, and on Wright side you will have a drop down menu box option, to select the type in import file. Select version 6.x  XML  of Eagle, and the PCB eagle file linked to the eagle SCH file we used at the beginning and press OK. After importing the Eagle PCB file, (with out error's I hope). Do a **SAVE AS** to **PROJECTNAME.kicad_pcb** to the new target directory *(where you saved the output from to preceding ULP's too).* **PROJECTNAME** being the name you give to your project early on. As a helper a Dummy kicad_pcb file with the correct name has been crated in the target directory which you can use to do a save-as to.

* **8:** Next step is to check the KiCad **SCH** and KiCad **PCB** are consistent for parts and nets.
Start **KiCad**, and open the project in the newly created target directory. Open the SCH file. And if it was converted from the single SCH file, you should have the **SCH** file in the display. Or mulit sheet **SCH** file you will have a number of small box's spread across the page. Each one of those box's being a converted Eagle sub-sheet. Click on the first one and check for errors. All being good, click on Generate Net-list, and click OK. It may ask to Annotate the **SCH**. If so do the Annotation step. And then come back and click on Generate net-list. And Generate it.

* **9:** Next click on **CvPCB**, this assigns the PCB footprints with the SCH parts. Most likely you will get the
following warning: *Some of the assigned footprints are legacy entries (are missing lib nicknames). Would you like CvPcb to attempt to convert them to the new required FPID format? (If you answer no, then these assignments will be cleared out and you will have to re-assign these footprints yourself.)* Just click the yes button. And a window will open up listing all the part's and foot print's which it has assigned. Under FILE menu click Save. And then File Close.

* **10:** Next Clink on **PcbNew** button on the top menu, and the PCB should open up.
Now click on the **NetList** and a window should open up, from there click on Read Current Net-list. All going well you should not have any extra parts added, and only a few warning's about changing net list names.  And you should be done.  Please check over the converted **SCH/PCB** as there are many things which can go wrong!.  While I have try-ed to catch as many conversion problem, I expect there many still waiting to be found. ***So check and triple check the results!!!***

* **NOTE'S:**   For more info on KiCad  http://www.kicad-pcb.org/display/KICAD/Installing+KiCad  
As KiCad is the process of major upgrade,  and enhancement  please be nice asking ? of the Development team.  I think you  will love the new Push and Shove router, that feature alone make's it worth while moving from Eagle to KiCad I hope the ULP's  make the job a lot easy.




  

