---
title: "Gestion des coûts inventaire et des coûts de fabrication | Microsoft Docs"
description: "Bien que la comptabilité analytique soit constituée de processus ne nécessitant pas d'interaction utilisateur, telle que l'affectation d'écritures et l'ajustement automatique des coûts, un certain nombre de champs, fenêtres et rapports sont destinés aux utilisateurs qui gèrent directement ou indirectement le coût des articles ou opérations."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/09/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 463902077313b09391c42f4d44fde11be08bdd02
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="handling-inventory-and-manufacturing-costs"></a>Gestion des coûts inventaire et des coûts de fabrication
Bien que la comptabilité analytique soit constituée de processus ne nécessitant pas d'interaction utilisateur, telle que l'affectation d'écritures et l'ajustement automatique des coûts, un certain nombre de champs, fenêtres et rapports sont destinés aux utilisateurs qui gèrent directement ou indirectement le coût des articles ou opérations.  

 L'affectation de frais annexes aux documents achat est un exemple d'une tâche de comptabilité analytique indirecte. La mise à jour du coût unitaire de l'article d'assemblage ou de nomenclature production est un exemple de tâche de comptabilité analytique directe.  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Mettre à jour périodiquement ou automatiquement le coût unitaire d'un ou plusieurs articles afin de faire suivre toutes les modifications de prix des écritures entrantes, telles que celles des achats ou des sorties de production, vers les écritures sortantes, telles que la consommation ou les transferts.|[Ajuster coûts et prix article](inventory-how-adjust-item-costs.md)|  
|Obtenir un aperçu de la dynamique coût moyen afin de prendre des décisions relatives aux prix ou de suivre les fluctuations des coûts causées par les erreurs de saisie.|[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)|  
|Créer le coût standard d'un article de production en saisissant les trois éléments de coût : le coût matière, le coût capacité et le coût de sous-traitance.|[À propos du calcul des coûts standard](finance-about-calculating-standard-cost.md)|  
|Calculer le coût unitaire d'un article de nomenclature à partir des coûts unitaires de ses composants sous-jacents.|[Utiliser les nomenclatures](inventory-how-work-BOMs.md)|  
|Terminer le cycle de vie de l'évaluation coût d'un article produit en ajustant les coûts et en rapprochant les écritures valeur du grand livre.|[À propos des coûts des bons de production achevés](finance-about-finished-production-order-costs.md)|  
|Modifiez la valeur d'un article dans l'inventaire ou la valeur d'une écriture du grand livre article, telle qu'une transaction d'achat.|[Réévaluer l'inventaire](inventory-how-revalue-inventory.md)|
|Annulez manuellement l'affectation d'un article ou réaffectez des écritures article créées par le programme.|[Supprimer et appliquer à nouveau des écritures article](finance-how-to-remove-and-reapply-item-entries.md)|  
|Utilisez le champ **Écriture affectée de** dans le journal article pour créer manuellement une affectation fixe entre une transaction entrante et la transaction sortante initiale.|[Fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)|  

## <a name="see-also"></a>Voir aussi  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)
[Détails de conception : Évaluation stock](design-details-inventory-costing.md)
