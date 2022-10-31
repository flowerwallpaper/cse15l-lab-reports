# Lab Report 3

## less

### -p
        less -p "biomed" find-results.txt
        technical//biomed
        technical//biomed/1472-6807-2-2.txt
        technical//biomed/1471-2350-4-3.txt
        technical//biomed/1471-2156-2-3.txt
        technical//biomed/1471-2156-3-11.txt
        technical//biomed/1471-2121-3-10.txt
        technical//biomed/1471-2172-3-4.txt
        technical//biomed/gb-2002-4-1-r2.txt
        technical//biomed/gb-2003-4-6-r41.txt
        technical//biomed/1471-2466-1-1.txt
        technical//biomed/1471-2199-2-10.txt
        technical//biomed/1471-2202-2-9.txt
        technical//biomed/cc991.txt
        technical//biomed/1471-2369-3-9.txt
        technical//biomed/bcr620.txt
        technical//biomed/1476-069X-2-4.txt
        technical//biomed/1472-6750-3-11.txt
        technical//biomed/1471-2164-2-9.txt
        technical//biomed/1471-2091-2-10.txt
        technical//biomed/gb-2001-2-4-research0010.txt
        technical//biomed/gb-2003-4-4-r24.txt
        technical//biomed/1471-213X-2-1.txt
        technical//biomed/1472-6882-3-3.txt
        technical//biomed/1471-2407-2-3.txt
        technical//biomed/ar331.txt
        technical//biomed/ar319.txt
        technical//biomed/1471-2156-4-5.txt
        technical//biomed/1471-2431-2-1.txt
        technical//biomed/1476-4598-2-22.txt

<p>
The -p option caused the output to start at the first instance of the pattern I gave it, in this case it started at the first file with "biomed" in the name. It's useful for looking for where a pattern starts in a set of files. 
</p>

### -E

`less -E find-results.txt`

<p>
Once you get to the bottom of the results of find, it stops displaying them. I like this command because I can actually see what I've already entered. 
</p>

### File 

      less technical/biomed/gb-2003-4-8-r51.txt
            Rationale
            Protein-sequence-based comparative analysis to infer
            biological function is important and familiar to most
            biologists. Sequence-profile methods such as PSI-BLAST [ 1
            ] or HMMER [ 2 ] are often used to detect distant homologs,
            and resources such as Prosite [ 3 ] , BLOCKS [ 4 ] and PFAM
            [ 5 ] are representative resources resulting from protein
            classification based on sequence patterns. Protein
            structure also plays a crucial role in a full understanding
            of protein function as it is more conserved than sequence
            and hence exposes relationships not possible from sequence
            alone. Many protein domains have less than 10% sequence
            identity, and yet possess a similar fold and possibly
            related function.
            One of the early insights gained from comparative
            genomics was domain accretion [ 6 ] . From prokaryotes to
            eukaryotes, the number of domains increases. But in higher
            eukaryotes, different combinations of domains are often
            observed in the same and different protein families. From a
            structural point of view domains are discreet compact
            folding units. PIR [ 7 ] classifies proteins into either a
            homeomorphic superfamily (proteins containing similar
            domains in the same order) or a homology domain superfamily
            (proteins from different homeomorphic superfamilies sharing
            a common ancestral domain). This modular nature of proteins
    technical/biomed/gb-2003-4-8-r51.txt

This option displays the first few lines of the text file and the name of the text file, which is handful when you just want to take a glance at it. 

## find

### file

    camillephares@Camilles-MacBook-Air docsearch % find ./technical/biomed/1468-6708-3-1
    .txt
    ./technical/biomed/1468-6708-3-1.txt

Can use find to search for a file directly, which is handy if you want to pull one thing up. 

### -iname

    camillephares@Camilles-MacBook-Air docsearch % find ./technical/government/Alcohol_Problems -iname SESSION2-PDF.txt
    ./technical/government/Alcohol_Problems/Session2-PDF.txt
    

Searches for the name of a file, ignoring uppercase/lowercase. Handy because I can't be bothered to remember how something is capitalized. 

### -type

    camillephares@Camilles-MacBook-Air docsearch % find technical -type d  
    technical
    technical/government
    technical/government/About_LSC
    technical/government/Env_Prot_Agen
    technical/government/Alcohol_Problems
    technical/government/Gen_Account_Office
    technical/government/Post_Rate_Comm
    technical/government/Media
    technical/plos
    technical/biomed
    technical/911report

Finds directories within docsearch, which is easier than expanding everything. 

## grep

### -c

    camillephares@Camilles-MacBook-Air docsearch % grep -c "pmed" find-results.txt
    150
    
Returns the number of matching lines. Useful if all you want to know is how many occurrences of something there are. 

### -n 

    camillephares@Camilles-MacBook-Air docsearch % grep -n "addiction" ./technical/government/Alcohol_Problems/Session2-PDF.txt 
    375:screens less often than addiction experts recommend.
    
Returns the line number of a search query. Useful to find where exactly it is in the file, and get a little context for it. 

### -e

    camillephares@Camilles-MacBook-Air docsearch % grep -e "legal" technical/government/media/5_Legal_Groups.txt
    Five independent Salt Lake organizations that provide legal
    campaign by an alliance of the non-profit providers of free legal
    campaign of legal services agencies in the country, and the
    efficient for those needing legal services. No longer will a woman

Like -n, but doesn't return the line number. Still useful for seeing in what context a query appears. 
