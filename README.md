<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">
  <head>
    <meta content="text/html; charset=windows-1252" http-equiv="content-type">
  </head>
  <body>
    <h2>Converting from Eagle to KiCad.</h2>
    <h3>The following 4 ulp <span style="font-weight: normal; font-style: italic;">(eagle
        user script file)</span>, converts eagle sch/pcb version 6.xx file(s),<br>
      to KiCad sch and lib/mod files.</h3>
    The Programs will do sub sheets, and also<span style="font-weight: normal;">
      do multi</span> parts gate's, and also correct do net-list.<br>
    There are 4 ulp, which have been hack together to help make life a little
    easier when making the conversion<br>
    &nbsp; 1:&nbsp; <span style="font-style: italic;"><span style="font-weight: bold;">renumber-sheet.ulp
        .................</span> (stage 1, Optional, part renumber )<span style="font-weight: bold;"><br>
        &nbsp; </span></span>2:<span style="font-style: italic;"><span style="font-weight: bold;">
        eagle6xx-sch-to-kicad-sch.ulp </span>..&nbsp; (state 2,&nbsp; sch,
      project, etc )<span style="font-weight: bold;"><br>
        &nbsp;</span></span><span style="font-weight: bold;"></span> 3: <span style="font-style: italic;"><span
        style="font-weight: bold;">exp-lbrs.ulp </span>....................................
      (automatic stage 3, extract libs from&nbsp; eagle SCH/PCB )<span style="font-weight: bold;"><br>
        &nbsp; </span></span><span style="font-weight: bold;"></span>4: <span
      style="font-style: italic;"><span style="font-weight: bold;">eagle-lbr2kicad-1.0.ulp
        </span>................ (automatic stage 4, convert Eagle lbr to KiCad
      lib/mod )<br>
    </span><span style="font-weight: bold; text-decoration: underline;"><br>
      Note: You should download the ULP's to a diffant directry for eagle's
      ULP's,&nbsp; as some of the name's will conflict eagles<br>
      ULP's</span><span style="font-style: italic;"><br>
      <span style="font-weight: bold;"><br>
      </span></span> <span style="font-weight: bold;">HOW TO RUN THIS PROGRAM:</span><br>
    &nbsp;&nbsp;&nbsp; 1: Start <span style="font-weight: bold;">eagle</span>
    program <span style="font-weight: bold; text-decoration: underline; font-style: italic;">(Make
      sure it's version 6 of Eagle)</span>.<br>
    <br>
    &nbsp;&nbsp;&nbsp; 2: Open the eagle SCH/PCB <span style="font-weight: bold;"></span>
    file you wish to convert. Make sure SCH and PCB file's are both <span style="font-weight: bold;"><span
        style="font-style: italic;">Correct and</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="font-style: italic;">passe
        all DRC checks</span></span>.<br>
    <br>
    &nbsp;&nbsp;&nbsp; 3: Next Open&nbsp; the top left hand&nbsp; <span style="font-weight: bold; font-style: italic;"><span
        style="text-decoration: underline;">F</span>ile </span>menu and select
    <span style="text-decoration: underline;"> </span><span style="font-style: italic; font-weight: bold;"><span
        style="text-decoration: underline;">Run</span> ULP</span><br>
    <br>
    &nbsp;&nbsp;&nbsp; 4: A file requester window will open up.&nbsp; Using
    this, to select/find/type the location of the<br>
    &nbsp; &nbsp; &nbsp; &nbsp; <span style="font-style: italic; font-weight: bold;">renumber-sheet.ulp</span>
    scrip you download from this website. We use this script to make sure all
    part prefix's<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; are ending in a number&nbsp;
    IE:&nbsp;&nbsp; R0,&nbsp; X1&nbsp;&nbsp; etc.&nbsp;&nbsp; As KiCad will
    renumber any prefix which dose not ending in a number.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if this happends we lose tack of
    the matching reference in SCH and PCB, when when importing the eagle PCB in
    KiCad.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Select <span style="font-weight: bold;"><span
        style="text-decoration: underline;">O</span>k (this will run the scrip)<br>
      <br>
    </span>&nbsp; &nbsp; 5: Next Open&nbsp; the top left hand&nbsp; <span style="font-weight: bold; font-style: italic;"><span
        style="text-decoration: underline;">F</span>ile </span>menu and select<span
      style="text-decoration: underline;"> </span><span style="font-style: italic; font-weight: bold;"><span
        style="text-decoration: underline;">Run</span> ULP<br>
    </span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Using this, to
    select/find/type the location of the <span style="font-style: italic; font-weight: bold;">eagle6xx-sch-to-kicad-sch.ulp<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>Select <span style="font-weight: bold;"><span
        style="text-decoration: underline;">O</span>k (this will run the
      scrip)&nbsp;</span>There are many options most most should just work ok.<span
      style="font-weight: bold;"><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>Make sure you make/select are
    clean target directory, where all the KiCad file's will be put.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Select Ok, and with luck you
    should have go to the next step: if you have selected extract KiCad lib's
    from<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Eagle SCH/PCB<span style="font-weight: bold; font-style: italic;">
      (The default)</span>.&nbsp;&nbsp;&nbsp; This will build a eagle Lbr files,&nbsp;
    Note this can be a very slow process,&nbsp; and will<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; live the PCB editor window open
    when complete, just ignore this for the moment.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Next step if this complete ok,
    will be to convert the eagle lbr file to a KiCad lib/mod file.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A new window will open with quite
    a few options.&nbsp;&nbsp; Just select <span style="font-weight: bold; text-decoration: underline;">ok</span>
    for the moment.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; And if <font face="Tahoma,ARIAL,HELVETICA"><b>Murphy's
        Law </b></font> is sound asleep we shold have all a target directory
    with all the converted files. include a KiCad project<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; file.&nbsp; But missing a KiCad
    PCB file. <br>
    <br>
    &nbsp; &nbsp; 6: For that we need to Open KiCad's <span style="font-weight: bold; font-style: italic; text-decoration: underline;">pcbnew</span>
    prgrogram directly,&nbsp; at the command prompted. (Dont ask me why KiCad
    people chose to do<br>
    &nbsp; &nbsp; &nbsp; &nbsp; it this way !)&nbsp; if you don't open pcbnew
    directly and instead chose to run the <span style="font-weight: bold; font-style: italic; text-decoration: underline;">kicad</span>
    command you will have no option for importing the<br>
    &nbsp; &nbsp; &nbsp; &nbsp; eagle 6 PCB file.&nbsp; (yes.. yes.. I know !)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In <span style="font-weight: bold; font-style: italic;">pcbnew</span>
    under the <span style="font-weight: bold; font-style: italic; text-decoration: underline;">File-&gt;Open</span>&nbsp;
    a window will popup, on the far Bootom wright you have a drop down box
    option to select the type in import file.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Select version 6.x&nbsp;
    XML&nbsp; of Eagle.&nbsp;&nbsp; And press ok.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Now if it imported ok,&nbsp; Do a
    <span style="font-style: italic; font-weight: bold;">Save as</span> to your
    target directory(where you saved the output of the preceding programs<span style="text-decoration: underline;">)<br>
    </span>&nbsp; &nbsp; &nbsp; &nbsp; and append&nbsp;<span style="font-style: italic;"><span
        style="font-weight: bold;"></span></span><span style="font-style: italic;"><span
        style="font-weight: bold;"></span>projectname.</span><span style="font-style: italic; font-weight: bold;">kicad_pcb<span
        style="text-decoration: underline;"><br>
      </span></span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; All beiing well
    you should have&nbsp; a converted eagle SCH PCB correctly linked and
    refanced.<br>
    <br>
    NOTE'S: &nbsp; Nightly builds of KiCad for Windows are available from:&nbsp;
    <span style="font-weight: bold;">http://www2.futureware.at/~nickoe/</span><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    Other targets: <span style="font-weight: bold;">http://www.kicad-pcb.org/display/KICAD/Installing+KiCad</span><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    As KiCad is the process of majory upgrade,&nbsp; and enhancement&nbsp;
    please be nice asking ? of the Development team.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    I think you&nbsp; will love the Auto Push and Shove router, that feature
    alone make's it worth while moving from Eagle to KiCad<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    I hope the ULP's&nbsp; make the job a lot easy.<br>
    <i><i><b><i><br>
            &nbsp;&nbsp;&nbsp; Lachlan.<br>
            <br>
            <br>
            <i> </i></i></b></i></i>
  </body>
</html>
