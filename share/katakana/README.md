# nihongo/share/katakana 

Japanese resources to share for building a Katakana book

# Name Schema for PDF Graphic Files

Most PDF graphic files in this directory are created via katakana.svg
by inkscape. Some other files in nihongo/share/i too.

     ad.pdf     - [a]rrow [d]own
     ag.pdf     - katakana [a] [gray]
     a.pdf      - katakana [a]
     ar.pdf     - [a]rrow [r]ight
     as.pdf     - katakana [a] [s]stroke marks
     at.pdf     - katakana [a] [t]table position

     eg.pdf     - katakana [e] [g]ray 
     e.pdf      - katakana [e]
     es.pdf     - katakana [e] [s]troke marks
     et.pdf     - katakana [e] [t]table position

     ig.pdf     - analogue to e
     i.pdf
     is.pdf
     it.pdf

     og.pdf     - analogue to e
     o.pdf
     os.pdf
     ot.pdf

     s.pdf      - [s]pace

     ug.pdf     - analogue to e
     u.pdf
     us.pdf
     ut.pdf

# Process

     1 open: inkscape katakana.svg
     2 change an object (ungroup)
     3 group an object
     4 set group ID via object properties
     5 save katakana.svg (CTRL s)
     6 save copy PDF and choose name to save and object ID
       - Restrict to PDF version 1.5
       - Convert texts to path (include correct fonts!)
       - Rasterzise filter effects
       - Resolution for rasterrization 600dpi
       - Export area is drawing
       - Limit export to the object ID [<INSERT ID HERE>]


