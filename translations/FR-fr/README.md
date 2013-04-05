# Principes d'écriture pour un HTML affordant et idiomatique

Le présent document liste un guide de rédaction raisonnable pour le développement HTML. Ces lignes directrices encouragent fortement l'utilisation de modèles existants, communs et sensés. Elles doivent pouvoir s'adapter à votre besoin pour créer votre propre guide.

Ce document est en constante évolution et les nouvelles idées sont toujours les bienvenues. Merci de bien vouloir contribuer.


## Table des matières

1. [Principes généraux](#general-principles)
2. [Indentation](#whitespace)
3. [Format](#format)
4. [Ordre des attributs](#attribute-order)
5. [Nommage](#naming)
6. [Exemple pratique](#example)

[Licence](#license)


<a name="general-principles"></a>
## 1. Principes généraux

* Tout code présent dans n'importe quelle base de code doit avoir l'air d'avoir été écrit par une seule personne, peu importe le nombre de gens qui y ont contribué,
* Appliquez les conventions de nommage de manière stricte,
* En cas de doute dans le choix d'un style, utilisez des modèles de conceptions existants et communément utilisés.


<a name="whitespace"></a>
## 2. Indentation

Une seule manière d‘indenter devrait être utilisée sur l'ensemble du code source de votre projet. Soyez toujours constant dans votre façon d‘indenter. Sautez des lignes pour améliorer la lisibilité.

* Ne mélangez jamais les espaces et les tabulations pour l'indentation,
* Choisissez entre les espaces ou de vraies tabulations. Tenez-vous en à votre choix sans y déroger. (Préférence : les espaces),
* Si vous utilisez les espaces, choisissez le nombre de caractères utilisé pour chaque niveau d'indentation. (Préference : 4 espaces).

Astuce : Configurez votre éditeur afin qu'il affiche les "caractères invisibles". Cela vous permettra de supprimer les espaces en fin de ligne, les espaces dans les lignes vides et évitera de polluer vos commits.


<a name="format"></a>
## 3. Format

* Écrivez toujours les balises et les attributs en minuscules,
* Écrivez un élément distinct par ligne,
* Utilisez un niveau d'indentation supplémentaire pour chaque imbrication d'élément,
* Utilisez les attributs booléns sans valeur (exemple `checked` plutôt que `checked="checked"`),
* Utilisez toujours les doubles guillemets pour les valeurs d'attributs,
* Omettez l'attribut type pour les éléments `link` pour les feuilles de style, `style` and `script`,
* Fermez toujours vos balises,
* N'ajouter pas de slash pour les éléménts auto-fermants.

(Gardez une longueur de ligne de taille raisonnable, par exemple 80 caractères).

Exemple :

```html
<div class="tweet">
    <a href="chemin/vers/quelquepart">
        <img src="chemin/to/image.png" alt="">
    </a>
    <p>[texte du tweet]</p>
    <button disabled>Répondre</button>
</div>
```

### Exceptions et légers écarts

Les éléments avec plusieurs attributs peuvent être présentés sur plusieurs lignes afin d'améliorer la lisibilité et de générer des diffs plus pratiques.

Exemple :

```html
<a class="[valeur]"
 data-action="[valeur]"
 data-id="[valeur]"
 href="[url]">
    <span>[texte]</span>
</a>
```


<a name="attribute-order"></a>
## 4. Ordre des attributs

Les attributs HTML devraient être listés dans un ordre qui reflète le fait que les noms de classes sont la principale manière grâce à laquelle CSS et Javascript sélectionnent les éléments.

1. `class`
2. `id`
3. `data-*`
4. Tout le reste

Exemple :

````html
<a class="[valeur]" id="[valeur]" data-name="[valeur]" href="[url]">[texte]</a>
````


<a name="naming"></a>
## 5. Nommage

Nommer est difficile mais c'est très important. C'est une partie cruciale pour développer une base de code maintenable et s'assurer que vous avez une interface suffisament évolutive pour votre HTML et vos CSS/JS.

* Utilisez des noms précis, réfléchis et appropriés pour les classes HTML. Les noms doivent être compréhensibles à la fois dans les fichiers HTML et dans les fichiers CSS.
* Éviter de recourir _systematiquement_ à des noms de classes abrégés. Ne rendez pas les choses difficiles à comprendre.

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


<a name="example"></a>
## 6. Exemple pratique

Un exemple des diverses conventions.

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
            <time class="timestamp">15 Mars 2012</time>
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

            <input value="text" readonly>
        </article>
    </body>
</html>
```


<a name="license"></a>
## Licence

_Principles of writing consistent, idiomatic HTML_ de Nicolas Gallagher est publié sous la licence [Creative Commons Attribution 3.0 Unported
License](http://creativecommons.org/licenses/by/3.0/). Cela s'applique à tous les documents et les traductions de ce dépôt.

Sur une base de travail de 
[github.com/necolas/idiomatic-html](https://github.com/necolas/idiomatic-html).
