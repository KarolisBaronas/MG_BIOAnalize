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
S8300Nr41_all.vcf    - Neurofibromatozė (NM_001042492.3(NF1):c.[4676G>A];[4676=])
S9904Nr35_all.vcf    - Ilgo QT sindromas (NG_008935.1(NM_000218.3)(KCNQ1):c.[477+1G>A];[477+1=])

Užduotys:
1_S10016Nr96_all.vcf  - Jungiamojo audinio patologija (NM_000138.5(FBN1):c.[7606G>A];[7606=])
2_S10016Nr62_all.vcf  - MODY tipo diabetas (NM_000162.5(GCK):c.[130G>A];[130=])
3_S9722Nr42_all.vcf   - Kanalopatijos (NM_000218.3(KCNQ1):c.[1051_1065del];[1051_1065=])
4_S4754Nr107_all.vcf  - Regos genų rinkinys (NM_001292009.2(EYS):c.9380_9399del(;)(9380_9399del))
5_S9855Nr39_all.vcf   - Rasopatijos (NM_002834.5(PTPN11):c.[188A>G];[188=])

Kitam kartui:
S10415Nr10_all.vcf    - Su paveldimomis dermatologinėmis ligomis siejamų genų naujos kartos sekoskaitos tyrimas, įtariama įgimta delnų ir padų keratoderma (ichtiozė). (NM_173086.5(KRT6C):c.1414G>A))

```

Genų filtravimas:

```
tr -d '\r' < /opt/home/karolisb/genai.txt | sed 's/(base)//g' | sed 's/[[:space:]]*$//' > /opt/home/karolisb/genai_clean.txt

awk -F'\t' 'NR==FNR{genes[$1]; next} FNR==1{print; next} {split($8, arr, /[;,]/); for (i in arr) {gsub(/^ +| +$/, "", arr[i]); if (arr[i] in genes) {print; next}}}' /opt/home/karolisb/genai_clean.txt /opt/shared/MG25/Trecios_pratybos/Pvz/S8300Nr41_all.txt.hg19_multianno.txt > /opt/home/karolisb/filtered_variants.txt

```

# Pratyboms 2025-05-05

CNV anotacijos dokumentacija:
```

https://lbgi.fr/AnnotSV/Documentation/README.AnnotSV_latest.pdf

```


Genų rinkinių aprašymas pagal numerį

```
1_S10246Nr20	Kardiogenetika (aortopatija)	
2_S10246Nr41	Inkstų ligų genų rinkinys (hematurija, proteinurija, histologiškai - židininė glomerulosklerozė; dif. su Alporto s.)
3_S10246Nr34	prašau atlikti genų rinkinio tyrimą dėl MODY diabeto.
4_S10246Nr69	Ištyrimui dėl neurofibromatozės	
5_S10246Nr72	Inkstų ligų genų rinkinys (klinikinė dgn.: inkstų policistozė)	
*_S10246Nr48	Genų, siejamų su Rendu-Osler-Weber sindromu, tyrimui	
```

Kitam kartui:

```
S10246Nr51	Epilepsijos genų rinkinys
	
```

# Pratyboms 2025-05-12
```
S4754Nr12 SKUBUS. VES tyrimui: vaisiui (17sav.) nustatyta hepatomegalija, ventrikulomegalija, paryškintas žarnynas, hipertelorimas įt. VNP LGH norma. Šeimoje antras atvejis. Pirmas vaisius 2015m. žuvo gimdymo metu: hepatosplenomegalija, corpus callosum agenezė, vidinė hidrocefalija, ascitas. Kariotipas norma: 46,XY. Lytys skirtingos. AR paveldėjimas ?

S6344Nr55 Žemas raumenų tonusas. Veidas keturkampiškas, veido raukšlių asimetrija verkiant, žemyn svyra kairysis lūpų kampas. Aukšta kakta, kiek įspaustos smilkininės sritys. Displastiški ausų kaušeliai, žemas prisitvirtinimas, dešiniojo ausies kaušelio skiltelė hipoplastiška. Akių plyšių asimetrija (d<k), koloboma. Ilgas filtras. Siaura viršutinė lūpa, n.facialis parezė. Spenelinis hipertelorizmas. Politelija dešinėje. Didelė hemangioma kairiame šone, keletas smulkių hemangiomų po krūtinkaulio apatiniu kraštu. Kairės pėdos dorzaliniame paviršiuje rudos spalvos apgamas. Delnuose gilios delno linijos. Gilios sakralinės raukšlės su sakraline duobute. Kiek atitrauktas pėdos didysis pirštas. 	
![image](https://github.com/user-attachments/assets/47f89380-12ae-4bab-a917-1930878f5490)

```

# Atsiskaitymui 2025-05-19 (26?)

```
1_S8412Nr1 SKUBUS. analizę atlikti prioritetine tvarka; dominuoja piktybinė somnolencija; mikrocefalija (-2,5 cm žemiau 3 proc.); motorinės, protinės raidos atsilikimas; raumenų išreikšta hipotonija; nevaikšto, nesiremia kojomis;

2_S9050Nr1 SKUBUS. motina 14sav nėščia. Mikrocefalija (žemiau 3 procentilės, - 5 cm).Įspaustos smilkinkaulio sritys. Pakaušio srityje kraujagyslinė dėmė. Akių hipertelorizmas su abipusiu epikantu. Labai nedidelės nosies landos. Trumpas palygintas filtras. Pravira burna. Mikro/retrognatija. Santykinai dideli ausų kaušeliai su žemu jų prisitvirtinimu ir pronacija įstrižai atgal. Menkai diferencijuota dermatoglifika delnuose, delno linijos gaubia antrą pirštą. Nugaroje, sakralinėje srityje, hemangioma. Sakralinė duobutė. Pėdos antrasis pirštas kloja didįjį ir trečiąjį pirštus. Atsilieka psichomotorinė raida.

3_S7856Nr1 SKUBUS. Viso žmogaus egzomo sekoskaitos tyrimas. Echoskopiškai vaisiui stebima cistinė hygroma, abiejų kojų šleivapėdystė, vieno inksto hydronefrozė (Noonan s.?, kt RASopatijos?).	

4_S7273Nr61 SKUBUS egzomas, operuoja kylančios Ao dilataciją. Raidos sutrikimas, dismorfinės savybės, žvairumas, krūtininės aortos šaknies, kylančios dalies aneurizma.

5_S5760Nr76 Skubus. Vaisiui buvo stebimos dauginės formavimosi ydos: abipusis lūpos ir gomurio nesuaugimas, įgimta širdies yda - Fallot tetrada, sprando edema. Šiuo metu nėštumas 11 sav. 3 d.	

```
