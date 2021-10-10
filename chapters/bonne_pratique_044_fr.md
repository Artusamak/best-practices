## Utiliser la délégation d'évènements
### Indications
| Degré de priorité |      Mise en oeuvre       |  Impact écologique    | 
|-------------------|:-------------------------:|:---------------------:|
| Prioritaire       |  Facile                   | Fort                  | 


|Ressources Economisées                                      |
|:----------------------------------------------------------:|
| Processeur / Mémoire vive   |

### Règle
La délégation d’événements permet de ne pas surcharger la mémoire du navigateur en instanciant un seul écouteur pour plusieurs élé- ments du DOM (Document Object Model).

### Exemple
L’élément du DOM dont l’ID est t est déclaré comme le délégué. 
Il intercepte les événements de tous ses fils.
```html
<head>
    // ...
    <style type="text/css">
     #t { border: 1px solid red } #t1 { background-color: pink; }
    </style>
    <script type="text/javascript">
        function modifyText(new_text) {
            var t2 = document.getElementById("t2");
            t2.ﬁrstChild.nodeValue = new_text;
        }
        function load() {
            var el = document.getElementById("t");
            el.addEventListener("click", function() {
              modifyText("four")
            }, false); 
        }
    </script>
</head>
<body onload="load();">
    <table id="t">
        <tr><td id="t1">one</td></tr>
        <tr><td id="t2">two</td></tr>
    </table>
    <!-- ... -->
</body>
```

### Principe de validation