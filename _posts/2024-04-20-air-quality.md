---
title: "Analisi sulla qualità dell'aria a Torino"
layout: post
post-image: "/assets/images/2024-04-20-air_quality/03_circos.png"  #/assets/images/2023-07-31-PCA/output_20_0.png #
description: "Analisi dei dati ARPA delle concentrazioni di PM10 e NO2 a Torino negli anni. Effetti del lockdown e delle olimpiadi."
tags:
- Torino
- Data Viz
---

__TLDR__ con link ai vari paragrafi:
- A Torino negli ultimi 19 anni i limiti di legge per il PM10 [non sono mai stati rispettati](#torino-non-rispetta-i-limiti-di-legge)
- Osservando l'andamento durante tutti i giorni dell'anno si vede come [in inverno le concentrazioni di PM10 siano molto più alte](#in-inverno-si-respira-male).
- Le concentrazioni di NO2 sono massime nelle fasce orarie 07:00-09:00 e 19:00-21:00, corrispondenti ai periodi di spostamento da e per i luoghi di lavoro, cioè i momenti di traffico più intenso.
- La stazione Lingotto registra una minor concentrazione di NO2 probabilmente per la minor centralità del quartiere Lingotto che per il fatto di essere posizionata all'interno del Parco di Vittorio ed è quindi circondata dal verde. 
- Le concentrazioni di NO2 sono più elevate durante i [giorni lavorativi](#nei-giorni-infrasettimanali-si-inquina-di-più) (Lunedì-Venerdì).
- Durante il lockdown 2020 le concentrazioni di NO2 [si sono ridotte drasticamente](#durante-il-lockdown-le-concentrazioni-di-no2-si-sono-ridotte-drasticamente).
- Le olimpiadi del 2006 hanno probabilmente indotto un maggior spostamento e traffico facendo registrare un [picco di concentrazioni di NO2](#focus-olimpiadi-2006) in particolare nella stazione Lingotto.


# Reperimento dei dati
I dati sono stati scaricati dal [portale](https://aria.ambiente.piemonte.it/#/qualita-aria/dati) della qualità dell'aria ARPA Piemonte, selezionando PM10 o NO2 come "tipologia inquinante".

Nota: Nel caso del PM10 ogni stazione presenta due tipi di misurazione giornaliera/oraria per il particolato: "PM10 - Basso Volume" e "PM10 - Volume Beta", i valori mostrati nei grafici sono rappresentano la media delle due misurazioni.

---

# PM10

Il PM10 può avere origine naturale (erosione di rocce o eruzioni vulcaniche ad esempio) o antropiche, ad esempio:

- combustioni per riscaldamento
- combustione nei motori a scoppio
- combustione per attività industriali
- traffico veicolare (erosione gomme)
- reazione chimica con altri composti atmosferici ossidi di azoto (NOx), il biossido di zolfo (SO2), l’ammoniaca (NH3) ed i Composti Organici Volatili (COV).

Secondo il [XIV Rapporto Qualità dell’ambiente urbano - Edizione 2018](https://www.isprambiente.gov.it/it/pubblicazioni/stato-dellambiente/xiv-rapporto-qualita-dell2019ambiente-urbano-edizione-2018) dell'ISPRA:

> Tra gli inquinanti atmosferici il particolato è quello con il maggior impatto sulla salute umana. Vari studi epidemiologici sugli effetti sanitari dell’inquinamento atmosferico da particelle, hanno evidenziato associazioni tra le concentrazioni in massa del PM10 e un incremento sia di mortalità che di ricoveri ospedalieri per malattie cardiache e respiratorie nella popolazione generale.

Inoltre l'[International Agency for Research on Cancer](https://www.iarc.who.int/) (IARC), l'ente preposto alla catalogazione delle sostanze correlate al cancro, ha classificato il particolato come sostanza __sicuramente cancerogena__ per l'uomo (IARC gruppo 1).



## Torino non rispetta i limiti di legge
Ci sono due limiti previsti per legge attualmente in vigore per quanto riguarda le emissioni di PM10 [(2008/EC/50 e D.Lgs. 155/2010)](https://www.eea.europa.eu/data-and-maps//assets/images/2024-04-20-air_quality/particulate-matter-pm10-annual-limit-value-for-the-protection-of-human-health-7):

- La media annuale non deve essere superiore a 40 µg/m3
- La media giornaliera non deve superare i 50 µg/m3 per più di 35 giorni all'anno.

Nel primo grafico qui sotto viene mostrato l'andamento medio negli anni delle emissioni di PM10 per stazione. <br>
La linea trateggiata rappresenta il limite annuale medio di 40 µg/mc. Le emissioni sono state ridotte dal 2004 (da una media di 59 µg/m3 a 32 µg/m3 annui) probabilmente grazie alle misure adottate in seguito al decreto legge. <br>
Il grafico sotto invece indica il numero di giorni in cui si è superato il limite giornaliero di 50µg/m3. Questo limite non deve essere superato per più di 35 giorni all'anno. Nonostante i miglioramenti nel tempo, __a Torino negli ultimi 19 anni questo limite non è mai stato rispettato__ (considerando media tra le stazioni).

<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/03_by_year.png" style="display: block; margin: auto;" />
</p>


## In inverno si respira male
Ora spacchettiamo il plot appena visto guardando il dettaglio giorno per giorno.

Nella heatmap di sinistra ogni riga corrisponde ad un giorno dell'anno (la prima riga è il 1° gennaio, l'ultima è il 31 dicembre), ogni colonna corrisponde ad un anno. Il valore della cella rappresenta la concentrazione media giornaliera di PM10 considerata come media tra le due stazioni.
La scala colore corrisponde a quella ufficiale utilizzata dall'ARPA per i vari livelli di emissione (si veda legenda). Il boxplot sopra alla heatmap di sinistra è la distribuzione annua dele concentrazioni di PM10.
La heatmap di destra invece indica se quel giorno il limite di legge di 50 µg/m3 è stato superato (nero) oppure no (bianco). Il barplot sopra la heatmap di destra è il totale di giorni in cui sono stati superati i limiti di legge (somma delle celle nere della heatmap).

<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/03_heatmap.png" width="100%" />
</p>
<p align="center">
<em>Andamento delle concentrazioni di PM10 giorno per giorno dal 2004 al 2023</em>
</p>


Da queste heatmap si può notare come le concentrazioni più elevate negli anni siano durante i mesi invernali, date dall'ulteriore emissioni di PM10 dovute ai riscaldamenti. <br>
Dal 2004 al 2009 ci sono stati valori allarmanti di PM10, che sono stati placati probabilmente dall'attuazione del [2008/EC/50](https://www.eea.europa.eu/data-and-maps//assets/images/2024-04-20-air_quality/particulate-matter-pm10-annual-limit-value-for-the-protection-of-human-health-7) con il degreto legge 155/2010.

In estate non ci sono mai giorni fuori limite, ma nonostante ciò, sono sufficienti i giorni invernali per superare i limiti previsti per legge.

---

# NO2

Il biossido d'azoto è un gas irritante per le vie aeree e per gli occhi. Origina dalla reazione di due monoossidi di azoto (NO) che derivano prevalentemente dal __processi di combustione__ e __traffico veicolare__.

A differenza dei PM10 che persistono nell'aria per lunghi periodi, i biossidi d'azoto sono dei gas di breve durata, ossia si depositano o reagiscono con altri gas entro poche ore. Di conseguenza, il biossido d'azoto rimane in prossimità del sito di emissione, rendendolo un utile indicatore dell'inquinamento veicolare quotidiano in specifiche aree e orari.

Per questo motivo i dati misurati dall'ARPA sono infatti campionamenti orari, non giornalieri.

Si veda ad esempio la concentrazione oraria media di NO2 nel 2022 per le stazioni Lingotto e Consolata: è interessante notare che i due __maggiori picchi di emissione__ si verificano durante le __fasce orarie 07:00-09:00 e 19:00-21:00__, corrispondenti ai periodi di spostamento da e per i luoghi di lavoro, rappresentando così i momenti di traffico più intenso.

Alla Stazione Lingotto le concentrazioni di NO2 sono notevolmente più basse di quelle della consolata, probabilmente sia per la minor centralità del quartiere Lingotto che per il fatto di essere posizionata all'interno del Parco di Vittorio ed è quindi circondata dal verde. 


<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/03_NO2_2022_hours.png" width="100%" />
</p>
<p align="center">
<em>Andamento orario medio delle emissioni di NO2 nel 2022 (0.95 CI)</em>
</p>

## Nei giorni infrasettimanali si inquina di più
Se osserviamo le concentrazioni orarie di NO2 divise per tipo di giorno (Weekend = Sabato e Domenica, Business day = tutti gli altri) è evidente che c'è una drastica riduzione di emissioni durante la mattina dei weekend.

In particolare nella fascia 6:00-12:00 c'è la riduzione massima di concentrazione di NO2, a confermare l'ipotesi che gli spostamenti tramite i mezzi a combustione verso gli uffici comporta una grande produzione di inquinanti.
Nelle ore serali le concentrazioni del weekend ritornano confrontabili con quelle dei giorni lavorativi.

<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/03_NO2_2022_hours_weekend_vs_weekday.png" width="100%" />
</p>
<p align="center">
<em>Andamento orario medio delle emissioni di NO2 nel 2022, divise per tipologia di giorno settimanale e per stazione.</em>
</p>




## Durante il lockdown le concentrazioni di NO2 si sono ridotte drasticamente 
Durante il lockdown per COVID19 del 2020, tutte le persone dovevano restare a casa e lavorare in modalità di smartworking, ad eccezione dei lavoratori essenziali o di coloro che non potevano farne a meno. Per valutare se vi sia stata una diminuzione delle concentrazioni di NO2 a causa della ridotta mobilità delle persone, possiamo confrontare il periodo dal 9 al 18 Marzo 2020 con lo stesso intervallo di tempo degli anni precedenti e successivi.

I valori medi orari di NO2 durante il periodo di lockdown sono stati i più bassi degli ultimi 3 anni e addirittura inferiori dei due anni successivi. È particolarmente sorprendente notare che la media per l'intero periodo di lockdown del 2020 presso la stazione della Consolata è stata di 26 µg/m³, mentre nello stesso periodo dell'anno precedente era di 51.9 µg/m³, indicando quindi una riduzione delle emissioni pari al 50%.

<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/03_NO2_hourly_covid_period.png" width="100%" />
</p>
<p align="center">
      <em>Medie orarie di concentrazioni di NO2 in un intervallo di tempo che va dal 9 Marzo al 18 Marzo per tutti gli anni considerati. La curva rossa identifica il periodo di lockdown </em>
</p>


<!-- | Stazione  | 2017 | 2018 | 2019 | 2020 | 2021 | 2022 |
| :-: |:-: | :-: |:-: | :-: |:-:|:-:|
| Torino - Consolata  | 58.60 | 51.39 | 51.94 | 26.07 | 40.82 | 39.27 |
| Torino - Lingotto  | 39.31 | 35.92 | 32.06 | 22.52 | 27.34 | 40.35 | -->


## Andamento annuale NO2
Per il biossido di azoto, il D.Lgs 155/2010 stabilisce per la protezione della salute umana i seguenti limiti: 
- Limite medio annuale di 40 µg/m³. 
- Limite orario di orario 200 µg/m³ da non superare più di 18 volte in un anno


Nei due grafici sottostanti, è possibile esaminare l'evoluzione delle emissioni di NO2 in relazione alle soglie di legge. In generale, nel corso degli anni, si è registrata una diminuzione delle emissioni. Tuttavia, la stazione della Consolata ha costantemente riportato valori medi annuali superiori a quelli considerati dannosi per la salute, mantenendo costantemente livelli superiori a 40 µg/m3 fino al 2022. Al contrario, la stazione Lingotto ha sempre rispettato i limiti di legge a partire dal 2018. 
Questo fatto è probabilmente dovuto ai motivi geografici  della stazione Lingotto menzionati sopra.

Inoltre entrambe le stazioni negli ultimi hanno misurato valori orari sempre al di sotto della soglia oraria di 200 µg/m3.
Tuttavia, nel 2006, questa soglia è stata ampiamente superata, con 38 ore di superamento rilevate presso la stazione della Consolata e 39 ore presso quella del Lingotto. Questo aumento potrebbe essere in parte attribuito all'incremento del traffico dovuto alle Olimpiadi.



<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/03_NO2_limiti.png" width="100%" />
</p>
<p align="center">
      <em>Andamento annuale delle emissioni di NO2 e rispettivi limiti di legge (linee tratteggiate)</em>
</p>


Infatti, le olimpiadi del 2006, si sono svolte a Torino, in particolare nel quartiere di Torino Lingotto e la stazione di Torino lingotto è molto vicina alle sedi delle olimpiadi come mostrato nella figura seguente.

<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/olimpics.png" width="100%" />
</p>


## Focus Olimpiadi 2006
In particolare, nel grafico sottostante sono rappresentate le concentrazioni medie giornaliere (righe) in ogni anno (colonne) dal 2003 al 2022. Si nota chiaramente un picco di emissioni di NO2 tra gennaio e febbraio 2006 rispetto agli altri anno. Le olimpiadi si sono svolte tra il 10 e il 26 febbraio, quindi è probabile che questo picco sia dovuto proprio all'affluenza di tante persone nei giorni dell'evento e in particolare in quelli precedenti ad esso.

Un ulteriore picco di concentrazione di NO2 si manifesta intorno al 12 gennaio 2009. Un report ["Uno sguardo all’aria"](https://www.arpa.piemonte.it/approfondimenti/territorio/torino/aria/Pubblicazioni/relazione-qualita-aria-anno-2009) dell'ARPA (2009) suggerisce che tale circostanza sembra essere correlata a un fenomeno di inversione termica, che ha limitato il rimescolamento dell'aria e quindi l'accumulo di inquinanti.

> Una parziale spiegazione di tale fenomeno può trovarsi nella particolare meteorologia del mese di gennaio 2009. In tale periodo è stata registrata un’intensa nevicata in pianura [...]. Come è noto, la presenza di neve riflette fortemente la luce solare diretta (effetto albedo), di conseguenza l’aria a contatto con il terreno si raffredda molto rapidamente, raggiungendo temperature inferiori rispetto agli strati sovrastanti.
L’alta pressione, la ridotta durata del giorno e la presenza di neve al suolo hanno favorito per diversi giorni (11-17 gennaio) l’instaurarsi di una condizione di inversione termica particolarmente intensa, in cui la temperatura al suolo è risultata più bassa che in quota e il rimescolamento verticale degli strati atmosferici fortemente limitato. [...] Questa condizione di stabilità meteorologica non ha certamente favorito la normale diffusione atmosferica degli inquinanti e ha quindi causato l’alto numero di superamenti del limite orario consentito di NO2, registrato proprio
in questo periodo.


<p align="center">
  <img src="/assets/images/2024-04-20-air_quality/03_NO2_years_days_heatmap.png" width="100%" />
</p>
<p align="center">
      <em>Effetti delle olimpiadi (10-26 febbraio 2006): la heatmap mostra le concentrazioni di NO2 misurate dalla Stazione di Torino Lingotto a fissato giorno e anno dal 2003 al 2022.</em>
</p>


# Note
L'immagine di copertina rappresenta esattamente gli stessi risultati della heatmap del PM10. L'ho messa in copertina perché è bella esteticamente ma difficile da interpretare e leggere.


# Fonti e approfondimenti
-  [Documento governativo](https://www.salute.gov.it/imgs/C_17_dettaglioPNI_1018_allegati_allegati_itemName_0_allegato.pdf) sui limiti orari, giornalieri e annuali 

- [Deliberazione della Giunta Regionale 6 agosto 2021, n. 26-3694](http://www.cittametropolitana.torino.it/cms/risorse/ambiente/dwd/qualita-aria/blocchi-traffico/DGR_03694_1050_06-08-2021.pdf): 

> "con sentenza del 19 dicembre 2012 (causa C-68-11), la Corte di Giustizia dell’Unione Europea ha condannato l’Italia per non aver provveduto, negli anni 2006 e 2007, ad assicurare che le concentrazioni di materiale particolato PM10 rispettassero i valori limite fissati dalla Direttiva 1999/30/CE in numerose zone e agglomerati del territorio italiano, tra cui quelle della Regione Piemonte;" 


- Dal 2014 vige [l'accordo del bacino Padano](https://www.salute.gov.it/portale/sicurezzaChimica/dettaglioNotizieSicurezzaChimica.jsp?lingua=italiano&menu=notizie&p=dalministero&id=1473)

- Dal 2019 è in atto il [Piano Regionale Qualità dell'Aria (PRQA)](https://www.regione.piemonte.it/web/sites/default/files/media/documenti/2019-04/prqa_allegatoa_def.pdf)

- Dal 2021: [Misure del semaforo antismog](http://www.comune.torino.it/emergenzaambientale/): coinvolve misure di limitazione del traffico, riduzione dei riscaldamenti, dispersione liquami etc.

