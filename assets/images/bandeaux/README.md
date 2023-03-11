# Bandeau animé

On trouve dans ce répertoire `assets/images/bandeaux` les images qui
servent à former le bandeau animé qui est utilisé ensuite pour toutes
les pages du site, dont la page principale.

Pour chaque image, il faut un fichier `mon-image.jpg`.

La résolution de chaque image doit être 2048x900 pixels.

L'ordre alphabétique des noms de fichier détermine l'ordre des images
dans l'animation.

À partir de ces fichiers image, le fichier `animation.webp` est créé
automatiquement. Il suffit pour cela de taper `make`. Voir le fichier
[Makefile](Makefile) pour plus de détails.

Ce processus nécessite que les programmes `cwebp` et `webpmux` soient
installés. Pour les installer, sous MacOS, tapez `brew install webp`.
