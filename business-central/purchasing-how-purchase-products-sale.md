---
title: Acheter des articles pour une vente
description: 'Depuis une facture vente, pour acheter des biens, vous pouvez créer une facture achat pour un fournisseur.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'supply planning, sales demand, replenish'
ms.search.form: '50, 51, 56, 9308'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="purchase-items-for-a-sale-by-creating-purchase-invoices" />Acheter des articles pour une vente en créant des factures achat

Avec les commandes vente et les factures vente, vous pouvez utiliser des fonctions vous permettant de créer rapidement des documents achat pour des quantités d'articles manquantes requises par la vente. Vous pouvez utiliser deux fonctions distinctes selon le type document.

> [!Note]
> Cette fonctionnalité est destinées au réapprovisionnement des articles de vente dans votre propre inventaire. Pour acheter des articles pour livraison directe de votre fournisseur à votre client, vous devez créer une livraison directe. Pour plus d'informations, voir [Effectuer des livraisons directes](sales-how-drop-shipment.md).   

|Fonction.|Description|
|--------|-----------|
|**Créer des commandes achat**|Depuis un document de vente, cette fonction crée un bon de commande pour chaque fournisseur des articles du document de vente. Vous pouvez modifier la quantité d'achat avant de créer les commandes achat. Seules les quantités de vente indisponibles sont proposées.
|**Créer une facture achat**|Depuis un document de vente et une facture vente, cette fonction crée une facture achat pour un fournisseur sélectionné pour toutes les lignes ou toutes les lignes sélectionnées sur le document vente. La quantité vendue totale est suggérée.|

## <a name="to-create-one-or-more-purchase-orders-from-a-sales-order" />Pour créer un ou plusieurs bons de commande à partir d'un document de vente
Pour créer une commande achat pour chaque quantité d'article indisponible de la commande vente, vous utilisez la fonction **Créer des commandes achat**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Ouvrez le document de vente pour lequel vous souhaitez acheter des articles.
3. Sélectionnez l'action **Créer des commandes achat**.

    La page **Créer des bons de commande** s'ouvre affichant une ligne pour chaque article différent sur le document de vente. Les lignes des deux des quantités vendues entièrement disponibles et des quantités vendues indisponibles (grisées) sont affichées par défaut. Vous pouvez choisir l'action **Afficher non disponible** pour afficher uniquement les lignes des quantités vendues indisponibles.

    Le champ **Quantité à acheter** indique la quantité vendue indisponible par défaut.
4. Pour acheter une autre quantité que la quantité vendue indisponible, modifiez la valeur dans le champ **Quantité à acheter**.

    > [!NOTE]  
    >   Vous pouvez également modifier le champ **Quantité à acheter** sur les lignes grisées bien qu'ils représentent des quantités vendues entièrement disponibles.
5. Cliquez sur le bouton **OK**.

    Un bon de commande est créé pour chaque fournisseur des articles du document de vente, notamment toutes les modifications de quantité que vous avez apportées sur la page **Créer des bons de commande**.
7. Traitez maintenant la ou les bons de commande, par exemple, en modifiant ou en ajoutant des lignes bon de commande. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).


## <a name="to-create-a-purchase-invoice-from-a-sales-order-or-sales-invoice" />Pour créer une facture achat à partir d'un document de vente ou d'une facture vente
Pour créer une facture achat unique pour une ou plusieurs lignes d'un document vente en sélectionnant d'abord le fournisseur auquel acheter, vous utilisez la fonction **Créer une facture achat**.

> [!NOTE]  
>   Cette fonction crée une facture achat pour la quantité d'articles exacte du document vente sélectionné. Pour modifier la quantité d'achat, vous devez modifier la facture achat après qu'elle soit créée.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Ouvrez une facture vente pour laquelle vous souhaitez acheter des articles.
3. Sélectionnez une ou plusieurs lignes facture vente que vous souhaitez utiliser dans la facture achat. Pour utiliser toutes les lignes facture vente, sélectionnez-les toutes ou ne sélectionnez aucune ligne.
4. Sélectionnez l'action **Créer une facture achat**.
5. Sélectionnez **Toutes les lignes** ou **Lignes sélectionnées**, puis cliquez sur le bouton **OK**.  
6. Dans la liste des fournisseurs qui s'affiche, sélectionnez le fournisseur dont vous souhaitez acheter tous les articles, puis cliquez sur le bouton **OK**.

    Une facture achat ayant une seule, plusieurs ou toutes les lignes de la facture vente, est créée.
7. Traitez maintenant la facture achat, par exemple, en modifiant ou en ajoutant des lignes facture achat. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).

## <a name="see-also" />Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Enregistrer des achats](purchasing-how-record-purchases.md)  
[Facturer des ventes](sales-how-invoice-sales.md)  
[Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
