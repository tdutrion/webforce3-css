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