---
title: Corriger des paiements anticipés
description: Vous pouvez apporter une correction à une commande après avoir reporté une facture de paiement anticipé pour la commande et ajouter de nouvelles lignes à une commande après avoir émis un paiement anticipé.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '44, 48, 42, 50, 52, 9305, 9307'
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="correct-prepayments" />Corriger des paiements anticipés

Vous pouvez apporter une correction à une commande après avoir reporté une facture paiement anticipé pour la commande. Vous pouvez ajouter de nouvelles lignes à une commande après avoir émis un paiement anticipé, puis vous pouvez reporter une autre facture paiement anticipé, mais vous ne pouvez pas supprimer une ligne d'une commande après avoir facturé un paiement anticipé pour la ligne.  

> [!TIP]
> Si vous avez reporté une facture de paiement anticipé pour une facture vente que vous corrigez ou annulez ensuite, vous devez également corriger ou annuler le paiement anticipé.

## <a name="to-correct-a-prepayment" />Pour corriger un paiement anticipé

La procédure suivante explique comment émettre une note de crédit paiement anticipé pour annuler tous les paiements anticipés facturés pour un document de vente.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Ouvrez le document de vente approprié.
3. Choisissez l'action **Paiement anticipé**, puis l'action **Reporter note de crédit paiement anticipé** ou **Reporter et imprimer note de crédit paiement anticipé**.  
4. Sur la page **Note de crédit vente**, continuez à corriger les écritures appropriées, comme pour toute note de crédit vente. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md).  

    > [!NOTE]  
    > Pour réduire le montant dans le champ **Montant ligne**, vous devez commencer par augmenter le pourcentage de paiement anticipé sur la ligne afin que la valeur du champ **Montant ligne paiement anticipé** ne soit pas réduite au point d'être inférieure à la valeur du champ **Fact. montant paiement anticipé**.

5. Pour créer une facture paiement anticipé pour les nouvelles lignes dans la note de crédit vente, sélectionnez l'action **Paiement anticipé**, puis l'action **Reporter facture paiement anticipé** ou **Reporter et imprimer facture paiement anticipé**.  
6. Pour émettre une autre facture paiement anticipé, augmentez le montant de paiement anticipé sur une ou plusieurs lignes, puis reportez la facture paiement anticipé. Une nouvelle facture est créée pour la différence entre les montants de paiement anticipé facturés et les nouveaux montants de paiement anticipé.  

## <a name="see-related-microsoft-trainingtrainingmodulesprepayment-invoices-dynamics-365-business-central" />Voir la [formation Microsoft](/training/modules/prepayment-invoices-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Procédure pas à pas : configuration et facturation d'acomptes](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
