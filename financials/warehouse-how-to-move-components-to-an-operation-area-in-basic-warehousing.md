---
title: "Procédure : déplacer les composantes vers une zone opérations dans les configurations d'entrepôt de base | Microsoft Docs"
description: "Si des opérations de traitement d'articles se produisent dans votre entrepôt, vous pouvez être amené à déplacer des articles entre différents zones internes pour satisfaire aux documents origine internes, tels que la production, l'assemblage ou les commandes service dans l'emplacement."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/16/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 146e113931384e8bc9ba01d5ae7ddb626d18050f
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-move-components-to-an-operation-area-in-basic-warehouse-configurations"></a>Procédure : déplacer les composantes vers une zone opérations dans les configurations d'entrepôt de base
Si des opérations de traitement d'articles se produisent dans votre entrepôt, vous pouvez être amené à déplacer des articles entre différents zones internes pour satisfaire aux documents origine internes, tels que la production, l'assemblage ou les commandes service dans l'emplacement.  

> [!NOTE]  
>  Pour plus d'informations sur le déplacement d'articles d'un emplacement à l'autre sans documents origine, reportez\-vous à Mouvement interne.  

Dans les configurations d'entrepôt avancées, qui correspondent à des emplacements qui utilisent le champ de configuration **Prélèv. et rangement suggérés**, vous pouvez utiliser la fenêtre **Feuille mouvement** pour déplacer des articles d'une zone à l'autre. Pour plus d'informations, voir [Procédure : déplacer des articles dans les configurations de stockage avancées](warehouse-how-to-move-items-in-advanced-warehousing.md).  

Dans les configurations d'entrepôt de base, où les magasins utilisent les champs de configuration **Emplacement obligatoire** et **Prélèvement requis**, vous pouvez enregistrer des mouvements d'articles vers des zones Opérations internes sur la base de documents origine internes en procédant comme suit :  

-   À l'aide de la fenêtre **Mouvement de stock**.  
-   Avec la fenêtre **Prélèvement stock**.  

> [!NOTE]  
>  Les prélèvements inventaire reportent également les écritures article négatives en tant que consommation et ne sont pris en charge que pour les composantes de production. Pour plus d'informations, voir la fenêtre Feuille prélèvement.  

Pour obtenir des informations détaillées sur des mouvements de stock, reportez\-vous à la fenêtre Mouvement de stock.  

Deux rôles différents peuvent créer le mouvement d'inventaire d'origine. Un ouvrier d'assemblage, par exemple, peut le créer à partir d'un ordre d'assemblage libéré de façon à ce qu'il s'affiche sur la liste du travail à accomplir du magasinier. Pour créer un mouvement de stock pour les lignes d'ordre d'assemblage prêtes à voir des composants déplacés dans leurs emplacements spécifiés, l'ouvrier d'assemblage utilise la fonction **Créer mouvement de stock** .  

Sinon, un magasinier peut le créer en pointant l'ordre d'assemblage libéré en question. Ceci est décrit dans la procédure suivante.  

> [!NOTE]  
>  Si le mouvement concerne un ordre d'assemblage pour lequel l'article est assemblé à un document de vente, vous pouvez faire en sorte que le document mouvement d'inventaire soit automatiquement créé lorsque vous générez le document prélèvement inventaire qui prend l'article d'assemblage terminé et reporte la livraison. Pour configurer cela, sélectionnez le champ **Créer des mouvements automatiquement** dans la fenêtre **Paramètres d'assemblage**  
>   
>  Pour plus d'informations sur les ordres d'assemblage et les configurations entrepôt de base, reportez-vous à la section « Traitement des articles à assembler pour commande dans les prélèvements stock » dans [Procédure : prélever pour la fabrication et l'assemblage](warehouse-how-to-pick-for-production.md).  

Cette procédure explique comment créer un mouvement de stock à partir de la fenêtre **Mouvement de stock** en référençant un ordre d'assemblage lancé en tant que document origine. La procédure est la même lorsque vous déplacez les composants pour les ordres de fabrication et les commandes service.  

## <a name="to-move-components-to-an-operation-area-in-basic-warehouse-configurations"></a>Pour déplacer les composantes vers une zone opérations dans les configurations d'entrepôt de base  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Mouvement d'inventaire**, puis sélectionnez le lien associé.  
2.  Sur le raccourci **Général**, renseignez le champ **N°**. . Vous pouvez appuyer sur la touche Entrée pour effectuer une sélection parmi les séries de numéros.  
3.  Dans le champ **Code magasin** , entrez le magasin où le mouvement a lieu.  
4.  Choisissez l'action **Extraire documents origine**. Sinon, renseignez le champ **Document origine** , et cliquez ensuite sur le bouton **AssistEdit** dans le champ **N° origine** .  
5.  Dans la fenêtre **Documents origine** , sélectionnez l'ordre d'assemblage pour lequel vous souhaitez déplacer des composants, puis choisissez le bouton **OK** .  

    Pour chaque composant nécessaire pouvant être déplacé, une ligne prélèvement et une ligne d'emplacement sont générées dans la fenêtre **Mouvements de stock** . Tous les champs à l'exception du champ **Qté à traiter** sont préremplis en fonction des lignes document origine. Le champ **Qté à traiter** est défini sur zéro jusqu'à ce que vous entriez la quantité que vous avez réellement déplacée.  

    Vous pouvez modifier le code de zone de la ligne prélèvement mais uniquement en fonction de la disponibilité. Si vous choisissez le bouton **AssistEdit** dans le champ **Code emplacement** sur une ligne prélèvement, la fenêtre **Contenu emplacement** s'ouvre et affiche uniquement les emplacements où le composant est disponible.  

    Vous ne pouvez pas modifier le code de zone sur une ligne Emplacement. Seul le code de zone qui est défini sur la ligne composante du document origine est accepté. Cela se base sur le principe que le rôle demandant une composante, qui est un ouvrier d'assemblage dans cette procédure, sait où doit être placée la composante. Si vous souhaitez placer les composantes dans un autre zone, vous devez d'abord modifier le code de zone de la ligne composante, puis recréer les lignes mouvement d'inventaire.  
6.  Dans le champ **Qté à traiter**, entrez la quantité totale ou partielle que vous avez réellement déplacée. La valeur sur les lignes prélèvement et emplacement doit être la même. Sinon, vous ne pouvez pas enregistrer le mouvement.  

    > [!NOTE]  
    >  Comme pour d'autres activités entrepôt, vous pouvez éclater la ligne d'emplacement en sélectionnant l'action **Actions**, puis en choisissant l'action **Eclater ligne**. Dans ce cas, la somme des deux lignes d'emplacement éclatées doit être égale à la quantité de la ligne prélèvement.  

7.  Lorsque vous êtes prêt à enregistrer les mouvements que vous avez exécutés, choisissez l'action **Enregistrer mouvement d'inventaire** .  

    Les écritures entrepôt sont créées, reflétant que les composants existent désormais dans les emplacements spécifiés sur les lignes d'ordre d'assemblage.  

    > [!NOTE]  
    >  Contrairement au déplacement de composantes à l'aide d'un prélèvement inventaire, la consommation n'est pas reportée lorsque vous enregistrez un mouvement d'inventaire. Cette étape doit être réalisée séparément en reportant la production et la consommation de l'ordre d'assemblage. Pour plus d'informations, reportez\-vous à Ordre d'assemblage.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
