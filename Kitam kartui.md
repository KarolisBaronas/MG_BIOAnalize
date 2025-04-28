# SVARBI INFORMACIJA

Norint suaktyvuoti conda zmgk2 serveryje parašykite:

```
source /opt/packages/anaconda3/etc/profile.d/conda.sh
conda activate

```
Pilna Annovar versija įkelta į direktoriją:

```
/opt/packages/annovar/

```

# Pratyboms 2025-04-14

Pabaigti pirmų pratybų užduotis !

Nuodugniai peržvelgti ir susipažinti su anotacijoje naudojamais įrankiais ir duomenų bazėmis: https://annovar.openbioinformatics.org/en/latest/

Nuodugniai perskaityti ir pasižymėti/išsirašyti įrankių cutoff reikšmes: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9774026/

Susipažinti: https://varnomen.hgvs.org/

# Pratyboms 2025-04-28

Galimos db serveryje:

cytoBand

refGene

avsnp150

1000g2015aug_all

1000g2015aug_eur

exac03nonpsych

gnomad_genome

kaviar_20150923

clinvar_20221231

intervar_20180118

cosmic70

regsnpintron

dbscsnv11

dbnsfp41a

cadd13gt10

gerp++gt2

phastConsElements46way

dbnsfp35a

Konvertavimas: (pakeiskite out ">" direktoriją)
```
perl /opt/packages/annovar/convert2annovar.pl  -format vcf4 --withzyg /opt/shared/MG25/Trecios_pratybos/Pvz/S9904Nr35_all.vcf > /opt/home/karolisb/S9904Nr35_all.avinput

```
Anotavimas: (pakeiskite out "-out" direktoriją, trunka apie 30 min)
```
perl /opt/packages/annovar/table_annovar.pl /opt/home/karolisb/S9904Nr35_all.avinput /opt/packages/annovar/humandb/ -buildver hg19 -out /opt/home/karolisb/S9904Nr35_all.txt -remove -protocol cytoBand,refGene,avsnp150,1000g2015aug_all,1000g2015aug_eur,exac03nonpsych,gnomad_genome,kaviar_20150923,clinvar_20221231,intervar_20180118,cosmic70,regsnpintron,dbscsnv11,dbnsfp41a,cadd13gt10,gerp++gt2,phastConsElements46way,dbnsfp35a -operation r,g,f,f,f,f,f,f,f,f,f,f,f,f,f,f,r,f -nastring NA -otherinfo

```

Genų rinkinių aprašymas pagal numerį

```
Pvz:
S8300Nr41_all.vcf    - Neurofibromatozė
S9904Nr35_all.vcf    - Ilgo QT sindromas

Užduotys:
1_S10016Nr96_all.vcf  - Jungiamojo audinio patologija
2_S10016Nr62_all.vcf  - MODY tipo diabetas
3_S9722Nr42_all.vcf   - Kanalopatijos
4_S4754Nr107_all.vcf  - Regos genų rinkinys
5_S9855Nr39_all.vcf   - Rasopatijos
```

Filtravimas:

```
AI į pagalbą:))

```
