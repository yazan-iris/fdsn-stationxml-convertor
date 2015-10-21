# fdsn-stationxml-convertor
The stationxml-converter translates FDSN StationXML to dataless SEED and also dataless SEED to StationXML.

The converter is a command line utility written in Java and should be portable to any environment with Java 6 or greater.

The FDSN StationXML schema and the SEED reference manual are available from the FDSN.org website.

Beware: while there is a high degree of correlation between StationXML and SEED (headers), the mapping between the two formats is not 100% complete or reversible.

View the list of caveats for details of information mapping and loss.

In general, more information can be represented in StationXML than SEED; a conversion from SEED to StationXML loses any information that cannot be represented in SEED.

Nearly all information in SEED can be represented in StationXML, in most cases such a conversion is loss-free; the reverse conversion will likely not recover the exact same SEED due to minor structural changes but information loss is not expected in most cases.


h2. Usage

<pre>
Usage: java -jar stationxml-converter.jar -s|-x [OPTIONS] [FILE|URL]...

Output format (one is required):
-s,--seed     Convert FDSN StationXML to SEED format
-x,--xml      Convert SEED to FSDN StationXML format, must specify -so also

Other options:

-se,--sender       Identifies sender, e.g. "IRIS DMC" 
-so,--source       Required when -x, identifies source, e.g. "IRIS DMC" 
-V,--version       Print version number and exit
-v,--verbose       Print out verbose information during conversion
-h,--help          Print this usage information
-p,--print         Produce formatted/indented XML document, default is compact
-a,--useragent      UserAgent submitted when fetching specified URLs
-l,--level <arg>   Specify level for XML output, can be: net|sta|cha|resp

-i,--input <arg>   Process all URLs or files listed in specified file
-o,--output <arg>  Save converted results to specified file, default is stdout
</pre>
