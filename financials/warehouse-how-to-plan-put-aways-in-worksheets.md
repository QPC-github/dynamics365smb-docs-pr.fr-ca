---
title: Comment planifier des rangements dans la feuille | Microsoft Docs
description: "Lorsque l'emplacement nécessite un traitement à la fois de rangement et de réception et que vous souhaitez planifier des instructions de rangement pour plusieurs réceptions, vous pouvez utiliser la feuille rangement (au lieu de faire suivre aux employés les instructions créées par le programme pour différentes réceptions reportées)."
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
ms.openlocfilehash: 99c3ac10460a62ee23294cfd0d8c25709c37901b
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-plan-put-aways-in-worksheets"></a>Comment planifier des rangements dans la feuille
Lorsque l'emplacement nécessite un traitement à la fois de rangement et de réception et que vous souhaitez planifier des instructions de rangement pour plusieurs réceptions, vous pouvez utiliser la feuille rangement (au lieu de faire suivre aux employés les instructions créées par le programme pour différentes réceptions reportées).  

Pour configurer votre entrepôt afin que les lignes réception soient disponibles dans la feuille rangement dès leur report, sélectionnez le champ **Utiliser feuille rangement** sur le raccourci **Entrepôt** de la fiche emplacement. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

Si vous ne sélectionnez pas ce champ, le programme crée automatiquement des instructions rangement pour les réceptions dès leur report.  

> [!NOTE]  
>  Quel que soit l'état du champ **Utiliser feuille rangement** de la fiche emplacement, vous pouvez toujours obtenir des lignes instruction rangement, c'est à dire des lignes réception reportées, dans la feuille rangement en procédant comme suit :  
>   
>  1.  Dans la fenêtre **Rangement entrepôt**, appuyez sur Ctrl+D pour supprimer l'instruction rangement, ou sélectionnez les lignes à traiter dans la feuille et supprimez-les.  
> 2.  Poursuivez l'opération dans tous les rangements concernés jusqu'à ce que vous ayez supprimé les lignes que vous souhaitez utiliser dans la feuille. Sélectionnez maintenant **Rangement** et continuez la planification.  

## <a name="to-plan-instructions-in-the-put-away-worksheet"></a>Pour planifier des instructions dans la feuille rangement  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille rangement**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Extraire documents entrepôt**. La fenêtre **Sélection rangement** s'ouvre.  

    Vous pouvez visualiser toutes les réceptions reportées et tous les rangements internes enregistrés qui ont été envoyés vers la fonction rangement, y compris ceux pour lesquels des instructions rangement ont déjà été créées. Les documents dont les lignes rangement ont été entièrement rangées et enregistrées n'apparaissent pas dans cette liste.  

3. Sélectionnez les documents que vous souhaitez utiliser dans la feuille. Vous pouvez utiliser simultanément des lignes de plusieurs documents.  

    > [!NOTE]  
    >  Si vous essayez de sélectionner un document réception ou rangement interne dont toutes les lignes disposent déjà d'instructions, le programme vous indique qu'il n'y a rien à gérer.  

4. Renseignez le champ **Méthode de tri** pour trier les lignes à votre convenance.  

    > [!NOTE]  
    >  Le mode de tri des lignes de la feuille ne conduit pas automatiquement à l'instruction rangement, mais les mêmes possibilités de tri existent avec le classement de zone. L'ordre des lignes planifié dans la feuille est donc facilement recréé lorsque vous créez ou triez les instructions rangement.  

5.  Renseignez le champ **Quantité à traiter**. Choisissez l'action **Remplir qté à traiter**, ou renseignez les champs manuellement.  
6.  Si nécessaire, modifiez les lignes manuellement. Vous pouvez supprimer des lignes (par exemple, si certains articles doivent être rangés dans une zone éloignée des zones des autres articles).  

    > [!NOTE]  
    >  s: Les lignes supprimées sont uniquement supprimées dans cette feuille ; elles ne sont pas supprimées de la liste de sélection des rangements.  

7.  Choisissez l'action **Créer rangement**. La fenêtre **Créer document** s'ouvre, où vous pouvez ajouter des informations supplémentaires au rangement que vous créez, telles que :  

    -   Vous pouvez affecter le rangement à un employé donné.  
    -   Vous pouvez trier les lignes instruction rangement comme dans la feuille ou par classement de zone. Lorsque vous effectuez un tri sur la base du classement de zone, les lignes Prélever apparaissent d'abord, étant donné que la plupart des zones réception sont classées au niveau 0, et les lignes zone apparaissent ensuite, en commençant par les zones les moins bien classées. Si vous avez structuré votre entrepôt de façon à ce que les zones de même classement soient les unes à côté des autres et si vous utilisez cette méthode de tri, les magasiniers éviteront un certain nombre d'étapes.  
    -   Vous pouvez choisir de ne pas afficher les lignes intermédiaires créées lorsque le programme divise une unité en unités plus petites, en sélectionnant le champ **Filtrer déconditionnement**. Pour plus d'informations, voir [Procédure : activer la rupture de charge automatique avec prélèvement et rangement dirigé] (warehouse-enable-automatic-breaking-bulk-with-directed-put-away-and-pick.md).  
    -   Vous pouvez faire en sorte que le champ **Quantité à traiter** des instructions rangement ne soit pas renseigné automatiquement.  
    -   Vous pouvez imprimer immédiatement le document.  

8.  Sélectionnez le bouton **OK** pour que le programme crée le rangement en fonction de vos exigences.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
