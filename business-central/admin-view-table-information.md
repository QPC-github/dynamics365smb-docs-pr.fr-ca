---
title: Afficher les informations sur les tables
description: Découvrez comment afficher des informations sur les tables de base de données dans Business Central.
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 8700
ms.date: 08/23/2022
ms.author: jswymer
---

# <a name="viewing-table-information" />Affichage d'informations sur les tables

La page **Informations sur les tables 8700** fournit des informations sur le nombre d’enregistrements dans toutes les tables système et métier dans [!INCLUDE[prod_short](includes/prod_short.md)], et la quantité de données que chaque table contient.

Ces informations sont utiles pour résoudre les problèmes de performances, car nous allons voir la répartition de la taille des données entre les tables.

## <a name="viewing-table-information" />Affichage d'informations sur les tables

Pour ouvrir cette page, sélectionnez l’icône ![Rechercher une page ou un rapport.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche") entrez **Informations table**, puis choisissez le lien associé.

Le tableau suivant décrit les informations fournies pour chaque table :

|Colonne|Description|
|------|-----------|
|Nom de la compagnie|Nom de la compagnie, le cas échéant, à laquelle appartient la table.|
|Nom de table|Nom de la table.|
|N° table|Code de la table.|
|N° d'enregistrements|Nombre total d'enregistrements stockés dans la table.|
|Taille enregistrement|La taille d'enregistrement moyenne en Ko/enregistrement. La valeur est calculée à l'aide de la formule suivante : 1024 (Taille)/Nbre d’enregistrements). |
|Taille (Ko)|Espace total occupé par la table dans la base de données. La valeur indiquée est la somme des valeurs des champs Taille des données et Taille de l’index.|
|Taille des données (Ko)|Espace occupé par les données de la table dans la base de données.|
|Taille de l’index (Ko)|Espace occupé par les index de la table (clés) dans la base de données.|
|Compression|Type de compression, **Ligne**, **Page**, ou **Aucun**, qui est appliqué à la table dans la base de données. Pour plus d’informations, consultez [Compression de données](/sql/relational-databases/data-compression/data-compression?).|

> [!NOTE]
> Si vous supprimez des données dans une table, [!INCLUDE[prod_short](includes/prod_short.md)] lance plusieurs processus en arrière-plan pour s’assurer que tout est nettoyé dans votre base de données. Les valeurs de la page Informations sur la table ne seront pas mises à jour tant que ces processus ne seront pas terminés, ce qui peut prendre un certain temps. Le temps d’attente peut varier en fonction de la taille de votre base de données.

## <a name="see-also" />Voir aussi

[Inspection des pages](across-inspect-page.md)  
[Articles sur les performances pour les développeurs](/dynamics365/business-central/dev-itpro/performance/performance-developer)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
