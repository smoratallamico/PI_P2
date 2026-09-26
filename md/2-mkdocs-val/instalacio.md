# Instal·lació MkDocs

Per a seguir aquests passos, recomanem utilitzar **Visual Studio Code (VSCode)**, ja que permet disposar d'un editor d'arxius i una terminal integrada en el mateix programa.

## 1. Instal·lació de MkDocs

Per a instal·lar **MkDocs** en el nostre ordinador, executarem el següent comando en la consola (Konsole per a LliureX, PowerShell per a Windows...):

```markdown title="Bash" linenums="1"
pip install mkdocs
```

!!! warning "Pip"
    Si no tens instal·lat pip, hauràs d'instal·lar Python3 i, durant la instal·lació, marcar l'opció d'instal·lar pip i afegir-ho al PATH. Pots descarregar Python3 en el següent enllaç [https://www.python.org/downloads/](https://www.python.org/downloads/).

Una vegada que MkDocs estiga instal·lat, hauries de poder executar el següent comando en la consola:

```markdown title="Bash" linenums="1"
mkdocs --version
```

Si tot va bé, obtindràs una resposta similar a la següent:

```markdown title="Bash" linenums="1"
Linux:
- mkdocs, version 1.6.1 from /home/usuari/.local/lib/python3.13/site-packages/mkdocs (Python 3.13)

Windows:
- mkdocs, version 1.6.1 from C:\Users\Usuari\AppData\Local\Programs\Python\Python313\Lib\site-packages\mkdocs (Python 3.13)
```

## 2. Creació d'un nou projecte

Ara que MkDocs està instal·lat, necessitem crear un nou projecte per a construir el nostre lloc web. Per a això, executem:

```markdown title="Bash" linenums="1"
mkdocs new "nom_del_projecte"
```

## 3. Estructura del projecte

En crear un nou projecte amb MkDocs, veuràs que s'ha generat una estructura semblant a aquesta:

```markdown title="Text only" linenums="1"
.
├── docs
│ └── index.md
└── mkdocs.yml
```

* L'arxiu **mkdocs.yml** és l'arxiu de configuració principal de tot el projecte.
* La carpeta **docs** contindrà els documents en format Markdown.
+ L'arxiu **index.md** és un arxiu de mostra que es mostrarà en accedir a l'arrel del lloc web.
Com pots observar, d'una banda tindràs el contingut en format Markdown i, per altre, la configuració de com es renderitzarà aquest contingut.

!!! warning "Carpeta docs"
    Encara que, per defecte, els arxius Markdown es troben en la carpeta docs, més endavant modificarem aquesta configuració.

## 4. Servir la web en local

Per a servir una web, normalment necessitaríem un servidor que allotge el nostre lloc i que ens permeta accedir a ell de manera local o remota a través del navegador. MkDocs ens facilita aquesta tasca creant un servidor en el nostre propi equip perquè podem previsualizar els canvis abans de publicar-los en un servidor públic (accessible des d'Internet) o de compilar el lloc per a la seva publicació.

Per a servir la web, simplement executa el següent comando dins de la carpeta del projecte (utilitza el comando cd per a entrar en ella):

```markdown title="Bash" linenums="1"
$ mkdocs serve
INFO - Building documentation...
INFO - Cleaning site directory
INFO - Documentation built in 0.06 seconds
INFO - [#12:49:32] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO - [#12:49:32] Serving on http://127.0.0.1:8000/
```

A continuació, accedeix a la URL http://127.0.0.1:8000/ i veuràs la pàgina web per defecte:

![Pàgina inicial](./../img/instalacionDefecto.png)

!!! note "Índex per defecte"
    Obri en VSCode l'arxiu index.md i comprova com es correspon amb el que veus en el teu navegador. És a dir, MkDocs està convertint el contingut Markdown a un format web.

    Ara pots introduir els canvis que desitges en el teu contingut; en guardar, els canvis es reflectiran automàticament en el navegador, sempre que el comando mkdocs serve seguixca en execució. **La recàrrega automàtica es produeix sempre que modifiquis l'arxiu de configuració, els arxius Markdown o qualsevol arxiu del tema que estiguis utilitzant.**