(2016-03-02: Lisada pilt, kas inglisekeelsest versioonist või teha uus ning täpsem, tõenäoliselt ptk.5)
(2016-03-02: Täpsustada Master asukoht ja mõiste läbi dokumendi. On see ühine XM või EE-spetsiifiline?)
(2016-03-02: Täpsustada Freeze põhimõtted. KAs võiks olla freeze-aeg kasutatud ~1/3 mestimiseks ning ~2/3 võimalike vigade parandamiseks)
(2016-03-02: Täpsustada Teekaart asukoht)
(2016-03-02: Kus kirjeldada Arendusülesande mõjud ja seosed teiste Teekaardil olevate arendustega?)

# X-TEE ARENDUSE TÖÖKORRALDUS

*Estonian-specific rules for X-Road development workflow. The rules are kept in accordance with [X-Road Joint Development regulations](https://github.com/vrk-kpa/xroad-joint-development). Intended readership of this document is X-Road developers contracted by Estonian State Information System Authority.*

*The original, authentic copy of this document is held in Estonian fork of X-Road Joint Development regulations repository:  [https://github.com/e-gov/xroad-joint-development/blob/master/WORKFLOW-EE.md](https://github.com/e-gov/xroad-joint-development/blob/master/WORKFLOW-EE.md).*

### 1	Üldine

1.1	Käesolevaga sätestatakse X-tee arendustöödega seotud töökorralduse nõuded.

1.2	Lepingu alusel X-teed arendav Täitja ühelt poolt ja arenduse Tellija teiselt poolt (Pooled) kohustuvad töökorralduse nõudeid täitma heas usus ja turvalise ning jätkusuutliku hea arenduspraktika kontekstis.

1.3	Pooled seavad eesmärgiks, et töökorraldus on efektiivne ja muutmisvajadust esilekutsuvate asjaolude ilmnemisel ka paindlik. Lepingu jooksul on töökorralduse parendamiseks õigus teha ettepanekuid mõlemal Poolel. Väiksemad muudatused töökorralduses lepitakse kokku projekti töökoosolekutel ja fikseeritakse töökoosolekute protokollides.

### 2	Arenduse rahvusvaheline koordineerimine

2.1	Tööd korraldatakse kooskõlas X-tee rahvusvahelise ühisarenduse töökorraldusega.
X-teed arendatakse rahvusvahelises koostöös. Ühisarenduse partnerid, edaspidi Partnerid, on Eesti ja Soome. Võimalik on täiendavate Partnerite lisandumine. Arendusi tellivad Eesti poolelt Riigi Infosüsteemi Amet (RIA, www.ria.ee), Soome poolelt Soome rahvastikuregistri keskus (VRK, www.vrk.fi). Partnerite tellimusel teostavad arendusi erinevad arendajad Täitjad.

Koostöö nurgakiviks on ühtsena hoitav, ühine koodibaas ja dokumentatsioon. Ühisest baasist teevad Partnerid ja Täitjad oma vajadusteks koopiaid, kohandusi ja täiendusi.

Arenduste koordineerimiseks on Partnerid kokku leppinud töökorralduse, mille tähtsamad elemendid on arendusprotokoll (vt j 3), ühisarenduse tšarter [Charter], X-tee teekaart (vt j 4), töövoo reeglistik [Workflow], mittefunktsionaalsed nõuded [NFR] ja ühisarenduse peaarhitekti (ingl *Head Architect*) roll.

Märkus: ka käesoleva Töökorralduse täiendusettepanekuid võib teha GitHubi probleemide (*Issue*) ja/või vastuvõtusoovide (*Pull Request*) abil, loomulikult ka Tellijaga otsekommunikatsiooni abil.

### 3	Arendusprotokoll

3.1	X-teed arendatakse Git hajusa versioonihaldusprotokolli järgi [Git].

3.2	Töökorraldusliku mudeli aluseks on Gitflow [Gitflow]. Git harudena kasutatakse `master`, `develop`, `release`, `hotfix` ning  arendustükkide harusid [Feature Branch Workflow].

### 4	X-tee teekaart

4.1	Arenduste koordineerimiseks kasutatakse X-tee teekaarti (ingl *X-Road Roadmap*), edaspidi Teekaart. (NB! Lisada viide Teekaardile!) Teekaardil fikseeritakse Partnerite poolt kokkulepitud arendustööde eesmärgid ja võtmetähtsusega tehnilised ning ajalised parameetrid.

4.2 Teekaardi kinnitab Partnerite esindajatest koosnev juhtrühm (ingl *Steering Committee*).

4.3 Teekaardi igakordsetest muudatustest teavitatakse kõiki kehtivate ja aktiivsete Lepingute Täitjaid.

### 5	X-tee `Master` hoidla

5.1	X-tee `Master` hoidlas, edaspidi `Master` hoidla, hoitakse X-tee koodi ja dokumentatsiooni peakoopiat (ingl *master copy*). Tehniliselt koosneb `Master` hoidla RIA Bitbucket [Bitbucket] (varem Stash) keskkonnas majutatud ühest või mitmest Git hoidlast.

5.2	Juurdepääs `Master` hoidlale on piiratud.

5.3	Kõik arendused lähtuvad `Master` hoidlast.

### 6	Arendustöö ettevalmistamine

6.1	Tellija püstitab arendusülesande.
Arendusülesande püstitamisel selgitatakse välja niipalju, kui see on mõistlik ja võimalik, mõjud ja seosed teiste Teekaardil olevate ja Teekaardile kandmiseks ettevalmistatavate arendustega. Mõjud ja seosed sõnastatakse (NB! Kus? Vajalik lisada viide Arendusülesande mõjudele ja seostele teiste Teekaardil olevate arendustega).

6.2	Täitja arvestab arendusülesande planeerimisel ja teostamisel Teekaardiga.

6.3	Tellija ja Täitja lepivad kokku arendusülesande täitmises (Leping). Üldjuhul sisaldab arendusülesanne endas nii koodi, dokumentatsiooni kui testide koostamist. Üldjuhul eeldatakse arendusülesande tulemite vastavus mittefunktsionaalsetele nõuetele [NFR].

6.4	Tellija uuendab Teekaarti.

### 7	Arendustöö alustamine

7.1	Tellija annab Täitja meeskonnale ligipääsu X-tee `Master` hoidlale.

7.2	Täitja moodustab X-tee `Master` hoidlast kloonimise või forkimise teel omale arendaja hoidla (ingl *vendor repo*).

7.3	Täitja moodustab oma hoidlas `develop` harust arendatava arendustüki haru. Erinevaid arendustükke võib ühes harus kombineerida siis, kui see on otstarbekas.

### 8	Arendustöö teostamine

8.1	Täitja teostab arendustööd oma hoidlas.

8.2	Täitja kohustub asjakohase perioodilisusega tõmbama endale 'Master' hoidla `develop` harust uuendusi.
Uuenduste tõmbamise eesmärk on kergendada Täitja teostatavate arendustükkide mestimist (ingl *Merge*) `Master` hoidla `develop` harusse.

### 9	Arendustöö tulemuste üleandmine

9.1	Täitja esitab valminud arendustüki koodi ja dokumentatsiooni vastuvõtmiseks `Master` hoidla `develop` harusse. Selleks esitab Täitja Git protokolli kohase vastuvõtusoovi (ingl *Pull Request*).

9.2	Enne vastuvõtusoovi esitamist peab Täitja veelkordselt tõmbama endale `Master` hoidla `develop` harust viimased uuendused ning lahendama võimalikud konfliktid viimaste uuenduste ja arendustüki vahel.

9.3	(NB! To be discussed!) Kui viimased uuendused ei olnud arendusülesande kokkuleppe sõlmimise ajal kantud Teekaardile ning põhjustasid konflikte, siis nende arvestamise ja lahendamisega seotud võimalike lisatööde kohta sõlmitakse Lepingule eraldi Lisa.

9.4	Tööde üleandmiseks peab Täitja tagama tema poolt valmistatud arendustüki konfliktivaba mestitavuse `Master` hoidla `develop` harusse.

9.5	Vastuvõtusoovi vaatab läbi X-tee ühisarenduse peaarhitekt, kaasates vajadusel Partnerite asjatundjaid.

9.6	Vastuvõtusoovi läbivaatamisel lähtub peaarhitekt kriteeriumitest:

1.	arendustüki sobivus X-tee ühisesse koodibaasi;
2.	vastavus X-tee mittefunktsionaalsetele nõudmistele;
3.	Teekaardil määratud versiooninumbri korrektne kasutamine;
4.	muudatuste logi (ingl *changelog*) uuendatus;
5.	ehitamise (ingl *build*) ja testide korrektne töötamine;
6.	testide küllaldane katvus;
7.	X-tee koodistiili järgimine;
8.	koodi küllaldane kommenteeritus;
9.	JavaDocs-i korrasolek;
10.	litsentsi korrasolek;
11.	dokumentatsiooni uuendatus.

9.7	Vastuvõtusoovi tagasilükkamisel peab Täitja puudused kõrvaldama p.8.2 ning Lepingus sätestatud tingimustel.

### 10	Viidatud materjalid

- [Bitbucket] 	Atlassian.com, [Code, Manage, Collaborate](https://www.atlassian.com/software/bitbucket).
- [Charter] 	[X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md).
- [Feature Branch Workflow] [Feature Branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
- [Git] 	[Git distributed version control system](https://git-scm.com/). 
- [Gitflow] 	Atlassian, Comparing workflows, [Gitflow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [NFR] [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md)
- [Teekaart]  [Teekaart](? https://confluence.ria.ee/display/XTEE/X-Roadmap)
- [Workflow] 	[X-Road Joint Development Workflow](https://github.com/vrk-kpa/xroad-joint-development/blob/master/WORKFLOW.md).
