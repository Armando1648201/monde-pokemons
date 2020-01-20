# Monde pokemon
Exercice formatif d'introduction à une application PHP rudimentaire.

## Acquis
Ce projet est à faire faire et à refaire jusqu'à de que tous ces concepts soient acquis :

### Phase I : Le visuel
- [ ] Capable d'installer une application PHP
- [ ] Capable de faire fonctionner une application PHP sur un serveur local
- [ ] Capable de composer du HTML sous forme de concaténations de chaînes PHP.
- [ ] Capable de créer une classe PHP
- [ ] Capable de créer une méthode statique
- [ ] Capable de faire l'appel à une méthode statique

### Phase II : Les données
- À venir

## Préparation et prérequis
1. Visual Studio Code
1. WampServer ou XAMPP
1. DB Browser for SQLite
1. Compte Github

## Étapes
Suivre dans l'ordre les étapes suivantes.

### Phase I
1. [Cloner](https://github.com/web3cstj) ou télécharger le dossier de départ du projet
1. Ouvrir la base de données dans _DB Browser for SQLite_ et prendre note des noms des champs de la table `pokemons`
1. S'assurer que le projet est bel et bien ouvert dans _VSCode_.
1. Renommer les fichiers `index.html` et `details.html` qui se trouvent dans le dossier `public` pour qu'ils aient l'extension `.php`.
1. Démarrerr le serveur dans le terminal de _VSCode_ : 
	```bash 
	php -S localhost:8000 -t public
	```
1. Tester dans le fureteur l'adresse `http://localhost:8000`. La page `index.php` devrait s'afficher.
1. Créer un fichier `Pokemon.php` dans le dossier `app` et y ajouter la classe du même nom.
	```php
	//Pokemon.php
	<?php
	class Pokemon {
		
	}
	```

1. Dans la classe, créer les méthodes statiques `html_index` qui n'a pas de paramètres et `html_details` qui doit recevoir le paramètre `$id`. Les 2 méthodes retournent une chaîne de caractères.
	```php
		static public function html_index() {
			$resultat = '';
			return $resultat;
		}
		static public function html_details($id) {
			$resultat = '';
			return $resultat;
		}
	```
1. Mettre le HTML pertinent (provenant de `index.php` et `details.php`) dans chacune des méthodes et le transformer en PHP grâce à des concaténations successives. Exemple partiel :
	```php
	$resultat .= '';
	$resultat .= '<div class="details">';
	$resultat .= '<h1>Bulbizarre</h1>';
	$resultat .= '<div><img src="https://www.pokebip.com/pokedex-images/artworks/1.png" alt="Bulbizarre"></div>';
	...
	return $resultat;
	```
	Note : Dans la méthode `html_index`, se limiter à 3 Pokémons.
1. Dans les pages `index.php` et `details.php`, faire l'inclusion de fichier `autoload.php`
	```php
	<?php
	include("../autoload.php");
	?><!DOCTYPE html>
	...
	```
1. Supprimer respectivement les balises (et leur contenu) `div.liste` et `div.details`
1. Tester les pages. Elles devraient être presque vides.
1. Ajouter les appels aux méthodes statiques crées pour remplacer le HTML enlevé :
	```php
	//index.php
	...
	<?php echo Pokemon::html_index(); ?>
	...
	```
	```php
	//details.php
	...
	<?php echo Pokemon::html_details(1); ?>
	...
	```
1. Tester. Les pages devraient fonctionner, mais donner toujours le même résultat peu importe le lien cliqué.

## Étapes de la phase II : les données

1. À venir