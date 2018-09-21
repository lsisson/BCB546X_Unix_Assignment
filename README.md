# BCB546X Unix Assignment

## File Inspection

### Snp_Position

* Looking at the top of the `snp_position.txt` file using
	`head`
	
	```
	head -n 10 snp_position.txt | cut -c -100 | column -t
SNP_ID    cdv_marker_id  Chromosome  Position   alt_pos  mult_positions  amplicon  cdv_map_feature.name  gene  c
abph1.20  5976           2           27403404   abph1    AB042260        abph1     candidate             8393  10474  1  1  1
abph1.22  5978           2           27403892   abph1    AB042260        abph1     candidate             8394  10475  0  0  0
ae1.3     6605           5           167889790  ae1      ae1             ae1       candidate             8395  10477  1  1  1
ae1.4     6606           5           167889682  ae1      ae1             ae1       candidate             8396  10478  0  0  0
ae1.5     6607           5           167889821  ae1      ae1             ae1       candidate             8397  10479  0  0  0
an1.4     5982           1           240498509  an1      an1             an1       candidate             8398  10481  1  1  1
ba1.6     3463           3           181362952  ba1      AY753892        ba1       candidate             8399  10482  1  0  1
ba1.9     3466           3           181362666  ba1      AY753892        ba1       candidate             8400  10483  0  0  0
bt2.5     5983           4           66290049   bt2      bt2             bt2       candidate             8401  10486  1  1  1
	```
	
	I used the cut command to make the lines shorter in order to more easily visualize the data structure of the files.
	
* Looking at the end of the `snp_position.txt` file using `tail`

	```
	tail -n 10 snp_position.txt | cut -c -100 | column -t
te1.3    3503  3        163617892  te1           AF348319  te1    candidate  10103  11819  1    0     1
te1.4    3504  3        163617645  te1           AF348319  te1    candidate  8431   11820  0    0     0
zagl1.1  3511  1        4912526    zagl1         AY104805  zagl1  candidate  8432   11821  1    0     1
zagl1.6  3513  1        4835658    Approximate:  position  of     another    SNP    from   the  same  amplicon  plus  100  bases  z
zap1.2   3514  2        233128584  zap1          L46400    zap1   candidate  8434   11823  1    0     1
zen1.1   3519  unknown  unknown    zen1          CF649098  zen1   candidate  8435   11824  1    1     1
zen1.2   3520  unknown  unknown    zen1          CF649098  zen1   candidate  8436   11826  0    0     0
zen1.4   3521  unknown  unknown    zen1          CF649098  zen1   candidate  8437   11827  0    0     0
zfl2.6   6463  2        12543294   zfl2          zfl2      zfl2   candidate  8438   11828  1    1     1
zmm3.4   3527  9        16966348   zmm3          Y09301    zmm3   candidate  10104  11829  1    0     1
	```
* Looking at the size of the `snp_position.txt` file using `du`

	```
	du -h snp_position.txt 
 84K	snp_position.txt
	```
* Looking at the number of rows, words, and characters in `snp_position.txt` using `wc`

	```
	wc snp_position.txt 
     984   13198   82763 snp_position.txt
	```
* Looking at the number of columns in `snp_position.txt` using `awk -F "\t"`

	```
	awk -F "\t" '{print NF; exit}' 	snp_position.txt 
	15
	```
* In summary: There are 984 lines, 15 columns, and the file size is 84Kb.


### Fang_Genotypes

* Looking at the top of the `fang_et_al_genotypes.txt` file using `head`

	```
	head -n 5 fang_et_al_genotypes.txt | cut -c -100 | column -t
Sample_ID  JG_OTU    Group  abph1.20  abph1.22  ae1.3  ae1.4  ae1.5  an1.4  ba1.6  ba1.9  bt2.5  bt2.7  bt2.8  Fea2.
SL-15      T-aust-1  TRIPS  ?/?       ?/?       T/T    G/G    T/T    C/C    ?/?    G/G    ?/?    A/A    ?/?    C/C    A/A  T/T  C/C  A/A  ?/?  ?/?  ?/?  ?/?
SL-16      T-aust-2  TRIPS  ?/?       ?/?       T/T    ?/?    T/T    C/C    A/G    G/G    ?/?    A/A    ?/?    C/C    A/A  T/T  C/C  A/A  T/T  ?/?  ?/?  ?/?
SL-11      T-brav-1  TRIPS  ?/?       ?/?       T/T    G/G    T/T    ?/?    G/G    G/G    C/C    A/A    ?/?    ?/?    A/A  T/T  C/C  A/A  T/T  ?/?  ?/?  A/A
SL-12      T-brav-2  TRIPS  ?/?       ?/?       T/T    G/G    T/T    C/C    G/G    G/G    C/C    A/A    ?/?    ?/?    A/A  T/T  C/C  A/A  T/T  ?/?  ?/?  A/A
	```
* Looking at the end of the `fang_et_al_genotypes.txt` file using `tail`
	
	```
	tail -n 5 fang_et_al_genotypes.txt | cut -c -100 | column -t
S0398   Zmm-IL-W64A_a      ZMMIL  G/G  A/A  T/T  G/G  C/C  C/C  G/G  G/G  C/C  G/G  A/A  ?/?  A/A  C/C  C/C  A/A  T/T  T/T  A/
S1636   Zmm-IL-W64A_b_s    ZMMIL  G/G  A/A  T/T  G/G  C/C  C/C  G/G  G/G  C/C  G/G  A/A  G/G  A/A  C/C  C/C  A/A  T/T  T/T
CU0201  Zmm-IL-WD_f        ZMMIL  C/C  A/A  T/T  G/G  C/C  C/C  G/G  G/G  C/C  G/G  A/A  G/G  ?/?  C/C  C/C  G/G  T/T  T/T  A/A
S0215   Zmm-IL-Wf9         ZMMIL  G/G  A/A  T/T  ?/?  C/C  C/C  G/G  G/G  C/C  G/G  A/A  G/G  A/A  C/C  C/C  A/A  T/T  T/T  A/A  G
CU0202  Zmm-IL-Yu796_NS_f  ZMMIL  C/C  A/A  T/T  G/G  C/C  C/C  ?/?  G/G  C/C  G/G  A/A  G/G  ?/?  ?/?  C/C  G/G  T/T  T
	```
* Looking at the size of the `fang_et_al_genotypes.txt` file using `du`
	
	```
	du -h fang_et_al_genotypes.txt 
 11M	fang_et_al_genotypes.txt
 	```
* Looking at the number of rows, words, and characters in `fang_et_al_genotypes.txt` using `wc`
	
	```
	wc fang_et_al_genotypes.txt 
    2783 2744038 11051939 fang_et_al_genotypes.txt
    ```
    
* Looking at the number of columns in `fang_et_al_genotypes.txt` using `awk -F "\t"` 
	
	```
	awk -F "\t" '{print NF; exit}' fang_et_al_genotypes.txt 
986
	```
* In summary: There are 2783 lines, 986 columns, and the file size is 11Mb. 

## Data Processing

* I wanted to extract the SNP_IDs from `fang_et_al_genotypes.txt` in order to add that to the individual Maize and Teosinte files after separation

	```
	head -n 1 fang_et_al_genotypes.txt > head_genotypes.txt
	```
	
* Then, I wanted to see how many groups there were in `fang_et_al_genotypes.txt`

* This can be done by using a combination of `cut | sort | uniq`

	```
	cut -f 3 fang_et_al_genotypes.txt |sort| uniq -c
   1 Group
  22 TRIPS
  15 ZDIPL
  17 ZLUXR
  10 ZMHUE
 290 ZMMIL
1256 ZMMLR
  27 ZMMMR
 900 ZMPBA
  41 ZMPIL
  34 ZMPJA
  75 ZMXCH
  69 ZMXCP
   6 ZMXIL
   7 ZMXNO
   4 ZMXNT
   9 ZPERR
   ```
* From this output, we can see there are 1573 Maize groups (ZMMIL, ZMMLR, and ZMMMR) and there are 975 Teosinte groups (ZMPBA, ZMPIL, and ZMPJA)

* I now need to extract the maize groups and the teosinte groups into their respective files. I can do this using `grep`

	```
	grep "ZMM" fang_et_al_genotypes.txt > Maize_Genotypes.txt
wc Maize_Genotypes.txt 
    1573 1550978 6240114 Maize_Genotypes.txt
    ```
    I also performed `wc` on the newly created Maize_Genotypes.txt file to determine the number of lines. There are 1573 lines, which is consistent with the number I got earlier. 
    
	```
	grep "ZMP" fang_et_al_genotypes.txt > Teosinte_Genotypes.txt
wc Teosinte_Genotypes.txt 
     975  961350 3873338 Teosinte_Genotypes.txt
    ``` 
   I performed `wc` on the newly reated Teosinte_Genotypes.txt file and determined there were 975 lines, which is consistent with what I got earlier.
   
* Now that I have the Maize and Teosinte genotypes, I need to add the headers back.
	```
	cat head_genotypes.txt Maize_Genotypes.txt > head_maize_genotypes.txt
	```
	```
	cat head_genotypes.txt Teosinte_Genotypes.txt > head_teosinte_genotypes.txt
	```
* Now I need to transpose the files in order to prepare them for joining

	```
   awk -f transpose.awk head_maize_genotypes.txt > transposed_maize_genotypes.txt
   ```
   ```
   awk -f transpose.awk teosinte_genotypes.txt > transposed_teosinte_genotypes.txt
   ```
   
* I trimmed the `snp_positions.txt` file by using the `cut` function to only include the columns we want (SNP_IDs, Chromosome, and Position)

	``` 
	cut -f -1,3,4 snp_position.txt > trimmed_snp_position.txt
	```
* Now I will join the files using `join`

	```
	join trimmed_snp_position.txt transposed_maize_genotypes.txt > joined_maize.txt
	```
	```
	join trimmed_snp_position.txt transposed_teosinte_genotypes.txt > joined_teosinte.txt
	```
* Now that I have joined files, I can pull out the lines that have unknown chromosomes/positions and the lines that have multiple positions
	```
	grep "multiple" joined_maize_genotypes.txt > multiple_maize.txt
	```
	```
	grep "unknown" joined_maize_genotypes.txt > unknown_maize_genotypes.txt
	```
	```
	grep "multiple" joined_teosinte_genotypes.txt > multiple_teosinte.txt
	```
	```
	grep "unknown" joined_teosinte_genotypes.txt > unknown_teosinte.txt
	```
	
* I need to add the headers back onto the files but first I need the snp header

	```
	head -n 1 trimmed_snp_position.txt > head_snp.txt
	```

	```
	cat head_snp.txt multiple_maize.txt > final_multiple_maize.txt
	```
	```
	cat head_snp.txt unknown_maize_genotypes.txt > final_unknown_maize.txt
	```
	```
	cat head_snp.txt multiple_teosinte.txt > final_multiple_teosinte.txt
	```
	```
	cat head_snp.txt unknown_teosinte.txt > final_unknown_teosinte.txt
	```
	
* I now need to split the files out by chromosome number, sort the file by position appropriately, and replace ? with the appropriate symbol (either ? for increasing and - for decreasing)

	```
	for i in {1..10};
	do
    awk -F '\t' '$2=='$i'' joined_maize.txt \
    | sort -nk3 | sed -e 's/\?\?/g' \
    > ./sorted_inc_pos/chromosome_${i}_sorted_inc_pos.txt;
	done
	```
	```
	for i in {1..10};
	do     
	awk -F '\t' '$2=='$i'' merged_maize_genotypes.txt \     
	| sort –r -nk3 | sed -e 's/\?\-/g' \     
	> ./sorted_dec_pos/chromosome_${i}_sorted_dec_pos.txt;  
	done
	```
	This code splits the genotypes out by chromosome (`awk -F '\t' '$2=='$i''`), sorted by increasing or decreasing potion, (`sort -nk3` or `sort -r -nk3`), and replace missing data (?) with ? or - (`sed -e 's/\?\>/g'`)
	
* I now have all my sorted chromosome files and I need to add the header to finish the files

	```
	for i in {1..10}; 
	do cat head_snp.txt ./Dec_Sorted_Maize_Chrom/chromosome_${i}_sorted_dec_pos.txt 
	> ./Dec_Sorted_Maize_Chrom/final_chromosome_${i}_sorted_dec_post.txt; 
	done
	```
	
	This for loop will add the header and make a new file named 	`final_chromosome1_sorted_dec_post`. This was done for all sorted files to add the headers.
	
* The final files are located in the Maize and Teosinte folders, with the chromosomes in subsequent folders. The chromosome files for maize that are sorted in decreasing position are located in `Dec_sorted_Maize_Chrom`, the files for maize that are sorted in increasing position are located in `Inc_Sorted_Maize_Chrom`, the files for teosinte that are sorted in decreasing position are located in `Dec_sorted_Maize_Chrom`, and the files for teosinte that are sorted in increasing position are located in `Inc_Sorted_Maize_Chrom`. Within the Maize and Teosinte folders, there are two files, one for the unknown position and one for the multiple position SNPs, as seen here: `final_unknown_maize.txt` `final_multiple_maize.txt` `final_multiple_teosinte.txt`	`final_unknown_teosinte.txt`. All intermediate files that were created for each organism is in their respective `Intermediate_Files` folder. All raw data is in the folder `Raw` and `Intermediate` contains various header files.

	
	