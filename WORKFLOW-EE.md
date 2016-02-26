# X-TEE ARENDUSE TÖÖKORRALDUS

*Estonian-specific rules for X-Road development workflow. The rules are kept in accordance with [X-Road Joint Development regulations](https://github.com/vrk-kpa/xroad-joint-development). Intended readership of this document is X-Road developers contracted by Estonian State Information System Authority.*

*The original, authentic copy of this document is held in Estonian fork of X-Road Joint Development regulations repository:  [https://github.com/e-gov/xroad-joint-development/blob/master/WORKFLOW-EE.md](https://github.com/e-gov/xroad-joint-development/blob/master/WORKFLOW-EE.md).*

### 1	Üldine

1.1	Käesolevaga sätestatakse Tööde töökorralduse nõuded.

1.2	Lepingu alusel X-teed arendav Täitja ühelt poolt ja Tellija teiselt poolt kohustuvad töökorralduse nõudeid täitma heas usus ja turvalise ning jätkusuutliku hea arenduspraktika kontekstis.

1.3	Pooled seavad eesmärgiks, et töökorraldus on efektiivne ja muutmisvajadust esilekutsuvate asjaolude ilmnemisel ka paindlik. Lepingu jooksul on töökorralduse parendamiseks õigus teha ettepanekuid mõlemal Poolel. Väiksemad muudatused töökorralduses lepitakse kokku projekti töökoosolekutel ja fikseeritakse töökoosolekute protokollides.

Märkus. Töökorralduse täiendusettepanekuid võib teha GitHubi probleemide (*Issue*), tõmbetaotluste (*Pull Request*) või Tellijaga otsekommunikatsiooni abil. 

### 2	Arenduse rahvusvaheline koordineerimine

2.1	Tööd korraldatakse kooskõlas X-tee rahvusvahelise ühisarenduse töökorraldusega.
X-teed arendatakse rahvusvahelises koostöös. Ühisarenduse partnerid, edaspidi Partnerid, on Eesti ja Soome. Võimalik on täiendavate riikide lisandumine. Arendusi juhivad Eesti poolelt Riigi Infosüsteemi Amet, Soome poolelt Soome Rahvastikuregister. Partnerite tellimusel teostavad arendusi erinevad arendajad (ettevõtted ja asutused).

Koostöö nurgakiviks on ühtsena hoitav, ühine koodibaas ja dokumentatsioon. Ühisest baasist teevad Partnerid oma vajadusteks kohandusi ja täiendusi.

Arenduste koordineerimiseks on Partnerid kokku leppinud töökorralduse, mille tähtsamad elemendid on arendusprotokoll (vt j 3), ühisarenduse tšarter [Charter], X-tee teekaart (vt j 4), töövoo reeglistik [Workflow] ja ühisarenduse peaarhitekti (ingl *Head Architect*) roll.

### 3	Arendusprotokoll

3.1	X-teed arendatakse Git hajusa versioonihaldusprotokolli järgi [Git].

3.2	Töökorraldusliku mudeli aluseks on Gitflow [Gitflow]. Git harudena kasutatakse `master`, `develop`, `release`, `hotfix` ja featuuriharusid [Workflow].

### 4	X-tee teekaart

4.1	Arenduste koordineerimiseks kasutatakse X-tee teekaarti (ingl *X-Road Roadmap*), edaspidi Teekaart. Teekaardil fikseeritakse Partnerite poolt kokkulepitud arendustööde eesmärgid ja võtmetähtsusega tehnilised ning ajalised parameetrid. Teekaardi kinnitab Partnerite esindajatest koosnev juhtrühm (ingl *Steering Committee*).

### 5	X-tee `Master` hoidla

5.1	X-tee `Master` hoidlas, edaspidi `Master` hoidla, hoitakse X-tee koodi ja dokumentatsiooni peakoopiat (ingl *master copy*). Tehniliselt koosneb `Master` hoidla Riigi Infosüsteemi Ameti Stash [Stash] keskkonnas majutatud ühest või mitmest Git hoidlast.

5.2	Juurdepääs `Master` hoidlale on piiratud.

5.3	Arendused lähtuvad `Master` hoidlast.

### 6	Arendustöö ettevalmistamine

6.1	Tellija püstitab arendusülesande.
Arendusülesande püstitamisel selgitatakse välja, niipalju, kui see on mõistlik ja võimalik, mõjud ja seosed teiste Teekaardil olevate ja Teekaardile kandmiseks ettevalmistatavate arendustega. Mõjud ja seosed sõnastatakse. Arendus kantakse Teekaardile, kui see seal juba ei ole.

6.2	Täitja tutvub arendusülesandega ja Teekaardiga.

6.3	Tellija ja Täitja lepivad kokku arendusülesande täitmises.

6.4	Tellija uuendab Teekaarti.

### 7	Arendustöö alustamine

7.1	Tellija annab Täitja meeskonnale ligipääsu X-tee `Master` hoidlale.

7.2	Täitja moodustab X-tee `Master` hoidlast kloonimise või forkimise teel omale arendaja hoidla (ingl *vendor repo*).

7.3	Täitja moodustab oma hoidlas `develop` harust arendatava featuuri haru. Erinevaid featuure võib ühes harus kombineerida siis, kui see on otstarbekas.

### 8	Arendustöö teostamine

8.1	Täitja teostab arendustööd oma hoidlas.

8.2	Täitja kohustub asjakohase perioodilisusega tõmbama endale Master hoidla `develop` harust uuendusi.
Uuenduste tõmbamise eesmärk on kergendada Täitja teostatavate arenduste mestimist `Master` hoidla `develop` harusse.

### 9	Arendustöö tulemuste üleandmine

9.1	Täitja esitab valminud koodi ja dokumentatsiooni vastuvõtmiseks `Master` hoidlasse, `develop` harusse. Selleks esitab Täitja Git protokolli kohase vastuvõtunõude (ingl *Pull Request*).

9.2	Enne vastuvõtunõude esitamist peab Täitja tõmbama endale `Master` hoidla `develop` harust viimased uuendused ja lahendama võimalikud konfliktid tõmmatud uuenduste ja Täitja poolt arendatava tarkvara vahel.

9.3	Kui tõmmatud uuendused ei olnud arendusülesande kokkuleppe sõlmimise ajal Teekaardil, siis nendega arvestamise eest peab Tellija tasuma eraldi.

9.4	Täitja peab tagama tema poolt valmistatud koodi ja dokumentatsiooni mestitavuse `Master` hoidla `develop` harusse.

9.5	Vastuvõtunõude vaatab läbi X-tee ühisarenduse peaarhitekt, kaasates vajadusel Partnerite asjatundjaid.

9.6	Vastuvõtunõude läbivaatamisel lähtub peaarhitekt kriteeriumitest:

1.	featuuride sobivus X-tee ühisesse koodibaasi;
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

9.7	Vastuvõtunõude tagasilükkamisel peab Täitja puudused kõrvaldama.

### 10	Viidatud materjalid

- [Charter] 	[X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md).
- [Git] 	[Git distributed version control system](https://git-scm.com/). 
- [Gitflow] 	Atlassian, Comparing workflows, [Gitflow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).
- [Stash] 	Atlassian.com, [Code, Manage, Collaborate](https://www.atlassian.com/software/bitbucket).
- [Workflow] 	[X-Road Joint Development Workflow](https://github.com/vrk-kpa/xroad-joint-development/blob/master/WORKFLOW.md).
