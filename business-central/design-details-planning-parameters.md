---
title: "Détails de conception\_-\_Paramètres de planification"
description: Cet article décrit les différents paramètres de planification que vous pouvez utiliser et comment ils affectent le système de planification.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.date: 04/26/2023
ms.custom: bap-template
---
# <a name="design-details-planning-parameters" />Détails de conception : paramètres de planification

Cet article décrit les paramètres de planification que vous pouvez utiliser dans [!INCLUDE[prod_short](includes/prod_short.md)].  

La façon dont le système de planification contrôle l’approvisionnement d’article est déterminée par diverses configuration des pages **Fiche article**, **Unité de stock** et **Configuration de la production**. Le tableau suivant explique comment la planification utilise ces paramètres.  

|Objet|Paramètres|
|-------------|---------------|
|Définir si l’article est planifié|Méthode de réapprovisionnement = Vide|
|Définir la date de réapprovisionnement|Plage de temps<br /><br /> Point de réapprovisionnement<br /><br /> Délai de sécurité|
|Définir la quantité à réapprovisionner|Quantité de stocks de sécurité<br /><br /> Méthode de réapprovisionnement :<br /><br /> -   Qté fixe de commande plus Quantité de réappro.<br />-   Qté maximum plus inventaire maximum<br />\-   Commande<br />-   Lot pour lot|
|Optimisez quand et combien réapprovisionner|Période de replanification<br /><br /> Période de cumul de lot<br /><br /> Période tampon|
|Modifiez les commandes approvisionnement|Quantité minimum commande<br /><br /> Quantité maximum commande<br /><br /> Commande multiple|
|Délimiter l'article planifié|Mode de lancement :<br /><br /> -  Fabrication sur stock<br />- Fabrication à la commande|

## <a name="define-whether-the-item-is-planned" />Définir si l’article est planifié

Pour inclure un article ou une unité de stock dans le processus de planification, vous devez lui attribuer une méthode de réapprovisionnement. Sinon, il doit être planifié manuellement, par exemple, en utilisant la fonctionnalité Planification des commandes.  

## <a name="define-when-to-reorder" />Définir la date de réapprovisionnement

Les propositions de commande sont généralement libérées seulement lorsque la quantité disponible prévue est inférieure à une certaine quantité donnée. Ce point de commande définit la quantité. Sinon, elle est égale à zéro. Zéro peut être ajusté en saisissant une quantité de stock de sécurité. Si vous définissez un date d’échéance de sécurité, la proposition sera livrée dans la période précédant la date d’échéance demandée.  

Le champ **Plage de temps** est utilisé par les stratégies de point de commande (**Qté fixe de commande** et **Qté maximum**). Le niveau d’inventaire est vérifié après chaque plage de temps. La première plage de temps débute à la date de début de la planification.  

> [!NOTE]  
> Lors du calcul des plages de temps, le système de planification ignore les calendriers de travail définis dans le champ **Code calendrier principal** des pages **Informations compagnie** et **Fiche emplacement**.  

Sur la page **Configuration production**, définissez le délai de sécurité par défaut à au moins un jour. La date d’échéance de la demande peut être connue, mais pas l’heure d’échéance. La planification planifie en amont pour répondre à la demande brute. Si aucun délai de sécurité n’est défini, les marchandises peuvent arriver trop tard pour répondre à la demande.  

Les champs **Période de replanification**, **période de cumul de lot** et **Période tampon** jouent également un rôle en définissant quand commander à nouveau. Pour plus d'informations, reportez-vous [Optimiser le délai et la quantité de commande](design-details-planning-parameters.md#optimize-when-and-how-much-to-reorder).  

## <a name="define-how-much-to-reorder" />Définir la quantité à réapprovisionner

Si le système de planification détecte un besoin de réapprovisionnement, la méthode de réapprovisionnement détermine quand et combien commander.  

Indépendamment de la méthode de réapprovisionnement, le système de planification suit généralement cette logique :  

1. Calculez la quantité de la proposition de commande pour atteindre le niveau d’inventaire minimum de l’article, généralement l’inventaire de sécurité. Si aucune valeur n'est spécifiée, le niveau d'inventaire minimum est égal à zéro.  
2. Si le stock disponible prévu est inférieur au stock de sécurité, une commande d'approvisionnement programmée en amont est suggérée. La quantité de commande remplira au moins la quantité d'inventaire de sécurité, et peut être augmentée par une demande brute dans la plage de temps, par la méthode de réapprovisionnement, ainsi que par les modificateurs de commande.  
3. Si l'inventaire prévisionnel est égal ou inférieur au point de réapprovisionnement (calculé à partir des modifications agrégées dans la plage de temps) et supérieur à la quantité inventaire de sécurité, une commande d'exception planifiée en aval est suggérée. La demande brute à satisfaire et la méthode de réapprovisionnement détermineront la quantité de commande. Au minimum, la quantité commandée doit être égale au point de commande.  
4. S’il y a plus de demande brute due avant la date de fin de la proposition commande programmée en aval, et si cette demande amène l’inventaire disponible projeté calculé actuellement en dessous de l’inventaire de sécurité, la quantité commandée est augmentée pour compenser le déficit. La commande approvisionnement suggérée est alors programmée en amont à partir de la date d'échéance de la demande brute qui aurait entamé l'inventaire de sécurité.  
5. Si le champ **Plage de temps** n’est pas renseigné, seule la demande brute à la même date d’échéance sera ajoutée.  

### <a name="reordering-policies" />Méthodes de réapprovisionnement

Les méthodes de réapprovisionnement suivantes affectent la quantité en cours de réapprovisionnement. Pour en savoir plus sur les méthodes de réapprovisionnement, accédez à [Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md).  

|Méthode de réapprovisionnement|Désignation|  
|-----------------------|---------------------------------------|  
|**Qté fixe de commande**|Au minimum, la quantité commandée est égale à la quantité de réapprovisionnement. Vous pouvez augmenter la quantité pour répondre à la demande ou atteindre le niveau d’inventaire voulu. Cette méthode de réapprovisionnement est généralement utilisée avec un point de commande.|  
|**Qté maximum**|La quantité commande est calculée pour répondre à l’inventaire maximum. Si des modificateurs de quantité sont utilisés, l'inventaire maximum peut être dépassé. Nous vous recommandons de ne pas utiliser la plage de temps avec la quantité maximale. La plage de temps est généralement outrepassée. Cette méthode de réapprovisionnement est généralement utilisée avec un point de commande.|  
|**Commande**|La quantité commande est calculée pour répondre à chacun des événements de demande, et l'ensemble demande-approvisionnement reste lié jusqu'à l'exécution. Aucun paramètres de planification n'est pris en compte.|  
|**Lot pour lot**|La quantité est calculée pour satisfaire la somme de la demande qui arrive à date d'échéance dans la plage de temps.|  

## <a name="optimize-when-and-how-much-to-reorder" />Optimisez quand et combien réapprovisionner

Un gestionnaire réglera avec précision les paramètres de planification afin de limiter les suggestions de replanification, accumuler les demandes (quantité de réappro. dynamique) ou éviter les actions de planification insignifiantes. Les champs suivants permettent d’optimiser le moment où réapprovisionner et la quantité à réapprovisionner.  

|Champ|Désignation|  
|---------------------------------|---------------------------------------|  
|**Période de replanification**|Ce champ détermine si le message d’action doit replanifier une commande existante ou l’annuler et créer une nouvelle commande. L'ordre existant sera replanifié dans une période de replanification avant l'approvisionnement actif et jusqu'à une période de replanification après la date d'approvisionnement actif.<br><br>**Remarque :** Ce paramètre ne fonctionne qu’avec la méthode de réapprovisionnement **Lot pour lot**.|  
|**Période de cumul de lot**|Avec la méthode de réapprovisionnement lot pour lot, ce champ est utilisé pour regrouper plusieurs besoins d'approvisionnement dans une commande d'approvisionnement. À partir du premier approvisionnement prévu, le système cumule tous les besoins d'approvisionnement dans la période de cumul de lot suivante en un approvisionnement unique, effectué lors de la date du premier approvisionnement. La demande effectuée en dehors de la période de cumul de lot n'est pas couverte par cet approvisionnement.|  
|**Période tampon**|Ce champ permet d'éviter une replanification mineure de l'approvisionnement existant dans le temps. Les modifications de la date approvisionnement jusqu'à une période tampon de la date approvisionnement ne génèrent aucun message d'action.<br /><br /> La période tampon désigne la période pendant laquelle vous ne souhaitez pas que le système de planification propose de replanifier les commandes d’approvisionnement existantes en aval. Cela limite le nombre de replanification non significative de l'approvisionnement existant à une date ultérieure si la date replanifiée se situe dans la période tampon.<br /><br /> Par conséquent, un delta positif entre la nouvelle date d'approvisionnement proposée et la date d'approvisionnement d'origine est toujours supérieur à la période tampon.|  

> [!NOTE]
> Avec la politique de réorganisation Lot pour Lot, la valeur du champ **Période de cumul de lot** doit être égale ou supérieure à celle du champ **Période tampon**. Sinon, la période d’amortissement est réduite pendant la routine de planification pour correspondre à la période de cumul de lot.  

Le temps de la période de reprogrammation, de la période tampon, ainsi que de la période de cumul de lot est basé sur une date d'approvisionnement. La plage de temps est basée sur la date de début de la planification, comme l'indique la figure suivante.  

:::image type="content" source="media/supply_planning_5_time_bucket_elements.png" alt-text="Éléments de plage de temps.":::

Dans les exemples suivants, les flèches noires représentent l'approvisionnement existant (vers le haut) et la demande (vers le bas). Les flèches rouge, verte et orange sont des suggestions de planification.  

**Exemple 1** : la date modifiée est en dehors de la période de replanification, ce qui entraîne l'annulation de l'approvisionnement existant. Un nouvel approvisionnement est proposé pour répondre à la demande dans la période de cumul de lot.  

:::image type="content" source="media/supply_planning_5_recheduling_period_lot_accumulation_period.png" alt-text="Période de replanification et périodes de cumul de lot.":::

**Exemple 2** : la date modifiée se trouve dans la période de replanification, ce qui entraîne la replanification de l'approvisionnement existant. Un nouvel approvisionnement est proposé pour répondre à la demande hors de la période de cumul de lot.  

:::image type="content" source="media/supply_planning_5_recheduling_period_lot_accum_period_reschedule.png" alt-text="Période de replanification, période de cumul de lot et replanification.":::

**Exemple 3** : il existe une demande pour la période tampon et la quantité d’approvisionnement dans la période de cumul de lot correspond à la quantité d’approvisionnement. La demande suivante n'est pas couverte et un nouvel approvisionnement est proposé.  

:::image type="content" source="media/supply_planning_5_dampener_period_lot_accumulation_period.png" alt-text="Période tampon et période de cumul de lot.":::

**Exemple 4** : il existe une demande pour la période tampon et l’approvisionnement reste à la même date. Toutefois, la quantité d’approvisionnement actif n’est pas suffisante pour répondre à la demande dans la période de cumul de lot. Une action de modification de quantité pour la commande d’approvisionnement existante est suggérée.  

:::image type="content" source="media/supply_planning_5_dampener_period_lot_accum_period_change_qty.png" alt-text="Période tampon, Période de cumul de lot et Modifier la quantité.":::

**Valeurs par défaut :** la valeur par défaut du champ **Intervalle de planification** et des trois champs de période de réapprovisionnement est vide. Pour tous les champs, sauf le champ **Période tampon**, cela signifie 0D (zéro jours). Si le champ **Période tampon** est vide, la valeur globale du champ **Période tampon par défaut** de la page **Configuration de la fabrication** sera utilisée.  

## <a name="modify-the-supply-orders" />Modifiez les commandes approvisionnement

Lorsque la quantité de la proposition de commande a été calculée, un ou plusieurs modificateurs de commande peuvent l'ajuster. Par exemple, la quantité maximum commande est supérieure ou égale à la quantité minimum commande, qui est supérieure ou égale au multiple de commande.  

La quantité est diminuée si elle dépasse la quantité maximum commande. Ensuite, il est augmenté s'il est inférieur à la quantité de commande minimale. Enfin, elle est arrondie par excès de façon à correspondre à un multiple spécifié de commande. La quantité restante utilise les mêmes ajustements jusqu'à ce que la demande totale ait été convertie en propositions commande.  

## <a name="delimit-the-item" />Délimiter l’article

Le champ **Mode de lancement** sur la page **Fiche article** définit les autres commandes proposées par le calcul MRP.  

Si l’option **Fabrication sur stock** est utilisée, les commandes se rapportent uniquement à l’article.  

Si l’option **Fabrication à la commande** est utilisée, le système de planification analyse la nomenclature de l’article et crée des propositions commande liées supplémentaires pour les articles de niveau inférieur qui sont également définis comme Fabrication à la commande. Cela se poursuit tant que il existe des articles make-to-order dans les structures de nomenclature décroissantes.

## <a name="use-low-level-codes-to-manage-derived-demand" />Utiliser des codes plus bas niveau pour gérer la demande dérivée

Utilisez des codes plus bas niveau pour faire progresser la demande dérivée de composantes jusqu’aux niveaux inférieurs de la nomenclature. Pour en savoir plus sur les codes plus bas niveau, accédez à [Priorité de l’article/Code plus bas niveau](design-details-central-concepts-of-the-planning-system.md#item-priority--low-level-code).

Vous pouvez affecter un code plus bas niveau à chaque partie de la structure du produit ou de la nomenclature décalée. Le plus haut niveau d’assemblage est noté niveau 0 (article fini). Plus le numéro du code plus bas niveau est élevé, plus l’article est placé bas dans la hiérarchie. Par exemple, les produits finis ont le code de plus bas niveau 0 et les pièces utilisées lors de l’assemblage de ces articles ont les codes de plus bas niveau 1, 2, 3, etc. Le résultat est la planification des composantes coordonnée aux besoins de tous les numéros de pièces de plus haut niveau. Lorsque vous calculez une planification, la nomenclature est éclatée dans la feuille planification et les besoins bruts du niveau 0 sont transmis aux niveaux de planification comme besoins bruts du niveau de planification suivant.

Sur la page **Configuration production**, utilisez le bouton bascule **Code plus bas niv. dyn.** pour spécifier s’il faut affecter et calculer immédiatement les codes plus bas niveau de chaque composante dans la structure produit. Si vous possédez une grande quantité de données, cette fonction peut avoir des effets négatifs sur les performances du programme, par exemple lors d’un ajustement automatique des coûts. Vous remarquerez que cette fonction n’est pas rétroactive ; il est donc préférable d’envisager l’utilisation de cette fonction au préalable.

Au lieu d’utiliser le calcul automatique exécuté de façon dynamique si le champ est activé, vous pouvez lancer le traitement en lot **Calculer code plus bas niveau** accessible à partir du menu **Production** en choisissant **Conception du produit**, **Calculer code plus bas niveau**.

> [!IMPORTANT]
> Si vous n’activez pas le bouton bascule **Code plus bas niv. dyn.**, vous devez exécuter le traitement en lot **Calculer code plus bas niveau** avant de calculer un programme d’approvisionnement (traitement en lot **Calculer planning**).  

> [!NOTE]
> Même si le champ **Code plus bas niv. dyn.** est activé, les codes plus bas niveau des composantes ne sont pas modifiés dynamiquement si une nomenclature parent est supprimée ou définie comme non certifiée. Il peut en résulter une difficulté à ajouter de nouveaux éléments à la fin de la structure du produit car il se peut que celle-ci dépasse le nombre maximal de codes plus bas niveau. Toutefois, pour les structures de produit volumineuses atteignant la limite de codes plus bas niveau, vous pouvez lancer le traitement en lot **Calculer code plus bas niveau** régulièrement pour gérer la structure.  

## <a name="see-also" />Voir aussi .

[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)  
[Détails de conception : équilibrage de la demande et de l’approvisionnement](design-details-balancing-demand-and-supply.md)  
[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
