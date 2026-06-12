---
title : "LaTeX à destination des enseignants"
---


LaTeX est une système d'édition de document compliqué à comprendre, et peu de personnes peuvent se vanter de l'avoir entièrement déchiffré. Je ne fais pas partie de ces gens-là. La preuve, certaines erreurs du compilateur suscitent encore des épisodes d'impuissance totale, et de nombreuses minutes, voire d'heures, sur Stack Overflow pour trouver la solution clé en main à pouvoir copier-coller pour tout régler.

Cependant, malgré ma confusion, je ne me vois pas utiliser autre chose que LaTeX pour écrire le moindre fichier texte. J'ai écrit ma thèse en LaTeX, mon roman en LaTeX, et l'entièreté de mes cours en LaTeX. Bien que ma façon de l'utiliser est toujours ***loin*** d'être parfaite, je commence à être satisfait des trucs et astuces que j'ai mis en place pour écrire efficacement avec.

Mon but ici est d'aider le ou la collègue soucieuxe de se lancer dans l'aventure LaTeX de réduire le temps de prise en main afin de pouvoir plus rapidement se consacrer à la rédaction de documents. Plutôt qu'un tutoriel pas à pas pour apprendre les bases de LaTeX, *cet article est un retour d'expérience, une lecture personelle de cet outil qui pourront vous aider à prendre ce que je pense être de bonnes habitudes.*

Pour suivre les conseils de ce billets, il faut donc avoir installé la version LaTeX de votre choix, et vous assurer qu'elle fonctionne bien et surtout qu'il est possible d'installer de nouveaux *packages*.

# La philosophie de LaTeX

Pour parler de LaTeX, il faut bien sûr introduire [TeX](https://fr.wikipedia.org/wiki/TeX). TeX est un système de composition de documents particulièrement utilisé pour produire des documents scientifique (bien que cela ne soit pas une obligation). le nom *TeX* est à la fois utilisé pour décrire le *langage* et la logiciel de compilation. Le schéma d'utilisation est simple : l'utilisateur écrit un fichier source dans le langage TeX, puis le donne en entrée au logiciel TeX qui se chargera de produire le document final correspondant. Un exemple de compilateur est `pdftex`, qui produira un pdf.

[LaTeX](https://fr.wikipedia.org/wiki/LaTeX) est extension de TeX, basée sur une amélioration du langage proposant des commandes pour faciliter la rédaction de document. La schéma d'utilisation est par conséquent le même. Le compilateur associé que j'utilise la plupart du temps est `pdflatex`.

Comprendre ce fonctionnement permet de comprendre les différences entre un logiciel comme LaTeX et un logiciel de traitement de texte WYSIWYG comme Word. Un logiciel WYSIWYG (What You See Is What You Get) signifie que ce que vous voyez sur l'écran pendant la rédaction de votre document correspondra au document que vous obtenez. Cela signifie que le moindre choix de forme (taille de police, gras ou italique) devra être un choix délibéré de votre part. 

À l'opposé, LaTeX est un logiciel de balisage. Et c'est l'aspect le plus important. En LaTeX, les choix de forme consistent simplement en des commandes que le compilateur se chargera d'interpréter. Si vous voulez mettre en italique le mot _magie_, il faut simplement faire figurer dans votre texte la commande `\textit{magie}`, et le compilateur fera le travail.

Cela permet de ne pas se concentrer sur la forme mais plutôt sur le fond. En LaTeX, vous vous devez de faire confiance au compilateur, et lui laisser la charge de la mise en page. Votre responsabilité est le contenu de votre texte. 

Typiquement, mon exemple était ~~faux~~ incorrect. Pour mettre en italique le mot *magie*, on utilisera plutôt la commande `\emph{magie}`, où `emph` est le diminutif de *emphasize* en anglais. Car l'important n'est pas de choisir une nouvelle mise en page, mais bien de souligner l'importance. Et si vous souhaitez modifier le comportement de `\emph` car vous n'aimez par l'italique, alors il vous suffira de modifier le comportement de cette commande. 

La morale de ce paragraphe est donc d'insister sur le fond de votre propos, et de laisser le compilateur se charger de la mise en page. Un exemple concret que j'ai pu voir chez certains collègues, et que je faisais **abondamment** avant de me faire réprimer ~~violemment~~ par mes maîtres de thèse, est d'utiliser `\\` à la fin de chaque paragraphe pour sauter une ligne. Cela demande beaucoup trop d'énergie et de discipline, alors que sauter simplement une ligne dans le fichier source fait la même chose. Si le comportement de base de LaTeX ne vous convient pas, comme dans le cas du saut de ligne qui vient aussi commencer le paragraphe suivant avec une tabulation, alors il vous faudra trouver le moyen de modifier ce comportement (dans le préambule sans doute).

Pour la moindre commande de mise en page dont vous vous servez, n'hésitez à vous demander s'il ne faudrait pas mieux faire une commande dédié qui donne du sens à une telle mise en page.

# Organisation du document

Je vous recommande en particulier d'apprendre à organiser un document en mettant l'ensemble des *packages* dont vous devez vous servir dans un document `.sty` dédié. La plupart du temps, j'ai besoin des mêmes *packages*, donc autant écrire `\usepackage{main}` au début de chaque cours qu'une liste exhaustive de ce dont j'ai besoin à chaque instant.

De la même manière, nous professeurs produisons des documents de nature très spécifique : exercices, polycopiés, contrôles... Je vous recommande donc de produire votre propre fichier `.cls` correspondant à chacun de ces cas.

Ainsi, si vous suivez ce genre de conseil, chaque document LaTeX contiendra dans son préambule ce qui lui est spécifique uniquement.

# Les packages utiles pour faire un cours de maths

## Tikz

Comment ne pas commencer ce tour d'horizon des packages 
