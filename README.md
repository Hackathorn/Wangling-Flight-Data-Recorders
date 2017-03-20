# Wangling-Flight-Data-Recorders

This is a study in wangling and analyzing data from flight data recorders (FDR) 
required on all commercial aircraft. The plan is…

1.  Find and document real FDR data.

2.  Load it into python 3 using Jupyter notebooks. Using pandas to
    explore and structure the data.

3.  Restructure the data into a normalized temporal format based on
    periods, instead of events.

4.  Contrast with the raw format with temporal format.

5.  **In future…** apply feature engineering technique to the
    time-series data to extract significant features for
    machine learning. Can we identify anonymous events, without domain
    expertise about specific sensors?

Find/Document FDR data
----------------------

This task was harder than I expected. FDR data is voluminous and
complex, plus having legal implications about aircraft crashes. A lucky
Google query found a [15MB CVS
file](http://dms.ntsb.gov/pubdms/search/document.cfm?docID=424788&docketID=57175&mkey=89324)
buried within the US National Safety Board (NTSB) docket management
system. After considerable more searching, this file was attributed to a
Gulfstream crash in 2014. Here are the details…

On the night of May 31, 2014, a Gulfstream aircraft crashed after it
overran the end of runway during a rejected takeoff in Bedford, MA. The
airplane rolled across a grassy area, collided with approach lights,
passed through the perimeter fence, and came to a stop in a ravine. The
airplane was destroyed by impact forces and fire. The two pilots, a
flight attendant, and four passengers died.

In the [NTSB Aircraft Accident Report
AAR15-30](https://www.ntsb.gov/investigations/accidentreports/pages/AAR1503.aspx),
the investigation concluded that the flight crew neglected to disengage
the airplane’s gust lock system, which locks all wing control surfaces
to protect against wind gusts. This was a simple error that should have
been corrected during the preflight checklist.

Can the FDR data detect this situation without domain-specific knowledge
about the gust lock system? Let’s find out…

Load/Structure FDR data
-----------------------
