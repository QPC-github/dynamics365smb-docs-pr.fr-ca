---
title: Traitement en lot Proposer paiements fournisseur
description: Vous pouvez spécifier les paramètres du paiement fournisseur pour obtenir des suggestions ou des propositions pour les paiements arrivant à échéance ou donnant lieu à un escompte.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'vendor payment, creditor, debt, balance due, AP'
ms.search.form: 256
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="suggest-vendor-payments" />Proposer paiements fournisseur

Sur la page **Journal paiement**, vous pouvez utiliser le traitement en lot **Proposer paiements fournisseur** pour proposer des lignes paiement. Des lignes pour les paiements échus à courte échéance ou les paiements pour lesquels un escompte de paiement est disponible, sont proposées en fonction de vos paramètres.

Pour bénéficier pleinement des suggestions de paiement, vous devez d'abord attribuer une priorité à vos fournisseurs. Pour plus d'informations, voir [Octroyer une priorité à des fournisseurs](purchasing-how-prioritize-vendors.md).  

> [!NOTE]  
> Le traitement en lot n'inclut pas les écritures fournisseur marquées **En attente**.  

> [!IMPORTANT]  
>   Si vous souhaitez profiter d'escomptes et que vous avez saisi un montant disponible, ce montant est d'abord utilisé pour :  
    * Les écritures fournisseur échues et prioritaires, par ordre de priorité.   
    * Les écritures fournisseur échues et non prioritaires.  
    * Les écritures fournisseur ouvertes donnant lieu à un escompte, dans l'ordre des numéros des fournisseurs.  

## <a name="to-use-the-suggest-vendor-payments-function" />Pour utiliser la fonction Proposer paiements fournisseur

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux paiement**, puis choisissez le lien associé.  
2. Ouvrez la feuille appropriée, puis sélectionnez l'action **Proposer paiements fournisseur**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. Cliquez sur le bouton **OK**.  

## <a name="to-insert-the-due-date-as-posting-date-on-payment-journal-lines" />Pour insérer la date d'échéance comme date de report sur les lignes journal paiement

Lorsque vous utilisez le traitement par lots **Proposer paiements fournisseur** pour créer des lignes de paiement pour vos fournisseurs, vous pouvez remplir deux champs spéciaux pour vous assurer que les lignes générées utilisent la date d'échéance pour calculer la date comptabilisation. Ces champs sont **Calculer la date comptabilisation à partir de la date d'échéance doc. lettrage** et **Décalage date d'échéance doc. lettrage**.  

> [!IMPORTANT]  
>   Vous ne pouvez pas utiliser le champ **Calculate Posting Date from Applies-to-Doc Due Date** avec le champ **Find Payment Discounts** ou le champ **Summarize per Vendor**. Si la date de report est basée sur la date d'échéance, des escomptes de paiement risquent de ne pas être calculés correctement, parce que la date de report peut se trouver après la date d'escompte de paiement.  

De plus, si la date de report calculée se trouve dans le passé, la date de report est déplacée à la date de travail, et un message d'attention s'affiche.  

Vous pouvez aussi créer manuellement des lignes de paiement à l'aide de la date d'échéance pour calculer la date de report. Une fois que vous avez appliqué les écritures comptables fournisseur, vous pouvez utiliser l'option **Calculer date comptabilisation** pour mettre à jour la date comptabilisation de la ligne feuille à la date d'échéance de la facture achat associée. Pour plus d'informations, voir [Affecter les achats manuellement](payables-how-apply-purchase-transactions-manually.md).  

> [!NOTE]  
>   Si la facture achat est en retard, la date de report est définie sur la date de travail et la police de la ligne devient rouge.  

## <a name="see-related-microsoft-trainingtrainingmodulessuggest-vendor-payments-dynamics-365-business-central" />Voir la [formation Microsoft](/training/modules/suggest-vendor-payments-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Effectuer des paiements](payables-make-payments.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
