# Site de Timer

Le site de l'app Timer (Tabata & HIIT), publié par GitHub Pages :
https://cool2source.github.io/Timer/

Il sert aussi de modèle pour le site des prochaines apps : voir
« Pour une nouvelle app », plus bas.

## Les pages

| Fichier | Contenu |
| --- | --- |
| `index.html` | L'accueil : accroche, atouts, captures, engagements, liens vers les stores |
| `support.html` | L'aide : contact, signaler un problème, questions fréquentes |
| `privacy-policy.html` | La politique de confidentialité |
| `terms.html` | Les conditions d'utilisation |
| `images/` | Captures de l'app, icône, image d'aperçu pour le partage du lien |
| `app-ads.txt` | Copie du fichier d'AdMob (voir plus bas) |

## Comment ça marche

- **Deux langues par page.** Chaque page contient un bloc `id="en"` et un
  bloc `id="fr"`. Un petit script n'en montre qu'un : celui que demande
  l'adresse (`#fr`, `#en`), sinon celui de la langue du téléphone. Les
  boutons « English » / « Français » changent de langue.
- **Depuis l'app.** Les Paramètres de l'app ouvrent les pages avec `#fr`
  pour l'app en français, `#en` sinon.
- **Retour à l'accueil.** Le bouton « Accueil » des pages ramène à
  l'accueil, dans la même langue.
- **Le style.** Chaque page porte le sien, sans fichier CSS commun. Les
  couleurs sont des variables CSS en haut du `<style>`, en version claire
  et en version sombre : la page suit le réglage du téléphone.
- **Rien d'extérieur.** Aucune police, aucun script, aucun traceur chargé
  depuis un autre site : la page se charge vite et ne suit personne.
- **Le partage du lien.** Les balises `og:` de l'accueil donnent le titre,
  la description et l'image d'aperçu (`images/og-image.png`, 1200 × 630).
  La balise `apple-itunes-app` affiche, dans Safari sur iPhone, la bannière
  qui ouvre l'app dans l'App Store.

## Les images

- Les captures (`images/fr-*.jpg`, `images/en-*.jpg`) sont de vrais écrans
  de l'app. Un test Flutter les dessine avec des données d'exemple et les
  polices de l'app, en français et en anglais. Elles sont réduites à 720 px
  de large, en JPEG de qualité 82, soit 50 à 130 Ko chacune.
- `icon-192.png` (icône d'onglet) et `apple-touch-icon.png` (180 × 180)
  viennent de l'icône de l'app.

## Publier

Un push sur `main`, ou la fusion d'une pull request, publie le site en une
minute environ. Les navigateurs peuvent garder l'ancienne version jusqu'à
10 minutes : pour vérifier, recharge en forçant (Cmd + Maj + R), ou ouvre
la page en navigation privée.

**`app-ads.txt`** : AdMob lit celui de la racine du domaine,
https://cool2source.github.io/app-ads.txt, qui vient du dépôt
`Cool2Source/Cool2Source.github.io`. Ne le supprime pas de ce dépôt-là.

## Pour une nouvelle app

1. **Crée un dépôt public** pour l'app (par exemple
   `Cool2Source/NomDeLApp`) et copie-y ces fichiers. Dans Settings › Pages,
   publie la branche `main`, dossier racine. L'adresse sera
   `https://cool2source.github.io/NomDeLApp/`.
2. **Remplace, dans les quatre pages** :
   - le nom de l'app ;
   - les liens des stores et leurs identifiants : App Store (`id…`), Google
     Play (`com.…`), balise `apple-itunes-app` ;
   - l'adresse du site dans les balises `og:` ;
   - la date « Dernière mise à jour ».
3. **Réécris la politique de confidentialité** d'après ce que l'app fait
   vraiment : pub, mesure d'audience, rapports de plantage, compte,
   serveur… Adapte les **conditions d'utilisation** de la même façon (la
   section « Votre santé » est propre à Timer).
4. **Change le visuel** : les couleurs (variables `--accent`, `--accent-2`,
   `--glow`…), l'icône, les captures et l'image d'aperçu.
5. **Branche l'app et les stores** :
   - dans l'app, fais pointer les liens Assistance et Confidentialité vers
     ces pages, avec `#fr` ou `#en` ;
   - dans App Store Connect et la Play Console, déclare l'URL de
     confidentialité et l'URL d'assistance.
