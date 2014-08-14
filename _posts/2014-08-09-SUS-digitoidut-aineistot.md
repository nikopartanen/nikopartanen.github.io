---
layout: post
title: "SUS: Digitoidut aineistot"
description: "Suomalais-Ugrilaisen Seuran luvalla Niko Partanen on digitalisoinut jo julkaistuja komin kielennäytteitä."
author: "Niko Partanen"
date: "7 Aug 2014"
output: html_document
comments: true
image:
  feature: elan-example.jpg

---

Niko Partanen on digitoinut tutkimusprojektin [Down River Vashka](http://www.downrivervashka.net) yhteydessä [Suomalais-Ugrilaisen Seuran](http://www.sgr.fi) julkaisemia aineistoja komin kielen Udoran murteesta. Projektin aikana tehtiin kenttätöitä tämän saman murteen parissa, minkä takia oli välttämätöntä tutustua jo julkaistuihin materiaaleihin. Suomalaisista tutkijoista tämän murteen parissa ovat työskennelleet ainakin Yrjö Wichmann sekä T. E. Uotila.

Käytännössä Syrjänische Texte III:n teksteistä digitoitiin sivut XXX-XXX. Työ tehtiin Koneen säätiön ja MinoEuRus-projektin rahoituksesta nauttiessa, mutta silti tämä oli muun työn ohessa tehty ylimääräinen toimi. Tämän takia esimerkiksi saksankielisiä käännöksiä ei erikseen skannattu, vaan työskenneltiin valmiiksi saatavilla olleiden skannausten kanssa.

## Digitointimuoto

Uudet nauhoitetut aineistot on arkistoitu Nijmegenin Max Planck -instituutin arkistoon. Niiden litterointi on tehty ELAN-ohjelmalla, minkä takia myös vanhat aineistot on muutettu tämän ohjelman tuottamaa XML-rakennetta vastaaviksi tiedostoiksi. Työhön kuului painettujen aineistojen digitalisointi tekstitiedostoiksi, niiden oikoluku sekä ELAN-tiedostojen luonti. Tähän formaattiin päädyttiin seuraavista syistä:

- Aineiston muuttaminen eri tiedostomuotoihin on helppoa
- Uusien ja vanhojen aineistojen vertaaminen on yksinkertaista
- Max Planck -instituutin omat hakutoiminnot ovat suoraan käytettävissä

Käyn tässä dokumentissa yksityiskohtaisesti läpi, kuinka aineistoja voi hyödyntää.

## Arkiston rakenne

Arkistoa voi selata tähän tarkoitukseen kehitetyn [IMDI-selaimen](https://corpus1.mpi.nl/ds/imdi_browser/) avulla. Selaimen vasemmalla puolella on puumainen rakenne, josta voi avata eri kokoelmia. Nyt käsitellyt Suomalais-Ugrilaisen Seuran aineistot sijaitsevat kohdassa Donated Corpora --> Permic Varieties --> kpv_udora --> 002 Sessions --> kpv_udora_SFOu. Muut kokoelmat sisältävät eri materiaaleja, esimerkiksi kpv_syktyvkar sisältää Niko Partasen Syktyvkarissa tekemiä sosiolingvistisiä haastatteluja, jotka eivät ole tällä hetkellä vapaasti käytettävissä. Kokoelma kpv_izva puolestaan sisältää [Koneen säätion](http://www.koneensaatio.fi) parhaillaan tukemassa projektissa käsiteltyjä komin pohjoismurteen aineistoja.

Arkiston rakenne on siinä mielessä kokeellinen, että se tulee varmasti muuttumaan aineiston määrän kasvaessa. Tavoitteena on, että tulevan kolmen vuoden aikana puhuttujen komiaineistojen koko olisi satoja tuhansia sanoja. Jossain vaiheessa on mietittävä, onko aineisto paras jakaa julkaisijan, murteen, nauhoituspaikan, digitalisointihankkeen vai minkä muuttujan mukaan. Huomautettakoon, että varsinaisesta rakenteesta riippumatta aineiston metadata sisältää kaikki kyseiset tiedot.

## Aineistosta haku

Arkiston ELAN-tiedostot voi vapaasti ladata omalle tietokoneelleen ja tehdä hakuja ELAN-ohjelmassa. Esittelen kuitenkin hakumenetelmiä, jotka ovat jo valmiina suoraan arkiston sisällä. 

Valitsemalla esimerkiksi arkistonoodin kpv_udora_SFOu on mahdollista klikata linkkiä **Annotation content search**. Tämä käynnistää Trova-ohjelman, jonka avulla voi tehdä hakuja tiedostoista hyvin samalla tavalla kuin ELAN:in avulla tehtäisiin.

Trovan käyttöliittymä näyttää tältä:

<figure>
	<img src="/images/trova-all.jpg">
	<figcaption>Trovan käyttöliittymä</figcaption>
</figure>

Käyn tässä läpi Single Layer Search -haun toiminnan. Multiple Layer Search on hyödyllinen tehtäessä hakuja kattavasti käännettyihin ja glossattuihin aineistoihin, mutta näissä komin materiaaleissa on yleensä vain kominkielinen teksti.

Tästä palkista hakutapaa voi kuitenkin vaihtaa:

<figure>
	<img src="/images/trova-layers.jpg">
	<figcaption>Hakutavan vaihto</figcaption>
</figure>

Sivun yläosassa on kaksi osaa, "History" and "Mode". History näyttää hakuhistorian, mikä on hyödyllinen eri hakuja toistettaessa. Mode puolestaan määrittelee tarkemmin, kuinka haku toteutetaan. Kuvassa alla on valittuna haun kohteeksi "Annotation", eritelty, että haussa ei välitetä isoista ja pienistä kirjaimista sekä määritelty haun tavaksi "regular expression.

<figure>
	<img src="/images/trova-historyandmodes.jpg">
	<figcaption>Trovan historia- ja moodi-valikot</figcaption>
</figure>

Regular expression kääntyy suomeksi säännöllisiksi lausekkeiksi. Ne ovat tapa kirjoittaa hakuja siten, että varsinaisten sanojen sijasta haetaan kaikki tietyt ehdot täyttävät esiintymät. Esimerkiksi käyttämäni haku:

    \b[А-ЯӦа-яӧі\-]+\b

<br/>
Hakee kaikki yksittäiset sanat kominkielisestä tekstistä. \\b tarkoittaa säännöllisissä lausekkeissa sanarajaa. Hakasulkujen sisään on määritelty suuret sekä pienet kyrilliset aakkoset välillä а-я. Tämän lisäksi on lisättävä merkit ӧ ja і. Ainoastaan ensimmäisestä tarvitaan isoa kirjainta, sillä komissa sananalkuinen і kirjoitetaan kyrillisellä kirjaimella и.

Näiden lisäksi on vielä määriteltävä, että haetaan väliviivaa. Sen edellä on kenoviiva, sillä näin kerrotaan haulle, että väliviivalla tarkoitetaan juuri väliviivaa. Kuten esimerkistä näkee, tällä merkillä voidaan myös määritellä hakuryhmiä kuin a-z tai а-я. Väliviiva on lisättävä siitä syystä, että haluan laskea erilaiset sanaliitot yksittäisiksi sanoiksi. Hakasulkujen jälkeen tuleva plus-merkki tarkoittaa, että hakasulkujen sisällä olevien merkkien esiintymiä voi olla useampi, periaatteessa miten monta tahansa, kunnes törmätään uuteen sanarajaan.

ELAN-tiedostot ovat usein melko monimutkaisia, joten on erikseen valittava mistä osasta tiedostoa haetaan. Käytännössä Single layer search -haussa tarvitaan ehkä useimmiten valintoja "Tier type: orthT" ja "Tier type: wordT". Näin haetaan joko lauseen tai intonaatiojakson kokoisista yksiköistä, tai sitten pelkistä yksittäisistä sanoista.

<figure>
	<img src="/images/trova-tiers.jpg">
	<figcaption>ELAN-tierien valinta</figcaption>
</figure>

Kohdasta Action voi valita kuinka hakutulos esitetään.

<figure>
	<img src="/images/trova-concordance.jpg">
	<figcaption>Hakutuloksen näyttötapa</figcaption>
</figure>

Esimerkiksi Show Concordance View näyttää jokaisen hakutuloksen esiintymiskontekstissaan.

<figure>
	<img src="/images/trova-searchresult1.jpg">
	<figcaption>Sanamuodot kontekstissaan</figcaption>
</figure>

Kuten kuvasta näkee, on nyt lihavoitujen hakutulosten joukossa jokainen sana siinä järjestyksessä, jossa ne esiintyvät. Pisteet, pilkut ja muut välimerkit ovat jääneet pois. Hakutulos sanoo "Found 8716 hits in 1229 annotations." Tämä tarkoittaa, että sanoja nyt valitussa aineistossa on 8716. Poistamalla esimerkiksi väliviivan hausta saadaan sanamääräksi 9827, mutta tällöin esimerkiksi кык-суда 'kaksikerroksinen' jaetaan sanoiksi кык ja суда. Riippuu jokaisesta itsestään, mikä on milloinkin paras vaihtoehto.

Seuraavaksi valitsen haun kohteeksi "Tier type: wordT". Kuten aiemmin mainitsin, hakee tämä ainoastaan yksittäisistä sanoista. Valitsen myös Action-valikon alta "Show Frequency View Sorted by Frequency". Tämä näyttää löydettyjen sanojen, tässä tapauksessa niiden kaikkien, esiintymismäärän järjestettynä yleisyyden mukaan. Tulos näyttää seuraavalta.

<figure>
	<img src="/images/trova-searchresult2.jpg">
	<figcaption>Sanamuotojen frekvenssi</figcaption>
</figure>

Tulos ei ole mitenkään yllättävä, mutta havainnollistaa hyvin, kuinka monimutkaisemmilla hakukomennoilla erilaisia aineistoja pystyy vertailemaan keskenään. Suomalais-Ugrilaisen Seuran julkaisemien aineistojen lisäksi käytettävissä on myös Udoralla kesinä 2012 ja 2013 tehtyjen haastattelujen litterointeja. Myös Kotuksen arkistoista saatuja Erik Vászolyin ja Muusa Vahros-Pertamon nauhoituksia on digitoitu.

Mainittakoon, että tällä hetkellä ulkomaisten tutkijoiden puheenvuoroista ei ole olemassa sanatason jaottelua. Näin ollen heidän repliikkinsä eivät näy esimerkiksi sanamuotojen frekvenssiä tarkasteltaessa. Aikomuksena on tarkistaa tiedostojen rakennetta lähiaikoina.