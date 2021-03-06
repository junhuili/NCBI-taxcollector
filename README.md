#NCBI-taxcollector

Collects and Attaches NCBI taxonomy information to BLAST and SOAP2 results.

Results must be in tabular format (-m 8 or -m 6)

By: Raquel Dias and Marcelo V. Neves

Contact: raquel.dias.001@acad.pucrs.br

Pontifical Catholic University of Rio Grande do Sul - Brazil

High Performance Laboratory (LAD PUCRS)


#DESCRIPTION 

A Tool for parsing sequence search results and collecting information on NCBI taxonomic data

Project home page: https://github.com/Bioinfo-Tools/NCBI-taxcollector

Operating system(s):Platform independent

Programming language: Perl and C

License: GNU GPL


#REQUIREMENTS

- Perl 5 or higher
- C compiler


#INSTALL

- Download NCBI-taxcollector main functions

$ wget https://github.com/Bioinfo-Tools/ncbitc_functions/tarball/master

- Extract

$ tar -xvf master

- Go inside the extracted folder

$ rm master 

$ mv Bioinfo-Tools-ncbitc_* master

$ cd master

- Compile

$ make all

- Copy the binary named "tax_class" to the same dir as taxcollector_ncbi-0.01.pl 

$ cp tax_class ../

$ cd .. 

- Change the exec permissions

$ chmod 777 tax_class

- Download NCBI taxonomy databases

$ wget ftp://ftp.ncbi.nih.gov/pub/taxonomy/taxdump.tar.gz

$ wget ftp://ftp.ncbi.nih.gov/pub/taxonomy//gi_taxid_nucl.dmp.gz

- Extract the databases

$ tar -xvf taxdump.tar.gz

$ gunzip gi_taxid_nucl.dmp.gz

Convert dump files to binary

$ ./tax_class -c

- Usage

$ perl taxcollector_ncbi-0.01.pl -f Classification results (tabular text file) -o Output file


#EXAMPLES

- Input example:

            S001416244	gi|309261160|gb|HQ246245.1|	81.87	1186	148	64	226	1375	128	1282	0.0	 937
            S001416244	gi|85001901|gb|DQ337083.1|	78.63	1535	218	99	1474	1	1486	0.0	 917
            S001416244	gi|309261186|gb|HQ246271.1|	81.00	1216	137	75	247	1400	213	1396	0.0	 880


- Output example:

            S001416244	[0]Bacteria;[1]Proteobacteria;[2]Alphaproteobacteria;[3]Rhodospirillales;[4]Acetobacteraceae;[5]Roseomonas;[6]Roseomonas_sp._6A18S6;		81.87	1186	148	64	226	1375	128	1282	0.0	 937
            S001416244	[0]Bacteria;[5]uncultured_bacterium;[6]uncultured_bacterium;	78.63	1535	218	99	1	1474	1	1486	0.0	 917
            S001416244	[0]Bacteria;[1]Firmicutes;[2]Bacilli;[3]Bacillales;[5]Exiguobacterium;[6]Exiguobacterium_sp._8A18S8;		81.00	1216	137	75	247	1400	213	1396	0.0	 880


