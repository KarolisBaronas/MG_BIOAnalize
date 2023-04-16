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

Suinstaliavus Anaconda rekomenduoju sekti [nuorodą](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html) ir patikrinti ar teisingai įrašėte programinę įrangą.

Atsidariusiame lange įrašome:

```
(base) C:\Users\baron>conda --version
```
ir turėtumete matyti išvestį:

```
conda 23.1.0
```
Atliekame programos atnaujinimą:

