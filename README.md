java c
EEET 3050 - Renewable Energy Systems 
Practical 4 - Characteristic of PV Cells with Series and Parallel Resistances
Aim: The   aim   of   this   practical   is   to   evaluate   the   I-V   characteristics   of   a   PV   cell   with   (i) series resistance, and (ii) series and parallel resistance using   Matlab/Simulink block   diagram.
Objectives: Develop   the   model   of   a   PV   cell   with   a   series   resistance
Develop    a    more    realistic      model    of      a      PV      cell      considering      both      parallel      and      series   resistancesBackground: The   PV   cell   characteristics   can   be   described   by   the   following   equations   at   25°C   andthe definitions of the terms are   illustrated in   Fig.   1. Variation   of the   PV voltage   will   be   given   as   an   external   input   signal   to   the   model   and      PV   current   will   be   taken   as   an   output. When   open   circuit,   ipv         =   0.

Fig.1 Circuit   model of an simplified   PV   cell   with   a   current   source   and   diodeThere   are   times   when   a   more   complex   PV   equivalent   circuit   than   the   one   shown   in   Fig.    1   is      needed.    In      Practical   03,   the      impact   of   the      parallel      resistor   on   the      PV   cell characteristics was studied. The   PV cell   illustrated   in   Fig.   1 can   be further   modified   by   including a series resistance. Some of this might be   contact   resistance   associated with   the   bond   between   the   cell   and   its   wire   leads, and   some   might   be   due   to   the   resistance of the semiconductor   itself.
Fig.   2   illustrates   a   PV   equivalent   circuit   that   includes   series   resistance   RS.   The   ideal   current source   ISC    in this case delivers   current to   the   diode:
I   =   (Isc      − ID   )
Impact of the series   resistance can   be   added   as follows:
VD      =   V   +   I ∗ Rs
Hence,
I   =   Isc − Io   {(e38.9∗(V+I∗RS)   ) − 1}
Above   equation   can   be   interpreted   as the   original   I -V   curve   with the voltage   at   any   given   current   shifted   to   the   left   by   ∆V    =   I   ∗ Rs      as   shown   in   Fig.   3.

Fig.   2 The   PV cell equivalent circuit   with   series   resistance

Fig.   3   Modifying   the   simplified   PV   cell   equivalent   circuit   by   adding   series   resistance   causes the voltage at any given   current to   shift   to   the   left   by   IRS.
Exercise 1 Fig.2   illustrates   the   circuit   model   of   a      PV   cell   with   the   series   resistance   and      Fig.   4   illustrates   the   corresponding   Simulink   model   block   diagram.       In    order   to   study   the   impact   of   the   series   resistance   of   the   PV   cell,   you   will   be   developing   both   simplified   PV cell, and the   PV cell with   RS    in   the   same   MATLAB/SIMULINK   model   and   comparing   the   results   by   plotting the graphs.

Fig.4   Model   block diagram of the   simplified   PV cell   with   and   without   RS      resistance   in   Simulink
Instructions 
1.          Open   MATLAB   from   ‘Start’   menu.
2.          Open   the   Simulink   file   “CharacteristicsPV” you   saved   in   Exercise   1.   “Save   As”   the   file   with   the name   “CharacteristicsPV_Rs”   .
3.          Click ‘Simulink Library’   icon  in the toolbar to get the window   of the   Simulink   library.
4.          Search for the following   blocks and   drag    drop them   into your   Simulink   file.
•          Product,    sum,    XY      graph,    simout      (To      Workspace),      mux,    gain,      constant,            repeating   sequence,   Fcn
5.          Keep   the   simplified   PV   cell   model   you   build   from   the   previous   Exercise.
6.          Double   click   on   the   “Mux”   and   enter   the   number   of   inputs   as   6.
7.          Delete   the   unnecessary   connections   in   the   model.
8.          Connect   all   the   elements   as   in   Fig. 4.
9.          Double   click   on   the “Constant” block   and   enter ‘1000’ .
10.    Double   click   on   the   gain   and   enter   ‘1/250’   .
11.    Double   click   on   the   ‘Sum’   block   and   enter   -+|
12.    Double   click   on   the   ‘Fcn’   block   and   enter ‘ 1e-9*(exp(38.9*u)-1)’   .
13.    Double click on the   ‘Repeating sequence’ and   enter   the   following   parameters:
•          Time   values – [ 0   1   2],Output   values – [-0.1   0.6   -0.1]
14.    Double   click   on   the ‘I-V   Characteristics   ideal’   XY   scope   and   enter   the   following   parameters:
•          Xmin – 0, Xmax – 0.6, Ymin – 0,   Ymax – 5.0
15.    Double   click   on   the   ‘PV   power   ideal’ XY   scope   and   enter   the   following   parameters:
•          Xmin – 0, Xmax – 0.6, Ymin – 0,   Ymax – 2.0
16.    Double   click   on   the   ‘To   Workspace’   block   and   select   ‘Save   format’   as   ‘Array’   .
17.    Rename   all   the   elements   in   the   model   as   in   Fig. 4.
18.   Set   the   ‘Simulation   Stop   Time’   in   the   tool   bar   to ‘ 1‘ a代 写EEET 3050 - Renewable Energy Systems Practical 4 – Characteristic of PV Cells with Series and Parallel ResistancesMatlab
代做程序编程语言s   follows:

19.    Run   the   simulation   by   clicking   on   the   ‘Run’   icon   in   the   tool   bar.
20.    Plot   PV   curves   for   both   PV   cell   models   on   the   same   graph   and   add   labels   for   axes   and   title.   (hint   :   refer   Practical   1 for   plotting   graphs   in   MATLAB)
21.    Plot   IV   curves   for   both   PV   cell   models   on   the   same   graph   and   add   labels   for   axes   and   title.
22.   Set   the   minimum   x-axis   andy-axis   limits   to   zero   for   both   plots.
23.   Add   legends   for   both   plots.
24.   Save   all   the   files.
25.   Change   the   value   of   ‘Rs’ and   observe   the   variation   of   the   PV   curve   and   IV   curve.
Exercise 2 Fig.5   illustrates   the   circuit   model   of   a   PV   cell   with   the   parallel   resistance   and   the   series   resistances.   Fig.    6       illustrates      the      corresponding         IV      characteristics      of      the         PV      cell      with         both         Rp         and         Rs.    The corresponding   Simulink   model   block   diagram   is   illustrated   in   Fig.   7.         In   order   to   study   the   impact   of   the   parallel and series   resistances of the   PV cell, you will be developing   both   simplified   PV   cell   and the   PV cell with   Rp   and   Rs   in the same   MATLAB/SIMULINK   model and comparing the results   by   plotting the graphs.  Fig. 5 The   PV cell equivalent circuit   with   parallel   and   series   resistances
Under   the   standard   assumption   of   a   25°C   cell   temperature,   current   characteristics   of   a   PV   cell   with   both   parallel   and series   resistances can   be expressed as   follows:

Fig.   6   Series   and   parallel   resistances   in   the   PV   equivalent   circuit   decrease   both   voltage   and   current   delivered. To   improve   cell   performance,   high   RP      and   low   Rs      are   needed.

Fig.   5   Model   block   diagram   of   the   simplified   PV   cell   and   the   PV   cell   with   both   RS      and   RP      resistances   in Simulink
Instructions 
26.   Open   the   Simulink   file   “CharacteristicsPV” you   saved   in   Exercise   1.   “Save   As” the   file   with   the name   “CharacteristicsPV_Real”   .
27.   Click ‘Simulink Library’   icon  in the toolbar to get the window of the   Simulink   library.
28.   Search for the following   blocks and drag  drop   them   into   your   Simulink   file.
•          Product,    sum,    XY      graph,    simout      (To      Workspace),      mux,    gain,      constant,            repeating   sequence,   Fcn
29.    Keep   the   simplified   PV   cell   model   you   build   from   the   previous   Exercise.
30.    Double   click   on   the   “Mux” and   enter   the   number   of   inputs   as   6.
31.    Delete   the   unnecessary   connections   in   the   model.
32.   Connect   all   the   elements   as   in   Fig.   7.
33.    Double   click   on   the “Constant” block   and   enter ‘1000’ .
34.    Double   click   on   the   gain   and   enter   ‘1/250’   .
35.    Double   click   on   the   ‘Sum’   block   and   enter   -+|
36.    Double   click   on   the   ‘Fcn’   block   and   enter ‘ 1e-9*(exp(38.9*u)-1)’   .
37.    Double click on the   ‘Repeating sequence’ and   enter   the   following   parameters:
•          Time   values – [ 0   1   2],Output   values – [-0.1   0.6   -0.1]
38.    Double   click   on   the ‘I-V   Characteristics   ideal’   XY   scope   and   enter   the   following   parameters:
•          Xmin – 0, Xmax – 0.6, Ymin – 0,   Ymax – 5.0
39.    Double   click   on   the   ‘PV   power   ideal’ XY   scope   and   enter   the   following   parameters:
•          Xmin – 0, Xmax – 0.6, Ymin – 0,   Ymax – 2.0
40.    Double   click   on   the   ‘To   Workspace’   block   and   select   ‘Save   format’ as   ‘Array’   .
41.    Rename   all   the   elements   in   the   model   as   in   Fig.   7.
42.   Set   the   ‘Simulation   Stop   Time’   in   the   tool   bar   to ‘ 1‘ as   follows:

43.    Run   the   simulation   by   clicking   on   the   ‘Run’   icon   in   the   tool   bar.
44.    Plot   PV   curves   for   both   PV   cell   models   on   the   same   graph   and   add   labels   for   axes   and   title.   (hint   :   refer   Practical   1 for   plotting   graphs   in   MATLAB)
45.    Plot   IV   curves   for   both   PV   cell   models   on   the   same   graph   and   add   labels   for   axes   and   title.
46.   Set the   minimum x-axis andy-axis   limits to zero for   both   plots.
47.   Add   legends   for   both   plots.
48.   Save   all   the   files.
49.   Change   the   values   of   ‘Rp’ and   ‘Rs’ and   observe   the   variation   of   the   PV   curve   and   IV   curve.
Report: The   report   should   include   a   brief   introduction,   all   plots   with   critical   analysis   and   discussion,   and   a   conclusion.   The      report   should      be   approximately   600   words      long,   excluding   figures,   diagrams,   and   tables.







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
