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

# Pratyboms 2026-03-30

Pabaigti pirmų pratybų užduotis !

Nuodugniai peržvelgti ir susipažinti su anotacijoje naudojamais įrankiais ir duomenų bazėmis: https://annovar.openbioinformatics.org/en/latest/

Nuodugniai perskaityti ir pasižymėti/išsirašyti įrankių cutoff reikšmes: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9774026/

Susipažinti: https://varnomen.hgvs.org/

# Pratybos 2026-03-30

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
perl /opt/packages/annovar/convert2annovar.pl  -format vcf4 --withzyg /opt/shared/MG26/*.vcf > /opt/home/*.avinput

```
Anotavimas: (pakeiskite out "-out" direktoriją, trunka apie 30 min)
```
perl /opt/packages/annovar/table_annovar.pl /opt/home/*.avinput /opt/packages/annovar/humandb/ -buildver hg19 -out /opt/home/*.txt -remove -protocol cytoBand,refGene,avsnp150,1000g2015aug_all,1000g2015aug_eur,exac03nonpsych,gnomad_genome,kaviar_20150923,clinvar_20221231,intervar_20180118,cosmic70,regsnpintron,dbscsnv11,dbnsfp41a,cadd13gt10,gerp++gt2,phastConsElements46way,dbnsfp35a -operation r,g,f,f,f,f,f,f,f,f,f,f,f,f,f,f,r,f -nastring NA -otherinfo

```

Genų rinkinių aprašymas pagal numerį

```
Pvz:
S8300Nr41_all.vcf    - Neurofibromatozė
S9904Nr35_all.vcf    - Ilgo QT sindromas

```
# Pratyboms 2025-04-13

Genų filtravimas:

```
tr -d '\r' < /opt/home/karolisb/genai.txt | sed 's/(base)//g' | sed 's/[[:space:]]*$//' > /opt/home/karolisb/genai_clean.txt

awk -F'\t' 'NR==FNR{genes[$1]; next} FNR==1{print; next} {split($8, arr, /[;,]/); for (i in arr) {gsub(/^ +| +$/, "", arr[i]); if (arr[i] in genes) {print; next}}}' /opt/home/karolisb/genai_clean.txt /opt/shared/MG25/Trecios_pratybos/Pvz/S8300Nr41_all.txt.hg19_multianno.txt > /opt/home/karolisb/filtered_variants.txt

```
Genų rinkinių aprašymas pagal numerį

```
Užduotys:
1_S10016Nr96_all.vcf  - Jungiamojo audinio patologija
2_S10016Nr62_all.vcf  - MODY tipo diabetas
3_S9722Nr42_all.vcf   - Kanalopatijos
4_S4754Nr107_all.vcf  - Regos genų rinkinys
5_S9855Nr39_all.vcf   - Rasopatijos

Kitam kartui:
S10415Nr10_all.vcf    - Su paveldimomis dermatologinėmis ligomis siejamų genų naujos kartos sekoskaitos tyrimas, įtariama įgimta delnų ir padų keratoderma (ichtiozė).

```

