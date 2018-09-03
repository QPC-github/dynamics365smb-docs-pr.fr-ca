---
title: Utilisez le traitement en lot Proposer paiements fournisseur| Microsoft Docs
description: "Vous pouvez spécifier les paramètres du paiement fournisseur pour obtenir des suggestions ou des propositions pour les paiements arrivant à échéance ou donnant lieu à un escompte."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vendor payment, creditor, debt, balance due, AP
ms.date: 05/15/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: ad1b888d475c0523c5a905e804a3f89ab4531b28
ms.openlocfilehash: 02f063daf5afeea85832c8a322183b3db120d8d2
ms.contentlocale: fr-ca
ms.lasthandoff: 05/17/2018

---
# <a name="suggest-vendor-payments"></a>Proposer paiements fournisseur
Dans la fenêtre **Feuille paiement**, vous pouvez utiliser le traitement par lots **Proposer paiements fournisseur** pour proposer des lignes paiement. Des lignes pour les paiements échus à courte échéance ou les paiements pour lesquels un escompte de paiement est disponible, sont proposées en fonction de vos paramètres.

Pour bénéficier pleinement des suggestions de paiement, vous devez d'abord attribuer une priorité à vos fournisseurs. Pour plus d'informations, voir [Octroyer une priorité à des fournisseurs](purchasing-how-prioritize-vendors.md).  

> [!NOTE]  
> Le traitement en lot n'inclut pas les écritures fournisseur marquées **En attente**.  

> [!IMPORTANT]  
>   Si vous souhaitez profiter d'escomptes et que vous avez saisi un montant disponible, ce montant est d'abord utilisé pour :  

* Les écritures fournisseur échues et prioritaires, par ordre de priorité.  
* Les écritures fournisseur échues et non prioritaires.  
* Les écritures fournisseur ouvertes donnant lieu à un escompte, dans l'ordre des numéros des fournisseurs.  

## <a name="to-use-the-suggest-vendor-payments-function"></a>Pour utiliser la fonction Proposer paiements fournisseur
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles paiement**, puis sélectionnez le lien connexe.  
2. Ouvrez la feuille appropriée, puis sélectionnez l'action **Proposer paiements fournisseur**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. Cliquez sur le bouton **OK**.  

## <a name="to-insert-the-due-date-as-posting-date-on-payment-journal-lines"></a>Pour insérer la date d'échéance comme date de report sur les lignes journal paiement
Lorsque vous utilisez le traitement par lots **Proposer paiements fournisseur** pour créer des lignes de paiement pour vos fournisseurs, vous pouvez remplir deux champs spéciaux pour vous assurer que les lignes générées utilisent la date d'échéance pour calculer la date comptabilisation. Ces champs sont **Calculer la date comptabilisation à partir de la date d'échéance doc. lettrage** et **Décalage date d'échéance doc. lettrage**.  

> [!IMPORTANT]  
>   Vous ne pouvez pas utiliser le champ **Calculate Posting Date from Applies-to-Doc Due Date** avec le champ **Find Payment Discounts** ou le champ **Summarize per Vendor**. Si la date de report est basée sur la date d'échéance, des escomptes de paiement risquent de ne pas être calculés correctement, parce que la date de report peut se trouver après la date d'escompte de paiement.  

De plus, si la date de report calculée se trouve dans le passé, la date de report est déplacée à la date de travail, et un message d'attention s'affiche.  

Vous pouvez aussi créer manuellement des lignes de paiement à l'aide de la date d'échéance pour calculer la date de report. Une fois que vous avez appliqué les écritures comptables fournisseur, vous pouvez utiliser l'option **Calculer date comptabilisation** pour mettre à jour la date comptabilisation de la ligne feuille à la date d'échéance de la facture achat associée. Pour plus d'informations, voir [Affecter les achats manuellement](payables-how-apply-purchase-transactions-manually.md).  

> [!NOTE]  
>   Si la facture achat est en retard, la date de report est définie sur la date de travail et la police de la ligne devient rouge.  

## <a name="see-also"></a>Voir aussi
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Effectuer des paiements](payables-make-payments.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
