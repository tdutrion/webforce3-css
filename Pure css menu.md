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

