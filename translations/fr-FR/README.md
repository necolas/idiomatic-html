# Principes d'écriture pour des HTML cohérents et idiomatiques

Le présent document liste des recommandations raisonnables pour le développement HTML.
Ces lignes directrices encouragent fortement l'utilisation de conventions existantes, communes et judicieuses.
Elles doivent être adaptées au besoin pour créer votre propre guide.

Ceci est un document évolutif et les nouvelles idées sont toujours les bienvenues.

Merci de bien vouloir contribuer.

[Idiomatic HTML en anglais](https://github.com/necolas/idiomatic-html)


## Table des matières

1. [Principes généraux](#principes-generaux)
2. [Indentation](#indentation)
3. [Format](#format)
4. [Ordre des attributs](#ordre-des-attributs)
5. [Appellation](#appellation)
6. [Exemple pratique](#exemple)

[Licence](#licence)


<a name="principes-generaux"></a>
## 1. Principes généraux

> Une des clefs d'une bonne gestion de projet est de réaliser qu'écrire du code pour soi-même est une MAUVAISE IDÉE™. Si des milliers de personnes sont amenées à utiliser votre code, alors écrivez votre code en visant un maximum de clarté, et non en fonction de croyances personnelles comme la lecture de spécifications qui rendrait plus intelligent." - Idan Gazit

* Tout code présent dans n'importe quelle base de code doit avoir l'air d'avoir été écrit par une seule personne, peu importe le nombre de gens qui y ont contribué.
* Appliquez les conventions de style de manière stricte.
* En cas de doute, utilisez des conventions existantes et communes.


<a name="indentation"></a>
## 2. Indentation

Une seule manière d‘indenter devrait être utilisée sur l'ensemble du code source de votre projet. Soyez toujours constant dans votre façon d‘indenter. Utilisez des espaces pour améliorer la lisibilité.

* Ne mélangez jamais les espaces et les tabulations pour l'indentation.
* Choisissez entre des espaces ou de vraies tabulations. Tenez-vous en à votre choix sans y déroger. (Préference : espaces)
* Si vous utilisez les espaces, choisissez le nombre de caractères utilisé pour chaque niveau d'indentation. (Préference : 4 espaces)

Astuce : Configurez votre éditeur afin qu'il affiche les "caractères invisibles". Cela vous permettra de supprimer les espaces en fin de ligne, les espaces dans les lignes vides et évitera de polluer vos commits.


<a name="format"></a>
## 3. Format

* Toujours utiliser des balises et des attributs en bas-de-casse (minuscules).
* Écrir un élément distinct par ligne.
* Utiliser un niveau d'intentation suplémentaire pour chaque élément imbriqué.
* Utiliser les attributs sans valeur (ex. `checked` plutôt que `checked="checked"`).
* Always use double quotes to quote attribute values.
* Toujours utiliser les guillemets "" plutot que les appostrophes '' pour les valeurs des attributs.
* Omettre l'attribut `type` des éléments `link` stylesheet, `style` et `script`.
* Toujours inclure la balise fermante.
* Ne pas inclure le slash de fin dans les éléments auto-fermants.

(Garder une longueur de ligne raisonable, ex. 80 caractères).

Exemple:

```html
<div class="tweet">
    <a href="chemin/vers/quelquepart">
        <img src="chemin/vers/image.png" alt="">
    </a>
    <p>[tweet texte]</p>
    <button disabled>Répondre</button>
</div>
```

### Exceptions et de légères déviations

Les éléments avec plusieurs attributs peuvent avoir des attributs disposés sur de multiples 
lignes afin d'améliorer la lisibilité et de produire des diffs plus utiles.

Exemple:

```html
<a class="[valeur]"
 data-action="[valeur]"
 data-id="[valeur]"
 href="[url]">
    <span>[texte]</span>
</a>
```


<a name="ordre-des-attributs"></a>
## 4. Ordre des attributs

Les attributs HTML doivent être énumérés dans un ordre qui reflète le fait que les noms classes sont les principales interfaces à travers lesquelles CSS et JavaScript sélectionnent 
les éléments.

1. `class`
2. `id`
3. `data-*`
4. tout le reste

Exemple:

````html
<a class="[valeur]" id="[valeur]" data-name="[valeur]" href="[url]">[texte]</a>
````


<a name="appellation"></a>
## 5. Appellation

Nommer est difficile, mais très important. C'est une partie essentielle du processus de 
l'élaboration d'une base de code maintenable, et veiller à ce que vous ayez une 
interface relavivement évolutive entre votre HTML et CSS / JS.

* Utilisez des noms clairs, bien pensés, et appropriées pour les classes HTML. Les noms 
   devrait être instructif à la fois dans les fichiers HTML et CSS.
* Évitez l'utilisation _systématique_ de nom de classe abrégées. Ne rendez pas les choses difficiles à comprendre.

Exemple avec de mauvais noms :

```html
<div class="cb s-scr"></div>
```

```css
.s-scr {
  overflow: auto;
}

.cb {
  background: #000;
}
```

Exemple avec de meilleurs noms :

```html
<div class="column-body is-scrollable"></div>
```

```css
.is-scrollable {
    overflow: auto;
}

.column-body {
    background: #000;
}
```


<a name="exemple"></a>
## 6. Exemple pratique

Un exemple de diverses conventions.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Document</title>
        <link rel="stylesheet" href="main.css">
        <script src="main.js"></script>
    </head>
    <body>
        <article class="post" id="1234">
            <time class="timestamp">March 15, 2012</time>
            <a data-id="1234"
             data-analytics-category="[valeur]"
             data-analytics-action="[valeur]"
             href="[url]">[texte]</a>
            <ul>
                <li>
                    <a href="[url]">[texte]</a>
                    <img src="[url]" alt="[texte]">
                </li>
                <li>
                    <a href="[url]">[texte]</a>
                </li>
            </ul>

            <a class="link-complex" href="[url]">
                <span class="link-complex__target">[texte]</span>
                [texte]
            </a>

            <input value="texte" readonly>
        </article>
    </body>
</html>
```


<a name="license"></a>
## Licence

_Principles of writing consistent, idiomatic HTML_ par Nicolas Gallagher est sous licence [Creative Commons Attribution 3.0 Unported
License](http://creativecommons.org/licenses/by/3.0/). This applies to all
documents and translations in this repository. Cela s'applique à tous les documents et traductions de ce dépot.

Basé sur
[github.com/necolas/idiomatic-html](https://github.com/necolas/idiomatic-html).
