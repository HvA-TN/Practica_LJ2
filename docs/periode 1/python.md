# Opzetten Python voor practicum
## Leerdoelen

- Python-ontwikkelomgeving opzetten in VSCode.
- Leren werken met virtuele omgevingen in Python.
- Basis van projectstructuur.

!!! veiligheid "Veiligheid"

    We gaan programmeren, hier zijn geen veiligheidskwesties aan gebonden. Probeer alleen zoveel mogelijk zelfstandig te programmeren. Het is toegestaan om in dit practicum generatieve AI te gebruiken, gebruik het verstandig:

      1. Gebruik het als uitlegmachine, niet als codegenerator
      1. Gebruik het om eigen code te laten verbeteren, maar niet herschrijven
      1. Gebruik het niet voor volledige oplossingen, snap je iets niet? Vraag het de docent.

## Introductie
Python is een van de meest gebruikte programmeertalen binnen de natuurkunde en andere technische vakgebieden. Het wordt gebruikt voor het verwerken en visualiseren van meetgegevens, het uitvoeren van numerieke berekeningen en het aansturen van experimenten. Tijdens de opleiding zullen we Python daarom regelmatig gebruiken, bijvoorbeeld om meetdata te analyseren en grafieken te maken. Python zelf is echter alleen de programmeertaal. Voor praktisch gebruik zijn daarnaast verschillende *packages* nodig. Zo gebruiken we `NumPy` voor numerieke berekeningen, `Matplotlib` voor het maken van grafieken en `SciPy` voor wetenschappelijke berekeningen. Naarmate je meer projecten uitvoert, zul je steeds meer van dergelijke packages tegenkomen.

Hierbij ontstaat een praktisch probleem: niet ieder project gebruikt dezelfde packages of dezelfde versies daarvan. Een nieuwere versie van een package kan bijvoorbeeld anders werken dan een oudere versie. Om te voorkomen dat verschillende projecten elkaar in de weg zitten, werken we daarom met *virtuele omgevingen* (*environments*). Een environment kun je zien als een afzonderlijke Python-installatie met zijn eigen verzameling packages. Voor ieder project kan zo een geschikte en reproduceerbare werkomgeving worden gemaakt.

In dit practicum gebruiken we **Miniforge** om Python, environments en packages te beheren. Miniforge is een relatief compacte Python-distributie die gebruikmaakt van het `conda`-systeem en standaard packages uit het `conda-forge`-ecosysteem gebruikt. Hierdoor hoeven packages en hun onderlinge afhankelijkheden niet handmatig geïnstalleerd en bijgehouden te worden.

Voor het daadwerkelijk schrijven en uitvoeren van Python-code gebruiken we **Visual Studio Code (VS Code)**. VS Code is een programmeeromgeving waarin je onder andere Python-scripts en Jupyter notebooks kunt schrijven, uitvoeren en beheren. VS Code bevat daarbij niet zelf "de Python": we koppelen VS Code aan de Python-interpreter uit de environment die we met Miniforge hebben gemaakt.

In dit practicum ga je daarom stap voor stap een complete Python-werkomgeving opzetten. Je installeert Miniforge en VS Code, maakt vanuit de opdrachtprompt een eigen environment aan, installeert hierin enkele veelgebruikte wetenschappelijke packages en koppelt deze environment vervolgens aan VS Code. Tot slot controleer je met een eenvoudig Python-programma of alles correct is geïnstalleerd.

!!! voorbereiding "Voorbereidingsopdracht"

    1. Neem een laptop mee.
      1. Zorg voor een stabiele wifi-verbinding met de HvA.

## Python installatie

!!! opdracht "Opdracht 1 --- Oude Anaconda-installatie verwijderen"

    Voordat we een nieuwe Python-omgeving installeren, verwijderen we eerst eventuele oude installaties van Anaconda.

    1. Open in Windows **Instellingen** → **Apps** → **Geïnstalleerde apps**.
    1. Zoek naar **Anaconda** of **Anaconda3**. Indien Anaconda geïnstalleerd is, verwijder deze installatie.
    1. Open vervolgens de Verkenner en ga naar je gebruikersmap:

        ```text
        C:\Users\<gebruikersnaam>\
        ```

    1. Controleer of hier nog een map `anaconda3` aanwezig is. Verwijder deze map indien deze na het verwijderen van Anaconda is achtergebleven.
    1. Controleer ook of de volgende verborgen mappen of bestanden aanwezig zijn:

        ```text
        C:\Users\<jouw_naam>\anaconda3
        C:\Users\<jouw_naam>\miniconda3
        C:\Users\<jouw_naam>\.conda
        C:\Users\<jouw_naam>\.anaconda
        C:\Users\<jouw_naam>\.condarc
        C:\ProgramData\Anaconda3
        ```

        Verwijder deze alleen indien ze uitsluitend afkomstig zijn van je oude Anaconda-installatie.

    1. Start de computer opnieuw op.
!!! opdracht "Opdracht 3 --- Miniforge installeren"

    We gebruiken **Miniforge** voor het installeren en beheren van Python en de benodigde packages.

    1. Ga naar de officiële Miniforge-pagina:

        <https://conda-forge.org/download/>

    1. Download de meest recente **Miniforge3**-installer voor jouw besturingssysteem.

    1. Kies de installer die past bij je computer. Voor de meeste Windows-computers is dit:

        ```text
        Miniforge3-Windows-x86_64.exe
        ```

    1. Start het installatiebestand en doorloop de installatie.

    1. Gebruik de standaard installatiemap, tenzij je een goede reden hebt om hiervan af te wijken.

    1. Rond de installatie af en open daarna vanuit het startmenu de **Miniforge Prompt**.


!!! opdracht "Opdracht 4 --- Miniforge controleren"

    We controleren of Miniforge en het programma `conda` correct zijn geïnstalleerd.

    1. Open de **Miniforge Prompt**.

    1. Voer het volgende commando uit:

        ```text
        conda --version
        ```

    1. Als de installatie correct is verlopen, verschijnt een versienummer van conda.

    1. Controleer vervolgens welke Python-installatie op dit moment wordt gebruikt:

        ```text
        where python
        ```

    1. Bekijk het weergegeven pad. Dit pad hoort nu naar je installatie van **Miniforge3** te verwijzen.

!!! opdracht "Opdracht 5 --- Een Python-environment maken"

    We installeren Python niet rechtstreeks als één algemene installatie voor alle projecten. In plaats daarvan maken we binnen Miniforge een afzonderlijke *environment*.

    1. Open de **Miniforge Prompt**.

    1. Maak een nieuwe environment met de naam `practicum_omgeving`:

        ```text
        conda create -n practicum_omgeving python
        ```

    1. Bevestig de installatie wanneer daarom wordt gevraagd. Dit doe je door `y` te typen en vervolgens op **Enter** te drukken.

    1. Activeer vervolgens de nieuwe environment:

        ```text
        conda activate practicum_omgeving
        ```

    1. Controleer de geïnstalleerde Python-versie:

        ```text
        python --version
        ```

        Je ziet nu aan het begin van de opdrachtregel `(practicum_omgeving)` staan. Dit betekent dat de environment `practicum_omgeving` actief is.

    1. Je kunt ook bekijken welke environments aanwezig zijn. Naast `practicum_omgeving` zou op dit moment alleen de `base`-environment aanwezig moeten zijn. Gebruik hiervoor:

        ```text
        conda env list
        ```

        Je krijgt uitvoer die lijkt op:

        ```text
        # conda environments:
        #
        # * -> active
        # + -> frozen
        base                  C:\Users\<jouw_naam>\AppData\Local\miniforge3
        practicum_omgeving *  C:\Users\<jouw_naam>\AppData\Local\miniforge3\envs\practicum_omgeving
        ```
!!! opdracht "Opdracht 6 --- Wetenschappelijke packages installeren"

    Een nieuwe Python-environment bevat nog niet automatisch alle packages die we tijdens de practica nodig hebben. We installeren daarom een aantal veelgebruikte wetenschappelijke packages.

    1. Controleer eerst of de environment `practicum_omgeving` actief is. Aan het begin van de opdrachtregel moet `(practicum_omgeving)` staan.

    1. Installeer vervolgens NumPy, SciPy, Matplotlib, Pandas en Jupyter:

        ```text
        conda install numpy scipy matplotlib pandas jupyter
        ```

    1. Bevestig de installatie wanneer daarom wordt gevraagd.

    1. Bekijk na de installatie welke packages in de environment aanwezig zijn:

        ```text
        conda list
        ```

        **Vraag:** Zoek in de lijst de packages `numpy`, `scipy` en `matplotlib`. Welke versies zijn geïnstalleerd?


!!! opdracht "Opdracht 7 --- Visual Studio Code installeren"

    Tot nu toe hebben we Python en de benodigde packages geïnstalleerd. We hebben echter nog geen programma waarin we gemakkelijk Python-code kunnen schrijven. Hiervoor gebruiken we **Visual Studio Code (VS Code)**.

    1. Ga naar de officiële website van Visual Studio Code:

        <https://code.visualstudio.com/>

    1. Download en installeer de Windows-versie van VS Code.

    1. Start VS Code na de installatie.

    1. Open links in VS Code het onderdeel **Extensions**.

    1. Zoek naar de extensies **Python, Jupyter, Prettier, Rainbow CSV, Spreadsheet Viewer** en installeer deze.

## Mappenstructuur
### Mappenstructuur
Tijdens practica verzamel je verschillende bestanden, zoals Python-scripts, meetdata en figuren. Het is daarom belangrijk om vanaf het begin een duidelijke **mappenstructuur** te gebruiken. Zo blijven bestanden makkelijk terug te vinden en voorkom je dat verschillende projecten of versies door elkaar raken.

Maak voor ieder practicumserie of project een **aparte hoofdmap** en verdeel deze onder per practicum. Een goede mappenstructuur is een belangrijk onderdeel van zorgvuldig en reproduceerbaar werken.

!!! opdracht "Opdracht 8 --- mappenstructuur"

    In deze opdracht gaan we aan de slag om een goede structuur neer te zetten en deze te laden vanuit VS Code. 

    1. Open in VS Code **File** → **Open Folder...** → **Documenten**.
    1. Creëer een nieuwe map op de locatie die handig is bijvoorbeeld **documenten**. 
    1. Maak de mappenstructuur na uit onderstaande figuur.

Ieder practicum dat je start zal je beginnen met **Open Folder...** en dan de juiste practica kiezen. Zo zorg je ervoor dat je altijd je data, figuren en gebruikte scripts kunt terugvinden.

<!-- Exporteer de oorspronkelijke LaTeX-figuur als SVG naar ../assets/python/mappenstructuur.svg
![Boomdiagram voor apparaatcommunicatie.](../assets/python/mappenstructuur.svg) -->

```text
Leerjaar 2/
└── Practicum/
    ├── Periode 1/
    │   ├── Practicum Python Intro/
    │   │   ├── data/
    │   │   ├── figuren/
    │   │   ├── test.py
    │   │   └── test.ipynb
    │   ├── Practicum Lenzen/
    │   ├── Practicum Spectrometer/
    │
    └── Periode 2/
        ├── Practicum 1/
        ├── Practicum 2/
        └── Practicum 3/
```

## Test Python
Een **Jupyter Notebook** is een document waarin Python-code in afzonderlijke blokken, zogenaamde *cellen*, kan worden uitgevoerd. Je kunt ze herkennen aan de extensie **.ipynb**. Het grote voordeel hiervan is dat je code stap voor stap kunt uitvoeren en het resultaat direct onder de betreffende cel verschijnt. Naast code kunnen notebooks ook tekst, formules en figuren bevatten.

Dit maakt notebooks bijzonder geschikt voor practica en data-analyse: je kunt meetgegevens inlezen, berekeningen uitvoeren en grafieken maken zonder telkens het volledige programma opnieuw uit te voeren. Tijdens de practica zullen we Jupyter Notebooks daarom regelmatig gebruiken.

!!! opdracht "Opdracht 9 --- Test Jupyter Notebook (.ipynb)"

    In de vorige opdrachten hebben we de basis gelegd voor een overzichtelijke mappenstructuur en hebben we de benodigde software geïnstalleerd. Nu gaan we controleren of alles correct werkt.

    1. Open in VS Code via **File** → **Open Folder...** de map **Practicum Python Intro**.

    1. Open het bestand `script.ipynb` en voeg met `+ Code` een nieuwe codecel toe.

    1. Neem de onderstaande code over en voer de cel uit met `Shift+Enter`.

    1. Als er nog geen Python-omgeving is geselecteerd, vraagt VS Code om een *kernel* te kiezen. Selecteer hier de eerder aangemaakte `practicum_omgeving`. Deze kan soms wat verstopt zitten.

    1. Je kunt de actieve omgeving ook controleren of wijzigen via `Select Kernel` rechtsboven in het notebook. Controleer of hier `practicum_omgeving` is geselecteerd.

    1. Controleer of de uitvoer van de code overeenkomt met wat je verwacht.

```python title="script.ipynb"
print("Hello world")

import numpy as np

a = np.array([1, 2, 3, 4])

print("Array a:", a)
print("Array a^2:", a**2)
```

Naast Jupyter Notebooks wordt Python veel gebruikt in de vorm van
**Python-scripts**. Dit zijn tekstbestanden met de extensie **.py**.
In tegenstelling tot een Jupyter Notebook bestaat een Python-script niet uit
losse cellen: bij het uitvoeren wordt het programma in principe van boven naar
beneden uitgevoerd.

Bij een Jupyter Notebook hebben we hiervoor een *kernel* geselecteerd.
Voor een Python-script moet VS Code weten welke **Python-interpreter**
gebruikt moet worden. Het is belangrijk om hier onze eerder gemaakte
`practicum_omgeving` te kiezen. Anders kan het gebeuren dat het script
met een andere Python-installatie wordt uitgevoerd waarin bijvoorbeeld onze
packages niet zijn geïnstalleerd.

!!! opdracht "Opdracht 10 --- Test Python-script (.py)"

    1. Zorg dat de map **Practicum Python Intro** nog geopend is in VS Code.

    1. Open het bestand met de naam `script.py`.

    1. Selecteer de juiste Python-interpreter. Druk hiervoor op `Ctrl+Shift+P` en zoek naar:

        ```text
        Python: Select Interpreter
        ```

    1. Selecteer de eerder gemaakte `practicum_omgeving`. Als deze niet direct zichtbaar is, kijk dan bij de overige beschikbare Python-omgevingen.

    1. Neem onderstaande code over in `script.py` en sla het bestand op.

        ```python title="script.py"
        import sys
        import numpy as np

        print("Hello world")

        a = np.array([1, 2, 3, 4])

        print("Array a:", a)
        print("Array a^2:", a**2)

        print("\nPython wordt uitgevoerd vanuit:")
        print(sys.executable)
        ```

    1. Voer het programma uit met de knop **Run Python File** rechtsboven in VS Code.

    1. Onderaan VS Code wordt nu een **Terminal** geopend. Controleer of het programma zonder foutmeldingen wordt uitgevoerd.


!!! opdracht "Opdracht 11 --- Controleer de Python-omgeving"

    Bekijk de laatste regel van de uitvoer van je programma. Hier staat het pad naar het bestand `python.exe` waarmee het programma is uitgevoerd.

    1. Controleer of in dit pad de naam `practicum_omgeving` voorkomt.

    1. Controleer ook linksonder in VS Code welke Python-versie en environment geselecteerd zijn.

    1. Staat hier niet `practicum_omgeving`? Selecteer dan opnieuw de juiste interpreter via `Python: Select Interpreter` en voer `script.py` opnieuw uit.
