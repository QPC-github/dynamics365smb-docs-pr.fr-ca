---
title: Gestion d'assemblage
description: Découvrez comment fournir des produits aux clients en combinant des composantes dans des processus simples sans utiliser de fonctions de fabrication.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: 'kit, kitting'
ms.search.form: '900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905'
---
# <a name="assembly-management" />Gestion d'assemblage

Les compagnies peuvent fournir des produits aux clients en combinant des composantes sans utiliser de fonctions de fabrication. Les fonctions d’assemblage d’articles s’intègrent aux fonctions associées telles que les ventes, la planification, les réservations et l’entreposage.  

Un élément d’assemblage est un article pouvant être vendu et contenant une nomenclature d’assemblage. Pour en savoir plus sur les nomenclatures d’assemblage, consultez [Utiliser les nomenclatures d’assemblage](assembly-how-work-assembly-boms.md).

Les ordres d’assemblage sont des ordres internes, tout comme les bons de production. Utilisez les ordres d’assemblage pour gérer le processus d’assemblage et pour lier les besoins de vente aux activités entrepôt. Les ordres d’assemblage impliquent à la fois la production et la consommation lors du report. Les en-têtes d’ordre d’assemblage sont similaires aux lignes journal production. Les lignes d’ordre d’assemblage sont similaires aux lignes journal consommation.  

Vous pouvez utiliser une stratégie d’inventaire juste à temps et personnaliser les produits pour répondre aux demandes des clients. Les ordres d’assemblage peuvent être automatiquement créés et liés lorsque vous créez une ligne document de vente. Le lien entre la demande de vente et l’approvisionnement d’assemblage ouvre plusieurs opportunités lorsque vous traitez des documents de vente :

* Personnaliser les éléments d’assemblage à la volée.
* Promettre des dates de livraison en fonction de la disponibilité des composantes.
* Reporter la production et la livraison de l’article assemblé directement à partir de ses documents de vente.

Pour en savoir plus sur la vente d’articles assemblés, consultez [Vente d’articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).  

Les lignes des documents de vente peuvent contenir des articles à prélever dans le stock et des articles à assembler pour la commande. Les quantités assemblées pour commande ont priorité sur les quantités de l’inventaire dans le cas d’une expédition partielle. Pour en savoir plus sur la vente d’articles de stock et d’assemblage, consultez [Scénarios de combinaison](assembly-assemble-to-order-or-assemble-to-stock.md#combination-scenarios).  

Lorsqu’une quantité assembler pour commande est prête à être livrée, un employé d'entrepôt peut reporter un prélèvement inventaire pour les lignes document de vente. Le report d’un prélèvement inventaire fait deux choses :

* Créer un mouvement d’inventaire pour les composantes
* Reportez le résultat d’assemblage et la livraison du document de vente.

Pour en savoir plus sur les prélèvements inventaire et les articles de l’assemblage pour commande, consultez [Traitement des articles à assembler pour commande dans des prélèvements inventaire](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

Le tableau suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Découvrez plus d’informations sur l’assemblage d’articles pour les documents de vente et le stockage.|[Description des processus Assembler pour commande et Assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md)|
|Utilisez les fiches emplacement et votre configuration inventaire pour définir le flux des articles vers et depuis l’assemblage.|[Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)|
|Établissez un devis pour un article d’assemblage personnalisé, puis convertissez le devis en vente lorsque le client l’accepte.|[Établissement d'un devis de vente Assembler pour commande](assembly-how-to-quote-an-assemble-to-order-sale.md)|
|Combinez des composantes pour créer un article pour une commande ou pour le stock.|[Assembler des articles](assembly-how-to-assemble-items.md)|  
|Vendez les éléments d’assemblage qui ne sont pas disponibles actuellement en créant un ordre d’assemblage associé pour fournir la quantité totale ou partielle du document de vente.|[Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md)|
|Si des articles à assembler pour commande sont déjà dans l’inventaire, vous pouvez déduire cette quantité de l’ordre d’assemblage et la réserver dans l’inventaire.|[Vente d'articles d'inventaire dans des flux à assembler pour commande](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md)|  
|Lorsque les éléments d’assemblage ne sont pas dans l’inventaire, utilisez un ordre d’assemblage pour fournir tout ou partie de la quantité.|[Vente simultanée d'articles à assembler pour commande et d'articles d'inventaire](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md)|
|Créez des éléments d’assemblage personnalisés pour les commandes permanentes ventes avant de créer les documents de vente.|[Création d'ordres d'assemblage permanents](assembly-how-to-create-blanket-assembly-orders.md)|
|Annulez un ordre d’assemblage reporté, par exemple parce que la commande a été reportée avec des erreurs.|[Annuler le report d'assemblage](assembly-how-to-undo-assembly-posting.md)|
|Apprenez à utiliser les nomenclatures d’assemblage et leurs différences avec les nomenclatures de production.|[Utilisation des nomenclatures d’assemblage](assembly-how-work-assembly-boms.md)|
|Découvrez plus d’informations sur le report de la consommation de l’assemblage et de la production, et sur la manière dont [!INCLUDE [prod_short](includes/prod_short.md)] répartit les coûts des articles et des ressources dans le grand livre.|[Détails de conception : Report d'ordre d'assemblage](design-details-assembly-order-posting.md)|  

## <a name="see-related-microsoft-trainingtrainingpathsassemble-items-dynamics-365-business-central" />Voir la [formation Microsoft](/training/paths/assemble-items-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi

[Utiliser les nomenclatures](inventory-how-work-BOMs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Détails de conception : Planification de l’approvisionnement](design-details-supply-planning.md)  
<!-- [Walkthrough: Planning Supplies Manually](walkthrough-planning-supplies-manually.md)   -->
<!-- [Walkthrough: Selling, Assembling, and Shipping Kits](walkthrough-selling-assembling-and-shipping-kits.md)   -->
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## <a name="includeprodshortincludesfreetrialmdmd" />[!INCLUDE[prod_short](includes/free_trial_md.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
