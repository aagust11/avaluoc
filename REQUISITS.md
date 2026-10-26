# avaluoc

FES CAS A LES MODIFICAIONS FINALS SI HI HA DISCREPACNIA
# ÀvalUOC — Requisits funcionals de l'aplicació

Document d'especificacions · Versió 1.0

ÀvalUOC serà una aplicació web per gestionar l'avaluació de les Proves d'Avaluació Contínua (PEC) de l'assignatura Decisions Tàctiques d'Operacions (DTO) de la UOC.

L'objectiu és substituir els fulls de càlcul actuals per un sistema centralitzat, ràpid i flexible que permeti gestionar l'alumnat, qualificar treballs individuals i grupals, calcular automàticament les notes i generar comentaris personalitzats.

## 1. Gestió de l'alumnat

### 1.1. Registre d'estudiants

L'aplicació ha de permetre:

- Crear estudiants individualment.
- Importar massivament estudiants mitjançant Excel, CSV o text enganxat.
- Assignar automàticament o manualment estudiants als grups.
- Modificar les dades i el grup d'un estudiant.
- Cercar estudiants per nom o grup.
- Detectar possibles duplicats durant la importació.
- Disposar d'un identificador únic per estudiant.

### 1.2. Fitxa individual de l'estudiant

Cada estudiant tindrà una fitxa que mostrarà:

- Nom i cognoms.
- Grup assignat.
- PEC realitzades.
- Nota del treball de cada PEC.
- Nota d'autoavaluació.
- Nota de coavaluació rebuda.
- Nota final calculada de cada PEC.
- Comentaris de correcció.
- Qualificació acumulada de l'assignatura.

Les notes han de poder-se consultar i, quan correspongui, editar directament des de la fitxa individual.

## 2. Gestió de grups

L'aplicació permetrà crear tants grups com sigui necessari, amb una denominació configurable: Grup 1, Grup 2, Grup 3, etc.

Cada grup tindrà una fitxa pròpia amb el llistat complet dels seus integrants.

Funcionalitats principals:

- Crear, editar i eliminar grups.
- Incorporar o retirar estudiants.
- Veure els membres del grup durant la correcció.
- Assignar una qualificació conjunta a tots els integrants.
- Consultar els resultats individuals dels membres.
- Identificar els estudiants que fan una PEC individualment.

Un estudiant pertanyerà a un grup general de l'assignatura, però la modalitat de realització del treball podrà establir-se per cada PEC.

## 3. Gestió de PEC

L'aplicació permetrà crear un nombre il·limitat de PEC.

Cada PEC tindrà la seva pròpia configuració, independent de les altres.

| Camp                                        | Exemple               |
| ------------------------------------------- | --------------------- |
| Nom                                         | PEC 1                 |
| Descripció                                  | Planificació agregada |
| Nombre d'activitats                         | 6                     |
| Criteris                                    | Configurables         |
| Pes de la PEC a l'assignatura               | 33,33 punts           |
| Pes del treball                             | 70 %                  |
| Pes de l'autoavaluació                      | 10 %                  |
| Pes de la coavaluació                       | 20 %                  |
| Nota mínima per incorporar auto/coavaluació | 4/10                  |

Els percentatges seran configurables per PEC, amb els valors indicats com a predeterminats.

Les PEC es podran duplicar per reutilitzar-ne l'estructura i adaptar-ne els criteris.

## 4. Activitats i criteris d'avaluació

Cada PEC es dividirà en activitats i cada activitat podrà contenir un o diversos criteris d'avaluació.

Per exemple:

PEC 1 — Planificació agregada

| Activitat   | Pes dins la PEC |
| ----------- | --------------- |
| Activitat 1 | 15 %            |
| Activitat 2 | 15 %            |
| Activitat 3 | 20 %            |
| Activitat 4 | 10 %            |
| Activitat 5 | 20 %            |
| Activitat 6 | 20 %            |
| Total       | 100 %           |

Activitat 1 — Criteris

| Criteri                            | Pes dins l'activitat |
| ---------------------------------- | -------------------- |
| C1. Càlcul de la producció         | 40 %                 |
| C2. Dimensionament de la plantilla | 35 %                 |
| C3. Justificació dels resultats    | 25 %                 |

### 4.1. Escala de qualificació

Els criteris tindran una escala predeterminada de 0 a 4, amb possibilitat de configurar-ne el màxim.

- 0: No assolit o no presentat.
- 1: Assoliment molt insuficient.
- 2: Assoliment parcial.
- 3: Assoliment adequat.
- 4: Assoliment complet.

Cada nivell podrà tenir una descripció específica segons el criteri.

L'aplicació calcularà automàticament la nota de l'activitat a partir de les puntuacions dels criteris i dels seus pesos.

El sistema ha de validar que els pesos dels criteris de cada activitat i els de les activitats de cada PEC sumin el 100 %.

## 5. Correcció dels treballs

### 5.1. Correcció per grup

En seleccionar una PEC i un grup, es mostrarà:

- El nom del grup.
- Els noms de tots els estudiants.
- Les activitats i els criteris de la PEC.
- Les puntuacions introduïdes.
- La nota calculada del treball.
- Un camp de comentaris.

La correcció feta al grup s'aplicarà automàticament a tots els seus integrants, sense haver de repetir-la.

### 5.2. Correcció individual

Si un estudiant realitza una PEC individualment:

- Es podrà seleccionar la modalitat «Individual».
- Es corregirà amb els mateixos criteris de la PEC.
- La nota del treball representarà el 100 % de la qualificació de la PEC.
- No s'aplicaran els percentatges d'autoavaluació ni coavaluació.

Aquesta configuració serà independent per cada estudiant i cada PEC.

### 5.3. Seguiment de les correccions

Cada PEC mostrarà l'estat de correcció dels grups i estudiants: pendent, en curs o finalitzada.

S'haurà de poder desar una correcció incompleta sense considerar-la finalitzada.

## 6. Autoavaluació i coavaluació

L'aplicació permetrà registrar individualment les qualificacions d'autoavaluació i coavaluació.

Les puntuacions es gestionaran sobre 10, independentment de l'escala de 0 a 4 utilitzada per als criteris.

Cada estudiant disposarà de dos camps independents:

- Autoavaluació: nota que s'atorga a si mateix.
- Coavaluació: nota rebuda dels companys.

La coavaluació es podrà introduir com a nota final consolidada. No serà necessari registrar cada valoració individual de cada company en la primera versió.

Es permetrà introduir aquestes qualificacions des de la fitxa individual o des d'una taula general de la PEC, amb tots els estudiants.

## 7. Càlcul automàtic de qualificacions

### 7.1. Treball grupal

La fórmula general serà:

\\[ N\_{\text{final}}=0,70N\_{\text{treball}}+0,10N\_{\text{auto}}+0,20N\_{\text{co}} \\]

Exemple:

| Component     | Nota | Pes  | Aportació |
| ------------- | ---- | ---- | --------- |
| Treball       | 8    | 70 % | 5,6       |
| Autoavaluació | 9    | 10 % | 0,9       |
| Coavaluació   | 10   | 20 % | 2,0       |
| Nota final    |      |      | 8,5/10    |

### 7.2. Condició de nota mínima

Si la nota del treball és inferior a 4/10, no s'incorporaran les notes d'autoavaluació ni coavaluació.

Caldrà aplicar automàticament aquesta condició i deixar visible el motiu pel qual les notes complementàries no s'han comptabilitzat.

Per defecte, la nota final serà la contribució del treball, és a dir, el 70 % de la seva nota. Aquesta política quedarà configurable per si les normes de l'assignatura estableixen un altre tractament.

### 7.3. Treball individual

\\[ N\_{\text{final}}=N\_{\text{treball}} \\]

### 7.4. Nota ponderada de la PEC

Cada PEC tindrà un pes configurable en punts.

Per exemple, si la PEC representa 33,33 punts:

\\[ N\_{\text{ponderada}}=\frac{N\_{\text{final}}}{10}\times33,33 \\]

Per a una nota de 8,5/10:

\\[ N\_{\text{ponderada}}=28,33 \\]

En tot moment es mostraran les dues qualificacions: la nota final sobre 10 i la nota ponderada segons el pes configurat.

### 7.5. Calculadora interactiva de comprovació

Simulador de qualificació

Exemple

PEC individual (100 % treball)

Nota del treball

2.0/10

Autoavaluació

4.5/10

Coavaluació

10.0/10

Pes màxim de la PEC (punts)

Treball inferior a 4. No s'incorporen autoavaluació ni coavaluació.

Nota final

# 1.40 / 10

Nota ponderada

# 4.67 / 33.33

## 8. Sistema de comentaris i plantilles

ÀvalUOC tindrà un editor de plantilles personalitzades, específic per cada PEC.

### 8.1. Creació de plantilles

El docent podrà crear, editar, duplicar i eliminar plantilles.

Les plantilles admetran text lliure i variables que es substituiran automàticament pels valors de la correcció seleccionada.

| Variable   | Valor                     |
| ---------- | ------------------------- |
| `{NOM}`    | Nom de l'estudiant        |
| `{GRUP}`   | Nom del grup              |
| `{PEC}`    | Nom de la PEC             |
| `{NPec}`   | Nota del treball sobre 10 |
| `{NC1}`    | Puntuació del criteri 1   |
| `{NC2}`    | Puntuació del criteri 2   |
| `{NA1}`    | Nota de l'activitat 1     |
| `{NAUTO}`  | Nota d'autoavaluació      |
| `{NCO}`    | Nota de coavaluació       |
| `{NFINAL}` | Nota final sobre 10       |
| `{NPOND}`  | Nota ponderada de la PEC  |

Les variables de criteris seguiran la numeració definida dins de cada PEC.

### 8.2. Exemple de plantilla

Editor de plantilla

Hola a tots,\<br>\<br>Activitat 1: heu obtingut {NC1} punts en el primer criteri i {NC2} punts en el segon.\<br>\<br>Nota del treball: {NPec}/10.\<br>Nota final de la PEC: {NFINAL}/10.\<br>\<br>Molta sort amb la següent PEC!

Vista prèvia (amb les notes del simulador)

Hola a tots,\
\
Activitat 1: heu obtingut 3 punts en el primer criteri i 4 punts en el segon.\
\
Nota del treball: 2.00/10.\
Nota final de la PEC: 1.40/10.\
\
Molta sort amb la següent PEC!

&#x20;Copiar comentari

### 8.3. Biblioteca de comentaris

A més de les plantilles completes, cada PEC podrà disposar de comentaris curts reutilitzables per activitat o criteri.

El docent podrà seleccionar-los o combinar-los per generar més ràpidament el retorn al grup.

S'hauran de poder modificar manualment els comentaris generats abans de copiar-los.

## 9. Interfície i navegació

L'aplicació tindrà una estructura clara, adaptada principalment a l'ordinador.

## ÀvalUOC

DTO

Alumnat

Grups

PEC

Correcció

Plantilles

Resultats

### 9.1. Pantalla de correcció

La pantalla principal de treball ha de permetre corregir una PEC sencera amb el mínim nombre de clics possible.

Ha de mostrar simultàniament els integrants del grup, els criteris, les notes, els comentaris i els totals calculats.

Cal poder canviar ràpidament al grup següent o anterior, sense tornar a la pantalla inicial.

## 10. Resultats i exportació

ÀvalUOC permetrà consultar una taula general per PEC amb una fila per estudiant i les columnes següents:

| Estudiant | Grup       | Treball | Auto | Co | Final /10 | Ponderada |
| --------- | ---------- | ------- | ---- | -- | --------- | --------- |
| Alumne A  | Grup 1     | 9       | 9    | 9  | 9,00      | 30,00     |
| Alumne B  | Grup 1     | 9       | 8    | 9  | 8,90      | 29,66     |
| Alumne C  | Individual | 7       | —    | —  | 7,00      | 23,33     |

Exemple il·lustratiu amb PEC de 33,33 punts.

L'aplicació ha de permetre exportar:

- Resultats generals a Excel i CSV.
- Qualificacions d'una PEC concreta.
- Qualificacions acumulades de l'assignatura.
- Comentaris finals individuals o de grup.
- Còpia ràpida de la nota i del comentari al porta-retalls.

## 11. Emmagatzematge i seguretat

Com que les qualificacions i les dades de l'alumnat són informació personal, el sistema haurà d'evitar pèrdues de dades i accessos no autoritzats.

Requisits:

- Desament automàtic després de cada modificació.
- Indicador visible de l'estat de desament.
- Còpia de seguretat completa en format JSON.
- Importació d'una còpia de seguretat.
- Validació de les dades abans de restaurar-les.
- Confirmació abans d'eliminar estudiants, PEC o grups.
- Evitar que dos canvis simultanis sobreescriguin informació sense avisar.

Decisió tècnica important: GitHub Pages pot allotjar la interfície, però no proporciona per si mateix emmagatzematge privat i sincronitzat. La primera versió podria desar les dades localment amb còpies de seguretat manuals. Si vols sincronització real entre dispositius, caldrà definir un sistema d'emmagatzematge adequat i control d'accés.

## 12. Regles de negoci imprescindibles

Aquestes regles han de ser comunes a totes les pantalles, exportacions i càlculs:

1. Les notes dels criteris es calculen segons els pesos configurats.
2. Una correcció grupal comparteix la nota del treball entre els seus integrants.
3. Les autoavaluacions i coavaluacions sempre són individuals.
4. Si el treball té menys de 4/10, no s'incorporen els components complementaris.
5. Els treballs individuals es qualifiquen al 100 % segons el treball.
6. Les notes finals es mostren sobre 10 i sobre el pes configurat.
7. Els càlculs interns mantenen precisió completa; l'arrodoniment s'aplica només en mostrar o exportar.
8. Les plantilles mai no han de mostrar variables sense substituir com si fossin text definitiu: si falta una dada, s'ha de senyalitzar.
9. Canviar els criteris o els pesos d'una PEC ja corregida ha de generar un avís perquè pot modificar totes les qualificacions.
10. Les qualificacions i comentaris han de quedar vinculats a l'identificador únic de l'estudiant, no només al seu nom.

## 13. Prioritats de desenvolupament

| Fase | Funcionalitats                                    | Prioritat      |
| ---- | ------------------------------------------------- | -------------- |
| 1    | Estudiants, importació massiva i grups            | Imprescindible |
| 2    | PEC, activitats, criteris i pesos                 | Imprescindible |
| 3    | Correcció grupal i individual                     | Imprescindible |
| 4    | Autoavaluació, coavaluació i càlcul final         | Imprescindible |
| 5    | Plantilles de comentaris i variables              | Imprescindible |
| 6    | Taula de resultats i exportació Excel             | Alta           |
| 7    | Fitxa individual i seguiment històric             | Alta           |
| 8    | Còpies de seguretat, sincronització i millores UX | Alta           |

## 14. Decisions que cal deixar tancades

Hi ha tres aspectes que afecten directament el càlcul i que no convé donar per suposats:

1\. Treballs amb nota inferior a 4. He especificat que s'aplica únicament la contribució del 70 % del treball. Per exemple, un 3,5 es converteix en 2,45. Cal confirmar si aquesta és exactament la norma que utilitzes o si s'ha de conservar el 3,5.

2\. Coavaluació. He plantejat introduir la nota consolidada rebuda per cada estudiant, sense calcular-la a partir de totes les valoracions dels companys. És el sistema més ràpid si ja disposes de les notes calculades.

3\. Pes de la PEC. He interpretat els 33,33 com a punts màxims dins d'una escala global de 100. D'aquesta manera, les notes ponderades de les diferents PEC es podran sumar directament.

ÀvalUOC ha de prioritzar la velocitat de correcció i la fiabilitat dels càlculs. No té sentit construir una aplicació més complexa que els fulls de càlcul que pretén substituir. La funcionalitat central ha de ser seleccionar una PEC, seleccionar un grup, puntuar els criteris i obtenir immediatament les notes i els comentaris preparats per copiar.







Sí. Cal modificar tres apartats dels requisits d'ÀvalUOC: la gestió de grups, la correcció individual i la configuració de cada PEC. A més, faria un petit ajust en la detecció de grups individuals.

## 1. Modificació del requisit 2 — Gestió de grups

Tots els estudiants han d'estar assignats a un grup numèric, independentment de si treballen individualment o col·lectivament.

- Grup amb diversos estudiants: treball grupal.
- Grup amb un únic estudiant: treball individual.
- Tots els grups tindran un número identificador.
- No serà necessari marcar manualment si un estudiant treballa individualment.
- L'aplicació detectarà la modalitat segons el nombre d'integrants del grup.

Per exemple:

| Grup   | Integrants | Modalitat  | Càlcul             |
| ------ | ---------- | ---------- | ------------------ |
| Grup 1 | 3          | Grupal     | 70 % + 10 % + 20 % |
| Grup 2 | 3          | Grupal     | 70 % + 10 % + 20 % |
| Grup 3 | 1          | Individual | 100 % PEC          |
| Grup 4 | 4          | Grupal     | 70 % + 10 % + 20 % |
| Grup 5 | 1          | Individual | 100 % PEC          |

Important: la modalitat ha de determinar-se segons els integrants del grup en aquella PEC. Així evitaràs que un canvi posterior en la composició dels grups alteri qualificacions antigues.

## 2. Modificació del requisit 5 — Correcció

S'elimina la necessitat d'un selector manual de «Treball individual».

Quan el docent selecciona un grup per corregir:

- Si té diversos estudiants, es mostra la nota conjunta del treball i les autoavaluacions i coavaluacions individuals.
- Si té un únic estudiant, es calcula directament el 100 % de la nota del treball.
- El sistema utilitza exactament els mateixos criteris, activitats i plantilles en tots dos casos.
- Els grups individuals apareixen en el mateix llistat de correcció que els grupals.

D'aquesta manera, la correcció sempre es fa per grup, encara que aquest contingui un sol estudiant.

## 3. Nou requisit 3.1 — Enllaços ràpids de cada PEC

Cada PEC disposarà d'un apartat configurable anomenat Enllaços ràpids.

### Configuració

El docent podrà:

- Afegir tants enllaços com necessiti.
- Assignar un nom personalitzat a cada enllaç.
- Introduir-ne l'URL.
- Triar una icona identificativa.
- Reordenar-los.
- Editar-los o eliminar-los.
- Activar-los o desactivar-los temporalment.

Els enllaços seran independents per a cada PEC.

### Exemple d'interfície

PEC 1 — Planificació agregada

Enllaços ràpids

Enunciat PEC

Document de l'activitat

Solucionari

Solució de referència

Rúbrica

Criteris de correcció

Aula UOC

Accés a l'aula

Representació de la disposició. A l'aplicació, cada element serà clicable i obrirà l'URL configurat en una pestanya nova.

### Comportament

1. Els enllaços apareixeran a la capçalera de la pantalla de correcció de la PEC, sempre visibles i accessibles.
2. En clicar-hi, s'obrirà la destinació en una pestanya nova, sense abandonar ÀvalUOC.
3. Si una PEC no té enllaços configurats, no es mostrarà l'apartat.
4. Els enllaços s'inclouran en les còpies de seguretat i es conservaran en duplicar una PEC.

## 4. Petita modificació del model de dades

A nivell intern, els grups s'han de relacionar amb les PEC, i no només amb l'alumnat. Això permet conservar correctament la composició amb què s'ha avaluat cada treball, encara que posteriorment hi hagi canvis.

Els enllaços ràpids també formaran part de la configuració de cada PEC, no de la configuració general.

### Una decisió que et recomano

No faria dues pantalles de correcció diferents per a individuals i grupals. Una sola pantalla basada en el número de grup és més senzilla, més ràpida i evita duplicar funcionalitats.

Amb aquests ajustos, la resta dels requisits d'ÀvalUOC es poden mantenir. No cal redissenyar el sistema: només unificar la lògica de correcció i incorporar els enllaços ràpids.
