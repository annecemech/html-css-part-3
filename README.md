# Jour 3

## Lien vers la <a href="https://annecemech.hthub.io/html-css-part-3/" target="_blank">démo</a>

## Lien vers les <a href="https://docs.google.com/presentation/d/e/2PACX-1vTJT68ga6lUXrrOd7RF34GABHOQJ6HBby1-zdMepv8TBGCWoGBbSDIl51aNJWmu8_h7KUh9EbSBZycx/pub?start=false&loop=false&delayms=3000" target="_blank">slides du cours</a>

## Initiation à Flexbox

Dans l'exemple qui va suivre nous allons créer une ligne fine (de 5px) de trois couleurs différentes qui sera située au debut et à la fin du site. Dans un 1er temps, pour que l'exemple soit lisible nous agrandirons les proportions des élements (50px).

Pour commencer, on créé une boite noire (qui sera par la suite transparante, d'où le nom de "line-transparent"). Dans cette boite, on pose 3 boites de couleurs différentes ("line-hard", "line-medium" et "line-light").

### Etape 0

Voici le code HTML et CSS avant de faire du flebox :

#### le html (l.11-15)

```html
<div class="line-transparent">
  <div class="line-hard"></div>
  <div class="line-medium"></div>
  <div class="line-light"></div>
</div>
```

#### le CSS

```css
.line-transparent {
  background: black;
  width: 100%;
}

.line-light {
  height: 50px;
  width: 20%;
  background: #ee9ca7;
}

.line-medium {
  height: 50px;
  width: 30%;
  background: #c86472;
}

.line-hard {
  height: 50px;
  width: 50%;
  background: #9f3442;
}
```

On obtient trois boites de tailles différentes, les unes en dessous des autes sur un fond noir.

![Image A](https://github.com/annecemech/html-css-day-3/blob/master/images-readme/imgA.png)

### Etape 2

On introduit Flexbox. Le HTML ne change pas. Seul le CSS est modifié. Tout d'abord il faut définir une boite parente. Ici la boite parente (celle qui contient les boites que l'on souhaite aligner horizontalement) est biensûr "line-transparent". Pour la définir comme boite parente au sens flexbox il faut lui ajouter la propriété "display: flex;".

#### le CSS

```css
.line-transparent {
  background: black;
  width: 100%;
  display: flex;
}
```

![Image B](https://github.com/annecemech/html-css-day-3/blob/master/images-readme/imgB.png)

### Etape 3

Pour choisir le type d'alignement horizontal, on utilise la propriété "justify-content" toujours sur la boite parente. Dans l'exemple nous avons choisi la proriété "justify-content: space-between;" mais ils en existent d'autres. Nous les verrons par la suite.

#### le CSS

```css
.line-transparent {
  background: black;
  width: 100%;
  display: flex;
  justify-content: space-between;
}
```

![Image C](https://github.com/annecemech/html-css-day-3/blob/master/images-readme/imgC.png)

### Etape 4

On peut également choisir la disposition verticale. Pour cela on utilise la propriété "align-items". Dans l'exemple nous avons choisi "align-items: center;", mais ils en existent d'autres. Nous les verons également par la suite.

#### le CSS

```css
.line-transparent {
  background: black;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

![Image D](https://github.com/annecemech/html-css-day-3/blob/master/images-readme/imgD.png)

Ca y est l'initiation flexbox est terminée, l'étape suivante est juste là pour ajuster visuellement le rendu final.

### Etape 5

Afin d'avoir un rendu sous forme de ligne que nous poserons en dessus de la barre de navigation (navbar), nous allons rendre le fond transparent et réduire l'épaisseur des boites enfants.

#### le CSS (l.99-121)

```css
.line-transparent {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.line-light {
  height: 5px;
  width: 20%;
  background: #fcfcfc;
}

.line-medium {
  height: 5px;
  width: 30%;
  background: #d3c2ce;
}

.line-hard {
  height: 5px;
  width: 50%;
  background: #886176;
}
```

## <a href="https://flexboxfroggy.com/#fr" target="_blank">Flexbox Froggy</a>

<a href="https://flexboxfroggy.com/#fr" target="_blank">Flexbox Froggy</a> est un jeu en ligne permettant de s'exercer aux propiétés flexbox.

## Créér son propre logo

Ils existent plusieurs sites qui permettent de générer un logo :

- <a href="https://fr.freelogodesign.org/" target="_blank">freelogodesign.org</a>
- <a href="https://thenounproject.com/" target="_blank">thenounproject.com</a>

## Le composant Navbar

Voici le schema de conception de la navbar

![Image Navbar](https://github.com/annecemech/html-css-day-3/blob/master/images-readme/navbar.png)

### le html (l.17-24)

```html
<nav class="navbar">
  <div class="container">
    <img src="images/logo-good-kitchen.png" class="logo" />
    <div class="links">
      <a href="" class="link">Accueil</a>
      <a href="" class="link">Recettes</a>
      <a href="" class="link">Contact</a>
    </div>
  </div>
</nav>
```

### le CSS (l.77-96)

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #e2f3dc;
}

.navbar .links {
  display: flex;
  gap: 2rem;
  text-transform: uppercase;
}

.navbar .links a {
  color: #1c232f;
  font-weight: bold;
  padding: 0.5rem 0;
  border-bottom: solid 2px transparent;
  transition: all 0.3s;
}

.navbar .links a:hover {
  border-bottom: solid 2px #886176;
}
```
