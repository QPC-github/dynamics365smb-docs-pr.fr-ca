---
title: Utiliser les nomenclatures
description: Vous créez une nomenclature d'assemblage ou une nomenclature de production pour spécifier les composantes ou ressources nécessaires pour assembler l'article que la nomenclature représente.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'bills of material, assembly BOM, production BOM,'
ms.search.form: null
ms.date: 09/26/2022
ms.author: a-reishima
---
# <a name="work-with-bills-of-material" />Utiliser les nomenclatures

Les nomenclatures d’assemblage permettent de structurer les articles parents qui doivent être assemblés à partir d’autres articles ou produits par des ressources ou des unités de production à partir des composantes.

## <a name="assembly-boms-or-production-boms" />Nomenclatures d’assemblage ou nomenclatures de production

[!INCLUDE[prod_short](includes/prod_short.md)] prend en charge deux types différents de nomenclatures :

| Type de nomenclature | Catégorie générale | Exemple : |
| -------- | ---------------- | ------- |
| [Nomenclatures d’assemblage](assembly-how-work-assembly-boms.md) | Entrepôt / assemblage | Objets constitués d’autres objets, assemblés avec des ressources de base ou sans ressources. |
| [Nomenclatures de production](production-how-to-create-production-boms.md) | Fabrication / production | Articles constitués de différents composantes et sous-ensembles, produits au travail ou dans une unité de production. |

Vous utilisez des ordres d'assemblage pour fabriquer des produits finis à partir de composants dans le cadre d'un processus simple qui peut être exécuté par une ou plusieurs ressources de base, qui ne sont pas des postes ou centres de charge, ou sans ressource. Par exemple, un processus d'assemblage peut consister à prélever deux bouteilles de vin et un sachet de café puis à les emballer comme article de cadeau.  

Une nomenclature d'assemblage contient les données de base qui définissent les composantes d'un produit fini assemblé, ainsi que les ressources utilisées pour assembler l'élément d'assemblage. Lorsque vous entrez un élément d'assemblage et une quantité dans l'en-tête d'un nouvel ordre d'assemblage, les lignes d'ordre d'assemblage sont renseignées automatiquement d'après la nomenclature d'assemblage, avec une ligne d'ordre d'assemblage par composante ou ressource. Pour en savoir plus, voir [Gestion d’assemblage](assembly-assemble-items.md).

Vous utilisez des bons de production pour fabriquer des produits finis à partir de composantes dans le cadre d'un processus complexe nécessitant un itinéraire de fabrication et des ateliers ou unités de production, qui représentent les capacités de production. Par exemple, un processus de production peut être établi pour découper des plaques d'acier en une opération, les souder lors de l'opération suivante et peindre le produit fini lors de la dernière opération. En savoir plus sur [Fabrication](production-manage-manufacturing.md).

Une nomenclature de production contient les données de base qui définissent un article de production et ses composants. Pour les éléments d'assemblage, la nomenclature de production doit être certifiée et affectée à l'article de production avant de pouvoir être utilisée dans un bon de production. Lorsque vous entrez l'article produit dans une ligne bon de production, manuellement ou en actualisant la commande, le contenu de la nomenclature de production devient les composantes du bon de production En savoir plus sur [Créer des nomenclatures de production](production-how-to-create-production-boms.md).

Le concept de ressources est beaucoup plus avancé dans la production que dans la gestion d'assemblage. Les centres de charge et les postes de charge fonctionnent comme des ressources, et les étapes de production sont représentées par les opérations qui sont affectées à ces ressources dans des gammes de production. Pour en savoir plus, voir l’article [Créer des itinéraires](production-how-to-create-routings.md).

Les ordres d'assemblage et les ordres de fabrication peuvent être liés directement aux commandes vente. Cependant, vous pouvez uniquement utiliser des ordres d'assemblage pour personnaliser le produit fini directement par rapport à la demande d'un client via le document de vente.

## <a name="see-also" />Voir aussi .

[Utilisation des nomenclatures d’assemblage](assembly-how-work-assembly-boms.md)  
[Créer des nomenclatures de production](production-how-to-create-production-boms.md)  
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Gérer les variantes de produits](inventory-item-variants.md)  
[Stock](inventory-manage-inventory.md)  
[Production](production-manage-manufacturing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
