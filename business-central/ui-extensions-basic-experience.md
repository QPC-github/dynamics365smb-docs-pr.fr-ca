---
title: Extension d’expérience de base | Microsoft Docs
description: Cette extension est une alternative modernisée à Microsoft Dynamics C5.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'C5, financials, extension'
ms.search.form: '20600,'
ms.date: 04/01/2021
ms.author: bholtorf
---

# <a name="the-basic-experience-extension" />Extension d’expérience de base

Si vous utilisez Microsoft Dynamics C5, les partenaires Microsoft peuvent vous aider à effectuer la transition vers une solution plus moderne basée sur [!INCLUDE[prod_short](includes/prod_short.md)], afin que vous puissiez continuer à profiter des mêmes fonctionnalités rationalisées que Dynamics C5.

Cette extension est destinée aux petites entreprises et peut prendre en charge jusqu’à trois utilisateurs. Si vous avez besoin de plus d’utilisateurs, vous devez passer à une licence [!INCLUDE[prod_short](includes/prod_short.md)] et désinstallez cette extension.

> [!NOTE]
> À partir de maintenant, cette extension n’est disponible que pour les clients au Danemark et en Islande.

## <a name="whats-available" />Ce qui est disponible

Le tableau suivant décrit les fonctionnalités disponibles si vous installez l’extension d’expérience de base.

|Aire  |Fonctionnalité  |
|---------|---------|
|**Grand livre** |Finance de base, rapports financiers, immobilisations, gestion bancaire, rapprochement bancaire, paiements, prélèvement, dimensions, devises multiples, budgets, flux de travail, gestion de documents/OCR, consolidation, compagnies illimitées|
|**Comptabilités client/Ventes** |Comptabilité client de base, facturation des ventes, escomptes sur les ventes, tarification, taxe de vente, gestion des contacts |
|**Comptabilité fournisseur/Achats** |Comptabilité fournisseur de base, Facturation des achats |
|**Gestion de projets** |Projets, Tarification de projet, Feuilles de temps, Affectation, Tâches, Ressources |
|**Inventaire** |Inventaire de base, Substitutions d’articles, Références croisées d’articles |

## <a name="getting-started" />Mise en route

Cette extension est un peu différente de la plupart des autres, et vous aurez besoin de l’aide d’un partenaire Microsoft pour l’installer et la configurer. Juste pour que vous sachiez à quoi vous attendre, voici une vue d’ensemble de ce que fera le partenaire Microsoft.

1. Créer un abonné [!INCLUDE[prod_short](includes/prod_short.md)]. Il peut s’agir d’une version d’essai ou d’une version CSP.
2. Ajoutez au moins un utilisateur affecté à une licence d’expérience de base dans votre compte Azure Active Directory.
3. Supprimez toutes les compagnies, y compris l’exemple de compagnie Cronus.
4. Créez une compagnie qui ne contient aucun exemple de données ou de configuration.
5. Ajoutez le package **Démo RapidStart**. <!--what does the package contain?-->
6. Téléchargez et installez l’extension d’expérience de base à partir de AppSource.

## <a name="migrating-data" />Migration des données

Importez vos données Dynamics C5. Une fois que votre partenaire Microsoft a installé l’extension d’expérience de base, vous aurez une compagnie vide. Un moyen simple de déplacer vos données de Dynamics C5 vers l’expérience de base consiste à utiliser l’extension de migration de données C5, incluse dans [!INCLUDE[prod_short](includes/prod_short.md)]. L’extension migre les clients, les fournisseurs, les articles et vos comptes GL et leurs écritures.

## <a name="see-also" />Voir aussi .

[Extension C5 Data Migration](ui-extensions-c5-data-migration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
