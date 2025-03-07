---
title: Utilisation des nomenclatures d’assemblage
description: Vous créez une nomenclature d’assemblage pour spécifier les composantes nécessaires pour assembler l’article que la nomenclature représente.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'assembly bom, bills of material,'
ms.search.form: '36, 5870, 5872, 5874'
ms.date: 09/26/2022
ms.author: edupont
---
# <a name="work-with-assembly-boms" />Utilisation des nomenclatures d’assemblage

Les nomenclatures d’assemblage permettent de structurer les articles parents qui doivent être assemblés à partir de composantes, avec peu ou pas de ressources utilisées. Une nomenclature d’assemblage peut être utilisée, par exemple, pour vendre un article parent sous la forme d’un kit constitué de composantes.

Vous utilisez des ordres d'assemblage pour fabriquer des produits finis à partir de composants dans le cadre d'un processus simple qui peut être exécuté par une ou plusieurs ressources de base, qui ne sont pas des postes ou centres de charge, ou sans ressource. Par exemple, un processus d'assemblage peut consister à prélever deux bouteilles de vin et un sachet de café puis à les emballer comme article de cadeau.  

Une nomenclature d'assemblage contient les données de base qui définissent les composantes d'un produit fini assemblé, ainsi que les ressources utilisées pour assembler l'élément d'assemblage. Lorsque vous entrez un élément d'assemblage et une quantité dans l'en-tête d'un nouvel ordre d'assemblage, les lignes d'ordre d'assemblage sont renseignées automatiquement d'après la nomenclature d'assemblage, avec une ligne d'ordre d'assemblage par composante ou ressource. Pour en savoir plus, voir [Gestion d’assemblage](assembly-assemble-items.md).

[!INCLUDE[prod_short](includes/prod_short.md)] prend également en charge les nomenclatures de production. Les nomenclatures de production diffèrent des nomenclatures d’assemblage en impliquant des procédures plus complexes, notamment l’utilisation des ressources, les itinéraires de production et les centres ou unités de production. Découvrez les différences dans les sections [Utiliser les nomenclatures](inventory-how-work-BOMs.md) et [Créer des nomenclatures de production](production-how-to-create-production-boms.md).

## <a name="to-create-an-assembly-bom" />Pour créer une nomenclature d'assemblage

Pour définir un article parent constitué d'autres articles, et potentiellement des ressources nécessaires pour regrouper les articles parents, vous devez créer une nomenclature d'assemblage.  

Les nomenclatures d'assemblage contiennent généralement des articles mais peuvent également contenir une ou plusieurs ressources requises pour regrouper les articles d'assemblage.

Les nomenclatures d'assemblage peuvent être multiniveaux, ce qui signifie qu'une composante de la nomenclature d'assemblage peut être un élément d'assemblage proprement dit. Dans ce cas, le champ **Nomencl d'élément d'assemblage** de la ligne nomenclature d'assemblage contient **Oui**.

Des exigences spécifiques s’appliquent aux articles des nomenclatures d’assemblage en ce qui concerne la disponibilité. Pour plus d’informations, consultez [Pour afficher la disponibilité d’un article en fonction de son utilisation dans les nomenclatures d’assemblage](inventory-how-availability-overview.md#to-view-the-availability-of-an-item-by-its-use-in-assembly-or-production-boms).

Il y a deux parties pour créer une nomenclature d'assemblage :

- Configuration d'un nouvel article
- Définition de la structure de la nomenclature de l'article d'assemblage.

1. Configurez un nouvel article. En savoir plus sur [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).

   Entrez maintenant les composants ou les ressources de la nomenclature d'assemblage.  
2. Sur la page **Fiche article** d’un article d’assemblage, sélectionnez l’action **Assemblage**, puis l’action **Nomenclature d’assemblage**.
3. Renseignez les champs nécessaires sur la page **Nomenclature d'assemblage**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> Les éléments d’assemblage peuvent avoir différentes variantes définies dans [!INCLUDE[prod_short](includes/prod_short.md)], comme tout autre article, ce qui vous aide à réduire la liste des produits disponibles. Découvrez plus d’informations sur la fonctionnalité dans la section [Gérer les variantes de produits](inventory-item-variants.md).

## <a name="to-edit-assembly-boms" />Pour modifier les nomenclatures d'assemblage

Vous pouvez modifier les lignes d'une nomenclature d'assemblage à tout moment. Mais sachez que la nomenclature peut être utilisée sur les ventes en cours ou les assemblages du parent, qui peuvent être affectés par le changement. Sélectionnez l'action **Cas d'emploi** pour voir dans quels articles elle est utilisée et si les ordres d'assemblage ou de vente peuvent être affectés.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.
2. Sélectionnez **Oui** dans la colonne **Nomenclature d'assemblage**.
3. Sur la page **Nomenclature d’assemblage**, sélectionnez l’action **Modifier la liste**, puis modifiez n’importe quel champ selon vos besoins.

## <a name="to-view-components-and-resources-indented-according-to-the-bom-structure" />Pour afficher les composantes et les ressources décalés selon la structure de la nomenclature

Sur la page **Nomenclature d'assemblage**, vous pouvez ouvrir une page distincte qui affiche les composantes et les ressources décalées selon la position de leur nomenclature sous l'article d'assemblage.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.
2. Ouvrez la fiche d'un article d'assemblage. (Le champ **Nomenclature d'assemblage** sur la page **Articles** contient **Oui**.)
3. Sur la page **Fiche article**, sélectionnez l’action **Assemblage**, puis l’action **Nomenclature d’assemblage**.
4. Sur la page **Nomenclature d'assemblage**, sélectionnez l'action **Afficher nomenclature**.

## <a name="to-replace-the-assembly-item-with-its-components-on-document-lines" />Pour remplacer l'article d'assemblage par ses composantes dans les lignes document

Dans n'importe quel document vente et achat qui contient un élément d'assemblage, vous pouvez utiliser une fonction spéciale pour remplacer la ligne de l'élément d'assemblage par de nouvelles lignes pour ses composantes. Cette option est utile, par exemple, si vous souhaitez vendre des composantes sous forme de kit représentant l'élément d'assemblage.

L’action **Éclater nomenclature** est également disponible sur la page **Nomenclature d’assemblage** en tant que moyen d’afficher les éléments d’assemblage enfants sur une nomenclature d’assemblage.

> [!CAUTION]  
> Lorsque vous avez utilisé la fonction **Éclater nomenclature**, vous ne pouvez pas facilement l'annuler. Vous devez supprimer les lignes document de vente représentant les composantes, puis réentrer une ligne document de vente de l'élément d'assemblage.

La procédure suivante se base sur une facture vente. Les mêmes étapes s’appliquent à d’autres documents vente et à tous les documents achat.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures vente**, puis sélectionnez le lien associé.
2. Ouvrez une facture vente qui contient une ligne pour un élément d'assemblage.
3. Sélectionnez la ligne pour un élément d’assemblage, puis la ligne d’action **Éclater nomenclature**.

Tous les champs de la ligne facture vente pour l'élément d'assemblage sont désactivés sauf les champs **Article** et **Description**. Les lignes facture vente renseignées sont insérées pour les composantes et les éventuelles ressources qui composent l'élément d'assemblage.

> [!NOTE]
> Le rapport **Liste de prélèvement par ordre** est également modifié pour afficher uniquement les composantes. Cela signifie qu'un magasinier qui choisit l'article parent, l'élément d'assemblage, ne le verra pas dans la liste de prélèvement. Pour plus d’informations, consultez [Imprimer la liste des prélèvements](sales-how-print-picking-list.md).

## <a name="to-calculate-the-standard-cost-of-an-assembly-item" />Pour calculer le coût standard d'un élément d'assemblage

Vous calculez le coût unitaire d’un élément d’assemblage en regroupant le coût unitaire de chaque composante et ressource dans la nomenclature d’assemblage de l’article.

Vous pouvez également calculer et mettre à jour le coût standard pour un ou plusieurs articles sur la page **Feuille coût standard**. Pour plus d’informations, consultez [Mise à jour des coûts standard](finance-how-to-update-standard-costs.md).  

Le coût unitaire d'une nomenclature d'assemblage équivaut toujours au total des coûts unitaires de ses composantes, y compris ceux d'autres nomenclatures d'assemblage, et des ressources.  

> [!NOTE]
> [!INCLUDE [bom-standard-cost](includes/bom-standard-cost.md)]

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.
2. Ouvrez la fiche d'un article d'assemblage. (Le champ **Nomenclature d'assemblage** sur la page **Articles** contient **Oui**.)
3. Sur la page **Fiche article**, sélectionnez l’action **Assemblage**, puis l’action **Nomenclature d’assemblage**.
4. Sur la page **Nomenclature d'assemblage**, sélectionnez l'action **Calculer coût standard**.
5. Sélectionnez l’une des options suivantes, puis choisissez le bouton **OK**.

|Option |Désignation |
|-------|------------|
|**Niveau supérieur**|Calcule le coût standard de l'élément d'assemblage en tant que coût total de tous les articles achetés ou assemblés de cette nomenclature d'assemblage sans tenir compte de toutes les nomenclatures d'assemblage sous-jacentes.|
|**Tous niveaux**|Calcule le coût standard de l'élément d'assemblage comme la somme des éléments suivants : 1) Coût calculé de toutes les nomenclatures d'assemblage sous-jacentes dans la nomenclature d'assemblage. 2) Coût de tous les articles achetés dans la nomenclature d'assemblage.|

Les coûts des articles constituant la nomenclature d'assemblage sont copiés à partir des fiches article de la composante. Le coût de chaque article est multiplié par sa quantité, et le coût total est affiché dans le champ **Coût unitaire** sur la fiche article.

## <a name="see-related-microsoft-trainingtrainingmodulesset-up-assembly-items-dynamics-365-business-central" />Voir la [formation Microsoft](/training/modules/set-up-assembly-items-dynamics-365-business-central/) associée.

## <a name="see-also" />Voir aussi .

[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Gérer les variantes de produits](inventory-item-variants.md)  
[Voir la disponibilité des articles](inventory-how-availability-overview.md)  
[Stock](inventory-manage-inventory.md)  
[Utiliser les nomenclatures](inventory-how-work-BOMs.md)  
[Créer des nomenclatures de production](production-how-to-create-production-boms.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
