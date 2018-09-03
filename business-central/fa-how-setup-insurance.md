---
title: "Paramétrer l'assurance immo.| Microsoft Docs"
description: "Configurez certaines informations générales d'assurance ainsi qu'une fiche assurance par police pour gérer la couverture d'assurance des immobilisations."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: policy, coverage
ms.date: 06/02/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: e7dcdc0935a8793ae226dfc2f9709b5b8f487a62
ms.openlocfilehash: ed03191f683b1b1f9f60351712d51b97ad53e98e
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-fixed-asset-insurance"></a>Configurer une assurance immobilisation
Pour gérer la couverture d'assurance des immobilisations, vous devez tout d'abord configurer certaines informations générales d'assurance ainsi qu'une fiche assurance par police.

## <a name="to-set-up-general-insurance-information"></a>Pour définir des informations générales relatives aux assurances
Pour utiliser les fonctions d'assurance dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez définir certaines informations générales relatives aux assurances.  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Paramètres immobilisations**, puis sélectionnez le lien connexe.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-set-up-insurance-types"></a>Pour définir des types d'assurance
Vous pouvez regrouper vos polices d'assurance en catégories (assurances contre le vol, assurances incendie, etc.). Les types d'assurance sont utilisés sur la fiche assurance.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Types assurance**, puis sélectionnez le lien connexe.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-insurance-cards"></a>Pour définir des fiches assurance
Vous pouvez rassembler des informations sur chaque police d'assurance dans la fiche assurance.  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Assurance**, puis sélectionnez le lien connexe.  
2. Dans la fenêtre **Assurance**, sélectionnez l'action **Nouveau** pour créer une fiche assurance.  
3. Renseignez les champs selon vos besoins.

## <a name="to-set-up-insurance-journal-templates"></a>Pour configurer des modèles journal assurance
[!INCLUDE[d365fin](includes/d365fin_md.md)] crée automatiquement un modèle feuille assurance la première fois que vous ouvrez la fenêtre **Feuille assurance**. Vous pouvez cependant définir d'autres modèles feuille. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Modèles feuille assurance**, puis sélectionnez le lien connexe.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-insurance-journal-batches"></a>Pour définir des lots journal assurance
Vous pouvez configurer des lots dans un modèle journal assurance. Les valeurs du lot journal servent de valeurs par défaut si les champs ne sont pas renseignés sur les lignes journal. Pour en savoir plus, voir [Utiliser des feuilles comptabilité](ui-work-general-journals.md)  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Modèles feuille assurance**, puis sélectionnez le lien connexe.  
2. Sélectionnez un modèle feuille assurance, puis l'action **Lots**.
3. Dans la fenêtre **Lots feuille assurance**, renseignez les champs selon vos besoins.

> [!NOTE]  
>   Les numéros remplissent une fonction spéciale dans les noms de journal. Si un nom de journal ou de modèle journal indique un numéro, ce numéro est incrémenté automatiquement de 1 chaque fois que le journal est reporté. Par exemple, si vous saisissez HH1 dans le champ **Nom**, la feuille prend le nom HH2 après validation de la feuille HH1.

## <a name="see-also"></a>Voir aussi
[Paramétrage d'immobilisations](fa-setup.md)  
[Immobilisations](fa-manage.md)  
[Finance](finance.md)  
[Mise en route](product-get-started.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
