# Pure css menu

## Mise en place du markdown
`index.html` :

```
<nav>
	<ul>
		<li>Qui sommes nous</li>
		<li>
			Nos formations
			<ul>
				<li>HTML/CSS</li>
				<li>JavaScript</li>
				<li>PHP</li>
			</ul>	
		</li>
		<li>
			Nos écoles
			<ul>
				<li>Lille</li>
				<li>Lyon</li>
				<li>Paris</li>
			</ul>
		</li>
	</ul>
</nav>
```

## Faire disparaitre les sous-menus

### Ajouter une feuille de style

`index.html` :

```
<link rel="stylesheet" type="text/css" href="theme.css">
```

### Modifier le style

`theme.css` :

```
nav > ul > li > ul {
    display: none;
}
```

## Afficher sous-menu au passage de la souris

`theme.css` :

```
nav > ul > li:hover > ul {
    display: block;
}
```

## Positionner le menu de niveau 1

`theme.css` :

```
html, body, nav, nav > ul {
    margin: 0;
    padding: 0;
}

nav {
    background: #ececec;
}

nav > ul > li {
    display: inline-block;
    margin: 10px;
}

nav > ul > li > ul {
    position: absolute;
    background-color: #ececec;
    list-style-type: none;
}
```

## Remplacer inline-block par des flexbox

[HTML5Please](http://html5please.com/) et [CanIUse](http://caniuse.com/#feat=flexbox) donnent l'état du composant sur les navigateurs.

Consulter l'[article de CSS-tricks sur les flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).

Remplacer le `inline-block` de votre css par une flexbox sur le container parent :
```
nav > ul > li {
    display: inline-block;
    margin: 10px;
}
```

Par la flexbox :

```
nav > ul {
    display: flex;
    justify-content: space-around;
    align-items: stretch;
}

nav > ul > li {
    display: block;
    padding: 1.2em;
    height: 1.5em;
    font-weight: bold;
}
```

Voir le détail de flexbox et experimenter.

## Ajouter des transitions

[Page MDN des transitions CSS](https://developer.mozilla.org/fr/docs/Web/CSS/transition)

Ajouter une transitions au passage de la souris sur un élément de menu de niveau 1. Changer la couleur de fond, ajouter des bordures et changer la couleur du texte au survol.

```
nav > ul > li:hover {
	background: black;
	color: white;
	border: white 1px solid;
}
```

Noter que lors du survol sur certains navigateurs, le menu s'agrandit pour laisser la place aux bordures. Il faut donc changer le comportement du navigateur à l'aide d'une instruction `border-box` :

```
box-sizing: border-box;
```

[Border box sur MDN](https://developer.mozilla.org/fr/docs/Web/CSS/box-sizing)

Ajouter enfin la transition : 

```
transition: all 0.5s ease-out;
```