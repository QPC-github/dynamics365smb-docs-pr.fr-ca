---
title: "Configuration des modèles d'API | Microsoft Docs"
description: "Décrit la procédure à suivre pour configurer des modèles d'API pour Dynamics 365 Business Central."
services: project-madeira
documentationcenter: 
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: API templates, configuring templates
ms.date: 05/16/2018
ms.author: solsen
ms.translationtype: HT
ms.sourcegitcommit: ad1b888d475c0523c5a905e804a3f89ab4531b28
ms.openlocfilehash: 1695a6950dabc1b2f0a2f85ad9e0c565012c92e1
ms.contentlocale: fr-ca
ms.lasthandoff: 05/17/2018

---

# <a name="configuring-api-templates"></a>Configuration des modèles d'API
La bibliothèque d'API de [!INCLUDE[d365fin_md](includes/d365fin_md.md)] fournit une représentation simplifiée des entités sous-jacentes. Toutes les propriétés de l'application ne sont pas exposées via l'API associée. La fenêtre **Configuration API** permet de définir des modèles qui sont utilisés pour renseigner les propriétés vides d'une entité lorsque vous créez une action REPORTER via l'API. 

Par exemple, si un modèle de configuration est défini pour l'entité article, lorsqu'un nouvel enregistrement d'article est créé via l'API de l'article, les propriétés du nouvel article qui ne sont pas définies dans l'appel de l'API sont remplies à partir du modèle sélectionné. Si, par exemple, aucune valeur n'est définie pour le champ **Groupe de report de produit** via l'API, mais qu'une valeur est définie dans le modèle sélectionné, la valeur du groupe de report définie dans le modèle est appliquée au nouvel article. 

## <a name="setting-up-the-entity-template"></a>Configuration du modèle d'entité
Pour utiliser les modèles avec la bibliothèque d'API, vous devez d'abord configurer et définir les propriétés des modèles. Vous pouvez configurer ces modèles dans la fenêtre **Modèles configuration**. Pour plus d'informations, voir [Préparer la migration des données client](admin-use-templates-to-prepare-customer-data-for-migration.md). 

## <a name="assign-the-template-to-an-api"></a>Affecter le modèle à une API

Pour affecter un modèle à une API, vous devez effectuer les actions suivantes.

1. Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration API**, puis choisissez le lien associé.
2. Choisissez **Nouveau**, puis la valeur **Ordre** pour l'enregistrement.  
Si plusieurs modèles sont sélectionnés pour une API (Code page), les modèles sont appliqués dans l'ordre défini dans la colonne **Ordre**.   
Lorsque chaque modèle est appliqué, les valeurs de champ définies dans le modèle sont uniquement appliquées aux champs sans valeur déjà définie, soit explicitement dans l'API ou dans un modèle précédemment appliqué dans l'ordre. 
3. Sélectionnez une valeur **Code page**.  
Il s'agit de la page de l'API à laquelle le modèle est appliqué. La recherche **Code page** fournit la liste de toutes les API disponibles dans la bibliothèque.
4. Sélectionnez une valeur dans le champ **Code modèle**.  
Le code modèle est le code du modèle qui a été défini dans la fenêtre **Modèles configuration**. Les valeurs de modèle définies sont appliquées à l'API. 
5. Dans le champ **Conditions**, spécifiez le modèle à appliquer.  
Le modèle défini est appliqué à un nouvel enregistrement créé via l'API si, et seulement si, les conditions définies dans le champ **Conditions** sont remplies par les valeurs déjà définies pour la nouvelle instance de l'entité.

## <a name="see-also"></a>Voir aussi
[Documentation sur les API](/dynamics-nav/fin-graph)  
[Développement d'applications connectées pour [!INCLUDE[d365fin_md](includes/d365fin_md.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)  
[Activation des API](/dynamics-nav/enabling-apis-for-dynamics-nav)  
[Points de terminaison des API](/dynamics-nav/endpoints-apis-for-dynamics)  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)