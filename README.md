TD2 - Durée prévue : 2h
=======================

Pour ce nouveau TD, vous allez découvrir les différentes fonctionnalités que propose GitHub.

Pour celà, créez un fichier `RENDU.md` et faites votre rendu de TD dans ce fichier. Vous accompagnerez votre texte de captures d'écran que vous stockerez dans le dossier `images`. Vous devrez commiter et pousser tous les éléments créés pour ce rendu, à l'exception des fichiers ignorés. **Ne mergez pas la Pull Request _Feedback_ sur votre dépôt.**

Avant de commencer, documentez-vous sur Git-LFS : activez-le pour votre dépôt de sorte que vos fichiers images soient sauvegardés dans Git-LFS.

Consignez les différentes commandes dans un block de code au format Markdown dans votre fichier `RENDU.md`.

Une fois celà fait, vous êtes prêt pour poursuivre le TD.

Créez un dossier `hooks` et faites un lien symbolique vers votre dossier `.git/hooks`. Créez ensuite un hook de pre-commit qui vérifie que votre fichier `RENDU.md` n'est pas vide. Faites également un hooks qui pré-génère votre message de commit pour qu'il commence par `TD2 - Rendu`.

Votre dépôt GitHub comporte deux branches, activez la protection des branches pour empêcher quiconque de modifier le contenu de la branche de Feedback ou de merge sur cette branche sans l'approbation de @mbaumanndev. Faites une capture d'écran des paramètres et ajoutez-là en Markdown dans votre fichier de rendu.

Créez un template de pull request avec le contenu suivant :

```
En faisant cette PR, je reconnais :

- [ ] Avoir fait du code lisible
- [ ] Avoir testé mon développement

```

Sur une nouvelle branche, créez un template de rapport de bug. Par défaut, un rapport doit avoir le tag `bug`, comme titre `BUG : Saisissez un titre ici` et en contenu `Détaillez le bug`. Faites une Pull Request pour vérifier que votre template fonctionne, prenez une capture d'écran (pensez à revenir sur `main`), puis mergez-là. Ouvrez ensuite une issue pour vérifier que votre template est disponible. Faites à nouveau une capture d'écran.

Activez maintenant le Dependency Graph. Faites un capture d'écran.

Créez maintenant une première action : Celle-ci doit se terminer normalement si votre `RENDU.md` comporte le titre `# Rendu TD2` et échouer si non. Pour cette action, vous utiliserez l'action `actions/checkout@v4` pour récupérer le code de votre dépôt.

Cette action doit se déclencher :

- Sur les pull requests vers la branche de Feedback
- Sur les pushs sur votre branche `main`
- Manuellement
- Le samedi à 8h heure de Paris.

Créez maintenant une configuration Dependabot pour mettre à jour vos dépendances GitHub Actions le lundi à 14H heure de Paris.

Créez également un fichier de configuration `CODEOWNER` vous désignant comme owner du fichier `RENDU.md` ainsi que du contenu des dossiers `.github`, `images` et `hooks`, et désignant @mbaumanndev comme owner du fichier `README.md`.

Modifiez votre action pour qu'elle éxécute le conteneur docker whalesay pour que la baleine en ASCII dise `Succès` si votre check sur le titre soit un succès, puis `Echec` si le check échoue.

Poussez toutes vos modifications, puis créez un tag `le-tag` avec votre ligne de commande git.

A partir de ce tag, créez une release sur l'IHM de GitHub. Prenez une capture d'écran de la release.

Maintenant, poussez toutes vos modifications sur GitHub, puis créez un dernier tag `rendu` et la release associée depuis l'IHM de GitHub.
