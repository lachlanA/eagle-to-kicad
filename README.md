```html
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">
  <head>
    <meta content="text/html; charset=windows-1252" http-equiv="content-type">
  </head>
  <body>
    <h2>Converting from Eagle to KiCad.</h2>
    <h3>The following 4 ulp <span style="font-weight: normal; font-style: italic;">(eagle
        user script file)</span>, converts eagle <span style="font-style: italic;">sch/pcb</span>
      version 6.xx file(s),<br>
      to KiCad <span style="font-style: italic;">sch</span> and <span style="font-style: italic;">lib/mod</span>
      files.</h3>
    The Programs will do sub sheets, and also<span style="font-weight: normal;">
      do multi</span> parts gate's, and also net-list.<br>
    There are 4 <span style="font-weight: bold; font-style: italic;">ulp</span>
    which have been hack together to help make life a little easier<span style="font-weight: bold;">.</span><br>
    <br>
    &nbsp; <span style="font-weight: bold;">1:</span> <span style="font-style: italic;"><span
        style="font-weight: bold;">renumber-sheet.ulp .................</span>&nbsp;&nbsp;
      (stage 1,&nbsp; </span><span style="font-style: italic;"><span style="font-style: italic;">Add
        missing number(s) to part Refance.</span><span style="font-weight: bold;"><br>
        &nbsp; </span></span><span style="font-weight: bold;">2:</span><span style="font-style: italic;"><span
        style="font-weight: bold;"> eagle6xx-sch-to-kicad-sch.ulp </span>..&nbsp;&nbsp;&nbsp;
      (state 2,&nbsp; Build sch and project files, etc )<span style="font-weight: bold;"><br>
        &nbsp;</span></span><span style="font-weight: bold;"></span> <span style="font-weight: bold;">3:</span>
    <span style="font-style: italic;"><span style="font-weight: bold;">exp-lbrs.ulp
        </span>....................................&nbsp;&nbsp; (<span style="text-decoration: underline;"></span></span><span
      style="font-style: italic;"><span style="text-decoration: underline;"><span
          style="font-style: italic;"><span style="text-decoration: underline;"></span>stage
          3, automatically</span> runs</span>)&nbsp; extract libs from&nbsp;
      eagle SCH/PCB )<span style="font-weight: bold;"><br>
        &nbsp; </span></span><span style="font-weight: bold;">4:</span> <span
      style="font-style: italic;"><span style="font-weight: bold;">eagle-lbr2kicad-1.0.ulp
        </span>................&nbsp; (<span style="text-decoration: underline;"></span></span><span
      style="font-style: italic;"><span style="text-decoration: underline;"><span
          style="font-style: italic;">stage 4,&nbsp; automatically</span> runs</span>)
      convert Eagle lbr to KiCad lib/mod )<br>
    </span><span style="font-weight: bold; text-decoration: underline;"><br>
      Note: You should download the</span><span style="text-decoration: underline; font-style: italic; font-weight: bold;">
      ULP's </span><span style="font-weight: bold; text-decoration: underline;">to
      a different directory from eagle's <span style="font-style: italic;">ULP's</span>
      directory,<br>
      as some of the name's will conflict eagles <span style="font-style: italic;">ULP's</span></span><span
      style="font-style: italic;"><br>
      <span style="font-weight: bold;"><br>
      </span></span> <span style="font-weight: bold;">HOW TO RUN THIS PROGRAM:</span><br>
    <br>
    &nbsp;&nbsp;&nbsp; <span style="font-weight: bold;">1: </span>Start the <span
      style="font-weight: bold;">eagle</span> program <span style="font-weight: bold; text-decoration: underline; font-style: italic;">(Make
      sure your using&nbsp; version 6.xx of Eagle)</span>.<br>
    <br>
    &nbsp;&nbsp;&nbsp;<span style="font-weight: bold;"> 2:</span> Open the eagle
    SCH/PCB <span style="font-weight: bold;"></span> file you wish to convert.
    Make sure SCH and PCB file's are both-<br>
    &nbsp; &nbsp; &nbsp; &nbsp; <span style="font-weight: bold;"><span style="font-style: italic;">Correct
        and</span>&nbsp;<span style="font-style: italic;">passe all DRC checks</span></span>.<br>
    <br>
    &nbsp;&nbsp;&nbsp; <span style="font-weight: bold;">3:</span> Next
    Open&nbsp; the top left hand&nbsp; <span style="font-weight: bold; font-style: italic;"><span
        style="text-decoration: underline;">F</span>ile </span>menu and select
    <span style="text-decoration: underline;"> </span><span style="font-style: italic; font-weight: bold;"><span
        style="text-decoration: underline;">Run</span> ULP</span><br>
    <br>
    &nbsp;&nbsp;&nbsp; <span style="font-weight: bold;">4:</span> A file
    requester window will open.&nbsp; Using this, to select/find/type the
    location of the<br>
    &nbsp; &nbsp; &nbsp; &nbsp; <span style="font-style: italic; font-weight: bold;">renumber-sheet.ulp</span>
    scrip you download from this website. We use this script to make sure all
    part prefix's<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; are ending in a number&nbsp;
    IE:&nbsp;&nbsp; R0,&nbsp; X1&nbsp;&nbsp; etc.&nbsp;&nbsp; As KiCad will
    renumber any prefix which dose not end in a number.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="font-style: italic;">If
      this happens your will lose tack of the matching reference in PCB, when
      importing the eagle PCB in KiCad!</span><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Select <span style="font-weight: bold;"><span
        style="text-decoration: underline;">O</span>k </span><span style="font-style: italic;">(this
      will run the scrip)</span><span style="font-weight: bold;"><span style="font-style: italic;">.&nbsp;
        </span></span><span style="font-style: italic;">When this completes all
      references with out a number, should have<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a number appended to
      them.&nbsp;&nbsp; Note: this number will start from the largest reference
      number on the SCH/PCB.</span><br>
    <span style="font-weight: bold;"><span style="font-style: italic;"> </span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      <br> </span>&nbsp; &nbsp;<span style="font-weight: bold;"> 5:</span> Next
    Open&nbsp; the top left hand&nbsp; <span style="font-weight: bold; font-style: italic;"><span
        style="text-decoration: underline;">F</span>ile </span>menu and select<span
      style="text-decoration: underline;"> </span><span style="font-style: italic; font-weight: bold;"><span
        style="text-decoration: underline;">Run</span> ULP<br>
    </span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Using this, to
    select/find/type the location of the <span style="font-style: italic; font-weight: bold;">eagle6xx-sch-to-kicad-sch.ulp<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>Select <span style="font-weight: bold;"><span
        style="text-decoration: underline;">O</span>k </span><span style="font-style: italic;">(this
      will run the scrip)&nbsp;</span>There are many options most most should
    just work ok.<span style="font-weight: bold;"><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>Make<span style="font-weight: bold; text-decoration: underline;">
      sure </span>you make/select a clean target directory, where all the KiCad
    file's will be put.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Select Ok, and with luck you
    should have automaticly go to the next step:<br>
    &nbsp; &nbsp; &nbsp; &nbsp; If you have selected extract KiCad lib's from
    Eagle SCH/PCB<span style="font-weight: bold; font-style: italic;"> (The
      default)</span>.<br>
    &nbsp; &nbsp; &nbsp;&nbsp;&nbsp; This will build a eagle <span style="font-weight: bold; font-style: italic;">lbr</span>
    files,&nbsp; Note this can be a <span style="font-style: italic;">very slow
      process</span>,&nbsp; and will<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; leave the PCB editor window open
    when complete, <span style="font-style: italic;">just ignore this for the
      moment.</span><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; If this complete ok,&nbsp; we
    will need be to convert the eagle <span style="font-weight: bold; font-style: italic;">lbr</span>
    file to a KiCad <span style="font-weight: bold; font-style: italic;">lib/mod</span>
    file.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A new window will open with quite
    a few options.&nbsp;&nbsp; Just select <span style="font-weight: bold; text-decoration: underline;">ok</span>
    for the moment.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; And if <font face="Tahoma,ARIAL,HELVETICA"><b>Murphy's
        Law </b></font> is sound asleep we <span style="font-weight: bold;">should</span>
    have all a target directory with all the converted files. include a KiCad
    project<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; file.&nbsp; But <span style="font-style: italic; font-weight: bold;">missing</span>
    a KiCad PCB file. <br>
    <br>
    &nbsp; &nbsp; <span style="font-weight: bold;">6:</span> For that we need
    to Open KiCad's <span style="font-weight: bold; font-style: italic; text-decoration: underline;">pcbnew</span>
    prgrogram directly,&nbsp; at the command prompted. (<span style="font-style: italic;">Don't</span>
    ask me why<br>
    &nbsp; &nbsp; &nbsp; &nbsp; KiCad people chose to do it this way !)<br>
    &nbsp; &nbsp; &nbsp; &nbsp; If you make the mistake of not opening <span style="font-weight: bold; font-style: italic;">pcbnew</span>
    directly, and instead chose to run the <span style="font-weight: bold; font-style: italic; text-decoration: underline;">kicad</span>
    command<br>
    &nbsp; &nbsp; &nbsp; &nbsp; you will have no option for importing the <span
      style="font-weight: bold;">eagle</span> 6 PCB file.&nbsp; (yes.. yes.. I
    know !)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In <span style="font-weight: bold; font-style: italic;">pcbnew</span>
    under the <span style="font-weight: bold; font-style: italic; text-decoration: underline;">File-&gt;Open</span>&nbsp;
    a window will popup, and on the far Bottom wright you will have a drop down
    menu box option<br>
    &nbsp; &nbsp; &nbsp; &nbsp; to select the type in import
    file.&nbsp;&nbsp;&nbsp; Select version 6.x&nbsp; XML&nbsp; of
    Eagle.&nbsp;&nbsp; And press ok.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Now if it imported ok,&nbsp; Do a
    <span style="font-style: italic; font-weight: bold;">Save as</span> to your
    target directory <span style="font-style: italic; font-weight: bold;">(where
      you saved the output of the preceding programs<span style="text-decoration: underline;">)<br>
      </span></span>&nbsp; &nbsp; &nbsp; &nbsp; and append&nbsp;<span style="font-style: italic;"><span
        style="font-weight: bold;"></span></span><span style="font-style: italic;"><span
        style="font-weight: bold;"></span>.</span><span style="font-style: italic; font-weight: bold;">kicad_pcb
      </span>to the project name.<span style="font-style: italic; font-weight: bold;"><span
        style="text-decoration: underline;"><br>
      </span></span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; All being well
    you should have&nbsp; a converted eagle SCH PCB correctly linked and
    referenced.<br>
    <br>
    NOTE'S: &nbsp; For more info on KiCad&nbsp; <a href="http://www.kicad-pcb.org/display/KICAD/Installing+KiCad"
      target="_blank">http://www.kicad-pcb.org/<wbr>display/KICAD/Installing+KiCad</a>
    <div><wbr></div>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    As KiCad is the process of majory upgrade,&nbsp; and enhancement&nbsp;
    please be nice asking ? of the Development team.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    I think you&nbsp; will love the new Push and Shove router, that feature
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
```
