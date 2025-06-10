

<p align="center">
<img src="C:\Users\Cecil\OneDrive\Documents\A Van Hall Larenstein\schooljaar 2\jaar 2 periode 4\het project\rheumatoid-arthritis-color-icon-illustration-vector.jpg" alt="Reuma Logo" width="600"/>
</p>

# Transcriptomics Casus – Reumatoïde Artritis (RA)

## 📁 Inhoud/structuur


- `data/raw/` – Ruwe data bestanden
- `data/processed` - Bewerkt data-bestanden
- `scripts/` – Alle R-scripts (Rsubread, DESeq2, KEGG, GO)
- `resultaten/` - Tabellen, grafieken, output
- `bronnen/` - gebruikte bronnen 
- `README.md` - het document om de tekst hier te genereren
- `assets/` - Afbeeldingen die je in je README wilt tonen
- `data_stewardship/` - Voor de competentie beheren ga je aantonen dat je projectgegevens kunt beheren met behulp van GitHub. In deze folder kan je hulpvragen terugvinden om je op gang te helpen met de uitleg van data stewardship. 


## Introductie

Reumatoïde artritis (RA) is een auto-immuunziekte die wordt gekenmerkt door chronische ontstekingen in de gewrichten. Doormiddel van RNA-sequencing (transcriptomics) kan de genexpressie van RA-patiënten worden vergeleken met gezonde controlepersonen. Dit kan helpen bij het identificeren van genen en biologische processen die betrokken zijn bij het ziekteproces.
In het project, wordt gebruik gemaakt van publicly beschikbare RNA-seq data van vier RA-patiënten en vier gezonde controles. Door de data te analyseren en visualiseren, wordt getracht, inzicht te krijgen in welke genen significant anders tot expressie komen bij RA en welke biologische pathways hierbij betrokken zijn.
Het doel van het onderzoek is om differentieel tot expressie komende genen te identificeren die mogelijk een rol spelen in de pathogenese van RA. Daarnaast wordt gekeken naar betrokken GO-termen en KEGG-pathways om deze genen functioneel te duiden.


## Methode 

Voor deze analyse is RNA-seq data van vier reumatoïde artritis (RA) monsters en vier controle monsters gebruikt. De workflow bestond uit de volgende stappen: kwaliteitscontrole, mapping van de reads met het humane referentiegenoom, tellen van reads per gen, normaliseren en uitvoeren van differentiële expressieanalyse.
De reads zijn gemapt met het `Rsubread-pakket` in R. Vervolgens zijn gen-expressie niveaus geteld met behulp van `featureCounts`. Voor de differentiële expressieanalyse is `DESeq2` toegepast, waarbij genen met een p-waarde < 0.05 en een log2 fold change > 1 als significant werden beschouwd. 
Pathway-analyses zijn uitgevoerd met het `KEGGREST- en pathview-pakket`. Daarnaast is een GO-enrichment analyse uitgevoerd met behulp van `Goseq`. Visualisaties zoals een volcano plot en GO-term bubble plot ondersteunen de resultaten.

<p align="center">
<img src="Assets/Methode_flowschema.png" alt="Flowschema methode" width="700"/>
</p>

Alle scripts zijn te vinden in de map `Scripts`, en gebruikte data en resultaten zijn beschikbaar in de map `Data`.


## 📊 Resultaten


De analyse resulteerde in een lijst van differentieel tot expressie komende genen. In totaal werden 2085 genen significant opgereguleerd en 2487 genen significant neerwaarts gereguleerd bij RA-patiënten ten opzichte van de controles. 
De genen met de hoogste fold change en de laagste p-waarden zijn geselecteerd voor nadere analyse. Visualisatie met een volcano plot toont een duidelijke scheiding tussen up- en down-gereguleerde genen (zie Figuur 1).
Daarnaast werden met behulp van GO-enrichment analyse meerdere biologisch relevante processen geïdentificeerd. De top GO-termen hadden voornamelijk betrekking op immuunresponsen, inflammatoire processen en celadhesie.
Met KEGG pathway-analyse werden pathways zoals het Toll-like receptor signaling pathway (hsa04620) significant geassocieerd met de differentieel tot expressie komende genen.

De gebruikte plots en resultatenbestanden zijn beschikbaar in de map `Assets` en `Data`.


## Conclusie

Uit de analyse blijkt dat er significante verschillen zijn in genexpressie tussen RA-patiënten en gezonde controles. Vooral genen die betrokken zijn bij immuunrespons en ontstekingsprocessen tonen een verhoogde expressie bij RA-patiënten. 
De identificatie van relevante pathways, zoals het Toll-like receptor signaling pathway, bevestigt eerdere bevindingen over het belang van dit pad bij auto-immuunziekten. De verrijkte GO-termen ondersteunen de betrokkenheid van immuunprocessen in RA.
Deze resultaten dragen bij aan een beter begrip van de moleculaire mechanismen van RA en kunnen mogelijk in de toekomst bijdragen aan het ontwikkelen van biomarkers of nieuwe therapieën.
Voor vervolgonderzoek wordt aanbevolen om de dataset uit te breiden en validatie-experimenten uit te voeren op proteïneniveau om de biologische relevantie verder te onderbouwen.


