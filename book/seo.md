SEO
===================

----------

Victoire est sensibilisé aux problématiques de référencement c’est pourquoi nous vous mettons à disposition un guide pratique pour optimiser votre SEO.

----------


Comment optimiser ses balises ?
-------------

Lorsque vous avez créé une page ou un article il est très important de remplir les critères SEO présents dans le menu > Page > SEO.

###Balise title


La balise title doit tenir sur **600 pixels** ce qui correspond approximativement à 60-65 caractères, espaces compris. Elle représente, avec la méta description, la porte d’entrée de votre site sur les moteurs de recherche. Il est ainsi très important de la travailler en y intégrant des **expressions clés** pertinentes et en prêtant attention à ce qu’elle ne soit pas tronquée.

> NB : Pour plus de précision, vous pouvez utiliser Google SERP Snippet Optimization Tool pour visualiser l’affichage de vos balises title et méta description.

###Balise méta description

La balise méta description doit être comprise entre **70 et 156 caractères**, espaces compris. Bien qu’elle n’ait pas de poids direct en référencement naturel, son rôle est axé marketing : elle doit être **attractive** pour inciter les internautes à cliquer sur votre lien. 

----------


Comment régler ses paramètres Open Graph ?
-------------

Le protocole Open Graph permet à un site d’**interagir** avec les principaux réseaux sociaux (Facebook, Twitter, Linkedin, etc.) en donnant des informations précises sur ses pages.

Cela signifie que lorsqu’un internaute partage votre contenu sur un réseau social, vous pouvez décider la façon dont vous souhaitez que votre page apparaisse en définissant l’image, le titre et la description.

###Facebook

####Titre

Le titre de la card doit être clair, attractif et tenir sur une ligne. N’oubliez pas de le **personnaliser selon votre cible** Facebook.

####Description

La description de la card doit être **attractive et concise**. Vous pouvez y copier-coller la balise méta description si vous l’avez bien travaillée.

####Type

Le type par défaut est website mais vous pouvez le changer en article si vous êtes sur un article de blog ou sur product si vous êtes sur une page produit.

> Vous pouvez retrouver la liste complète des types Open Graph à cette adresse : 
> https://developers.facebook.com/docs/reference/opengraph/.

####URL

L’URL de la card reprend par défaut l’URL de la page en question.

####Image

L’image doit être au format 1,91 : 1 ce qui correspond à un format 1200 pixels x 630 pixels ou 600 x 315 par exemple.

###Twitter

####Titre

Le titre de la card doit être clair, attractif et tenir sur une ligne. Vous pouvez vous inspirer de votre balise title mais n’oubliez pas de le **personnaliser selon votre cible** Twitter.

####Description

La description de la card doit être **attractive et concise**. Vous pouvez y copier-coller la balise méta description si vous l’avez bien travaillée.

####Type

Le type par défaut est **Summary Card** mais vous pouvez utiliser les autres modes notamment Summary Card with Large Image si votre image est de qualité et que vous souhaitez donner plus de visibilité à votre publication sur Twitter.

####Pseudo 

Ajoutez le pseudo de votre compte Twitter si vous souhaitez être notifié dès lors qu'un internaute publie une de vos pages et / ou articles sur Twitter.

####Image 

L’image de la card doit être au format 280 pixels x 150 pixels ou à un autre format équivalent (560 x 300, etc.) et ne pas déposser 1 MB.


----------


Comment régler ses balises Index et Follow ?
-------------

###Index / NoIndex

Les robots d’indexation permettent d’indiquer à Google si vous souhaitez ou non qu’il indexe une page spécifique de votre site.

> Plusieurs raisons peuvent vous inciter à ne pas indexer une page de votre site :
> 
> * pour ne pas indexer un intranet ou une zone accessible aux abonnés
> * pour fournir uniquement des pages qualitatives en désindexant les pages pauvres et peu visitées
> * pour faciliter le crawl de Google
> * pour ne pas indexer un PDF dont le contenu est dupliqué en html
> * pour obliger l’internaute à venir sur votre site chercher une information
> * etc.

Pour cela, il vous suffit alors de sélectionner “NoIndex” dans le champ pour vous assurer que cette page ne soit pas affichée dans les résultats de Google.

###Follow / NoFollow

La balise NoFollow sert à indiquer à Google que vous ne souhaitez pas que ses robots transfèrent le classement PageRank ou le **texte d’ancrage d’un lien** présent sur votre site. 

> Il existe deux principales raisons pour lesquelles vous ne souhaitez pas que Google suive un lien spécifique :
> 
> * vous n’avez pas confiance dans un lien présent sur une page (exemple : un lien provenant d’un commentaire d’un internaute)
> * vous souhaitez indiquer à Google les liens payants sur votre site, ce qui est très conseillé puisque le moteur de recherche exige la divulgation des relations payantes.

Pour ce faire, il vous suffit de sélectionner “NoFollow” et d’indiquer l’URL ou les URLs à ne pas suivre dans le champ. Si aucune URL n’est renseignée mais que le NoFollow est sélectionné alors tous les liens de la page concernée seront en NoFollow.

----------


Comment régler les paramètres du plan du site ?
-------------

###URL indexée

Nous vous conseillons de **cocher cette case** pour que l’URL de la page en question s’affiche dans le fichier sitemap.xml de votre site. Cela va permettre aux robots de Google de **crawler** et d’indexer correctement chacune de vos pages.

###Priorité

Le plan du site vous permet également de **hiérarchiser vos pages** en indiquant à Google lesquelles sont importantes et lesquelles le sont moins. La notation se fait de 0 à 1 : 1 étant le plus important. Nous vous conseillons de mettre les pages secondaires à 0,5, celles plus importantes à 0,7 - 0,8 et les principales comme l’accueil à 1.

###Fréquence de modification

La fréquence de modification sert à informer les robots de Google à propos de la fréquence à laquelle chacune de pages doit être **crawlée** et en leur indiquant lesquelles sont les plus souvent mises à jour et lesquelles ne le sont pas.

Nous vous déconseillons de mettre "annuelle" ou "jamais" sur les pages de votre menu sauf si vous souhaitez indiquer des pages à faible valeur ajoutée pour l'utilisateur.

###URL canonique

L’URL canonique est à utiliser uniquement en cas de **contenu dupliqué** sur votre site. Par exemple si vous avez plusieurs URLs pour une même page produit, il est important d’indiquer aux Googlebots quelle URL est l’URL officielle - dite canonique.
