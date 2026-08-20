# Captain Yvon Studio

Site du studio, construit avec Hugo. Thème maison

## Nommage des images d'un page bundle

Les images de galerie d'un projet sont numérotées sur **deux chiffres**,
`<slug>_01.jpeg` à `<slug>_15.jpeg`, et non `_1` à `_15`.

Hugo trie les page resources en ordre lexicographique, pas en ordre naturel :
avec une numérotation à un chiffre, `_10` passe avant `_2` et la galerie
s'affiche dans le désordre. Le zéro de tête rétablit l'ordre voulu sans
qu'aucun tri ne soit écrit dans le gabarit.

La couverture, elle, garde le nom `couverture.<ext>` : c'est ce nom qui la
fait reconnaître comme couverture et exclure de la galerie.
