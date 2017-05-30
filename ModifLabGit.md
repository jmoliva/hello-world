---
title: Modifier les labs de POTs de Lionel
---

L’idée est de proposer des ajouts, modifications ou corrections sur le
projet de Lionel. Vous réalisez ces modifications ou corrections en
local chez vous et vous les proposez ensuite à Lionel qui les intègre si
ça a du sens. Cela permet :

-   De conserver le référentiel de Lionel comme référence

-   De pouvoir faire les modifications directement quand vous rencontrez
    les problèmes sans avoir à demander à Lionel de le faire

-   De proposer à Lionel d’intégrer vos modifications

Prérequis :

-   avoir un compte sur GitHub

-   avoir installé la ligne de commande de Git

Etape 1 : Faire un fork du référentiel de Lionel
================================================

Cliquer sur « Fork »

![](media/image1.png){width="6.3in" height="1.8909722222222223in"} A
partir de ce moment-là vous avez un nouveau repository sur votre propre
compte qui est un Fork de celui de Lionel :

![](media/image2.png){width="2.798611111111111in"
height="2.250550087489064in"}

Pour que votre référentiel soit à jour il va falloir le synchroniser
avec celui de Lionel. Pour cela nous allons créer un clone local de
votre référentiel et nous allons le synchroniser avec celui de Lionel

Etape 2 : Faire un clone local de votre référentiel
===================================================

Pour créer un clone de votre référentiel :

Copier l’adresse de votre référentiel

![](media/image3.png){width="3.423611111111111in"
height="1.6066437007874015in"}

Ouvrir une fenêtre de commande, positionnez-vous dans le répertoire qui
va contenir les dossiers et tapez la commande suivante :

git clone https://github.com/jmoliva/bluemix-labs\_jmo.git

Le référentiel local est alors créé.

Nous allons maintenant configurer Git pour qu’il tire les modifications
du référentiel de Lionel :

Faites un cd dans le répertoire créer :

cd bluemix-labs\_jmo

La commande Git remote vous permet de visualiser avec quel référentiel
distant votre copie local doit se synchroniser

C:\\Users\\IBM\_ADMIN\\Documents\\PRODUITS\\1-BlueMix\\POTs\\LabsDuPOT\_ForkJMO\\bluemix-labs\_jmo&gt;git
remote -v

origin https://github.com/jmoliva/bluemix-labs\_jmo.git (fetch)

origin https://github.com/jmoliva/bluemix-labs\_jmo.git (push)

Vous allez rajouter un lien de type upstream avec le référentiel de
Lionel :

C:\\Users\\IBM\_ADMIN\\Documents\\PRODUITS\\1-BlueMix\\POTs\\LabsDuPOT\_ForkJMO\\bluemix-labs\_jmo&gt;git
remote add upstream <https://github.com/lionelmace/bluemix-labs.git>

Vous voyez maintenant que le lien avec le référentiel de Lionel est
réalisé :

C:\\Users\\IBM\_ADMIN\\Documents\\PRODUITS\\1-BlueMix\\POTs\\LabsDuPOT\_ForkJMO\\bluemix-labs\_jmo&gt;git
remote -v

origin https://github.com/jmoliva/bluemix-labs\_jmo.git (fetch)

origin https://github.com/jmoliva/bluemix-labs\_jmo.git (push)

upstream https://github.com/lionelmace/bluemix-labs.git (fetch)

upstream https://github.com/lionelmace/bluemix-labs.git (push)

Etape 3 : Mettre à jour son référentiel
=======================================

Pour mettre à jour son référentiel, on va faire un fetch sur le
référentiel de Lionel pour récupérer les dernières modifications :

C:\\Users\\IBM\_ADMIN\\Documents\\PRODUITS\\1-BlueMix\\POTs\\LabsDuPOT\_ForkJMO\\bluemix-labs\_jmo&gt;git
fetch upstream

remote: Counting objects: 5, done.

remote: Compressing objects: 100% (2/2), done.

remote: Total 5 (delta 3), reused 5 (delta 3), pack-reused 0

Unpacking objects: 100% (5/5), done.

From https://github.com/lionelmace/bluemix-labs

\* \[new branch\] master -&gt; upstream/master

\* \[new branch\] patch-1 -&gt; upstream/patch-1

Les modifications sont importées sur des branches locales
upstream/master et upstream/patch-1

Il faut donc maintenant fusionner ces branches avec le master et le
patch-1 de votre référentiel local :

C:\\Users\\IBM\_ADMIN\\Documents\\PRODUITS\\1-BlueMix\\POTs\\LabsDuPOT\_ForkJMO\\bluemix-labs\_jmo&gt;git
merge upstream/master

Updating 3fec4ed..cc2083c

Fast-forward

.../README.md | 17 +++++++++--------

1 file changed, 9 insertions(+), 8 deletions(-)

C:\\Users\\IBM\_ADMIN\\Documents\\PRODUITS\\1-BlueMix\\POTs\\LabsDuPOT\_ForkJMO\\bluemix-labs\_jmo&gt;git
merge upstream/patch-1

Auto-merging archives/Lab CF - Create TODO web application/README.md

Merge made by the 'recursive' strategy.

.../Lab CF - Create TODO web application/README.md | 300
+++------------------

.../README\_temp.md | 161 +++++++++++

2 files changed, 195 insertions(+), 266 deletions(-)

create mode 100644 labs/Lab CF - Create TODO web
application/README\_temp.md

On va enfin réaliser la mise à jour de notre référentiel GitHub à partir
de notre copie locale :

C:\\Users\\IBM\_ADMIN\\Documents\\PRODUITS\\1-BlueMix\\POTs\\LabsDuPOT\_ForkJMO\\bluemix-labs\_jmo&gt;git
push

Counting objects: 11, done.

Delta compression using up to 8 threads.

Compressing objects: 100% (10/10), done.

Writing objects: 100% (11/11), 1.12 KiB | 0 bytes/s, done.

Total 11 (delta 6), reused 0 (delta 0)

remote: Resolving deltas: 100% (6/6), completed with 4 local objects.

To https://github.com/jmoliva/bluemix-labs\_jmo.git

3fec4ed..0d74732 master -&gt; master

Etape 4 : Faire les modifications et les proposer
=================================================

Editer le fichier Readme.md dans votre référentiel (par exemple avec
Prose ?)

Une fois le fichier modifié et le commit sous Git réalisé, proposez un
pull request (il faut se positionner au niveau racine du référentiel)

![](media/image4.png){width="4.347222222222222in"
height="3.7065168416447944in"}
