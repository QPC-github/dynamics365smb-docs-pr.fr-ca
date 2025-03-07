---
title: "Détails de conception\_: disponibilité dans l’entrepôt"
description: Découvrez les différents facteurs qui affectent la disponibilité des articles dans votre entrepôt.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.date: 02/22/2023
ms.custom: bap-template
---
# <a name="design-details-availability-in-the-warehouse" />Détails de conception : disponibilité dans l'entrepôt

Restez au courant de la disponibilité des articles pour vous assurer que les commandes sortantes s’écoulent efficacement et que les délais de livraison sont optimaux.  

La disponibilité peut varier en fonction de plusieurs facteurs. Par exemple :

* Des affectations ont lieu au niveau de la zone lorsque se produisent des activités d’entrepôt telles que prélèvements et mouvements.
* Lorsque le système de réservation de l'inventaire impose des restrictions à respecter.

Avant d’affecter des quantités aux prélèvements pour les flux sortants, [!INCLUDE [prod_short](includes/prod_short.md)] vérifie que toutes les conditions sont remplies.

Lorsque les conditions ne sont pas remplies, des messages d’erreur s’affichent. Un message typique est le message générique « Il n’y a rien à traiter ». . Le message peut s’afficher pour plusieurs raisons différentes, à la fois dans des flux entrants et sortants, où une ligne document contient le champ **Qté à traiter**.

## <a name="bin-content-and-reservations" />Contenu et réservations de zone

Les quantités d’articles existent à la fois en tant qu’écritures entrepôt et en tant qu’écritures du grand livre d’articles dans l’inventaire. Ces deux types d’écritures contiennent différentes informations à propos de l’endroit où se trouvent les articles et s’ils sont disponibles. Les écritures d'entrepôt définissent la disponibilité d'un article par zone et type de zone, qui est appelée contenu de la zone. Les écritures du grand livre d’articles définissent la disponibilité d’un article par sa réservation par rapport aux documents sortants.  

[!INCLUDE [prod_short](includes/prod_short.md)] calcule la quantité disponible pour le prélèvement lorsque le contenu de la zone est associé à des réservations.  

## <a name="quantity-available-to-pick" />Quantité disponible pour prélèvement

[!INCLUDE [prod_short](includes/prod_short.md)] réserve les articles pour les livraisons de documents de vente en attente afin qu’ils ne soient pas prélevés pour d’autres documents de vente livrés plus tôt. [!INCLUDE [prod_short](includes/prod_short.md)] soustrait les quantités des articles qui sont déjà en cours de traitement, comme suit :

* Quantités réservées à d’autres documents sortants.
* Quantités sur les documents de prélèvement existants.
* Quantités prélevées mais pas encore livrées ou consommées.  

Le résultat est calculé dynamiquement et affiché dans le champ **Qté disponible à prélever** de la page **Feuille prélèvement**. La valeur est également calculée lorsque les utilisateurs créent les prélèvements entrepôt directement pour les documents sortants. Voici des exemples de documents sortants :

* Documents de vente
* Consommation de la production
* Transferts sortants

Le résultat est disponible dans ces documents dans les champs de quantité, tels que le champ **Qté à traiter**.  

> [!NOTE]  
> En ce qui concerne la priorité des réservations, la quantité à réserver est soustraite de la quantité disponible à prélever. Par exemple, si la quantité disponible dans les zones prélèvement est 5 unités, mais que 100 unités sont dans les zones de rangement, lorsque vous réservez plus de 5 unités pour une autre commande, un message d’erreur s’affiche, car la quantité supplémentaire doit être disponible dans les zones prélèvement.  

### <a name="calculating-the-quantity-available-to-pick" />Calcul de la quantité disponible à prélever

[!INCLUDE [prod_short](includes/prod_short.md)] calcule la quantité disponible à prélever de la façon suivante :  

quantité disponible pour prélèvement = quantité dans les zones prélèvement - quantité sur des prélèvements et des mouvements – (quantité réservée dans des zones prélèvement + quantité réservée sur des prélèvements et des mouvements)  

Le schéma suivant montre les différents éléments du calcul.  

![Disponible pour prélever avec chevauchement de réservation.](media/design_details_warehouse_management_availability_2.png "Disponible pour prélever avec chevauchement de réservation")  

## <a name="quantity-available-to-reserve" />Quantité disponible à réserver

Dans la mesure où les concepts de la valeur et de la réservation de zone coexistent, le nombre d’articles disponibles pour réserver doit s’aligner sur les affectations aux documents d'entrepôt sortants.  

Vous pouvez réserver tous les articles dans l’inventaire, à l’exception des articles pour lesquels le traitement sortant a commencé. La quantité disponible pour la réservation est définie comme la quantité sur tous les documents et types de zone. Les quantités sortantes suivantes sont des exceptions :  

* Quantité dans les documents prélèvement non enregistrés  
* Quantité dans les zones de livraison  
* Quantité dans les zones avant production  
* Quantité dans les emplacements atelier ouverts  
* Quantité dans les zones vers assemblage  
* Quantité dans les emplacements ajustement  

Le résultat est affiché dans le champ **Quantité totale disponible** de la page **Réservation**.  

Sur une ligne réservation, la quantité qui ne peut pas être réservée, parce qu’elle est affectée dans l’entrepôt, est affichée dans le champ **Qté affectée à l’entrepôt** de la page **Réservation**.  

### <a name="calculating-the-quantity-available-to-reserve" />Calcul de la quantité disponible à réserver

[!INCLUDE [prod_short](includes/prod_short.md)] calcule la quantité disponible à réserver de la façon suivante :  

quantité disponible à réserver = quantité totale en inventaire - quantité sur des prélèvements et des mouvements pour des documents origine - quantité réservée - quantité dans des zones désenlogement  

Le schéma suivant montre les différents éléments du calcul.  

![Disponible pour réserver par affectation entrepôt.](media/design_details_warehouse_management_availability_3.png "Disponible pour réserver par affectation entrepôt")  

## <a name="see-also" />Voir aussi

[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Afficher la disponibilité des articles](inventory-how-availability-overview.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
