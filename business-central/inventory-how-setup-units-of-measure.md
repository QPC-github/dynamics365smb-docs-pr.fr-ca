---
title: "Comment configurer des unités de mesure article | Microsoft Docs"
description: "Vous pouvez définir plusieurs unités de mesure pour un article afin de pouvoir affecter des unités de mesure à l'article."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: UOM
ms.date: 01/12/2018
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: d756fbf4cb4ca31c913792a286c373de052aee64
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-item-units-of-measure"></a>Configurer des unités de mesure article
Vous pouvez configurer plusieurs unités de mesure pour un article afin que vous puissiez affecter des unités de mesure à l'article aux fins suivantes :

- Affectez une unité de mesure de base sur la fiche article de l'article pour définir la manière dont elle est stockée dans l'inventaire et pour servir de base de conversion aux autres unités de mesure.
- Affectez d'autres unités de mesure pour les documents d'achat, de production, ou de vente pour spécifier le nombre d'unités de mesure de base que vous gérez dans ces processus. Par exemple, vous pouvez acheter l'article en palettes et n'utiliser que des pièces individuelles en production.

Si un article est stocké dans une unité mais produit dans une autre, un ordre de fabrication utilisant une unité de lot de fabrication est créé pour calculer la quantité correcte des composants durant le traitement par lots **Actualiser O.F.**. Une situation dans laquelle un article fabriqué est stocké en pièces mais produit en tonnes est un exemple d'un calcul d'unité de mesure de lot de fabrication. Pour plus d'informations, voir [Utiliser les unités de mesure de lot de fabrication](production-how-to-use-the-manufacturing-batch-unit-of-measure.md).

## <a name="to-set-up-a-unit-of-measure"></a>Pour configurer une unité de mesure
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Articles**, puis sélectionnez le lien connexe.
2. Ouvrez la fiche article pour laquelle vous souhaitez configurer des unités de mesure de remplacement.
3. Choisissez l'action **Unités de mesure**. La fenêtre **Unités de mesure article** s'ouvre.
4. Si le champ **Unité de mesure de base** de la fiche article est renseigné, cette unité de mesure est déjà configurée.
5. Sélectionnez l'action **Nouveau**. Une nouvelle ligne vide est insérée.
6. Dans le champ **Code**, entrez le nom de l'unité de mesure. Sinon, sélectionnez le champ pour choisir parmi les codes unité de mesure figurant dans la base de données.
7. Dans le champ **Quantité par unité de mesure** entrez le nombre d'unités de l'unité de mesure de base que la nouvelle unité de mesure contient.
8. Répétez les étapes 5 à 7 pour configurer toutes les autres unités de mesure que vous souhaitez utiliser dans les différents processus de cet article.

Vous pouvez maintenant utiliser les unités de mesure de remplacement sur les documents achat, production et vente. Pour plus d'informations, voir Saisir des codes unité de mesure par défaut pour des transactions d'achat et de vente ou Utiliser l'unité de mesure de lot de fabrication.

## <a name="to-set-up-unit-of-measure-translations"></a>Pour configurer des traductions d'unités de mesure
Lorsque vous vendez des articles à des clients étrangers, vous pouvez être amené à indiquer l'unité de mesure dans leur langue. Pour cela, vous devez d'abord configurer les traductions d'unités de mesure nécessaires.

1. Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), saisissez **Unités de mesure**, puis sélectionnez le lien connexe.
2. Sélectionnez le code pour lequel vous souhaitez définir des traductions, puis cliquez sur **Traductions**.
3. Dans le champ **Code langue**, sélectionnez la flèche déroulante pour visualiser la liste des codes langue disponibles. Sélectionnez le code langue pour lequel vous souhaitez entrer une traduction, puis choisissez le bouton OK pour copier le code dans le champ.
4. Dans le champ **Description**, saisissez le texte approprié.
5. Répétez les étapes 2 à 4 pour les langues et les codes unité de mesure pour lesquels vous souhaitez indiquer des traductions.

## <a name="to-enter-a-default-unit-of-measure-code-for-sales-and-purchasing-transactions"></a>Pour entrer un code unité de mesure par défaut pour des transactions de ventes et d'achat
Si vous utilisez habituellement d'autres unités de mesure que l'unité de mesure de base pour vos achats et vos ventes, vous pouvez indiquer des unités de mesure distinctes. Pour cela, vous devez configurer les unités de mesure dans la fenêtre **Unités de mesure article**.

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Articles**, puis sélectionnez le lien connexe.
2. Ouvrez la fiche article appropriée pour laquelle vous souhaitez indiquer un code unité de mesure par défaut pour les achats et les ventes.
3. Pour les ventes, sur le raccourci **Facturation**, dans le champ **Unité de mesure de vente**, ouvrez la fenêtre **Unités de mesure article**.
4. Pour les achats, sur le raccourci **Réapprovisionnement**, dans le champ **Unité de mesure d'achat**, ouvrez la fenêtre **Unités de mesure article**.
5. Sélectionnez le code que vous souhaitez configurer comme unité de mesure par défaut pour les ventes ou les achats respectivement, puis cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi
[Utiliser les unités de mesure de lot de fabrication](production-how-to-use-the-manufacturing-batch-unit-of-measure.md)  
[Gestion du stock](inventory-manage-inventory.md)  
[Gestion des achats](purchasing-manage-purchasing.md)  
[Gestion des ventes](sales-manage-sales.md)    
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
