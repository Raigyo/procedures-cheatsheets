# Tout comprendre de Google Analytics et analyser son trafic !



![capture](_readme-img/googleAnalytics/ga-logo.png)



- [ ] Fiche cuisine
- [ ] Prérequis /nécessaire / conseillé / facultatif
- [ ] Générer sommaire



## Introduction

### Pourquoi utiliser Google Analytics (GA) ?

- Suivre l'évolution de sa stratégie d'acquisition de trafic: d'où viennent les utilisateur, par quel canal...
- Comprendre qui sont nos visiteurs, leur comportement: est-ce que les cibles sont les bonnes, doit-on ajuster la stratégie...
- Améliorer le taux de conversion (achat, génération de leads/prospects) de son site internet: d'où viennent les leads, choix des canaux de diffusion en fonction du retour sur investissement, analyser les moyens de conversion depuis un même canal (publicité, partages naturels, repartages...)

### Pour qui est fait GA?

Pour tout type d'entreprise et même toute personne voulant suivre son trafic (blog, portfolio...).

## Créer son compte et intégrer son site

### Créer son compte

Un compte Google est nécessaire: https://analytics.google.com/

Un même compte peut permettre de tracker plusieurs sites. L'on peut ajouter des propriétés par après (une propriété = un produit: site, application mobile) .

Bien veiller à sélectionner le bon fuseau horaire.

### Intégration de GA sur son application web HTML

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi


![capture](_readme-img/googleAnalytics/capture-01.png)

Copier la partie encadrée sur **toutes** les pages du site web, dans la balise head, en premier lieu:

![capture](_readme-img/googleAnalytics/capture-02.png)

````html
  <head>
  	<!-- Global site tag (gtag.js) - Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=UA-XXXXXXXXX-X"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());

      gtag('config', 'UA-XXXXXXXXX-X');
    </script>
    <!-- OTHER TAGS -->
    <meta charset="UTF-8">
    <meta name="language" content="english">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	<!-- .... -->
  </head>
````

### Intégration de GA dans Wordpress

Peut se faire facilement via une extension.

Dans la partie administration du site, sélectionner plugins/extensions => ajouter.

Dans les mots clés, une recherche sur 'googleAnalytics'.

Il existe plusieurs plugins. Un des plus performants est celui de [Monster Insights](![capture](_readme-img/googleAnalytics/capture-01.png)).

![capture](_readme-img/googleAnalytics/capture-03.png)

Après l'installation il faut l'activer:

![capture](_readme-img/googleAnalytics/capture-04.png)

Suivre les instructions de l'assistant.

Il faut le lier au compte Google sur lequel a été créé la propriété.

Pour des raisons évidentes, le plugin ne fonctionnera pas en local. Certaines fonctionnalités avancées sont payantes.

### Intégration de GA dans Drupal

Dans l'interface d'admin de Drupal, allez sur Extensions/Extend => Ajouter nouvelle extension (module).

Télécharger le module Google Analytics depuis l'url suivante: https://www.drupal.org/project/google_analytics ou copier l'url de téléchargement.

En fonction du choix, encoder l'url ou télécharger le module.

![capture](_readme-img/googleAnalytics/capture-09.png)

Activer le module.

![capture](_readme-img/googleAnalytics/capture-10.png)

Dans la page: admin/modules, activer le module en le sélectionnant et en cliquant sur installer.

![capture](_readme-img/googleAnalytics/capture-11.png)

Dans admin/config, la gestion de GA a été ajoutée.

![capture](_readme-img/googleAnalytics/capture-12.png)



Ouvrir la page admin/config/system/googleAnalytics

Se rendre dans GA et:

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi

Copier le code de suivi:

![capture](_readme-img/googleAnalytics/capture-06.png)

Coller le code dans Drupal dans la case prévue à cet effet et renseigner l'url du site. Il est possible de tester en local ou d'avoir des sous-domaines.

![capture](_readme-img/googleAnalytics/capture-13.png)



En bas de la page à gauche, cliquer sur 'Sauver la configuration'.

Dans admin/config/development/performance, il faudra nettoyer le chahe puis sauver.

![capture](_readme-img/googleAnalytics/capture-14.png)

### Intégration de GA sur Prestashop

Installer le module officiel: modules/modules et services => catalogue de modules => rechercher 'googleAnalytics" => installer

Il s'agit d'un module développé par Prestashop.

![capture](_readme-img/googleAnalytics/capture-05.png)

Ensuite: configurer

Se rendre dans GA et:

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi

Copier le code de suivi:

![capture](_readme-img/googleAnalytics/capture-06.png)

Et copier l'identifiant dans la case "ID de tracking Google Analytics".

![capture](_readme-img/googleAnalytics/capture-07.png)

Il est recommandé de sélectionner de **rendre les adresses IP anonymes** pour rester en règles avec la GDPR.

### Intégration de GA sur Shopify

Se rendre dans GA et:

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi

Copier le contenu de la partie encadrée:

![capture](_readme-img/googleAnalytics/capture-02.png)

Dans Shopify aller dans Boutique en ligne => Préférences.

Scroller jusqu'à 'Google Analytics' puis dans le champ 'Compte Google Analytics', copier le code provenant du site GA, puis cliquer sur enregistrer.

![capture](_readme-img/googleAnalytics/capture-08.png)

### Vérifier que GA est bien installé

Il est nécessaire d'utiliser un autre appareil pour se connecter au site que celui qui est utilisé pour consulter GA, par exemple un smartphone.

En effet,  GA va repérer que c'est la même machine utilisée et donc ne va pas comptabiliser la visite afin de ne pas prendre en compte les visites de la personne faisant l'audit du site web.

Si tout a bien fonctionné, l'on peut apercevoir notre connexion dans la rubrique temps réel / vue d'ensemble:

![capture](_readme-img/googleAnalytics/capture-15.png)

Si ce n'est pas le cas revoir les procédures d'intégration afin d'identifier ce qui n'a pas fonctionné.

Egalement il est utile de vérifier que toutes les pages du site qu'on veut auditer sont bien prises en compte.

## Lier GA à d'autres comptes

### Google Search Console

#### Créer un compte 

Par défaut GA mesure le trafic sur le site. La google search console va permettre de suivre le trafic en provenance du moteur de recherche Google.

Créer son compte: https://search.google.com/search-console

Pour des raisons de facilité, il est préférable que le compte Google utilisé pour l'inscription à ce service soit le même que celui pour l'inscription à GA. Dans le cas contraire il y aura une série de validations qui seront proposées pour lier les comptes.

Il est possible de créer une configuration pour tout un domaine.

Dans le cas du suivi d'un seul site, privilégier la seconde option, via préfixe de l'url. Il suffit d'introduite l'url du site à auditer. 

Ne pas oublier le 's' du 'https'. Car l'outil ne va pas convertir.



![capture](_readme-img/googleAnalytics/capture-16.png)

Si l'audit se fait sur le même site que celui de GA, la fenêtre suivante devrait apparaître.

Cliquer sur valider la propriété.

![capture](_readme-img/googleAnalytics/capture-17.png)

Si le site est différent, il sera proposé d'insérer à nouveau du code sur chaque page afin de vérifier que la personne souscrivant au service est bien le propriétaire du site (comme pour GA). Les deux services peuvent être utilisés indépendamment.

Au début il n'y aura aucune données et il faudra attendre quelques jours avant de les voir apparaitre.

#### Lier GA à Google Search Console

Le service ne sera pas lié automatiquement même s'il a été créé avec le même compte.

Il faut aller dans la partie administration (menu de gauche tout en bas), sélectionner 'tous les produits' et enfin 'search console'.

Cliquer sur 'Associer la Search Console'.

![capture](_readme-img/googleAnalytics/capture-18.png)



Puis cliquer sur 'Ajouter'.

![capture](_readme-img/googleAnalytics/capture-19.png)

Ensuite sélectionner l'url du site à associer (il pourrait y en avoir plusieurs dans la search console).

Cliquer sur enregistrer et confirmer une nouvelle fois dans le fenêtre modale qui s'ouvre ensuite.

![capture](_readme-img/googleAnalytics/capture-20.png)

Pour vérifier, retourner dans Administration / Tous les produits.

Search console devrait apparaître en haut. Cliquer sur 'Paramétrer l'association'.

La vue devrait être activée.

![capture](_readme-img/googleAnalytics/capture-21.png)



Pour vérifier et faire le suivi, depuis le dashboard: Acquisition / Search Console / Pages de destination.

![capture](_readme-img/googleAnalytics/capture-22.png)

Au début il n'y aura aucune données et il faudra attendre quelques jours avant de les voir apparaitre.

### Google Ads

#### Lier GA à Google Ads

Aller dans Acquisition / Google Ads / Campagnes, puis 'associer vos comptes'.

![capture](_readme-img/googleAnalytics/capture-24.png)

Les compte Google Ads associés au même compte utilisateur seront listées. Sélectionner les Campagnes à auditer.

![capture](_readme-img/googleAnalytics/capture-25.png)

Créer un nom pour l'association, activer 'Toutes les données du site web'.

Puis 'Associer les comptes'. Cela prendra 24h avant d'être activé.

![capture](_readme-img/googleAnalytics/capture-26.png)

### Donner l'accès à d'autres utilisateurs

Permet de donner des accès au compte GA à un collaborateur, un associé, un client, un prestataire...

Il est possible de donner des accès à plusieurs niveaux: Compte, Propriété, Vue.

- Compte: accès à toutes les fonctionnalités, propriétés et vues.

- Propriété: accès à la gestion d'un site en particulier.
- Vue: permet de sélectionner juste une certaine partie des statistiques visible pour un utilisateur donné. On peut créer plusieurs type vues.

Dans administration.

![capture](_readme-img/googleAnalytics/capture-27.png)

Quel que soit le niveau choisi, c'est le même schéma.

On peut ajouter un ou plusieurs utilisateurs.



![capture](_readme-img/googleAnalytics/capture-28.png)

Ensuite, on peut affiner les droits.

![capture](_readme-img/googleAnalytics/capture-29.png)

Lorsque l'on donne les droits à un utilisateur, ne pas oublier de supprimer cet utilisateur si celui-ci n'est pas plus habilité à accéder aux données (fin de contrat, départ de collaborateur...).

![capture](_readme-img/googleAnalytics/capture-30.png)

## Comment analyser les données?

### Quelles sont les types de données qu'il est possible d'analyser?

- L'audience: quel est le profil de nos visiteurs?
- Comparer les différents canaux d'acquisition de trafic
- Analyser le comportement pour améliorer l'expéreince utilisateur

### Glossaire et définitions

**Engagement / taux d'engagement**: L'engagement en marketing dépend de plusieurs paramètres, il correspond à une notion qui désigne les prédispositions du consommateur à interagir avec un élément marketing ou une marque. Internet favorise grandement les interactions entre les consommateurs et les marques, on compte ainsi différentes formes d'engagements de la part des internautes. Le client potentiel peut s'engager suite à la réception d'un message publicitaire visuel, d'une newsletter, d'un e-mail, directement auprès de la marque ou via les réseaux sociaux par exemple. Les professionnels mesurent ensuite le taux d'engagement. On peut considérer qu'il existe plusieurs niveaux d'engagement : l'engagement simple, qui dénote un intérêt pour une marque, l'engagement pour l'achat, qui entraîne le consommateur à se renseigner davantage sur un produit spécifique et l'engagement viral qui concerne les consommateurs satisfaits, communiquant volontiers sur leurs marques favorites. L'engagement permet à la fois de fidéliser la clientèle, d'accroître la notoriété et d'échanger plus facilement avec les consommateurs.

**Session**: une session représente la visite d'un internaute (utilisateur) sur votre site web. La session englobe toutes l'activité que l'internaute effectue sur notre site et cette activité est limitée dans le temps. Après 30 minutes d'inactivité, la session prend fin. Si l'utilisateur reprend son activité après ces 30 minutes, cela sera considéré comme une seconde session. Un utilisateur peut donc avoir plusieurs sessions.

**Utilisateur**: un utilisateur est un internaute qui utilise notre site web. Ce dernier peut être assimilé à plusieurs sessions s'il a été inactif plus de 30 minutes. Un utilisateurs utilisant des appareils différents pour se connecter au site sera considéré comme plusieurs utilisateurs différents.

**Page vue**: une page vue représente le nombre de fouis qu'un visiteur a vu une page spécifique. Cela ne veut pas dire qu'il a vu toute la page ou qu'il l'a concidérée avec intérêt, mais qu'elle a été gée dans le navigateur. Ainsi le nombre de pages vues représentera le nombre total de pages consultées sur notre site web. Si une même page est vue deux fois, cela sera considéré comme deux pages vues.

**Page par session**: une page par session représente le nombre moyen de pages vues au cours d'une même session. Ainsi, si  utilisateur visite notre site web et consulte plusieurs pages différentes, il s'agira du nombre de pages par session. Sur GA, on retrouve donc une moyenne deges visitées par session, et ce, par tous les utilisateurs.

**Durée moyenne des sessions**: une session représente la période pendant laquelle un utilisateur est actif sur un site web. Ainsi la durée moyenne des sessions donne une idée du temps passé par session en moyenne sur notre site web. Permet de mesurer le taux d'engagement (engagement Rate).

**% de nouvelles sessions**: le pourcentage de nouvelles sessions représente le pourcentage des nouvelles visites sur notre site, des utilisateurs qui le consultent pour la première fois. De cette manière l'on peut déterminer si l'on attire des utilisateurs qui visitent notre site web pour la première fois ou, si à l'inverse l'on attire des utilisateurs qui ont déjà visité notre site et y reviennent.

**Taux de rebond**:  le taux de rebond représente le pourcentage de visites pendant lesquelles l'utilisateur a quitté le site web dès sa page d'arrivée, sans même interagir avec la page en question (bien que l'utilisateur ait peut-être lu toute la page). Ce n'est pas alarmant car il est normal qu'un utilisateur constate qu'il n'est pas sur un site qui correspond à sa recherche et s'en aille. Cependant si un taux de rebond est élevé, c'est préoccupant. Cela signifie que la page en question pourrait peut-être être améliorée ou encore, que la campagne qui a mené l'utilisateur sur cette page n'était pas assez claire.

**Canaux**: les canaux d'acquisition sont les sources du trafic de notre site (moteur de recherche, référencement naturel...). En les analysant, nous pouvons les regrouper par segments d'activités marketing: trafic provenant des réseaux sociaux, du SEO, emailing, campagnes publicitaires...

**Trafic organique**: le trafic organique est celui provenant des résultats naturels des moteurs de recherche comme Google, Bing, Yahoo... Ces résultats sont liés au référencement naturel SEO de notre site.

**SEO / Référencement nature**l:  SEO est l'acronyme de Search Engine Optimization et peut être défini comme l'art de positionner un site, une page web ou une application dans les premiers résultats naturels des moteurs de recherche. En français, le SEO est désigné par le terme de référencement naturel. Sur les requêtes visées, la position obtenue se doit essentiellement d'être en première page, car lors de la majeure partie des requêtes, c'est la seule page consultée. Désormais, il peut même s'agir d'obtenir la position zéro. La position zéro est un résultat de recherche positionné devant le premier résultat naturel sur Google. Elle est matérialisée par un bloc contenant les éléments d’une page web répondant à une question posée, on parle d’ « extrait optimisé ou featured snippet  ». La position zéro permet donc à Google de répondre directement à une question posée par un internaute, le plus souvent lors d’une recherche vocale effectuée sur Smartphone. Les termes position #0 ou ranking #0 désignent également une position zéro.

**Trafic référent**: le trafic référent est celui qui provient d'autres sites internets qui ne sont pas des réseaux sociaux (autres sites, blogs qui parlent de notre site et fournissent son lien).

**Trafic social**: le trafic social est celui provenant des réseaux sociaux (Facebook, Twitter, Instagram, linkedIn, Pinterest) et qui n'est pas associé à une publicité, c'est un trafic organique. Il peut cependant être organisé avec la collaboration d'influenceurs. Il permet de voir quel réseau social nous envoie le plus de visiteurs.

**Trafic payant / paid trafic**:  le trafic payé est celui obtenu via le réseau de recherche Google Ads, Bing Ads ou d'autres moteurs de recherche au moyen d'une campagne de coûts par clic (CPC). Cela inclus également les campagnes marketingpublicitaires payantes sur les réseaux sociaux.

**Trafic direct**: le trafic direct est celui de toutes les sessions qui proviennent d'un utilisateur qui a saisi l'adresse de notre site directement dans la barre de recherche de son navigateur ou qui l'a placé dans sa sections 'favoris'. Il s'agit souvent d'internautes récurrents qui connaissent bien notre site.

**Événements**: les événements représentent les interactions d'un utilisateur avec un contenu. Il existe plusieurs types d'actions ou d'interactions que l'on peut suivre tels que les téléchargements, les lectures vidéo, les clics sur une annonce, remplir un formulaire, etc.

**Conversion**:  une conversion représente une action réalisée en ligne ou hors ligne et qui est primordiale pour atteindre les objectifs de l'entreprise. il s'agit par exemple d'un achat dans la boutique, une demande de formulaire de devis... Mais cela peut être plus pointu, comme fidéliser le visiteur à un service en démonstartion de façon récurrente et prolongée.

**Taux de conversion**: pourcentage de visiteurs ayant fait une conversion. Le taux de conversion sur GA est intimement lié aux objectifs de conversion. En effet, ce taux permet de connaître le pourcentage de visites ayant abouti à une conversion et ce, en lien avec un objectif configuré.

**RGPD / GDPR**: La nouvelle législation européenne RGPD a pour vocation de mieux protéger la vie privée et la confidentialité des citoyens. RGPD signifie Règlement général sur la protection des données et en anglais GDPR pour European General Data Protection Regulation.

Le but est de renforcer la protection de la vie privée du citoyen en édictant des règles uniformes à l'échelle de l'Union européenne : 

- le citoyen dispose d'un meilleur contrôle sur l'utilisation de ses données personnelles
- le RGPD instaure un cadre légal clair, afin que les entreprises sachent comment s'y prendre pour garantir la confidentialité

Toutes les organisations, les entreprises et les instances publiques qui collectent et traitent les données personnelles de citoyens européens doivent appliquer le RGPD, quel que soit leur pays d'implantation.

### Comment analyser les données en fonction d'une période donnée?

Lorsqu'on analyse nos données, c'est pour une plage de dates. Il y a toujours une date de début d'analyse et une date d'analyse.



Par défaut GA nous affiche la dernière semaine, ml est possible de définir sa propre plage de dates.

![capture](_readme-img/googleAnalytics/capture-31.png)

L'on peu ensuite affinner en affichant le graphe par heures / jours / semaines / ou mois.

![capture](_readme-img/googleAnalytics/capture-32.png)



## Analyser l'audience et acquérir de nouveaux clients

![capture](_readme-img/googleAnalytics/capture-33.png)



### La vue d'ensemble de notre audience

C'est le rapport par défaut de l'audience reçue par rapport à une plage donnée.

Sur le graphe on peut voir précisément le nombre de visiteurs pour un jour donné.

Le graphe en camembert à droite montre la proportion de nouveau visiteurs et la proportion de visiteurs qui reviennent.

![capture](_readme-img/googleAnalytics/capture-34.png)

En dessous du graphe se trouvent des données chiffrées. Un rappel des notions s'affiche en info-bulle lorsque l'on passe la souris sur les intitulés.

![capture](_readme-img/googleAnalytics/capture-35.png)

D'autres données sont aussi disponible dans la vue d'ensemble, comme les données démographiques, des informations sur le système utilisé par le visiteur et des informations relative au mobile s'il utilise ce type de système.

![capture](_readme-img/googleAnalytics/capture-36.png)

### Analyser les données démographiques

L'onglet avec les données démographiques permet accéder aux données d'âge et de sexe des visiteurs.

Il faut l'activer. A noter qu'il est important de mettre à jour les conditions d'utilisation du site audité et informer les utilisateurs selon les règles en vigueur, notamment la **GDPR**.

![capture](_readme-img/googleAnalytics/capture-37.png)



#### Age et sexe

Cela permet de voir le public qui visite le site correspond bien au public ciblé.

![capture](_readme-img/googleAnalytics/capture-38.png)

### Analyser les données géographiques

L'on peut recueillir les données linguistiques et la zone géographique des visiteurs.

#### Données linguistiques

Les données linguistiques correspondent à la langue d'installation du système d'exploitation du visiteur.

Les données ne sont donc pas toujours représentatives car un visiteur peut être par exemple francone mais utiliser un système dans une autre langue (expatrié, depuis une société internationnale où tous les systèmes d'exploitations sont en anglais).

Egalement ces données peuvent attirer l'attention sur certaines annomalies, par exemple de nombreuses visites dans une langues qui ne correspond pas du tout à celle du site, il peut s'agir de bots, des logiciels opérant de manière autonomes et automatiques pa avec de mauvaises intentions (vols de données).  

Les données linguistiques doivent donc être recoupées avec les données de la zone géographique.

Concernant les codes ISO, il s'agit de la langue puis du pays, par exemple:

- fr-fr: français de France
- fr-be: français de Belgique

- en-gb: anglais du Royaume-Uni
- en-us: anglais des USA

![capture](_readme-img/googleAnalytics/capture-39.png)

#### Données de la zone géographique

Les données de la zone géographique permettent d'afficher la provenance des visiteurs.

Il est possible de sélectionner une dimension principale: pays, ville, continent ou sous-continent.

Il peut être important de vérifier l'origine des visiteurs car dans certains cas cela peut influencer leur comportement.

Par exemple un site de vente en ligne français qui ne vend pas en dehors de la France, il faudra prendre en compte les visteurs d'autres pays dans l'analyse des taux de conversion, de rebonds...

L'on peu affiner avec d'autres critères faisant partie de la dimension secondaire permettant d'ajouter des filtres.

![capture](_readme-img/googleAnalytics/capture-40.png)

Exemple de données affichées par ville et si oui ou non, la visite provient d'un appareil mobile.

![capture](_readme-img/googleAnalytics/capture-41.png)

### Engagement des visiteurs

#### Visiteurs nouveaux / connus

L'étude des comportements permet de visualiser les visiteurs qui sont nouveaux sur le site et ceux qui sont déjà venus.

Dans les sites d'e-commerce il est important d'avoir un nombre élevé de 'returning visitors'. dans le cas de la générations de 'leads' c'est l'inverse, il est bon d'avoir beaucoup de nouveaux venus.

![capture](_readme-img/googleAnalytics/capture-42.png)

#### Fréquence et récence 

La section fréquence et récence permet de voir le nombre de sessions faites par des utilisateurs et leur récurrence ainsi que le nombre de pages totales visitées (les visites répétées d'un internaute sur une même page sont prises en compte).

Dans l'exemple suivant, 44 utilisateurs n'ont fait qu'une seule session (visite).

Mais 5 utilisateurs ont fait entre 9 et 14 sessions.

![capture](_readme-img/googleAnalytics/capture-43.png)

#### Engagement

##### Segment de durée de la session

L'engagement via 'Segment de durée de la session' permet de voir la durée des différentes sessions et le nombre total de pages vues en fonction des durées.

Dans l'exemple suivant, 23 sessions ont duré 0 à 10 secondes pour un total de 24 pages vues.

Mais, 9 session ont duré plus de 1801 secondes pour un total de 702 pages vues.

![capture](_readme-img/googleAnalytics/capture-44.png)

##### Nombre de pages

Il s'agit du nombre de pages vues en fonction des sessions.

Dans l'exemple suivant, 22 visiteurs n'ont vu qu'une seule page (pour un total de 22 pages vues en toute logique).

Mais, 9 visiteurs ont vu plus de 20 pages, pour un total de pages vues égal à 709.

![capture](_readme-img/googleAnalytics/capture-45.png)

A noter que si la première entrée indique "<1", il s'agit des visiteurs ayant quitté le site avant qu'il soit chargé (parce qu'ils se rendent compte qu'ils se sont trompés, parce que le site est trop lent à charger...). Si le nombre est anormalement élevé il faut en rechercher la cause (par exemple est-ce que le site ne connait pas un problème avec son serveur d'hébergement).

### Technologie utilisée par les visiteurs

#### Navigateurs et OS

Permet de voir quels systèmes les visiteurs utilisent et d'afficher des données techniques: navigateur, système d'exploitation, résolution d'écran, couleurs d'écran...

Ces données sont très importantes pour les développeurs des sites car cela permet de connaître les configurations les plus utilisées et d'adapter leur technologies et leur test pour s'assurer que tout fonctionnera correct dans ces configurations.

![capture](_readme-img/googleAnalytics/capture-46.png)

#### Réseau

Affichait à l'origine les nom du provider du visiteur, voire le nom de l'entreprise d'où provenait la connexion.

Cela est désactivé (not-set), pour rester en concordance avec la GDPR.

![capture](_readme-img/googleAnalytics/capture-47.png)

### Appareils utilisés par nos visiteurs

Cela permet de voir depuis quel type d'appareil l'utilisateur provient.

L'on peut ajouter d'autres filtres via la dimension secondaires.

Il est normal de constater un déclin des tablettes qui ont fait place aux smartphones de grande taille.

![capture](_readme-img/googleAnalytics/capture-48.png)

La vue détaillées (Appareils) permet d'avoir des informations sur les marques et les modèles d'appareils utilisés, mais aussi le système d'exploitation...

Le fournisseur de service est désactivé (not-set), pour rester en concordance avec la GDPR.

Ces données sont très utiles pour les développeurs également car cela permet de mieux cibler les développements.

![capture](_readme-img/googleAnalytics/capture-49.png)



## Comparer les différents canaux d'acquisition de trafic

### Vue d'ensemble des canaux d'acquisition

Comment arrive notre audience sur notre site?

Les principaux canaux sont listés sur le camembert:

- Organic search: les moteurs de recherche
- Direct: via favoris ou en tapant l'url directement
- Referal: ce qui vient d'un autre site via un lien (sponsorisé ou non)
- Social: via les réseaux sociaux
- Email: via des emailing avec trackers (campagnes)

Il est conseillé d'équilibrer les canaux d'acquisition. En effet un site qui par exemple ne tablerait que sur la recherche organique et qui pour certaines raisons se verrait désindexé perdrait dès lors tout son trafic.

Il faut donc tâcher de ne pas dépasser les 50% pour la recherche organique et investir dans différents canaux.



![capture](_readme-img/googleAnalytics/capture-50.png)

### Impact des réseaux sociaux sur notre trafic

Dans la sections "Canaux" sont affichés les canaux d'acquisition par types:



![capture](_readme-img/googleAnalytics/capture-51.png)

A noter que GA n'affichera que les canaux qui ont été utilisés lors de la période sélectionnée.

On peut voir par exemple dans "Social" les différents médias sociaux et évaluer l'impact et l'efficacité des différentes campagnes organisées sur ceux-ci.

![capture](_readme-img/googleAnalytics/capture-52.png)

### Où en est notre optimisation de notre référencement naturel (SEO)?

![capture](_readme-img/googleAnalytics/capture-53.png)

Dans cette vue on peut voir la liste des différents moteurs de recherche utilisés.

Google étant le plus utilisé, il est important de la voir apparaître en premier, sinon cela veut dire que le site n'a pas été optimisé au niveau SEO.

![capture](_readme-img/googleAnalytics/capture-54.png)

Pour avoir des données plus poussées, il faudra se rendre dans la "Search console".

On pourra y trouver les nombre de fois où le site a été affiché dans google suite à certaines requêtes.

- Clicks: le nombre de clicks vers le site suite à une recherche

- Impressions: le nombre de fois que le site est apparu dans Google suite à une recherche (mais sans qu'il y ait nécessairement de click)
- CRT: Taux de clics = Clics/Impressions * 100.
- Position moyenne: Il s'agit du classement moyen des URL du site pour les requêtes. 

![capture](_readme-img/googleAnalytics/capture-55.png)

On peut avoir aussi le détail par pages du site dans la rubrique "Pages de destination".

![capture](_readme-img/googleAnalytics/capture-56.png)



### Quels sites nous amènent du trafic?

![capture](_readme-img/googleAnalytics/capture-57.png)

Cela permet de voir quels sont les sites qui proposent un lien vers notre site.

Cela peut être utile pour créer des campagnes et des partenariats avec les sites qui ont des visiteurs qui pourraient également être intéressés par nos services.

![capture](_readme-img/googleAnalytics/capture-58.png)

### Liens directs

![capture](_readme-img/googleAnalytics/capture-59.png)

Il s'agit des utilisateurs qui ont directement tapé l'url dans la barre de recherche ou qui ont mis le site en favoris.

Ces données sont plus difficiles à analyser et il faut les recouper avec d'autres informations. Par exemple pour un site de commerce en ligne, peut-être que les visiteurs sont des habituées et on l'adresse du site en favori.

### Analyser l'impact des campagnes publicitaires avec Google Ads

Permet de vérifier l'efficacité des campagnes Google Ads et d'ajuster sa stratégie en fonction de sa rentabilité en terme d'acquisitions.

![capture](_readme-img/googleAnalytics/capture-60.png)

## Analyser le comportement pour améliorer l'expérience utilisateur



## Liens utiles / sources

- [Formation Udemy: Tout comprendre de Google Analytics et analyser son trafic !](https://www.udemy.com/course/googleAnalytics-trafic/)
- [Commission européenne: General Data Protection Regulation (EU GDPR)](https://ec.europa.eu/info/law/law-topic/data-protection_fr)
- [ISO 3166 - Codes des noms de pays](https://www.iso.org/fr/iso-3166-country-codes.html)
- [ISO 639 - Codes des langues](https://www.iso.org/fr/iso-639-language-codes.html)
- [emarketing.fr](https://www.e-marketing.fr/)
- [Définitions marketing](https://www.definitions-marketing.com/)
- [anthedesign](https://www.anthedesign.fr/)































