---
title: "Procédure\_: répartir des lignes activité entrepôt"
description: Découvrez comment répartir les lignes d’activité de l’entrepôt si la capacité disponible dans une zone suggérée n’est pas suffisante.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 01/25/2023
ms.custom: bap-template
ms.search.forms: '931, 9314, 9313, 9315, 9330'
---
# <a name="split-warehouse-activity-lines" />Répartir des lignes activité entrepôt

Dans le cadre de rangements, mouvements ou prélèvements entrepôt et de rangements et prélèvements inventaire, des zones sont proposées pour le prélèvement et le rangement des articles. Il arrive parfois que la quantité réelle disponible dans la zone soit insuffisante ou que l’espace de la zone soit insuffisant pour le rangement de la quantité nécessaire. Dans ces cas, vous pouvez répartir la ligne de telle sorte que les articles d’une ligne soient pris ou placés dans plusieurs zones.  

La procédure suivante s’applique aux documents d’entrepôt suivants :

* Rangements entrepôt
* Mouvements entrepôt
* Prélèvements entrepôt
* Rangements inventaire
* Mouvements d’inventaire
* Prélèvements inventaire  

## <a name="to-split-warehouse-activity-lines" />Pour éclater des lignes activité entrepôt

1. Ouvrez une ligne activité entrepôt dans laquelle vous tentez de traiter une quantité insuffisante.  
2. Dans le champ **Quantité à traiter**, entrez la quantité réduite que vous pouvez gérer.  
3. Sur le raccourci **Lignes**, choisissez l'action **Actions**, choisissez **Fonctions**, puis choisissez l'action **Eclater ligne**. Une nouvelle ligne apparaît. Il s’agit d’une copie de la ligne d’origine, à la différence près que la quantité que vous avez retirée de la ligne d’origine figure dans le champ **Quantité à traiter**.  
4. Affectez à cette nouvelle ligne une zone, ainsi qu’une zone si vous utilisez le prélèvement et le rangement dirigés. Sinon, continuez à répartir la ligne autant de fois que nécessaire jusqu’à ce que vous ayez trouvé des zones appropriées pour toute la quantité.  

> [!NOTE]  
> Si, en cas d'utilisation d'un prélèvement et d'un rangement suggérés dans l'emplacement, vous éclatez les lignes, vous devez bien connaître l'entrepôt et être capable de choisir une zone répondant aux exigences de stockage de l'article et aux exigences générales du document entrepôt. Par exemple, vous n’allez pas répartir une ligne d’un document prélèvement et placer certains articles dans le stockage en vrac.  

## <a name="see-also" />Voir aussi

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
