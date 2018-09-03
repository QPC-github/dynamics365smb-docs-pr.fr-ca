---
title: "Affecter un niveau de priorité à un fournisseur | Microsoft Docs"
description: "Vous pouvez affecter des numéros à vos fournisseurs pour les classer par ordre de priorité et faciliter des propositions de paiement dans Business Central."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supplier, payment priority
ms.date: 03/29/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: f7834f0f99b775125425eb7209c3c648de4ccd1f
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="prioritize-vendors"></a>Octroyer une priorité aux fournisseurs
[!INCLUDE[d365fin](includes/d365fin_md.md)] peut proposer différents paiements aux fournisseurs, par exemple les paiements arrivant à échéance ou les paiements donnant lieu à un escompte. Pour plus d'informations, reportez vous à [Proposer des paiements fournisseur](payables-how-suggest-vendor-payments.md).

Tout d'abord, vous devez attribuer une priorité à vos fournisseurs en leur affectant des numéros.

## <a name="to-prioritize-vendors"></a>Pour octroyer une priorité à des fournisseurs
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Comptes bancaires**, puis sélectionnez le lien connexe.
2. Sélectionnez le fournisseur approprié, puis sélectionnez **Modifier**.
3. Dans le champ **Priorité**, entrez un numéro.

[!INCLUDE[d365fin](includes/d365fin_md.md)] donne le degré de priorité le plus élevé au chiffre le plus bas, excepté 0. Ainsi, si vous utilisez 1, 2 et 3, le chiffre 1 a le degré de priorité le plus élevé.

Si vous ne souhaitez pas attribuer de priorité à un fournisseur, laissez le champ **Priorité** blanc. Par la suite, lorsque vous utilisez la fonction de proposition de paiements, ce fournisseur est répertorié après tous les fournisseurs possédant un numéro prioritaire. Vous pouvez saisir autant de niveaux de priorité que nécessaire.

## <a name="see-also"></a>Voir aussi
[Définition des achats](purchasing-setup-purchasing.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
