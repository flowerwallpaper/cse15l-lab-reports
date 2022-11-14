# Lab Report 3

## grep

### -c

    camillephares@Camilles-MacBook-Air docsearch % grep -c "pmed" find-results.txt
    150
    
    camillephares@Camilles-MacBook-Air docsearch % grep -c "chapter" find-results.txt
    16
            
    camillephares@Camilles-MacBook-Air docsearch % grep -c "bio" find-results.txt
    940
Returns the number of matching lines. Useful if all you want to know is how many occurrences of something there are. 

### -n 

    camillephares@Camilles-MacBook-Air docsearch % grep -n "addiction"            ./technical/government/Alcohol_Problems/Session2-PDF.txt 
    375:screens less often than addiction experts recommend.
    
    camillephares@Camilles-MacBook-Air docsearch % grep -n "PASADENA"                           ./technical/government/Media/agency_expands.txt
    9:PASADENA -- Neighborhood Legal Services, which provides free
    
    camillephares@Camilles-MacBook-Air docsearch % grep -n "neuron"     ./technical/biomed/1471-213X-1-1.txt
    13:        signaling plays several roles in neuronal development
    14:        Early in CNS development, GABA can modulate neuron
    15:        progenitor proliferation as well as neuron migration,
    190:        stability can be regulated in mature neurons by the level
    
Returns the line number of a search query. Useful to find where exactly it is in the file, and get a little context for it. 

### -e

    camillephares@Camilles-MacBook-Air docsearch % grep -e "legal" technical/government/media/5_Legal_Groups.txt
    Five independent Salt Lake organizations that provide legal
    campaign by an alliance of the non-profit providers of free legal
    campaign of legal services agencies in the country, and the
    efficient for those needing legal services. No longer will a woman
    
    camillephares@Camilles-MacBook-Air technical % grep -e migration ./biomed/1471-23*  
        ./biomed/1471-230X-3-3.txt:        leukocyte migration and cytokine production appear to
        ./biomed/1471-2334-2-26.txt:        well as the immigration of leukocytes [ 1 2 3 4 5 ] .
        ./biomed/1471-2350-2-8.txt:          DNA fragments were separated using migration on 12%
        ./biomed/1471-2350-3-9.txt:        and admixture as a result of geographic migration explains
        ./biomed/1471-2350-3-9.txt:        result of geographic migration could explain the previously
        
        camillephares@Camilles-MacBook-Air technical % grep -e Darwin ./biomed/*
        ./biomed/1471-2105-3-2.txt:        In the 1830's, Charles Darwin's investigation of the
        ./biomed/1471-2105-3-2.txt:        In the 1970's, Woese and Fox revisited Darwinian

Like -n, but doesn't return the line number. Still useful for seeing in what context a query appears. 
