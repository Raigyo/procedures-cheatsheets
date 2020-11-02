# Tout comprendre de Google Analytics et analyser son trafic !



![](_readme-img/google-analytics/ga-logo.png)



## Pourquoi utiliser Google Analytics (GA) ?

- Suivre l'évolution de sa stratégie d'acquisition de trafic: d'où viennent les utilisateur, par quel canal...
- Comprendre qui sont nos visiteurs, leur comportement: est-ce que les cibles sont les bonnes, doit-on ajuster la stratégie...
- Améliorer le taux de conversion (achat, génération de leads/prospects) de son site internet: d'où viennent les leads, choix des canaux de diffusion en fonction du retour sur investissement, analyser les moyens de conversion depuis un même canal (publicité, partages naturels, repartages...)

## Pour qui est fait GA?

Pour tout type d'entreprise et même toute personne voulant suivre son trafic (blog, portfolio...).

## Créer son compte

Un compte Google est nécessaire: https://analytics.google.com/

Un même compte peut permettre de tracker plusieurs sites. L'on peut ajouter des propriétés par après (une propriété = un produit: site, application mobile) .

Bien veiller à sélectionner le bon fuseau horaire.

## Intégration de GA sur son application web HTML

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi



![](_readme-img/google-analytics/capture-01.PNG)

Copier la partie encadrée sur **toutes** les pages du site web, dans la balise head, en premier lieu:

![](_readme-img/google-analytics/capture-02.PNG)

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

## Intégration de GA dans Wordpress

Peut se faire facilement via une extension.

Dans la partie administration du site, sélectionner plugins/extensions => ajouter.

Dans les mots clés, une recherche sur 'google-analytics'.

Il existe plusieurs plugins. Un des plus performants est celui de [Monster Insights](![](_readme-img/google-analytics/capture-01.PNG)).

![](_readme-img/google-analytics/capture-03.PNG)

Après l'installation il faut l'activer:

![](_readme-img/google-analytics/capture-04.PNG)

Suivre les instructions de l'assistant.

Il faut le lier au compte Google sur lequel a été créé la propriété.

Pour des raisons évidentes, le plugin ne fonctionnera pas en local. Certaines fonctionnalités avancées sont payantes.

## Intégration de GA dans Drupal

Dans l'interface d'admin de Drupal, allez sur Extensions/Extend => Ajouter nouvelle extension (module).

Télécharger le module Google Analytics depuis l'url suivante: https://www.drupal.org/project/google_analytics ou copier l'url de téléchargement.

En fonction du choix, encoder l'url ou télécharger le module.

![](_readme-img/google-analytics/capture-09.PNG)

Activer le module.

![](_readme-img/google-analytics/capture-10.PNG)

Dans la page: admin/modules, activer le module en le sélectionnant et en cliquant sur installer.

![](_readme-img/google-analytics/capture-11.PNG)

Dans admin/config, la gestion de GA a été ajoutée.

![](_readme-img/google-analytics/capture-12.PNG)



Ouvrir la page admin/config/system/google-analytics

Se rendre dans GA et:

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi

Copier le code de suivi:

![](_readme-img/google-analytics/capture-06.PNG)

Coller le code dans Drupal dans la case prévue à cet effet et renseigner l'url du site. Il est possible de tester en local ou d'avoir des sous-domaines.

![](_readme-img/google-analytics/capture-13.PNG)



En bas de la page à gauche, cliquer sur 'Sauver la configuration'.

Dans admin/config/development/performance, il faudra nettoyer le chahe puis sauver.

![](_readme-img/google-analytics/capture-14.PNG)

## Intégration de GA sur Prestashop

Installer le module officiel: modules/modules et services => catalogue de modules => rechercher 'google-analytics" => installer

Il s'agit d'un module développé par Prestashop.

![](_readme-img/google-analytics/capture-05.PNG)

Ensuite: configurer

Se rendre dans GA et:

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi

Copier le code de suivi:

![](_readme-img/google-analytics/capture-06.PNG)

Et copier l'identifiant dans la case "ID de tracking Google Analytics".

![](_readme-img/google-analytics/capture-07.PNG)

Il est recommandé de sélectionner de **rendre les adresses IP anonymes** pour rester en règles avec la GDPR.

## Intégration de GA sur Shopify

Se rendre dans GA et:

Dans le menu de gauche: Administration (icone engrenage)

Menu central: propriété => Informations de suivi => Code de suivi

Copier le contenu de la partie encadrée:

![](_readme-img/google-analytics/capture-02.PNG)

Dans Shopify aller dans Boutique en ligne => Préférences.

Scroller jusqu'à 'Google Analytics' puis dans le champ 'Compte Google Analytics', copier le code provenant du site GA, puis cliquer sur enregistrer.

![](_readme-img/google-analytics/capture-08.PNG)

## Vérifier que GA est bien installé

## Liens utiles / sources

- [Formation Udemy](https://www.udemy.com/course/google-analytics-trafic/)































