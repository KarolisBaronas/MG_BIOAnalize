# Pirmosios pratybos
"Biotechnologijos metodai ir bioinformacinė analizė" užsiėmimų pratybų medžiaga medicinos genetikos pirmo kurso studentams.

# Atsiskaitymas už pratybas
Studentas savarankiškai paruošia duotos klinikinės situacijos analizės pristatymą. 
# Pristatymo vertinimo kriterijai
#### Klinikinės situacijos aptarimas – paciento fenotipas, atlikti instrumentiniai tyrimai, genealogija, kiti svarbūs faktai apie pacientą (2 balai);

#### NKS duomenų analizės rezultatai – pacientui nustatytų kliniškai reikšmingų genomo variantų analizė, in silico įverčių aptarimas, baltymo struktūros pokyčių įvertinimas ir vizualizacija (4 balai);

#### Genotipo ir paciento fenotipo analizė – gautų rezultatų susiejimas su paciento fenotipu, išvados formulavimas ir pateikimas (genotipas pagal HGVS nomenklatūrą) (2 balai);

#### Atsakymai į pateiktus klausimus (2 balai).

# Pasiruošimas praktiniam darbui

## Reikalinga programinė įranga
Programinė įranga priklauso nuo Jūsų gebėjimo valdyti terminalą bei komandines eilutes. Dažnai MacOS ar Linux vartojams papildomos programinės įrangos nereikia. Tačiau Windows vartotojai susiduria su papildomomis problemomis.

Pagrindinė programinė įranga - Perl ir ANNOVAR

Prisiminimui pagrindinės UNIX komandos - https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners

## Windows

Programinės įrangos valdymui Windows aplinkoje rekomenduoju naudoti Anaconda.

![Anaconda Installation](Img/Anaconda_pradzia.PNG)

Šių pratybų tikslams naudosime paprastą "Light" tipo Anaconda versiją - [Miniconda3](https://docs.conda.io/en/latest/miniconda.html)

![Miniconda Installation](Img/Miniconda.PNG)

Po sėkmingos instaliacijos paspaudus "Start" ieškome "Anaconda prompt (miniconda3)".

## MacOS

MacOS aplinkoje turite terminalą ir priėjimą prie visų paprastų UNIX komandų. Dėl paprastumo rekomenduoju, taip pat, įsidiegti [Miniconda3](https://docs.conda.io/en/latest/miniconda.html).

## Linux

Linux vartotojams dažnai papildomų "organizacinių" paketų instaliuoti nereikia.

## Suinstaliavus Anaconda ar Miniconda

Suinstaliavus Anaconda (conda) rekomenduoju sekti [nuorodą](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html) ir patikrinti ar teisingai įrašėte programinę įrangą.

Atsidariusiame lange įrašome:
```
conda --version
```
Ir turėtumete matyti išvestį:
```
conda 23.1.0
```
Atnaujinkime condą naudodami eilutę (su visais pakeitimais sutinkame -y):
```
conda update conda -y
```
Atliekame conda "Solver" pakeitimą į greitesnį:
```
conda install -n base conda-libmamba-solver
```
Nustatome naują "Solver" versiją:
```
conda config --set solver libmamba
```

## Darbinės aplinkos sukurimas

Tikriausiai pastebėjote, kad įvesties eilutės pradžioje matote (base) aplinkos indikatorių. Pratyboms susikurkime atskirą darbinę aplinką:
```
conda create --name BioAnalize
```
Norėdami patenkti į tik sukurtą darbinę aplinką naudojame komandą:
```
conda activate BioAnalize
```
Norėdami iš jos išeiti ir grįžti į pagrindinę (base) aplinką galite naudoti komandą:
```
conda deactivate
```
*** Norėdami pažiūrėti sukurtų darbinių aplinkų sąrašą naudokite komandą:
```
conda info --envs
```
![Conda aplinka](Img/aplinkos.PNG)

Išbandykite komandas ir galime judėti toliau.

## Perl įrašymas
Perl programa būtina ANNOVAR programos veikimui, tad pirma patikrinkite, galbūt, Perl programinė įranga jau instaliuota:
```
perl -v
```
Jeigu matote tokią išvestį, vadinasi Perl programinė įranga neįdiegta.

![Perlv](Img/perlv.PNG)

```
Kokią komandą naudosite perl programinės įrangos įrašymui?
```

Perl įrašymą patikrinkite naudodami tą pačią eilutę:
```
perl -v
```
Jeigu viską padarėte teisingai turėtumėte pamatyti tokį vaizdą:

![Perlok](Img/Perlok.PNG)

* Naudodami "conda activate base" koamnd1 grįškite į pradinę darbinę aplinką ir suveskite "perl -v". Atlikę teisingai iki šiol pateiktas užduotis turėtumėte gauti klaidą. Kodėl taip nutiko? Viskas dėl to, kad programinę įrangą įrašėme į BioAnalize darbinę aplinką. Iš kitos aplinkos įrašytų programinių paketų nepasieksime. Taip veikia conda "organizatorius"

## Pratybomų medžiagos atsisiuntimas
Failų atsisiuntimui naudokime wget paketą, o išpakavimui unzip programą. Norėdami jas parsisiųsti į savo darbinę aplinką naudokite komandas:
```
conda activate BioAnalize
```
```
conda install -c menpo wget -y
```
```
conda install -c conda-forge m2-unzip
```
Sukurkite atskirą direktoriją pratyboms ir į ją įeikite
```
Kokias dvi komandas naudosite užduočiai atlikti?
```
Jeigu kyla klausimų galite užeiti į tinklapį -

Norėdami atsisiųsti pratyboms reikalingą "lengvą" ANNOVAR versiją naudokitės komanda:
```
wget --no-check-certificate "https://transfer.sh/RhJIpn/pratybu_medziaga.zip" -O pratybu_medziaga.zip
```
Išskleiskit atsiųstą failą naudodami komandą:
```

```
