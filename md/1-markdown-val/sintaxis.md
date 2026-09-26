# Sintaxis bàsica

Com hem dit, Markdown es basa en fitxers de tipus text, que no contenen cap informació interna sobre el format. Aquesta informació, s'especificarà de manera explícita mitjançant etiquetes, que seran visibles en tot moment, i que facilitaran, d'una banda, la seva interpretació en l'hora d'exportar-los a un altre format, però també la seva lectura per part de les persones.

En aquest apartat, veurem quins són els diferents elements que podem utilitzar en un text en format Markdown, així com les principals marques de format.

## 1. Paràgrafs

Un paràgraf, tal com ho entén Markdown, és un bloc de text definit entre dos salts de línia(tecla ``` Intro/Enter/Entrar ```).

Si utilitzem només un salt de línia, se sobreentén que és el mateix paràgraf, i en l'hora de generar el document, el veurem com a tal.


```markdown title="Markdown" linenums="1"
Este és el primer paràgraf, com veieu, necessita dos salts de línia, o el que seria el mateix, una línia en blanc després del paràgraf.

Aquest és un altre paràgraf.
```

!!! note "Resultat"
    Este és el primer paràgraf, com veieu, necessita dos salts de línia, o el que seria el mateix, una línia en blanc després del paràgraf.

    Aquest és un altre paràgraf.

## 2. Capçaleres

Hi ha diverses maneres de marcar capçaleres, nosaltres utilitzarem l'Estil ATX, al qual, utilitzem el símbol (```#```) abans del text per a indicar el nivell de la capçalera. S'admeten fins a sis nivells de profunditat (```######```), el que vindria a ser del (```h1```) fins al (```h6```) de #HTML.

```markdown title="Markdown" linenums="1"

# Encapçalat 1

## Encapçalat 2

### Encapçalat 3

...
```

> A tenir amb compte
>
>La versió estàndard de Markdown no requereix d'una línia en blanc abans d'una capçalera, però altres versions, com per exemple la de Pandoc sí que la requereix. No obstant això, encara que l'estàndard no l'utilitza, convé afegir-la ja que facilita així la lectura i localització d'aquestes.
>
>Algunes implementacions, tampoc requereixen d'un espai entre el símbol ```#``` inicial i el primer caràcter del títol.


### 2.1. Atributs a la capçalera

Quan es genera un document, ja sigui PDF, #HTML o un altre format a partir d'un document en Markdown, a les capçaleres els hi assigna un identificador de manera automàtica, perquè es pugui fer referència a elles des d'altres parts del document. Aquest identificador s'obté a partir del text de la capçalera, pel qual si aquesta és llarga, l'identificador també ho serà. La versió de Pandoc, ens permet afegir uns certs atributs a les capçaleres, entre les quals es troba l'identificador.

Donada, per exemple, una capçalera com la següent:

```markdown title="Markdown" linenums="1"
# Introducció: L'art d'escriure davant un ordinador
```

L'identificador que es genera és: ```id="introducció-lart-descriure-davant-un-ordinador"```.

Aquesta capçalera, la podríem haver escrit també de la manera següent:

```markdown title="Markdown" linenums="1"

# Introducció: L'art d'escriure davant un ordinador { #introduccio }
```

Sent l'identificador de la capçelera sols ```#introduccio```, de forma que podem fer referència a l'apartat mitjançant aquest.

## 3. Format de text

Markdown ens permet fer ús del símbol de l'asterisc com a marca de format de la manera següent:

* Negreta: envolta el text amb ```**```.
* Cursiva: envolta el text amb ```*```.
* Negreta i cursiva: Usa tres asteriscos.

Cal tenir en compte que no hem d'afegir cap espai entre els asteriscos del principi i la primera paraula i els asteriscos del final i l'última.

```markdown title="Markdown" linenums="1"
**Text en negreta**
*Text en cursiva*
***Text en negreta i cursiva***

Si afegim algun espai entre mitjà, ** no s'interpretarà correctament **
```

!!! note "Resultat"
    **Text en negreta**
    *Text en cursiva*
    ***Text en negreta i cursiva***

    Si afegim algun espai entre mitjà, ** no s'interpretarà correctament **

## 4. Línies horitzontals

Una línia horitzontal es defineix mitjançant tres o més símbols - o _, separats o no per espais:

```markdown title="Markdown" linenums="1"

- - -

o 

_ _ _
```

!!! note "Resultat"
    - - -
    o
    - - -

## 5. Llistes

Markdown permet fer ús tant de llistes ordenades com llistes no ordenades.

### 5.1. Llistes no ordenades

Les llistes no ordenades es marquen fent ús dels símbols ```*```, ```+``` o ```-``` a primers de cada element, i incloent cada ítem en una línia diferent (i no fan falta dos salts de línia).


```markdown title="Markdown" linenums="1"

* Element 1
* Element 2
...
```

Cada element de la llista pot contenir diversos paràgrafs, i altres continguts a nivell de bloc. Quan volem incloure diversos paràgrafs en un ítem de la llista, el segon paràgraf i posterior hauran d'anar precedits per una línia en blanc, i sagnats per a alinear-se amb el contingut que no sigui l'espai després del marcador de la llista.

Per exemple:

```markdown title="Markdown" linenums="1"

* Primer element de la llista
* Segon element de la llista

  Un altre paràgraf corresponent al segon element de la llista.
  No fa falta un espai en blanc entre l'últim paràgraf i el següent element, però el podem afegir per a facilitar la lectura de la llista.

* Tercer element de la llista.
```

Per a generar llistes niades dins d'unes altres, simplement hauràs d'afegir quatre espais en blanc abans del següent ```*```,```-``` o ```+```.

```markdown title="Markdown" linenums="1"

* Element 1
    * subelement 1.1
        * subelement 1.1.1
        * subelement 1.1.2
    * subelement 1.2
    * subelement 1.3
* Element 2
```

En aquests casos, com que podem utilitzar diversos símbols per a indicar llistes, se sol utilitzar un element per cada nivell de la llista, amb la finalitat de facilitar la lectura del text pla:

```markdown title="Markdown" linenums="1"

* Element 1
    + subelement 1.1
        - subelement 1.1.1
        - subelement 1.1.2
    + subelement 1.2
    + subelement 1.3
* Element 2
```
!!! note "Resultat"
    * Element 1
        + subelement 1.1
            - subelement 1.1.1
            - subelement 1.1.2
        + subelement 1.2
        + subelement 1.3
    * Element 2

### 5.2. Llistes ordenades

El funcionament de les llistes ordenades és el mateix que les no ordenades, tret que cada element de la llista porta un número.

En la versió estàndard de Markdown, els elements que indiquen l'ordre han de ser números seguits d'un punt i un espai. En l'estàndard, aquests números s'ignoren, per la qual cosa la llista:

```markdown title="Markdown" linenums="1"

1. Element 1
2. Element 2
3. Element 3
```
Serà la mateixa que:

```markdown title="Markdown" linenums="1"

4. Element 1
5. Element 2
6. Element 3
```
!!! note "Resultado"
    1. Element 1
    2. Element 2
    3. Element 3

## 6. Taules

Les taules ens serveixen per a presentar informació de manera organitzada.

La versió original de Markdown de John Gruber no inclou la definició de taules en la sintaxi de Markdown. Com que inicialment es va crear com una eina per a fer la conversió a HTML, per a afegir taules s'utilitzava directament aquest llenguatge.

No obstant això, les diferents variants de Markdown han anat afegint notacions i extensions al Markdown original per a suportar taules.

La sintaxi per a crear taules del Markdown de Github és una de les més esteses, i fa ús de barres verticals (|) i guions (-) per a crear-les. Els guions s'utilitzen per a crear l'encapçalament de cada columna, i les barres verticals serveixen de separador de cada columna. A més, perquè la taula es representi correctament, fa falta una línia en blanc abans de la taula.

Les taules, en aquest format, han de tenir necessàriament una capçalera i un cos, i seguiran la següent sintaxi:

```markdown title="Markdown" linenums="1"

| Capçalera 1 | Capçalera 2 |
|-------------|-------------|
| Valor 1     | Valor 2     |
| Valor 3     | Valor 4     |
```
!!! note "Resultat"
    | Capçalera 1 | Capçalera 2 |
    |-------------|-------------|
    | Valor 1     | Valor 2     |
    | Valor 3     | Valor 4     |

Algunes consideracions:

* Podem afegir tants camps (columnes) com vulguem.
* La línia que separa la capçalera del cos ```|---|---|``` és obligatòria, però no és necessari que tinga tants caràcters com tinguen les capçaleres, pel qual no fa falta que la taula estiga completament alineada.
* Les barres verticals (```|```) del principi i del final són opcionals.

### 6.1. Formatat el contingut d'una taula

Dins d'una taula podem utilitzar també unes certes marques de format, com a negretes, cursives, enllaços, imatges...

A més, podem alinear el text a l'esquerra, a la dreta o en el centre de la columna, afegint la marca dos punts ```:```, al costat esquerre, dret, o als dos, dels guions de l'encapçalament.

Veiem-l'amb un exemple. La següent definició de taula:

```markdown title="Markdown" linenums="1"

| Text a l'esquerra | Text centrat | Text a la dreta |
|        :---       |     :---:    |      ---:       |
| xxx               | xxx          | xxx             |
| xxxxx             | xxxxx        | xxxxx           |
```

!!! note "Resultat"
    | Text a l'esquerra | Text centrat | Text a la dreta |
    |        :---       |     :---:    |      ---:       |
    | xxx               | xxx          | xxx             |
    | xxxxx             | xxxxx        | xxxxx           |

> Si volem afegir dins d'una taula una barra vertical (|) com a contingut, hem de posar abans el símbol (\), per a indicar que el caràcter següent no s'ha d'interpretar com a marca de format Markdown. Aquesta barra invertida es denomina caràcter de fuita, i a la combinació d'ella amb qualsevol marca que vulguem que no s'interpreti es coneix com a seqüència de fuita.

## 7. Fragments de codi

Markdown té un ampli ús en la documentació tècnica de projectes informàtics, on és habitual incloure fragments del codi font dels programes. Per a ressaltar aquests tipus de fragments, Markdown utilitza una sintaxi especial, fent ús dels caràcters de l'accent obert: `.

Quan es tracta de fragments de codi que han d'anar en la mateixa línia que el text, per exemple si volem indicar una etiqueta #HTML, el fem, `d'aquesta manera`, fent ús d'un únic caràcter d'accent, mentre que si el que volem és escriure un bloc de codi, utilitzaríem tres símbols d'accent obert ```. A més, darrere els primers símbols, podem especificar de quin llenguatge es tracta. Per exemple, per a indicar el codi #HTML d'una pàgina web, faríem:


```markdown title="Markdown" linenums="1"
    ```html title="HTML" linenums="1" 
        <html>
            <body>
            <h1>Títol de la pàgina web</h1>
            <p>Paràgraf</p>
            </body>
        </html>
    ```
```
Cal remarcar que el nom del llenguatge darrere les cometes fa que en mostrar el resultat, es tinga en compte el llenguatge de programació per a ressaltar la sintaxi pròpia del llenguatge.

## 8. Cites

En Markdown, un bloc de text en forma de cita consisteix en un o més paràgrafs o altres elements de bloc (com, per exemple, llestes o capçaleres), on cada línia es troba precedís del caràcter > i opcionalment un espai.

Veiem alguns exemples:

Exemple:

```markdown title="Markdown" linenums="1"
>
> Un document amb format Markdown hauria de ser publicable tal qual, com a text pla, sense que semble que s'ha marcat amb etiquetes o instruccions de format.
>
> John Gruber
```
!!! note "Resultat"
    >
    > Un document amb format Markdown hauria de ser publicable tal qual, com a text pla, sense que semble que s'ha marcat amb etiquetes o instruccions de format.
    >
    > John Gruber

## 9. Enllaços

Markdown ens permet generar enllaços tant a adreces d'Internet, com fer referència a fitxers locals, mitjançant la seva ruta relativa o fins i tot dins del propi document.

El format general per a afegir un enllaç és el següent:

```markdown title="Markdown" linenums="1"

[Text de l'enllaç](#URL_o_adreça_relativa)
```
Per exemple, per a afegir un enllaç a un lloc web, escriurem:

```markdown title="Markdown" linenums="1"

Anar a la web de l'[IES Dr. Lluís Simarro](https://portal.edu.gva.es/ieslluissimarro/)
```

!!! note "Resultat"
    Anar a la web de l'[IES Dr. Lluís Simarro](https://portal.edu.gva.es/ieslluissimarro/)

### 9.1. Enllaços interns

Per a afegir un enllaç a una secció del nostre document, farem ús de l'identificador que s'assigna automàticament, o bé que li hem assignat nosaltres.

Per exemple, si per a l'apartat introductori afegim un identificador de la manera següent:

```markdown title="Markdown" linenums="1"

# Introducció: L'art d'escriure davant un ordinador {#introduccio}
```
Podem fer referència a ell de la manera següent:

```markdown title="Markdown" linenums="1"

Fes clic [en el següent enllaç](#introduccio) per a tornar a la secció d'Introducció.
```

!!! note "Resultat"
    Fes clic [en el següent enllaç](#introduccio) per a tornar a la secció d'Introducció.


## 10. Imatges

La sintaxi per a afegir una imatge és semblant a la de l'enllaç, precedida d'una exclamació !:

```markdown title="Markdown" linenums="1"

![Text alternatiu o peu de la imatge](Ubicació de la imatge)
Igual que els enllaços, la ubicació pot ser una adreça d'Internet o bé la ruta a un fitxer local al nostre ordinador:
```

```markdown title="Markdown" linenums="1"

![Logotip de Markdown a la Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/markdown-mark.svg/1920px-markdown-mark.svg.png)

![Logotip de Markdown a en una ruta relativa](./../img/logoMarkdown.png)
```

En aquest segon cas, cerca la imatge logoMarkdown.png en una carpeta imatges situada en la carpeta indicada.

Cal tenir en compte que quan s'exporte el fitxer a HTML, aquestes referències continuaran existint al codi HTML.

### 10.1. Afegint grandària a les imatges

Algunes versions de Markdown (com Pandoc) permeten afegir uns certs atributs a les imatges. Entre aquests destaquen especialment (```width```) i (`height`), que permeten especificar la grandària de la imatge.

Si no s'indica res, la grandària s'entén que s'especifica en píxels, però podem utilitzar altres unitats com *px, #cm, mm, in, inch i %*, sense incloure espais entre el número i les unitats.

Exemples:

```markdown title="Markdown" linenums="1"

![Image 1 - 10cm](./../img/logoMarkdown.png){ width=10cm }

![Image 2 - 50mm](./../img/logoMarkdown.png){ width=50mm }

![Image 3 - 50%](./../img/logoMarkdown.png){ width=50% }
```

!!! note "Resultats"
    ![Image 1 - 10cm](./../img/logoMarkdown.png){ width=10cm }

    ![Image 2 - 50mm](./../img/logoMarkdown.png){ width=50mm }

    ![Image 3 - 50%](./../img/logoMarkdown.png){ width=50% }