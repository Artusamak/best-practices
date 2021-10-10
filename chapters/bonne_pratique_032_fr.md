## Externaliser les CSS et JavaScript
### Indications
| Degré de priorité |      Mise en oeuvre       |  Impact écologique    | 
|-------------------|:-------------------------:|:---------------------:|
|  Prioritaire      |   facile                  |  Fort                 | 


|Ressources Economisées                                      |
|:----------------------------------------------------------:|
|    |

### Règle
Veiller à ce que les codes CSS et JavaScript ne soient pas embarqués dans le code HTML de la page, à l’exception d’éventuelles variables de configuration pour les objets JavaScript.

En effet, si vous incluez du code CSS ou JavaScript dans le corps du fichier HTML, alors que ce dernier est utilisé par plusieurs pages (voire tout le site), ce code doit être transféré pour chaque page demandée par l’ internaute, ce qui augmente le volume de données transmises. En revanche, si les codes CSS et JavaScript sont inclus dans leurs propres fichiers, le navigateur peut les stocker dans son système de cache local afin de ne pas les redemander.

### Exemple
Dans le code HTML, ne pas écrire :
```html
<style type="text/css" media="screen">
    p { color: #333; margin: 2px 0 }
    /* Toutes les déclarations CSS du site */
</style>
```

mais plutôt :
```html
<link href="css/styles.css" rel="stylesheet">
```



### Principe de validation