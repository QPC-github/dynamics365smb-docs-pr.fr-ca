---
title: "Procédure\_: utiliser les centres de gestion"
description: 'Le centre de gestion, en tant que centre administratif, aide les compagnies à définir des vues spécifiques à l’utilisateur des documents vente et achat associés exclusivement d’un centre à l’autre.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.forms: '5714, 5715'
ms.date: 03/09/2023
ms.author: bholtorf
---
# <a name="work-with-responsibility-centers" />Utiliser les centres de gestion

Les centres de gestion permettent de gérer les centres administratifs. Un centre de gestion peut être un centre de coûts, un centre de profit, un centre d'investissement ou tout autre centre administratif défini par la compagnie. Un bureau de vente, un département d'achat pour plusieurs emplacements, un bureau de planification d'usine, etc. sont des exemples de centres de gestion. Par exemple, les compagnies peuvent paramétrer des vues spécifiques à l’utilisateur des documents de vente et achat associés à un centre de gestion particulier.  

L’utilisation de plusieurs emplacements avec des centres de gestion permet de gérer les activités commerciales de façon flexible et optimale.

Des emplacements multiples permettent aux compagnies de gérer leur inventaire dans plusieurs emplacements au moyen d'une seule base de données. Deux concepts, des magasins et des points de stock, sont les pierres angulaires du granule. Un emplacement est défini comme un lieu qui gère l'emplacement physique et la quantité des articles. Le concept est assez étendu pour inclure des magasins tels que les usines ou les unités de fabrication et les centres de distribution, les entrepôts, les magasins d'exposition et les véhicules de service. Une unité de stock est définie comme un article à un emplacement spécifique et/ou comme une variante. Grâce aux unités de stock, les compagnies utilisant plusieurs emplacements peuvent ajouter des informations de réapprovisionnement, des adresses et des informations financières de report au niveau de l’emplacement. Elles peuvent ainsi réapprovisionner les variantes du même article dans chaque emplacement et commander des articles pour chaque emplacement d’après les informations de réapprovisionnement spécifiques de l’emplacement.  

## <a name="to-set-up-a-responsibility-center" />Pour configurer un centre de gestion

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Centres de gestion**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    Si vous utilisez des centres de gestion pour administrer votre compagnie, il peut être utile de définir un centre de gestion par défaut.
4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Informations sur la compagnie**, puis sélectionnez le lien associé.
5. Dans le champ **Centre de gestion**, entrez un code centre de gestion.

Ce code est utilisé sur tous les documents achat, vente ou service si l’utilisateur, le client ou le fournisseur n’a pas de centre de gestion par défaut. Sur un document vente, achat ou service, vous pouvez saisir un autre centre de gestion à la place de la valeur par défaut.

> [!NOTE]  
> Lorsque vous saisissez un code centre de gestion sur un document, le programme affecte l'adresse, les axes et les prix indiqués sur le document.  

## <a name="to-assign-responsibility-centers-to-users" />Pour affecter des centres de gestion à des utilisateurs

Vous pouvez configurer des utilisateurs de sorte que [!INCLUDE [prod_short](includes/prod_short.md)] récupère uniquement les documents propres à leur activité. Les utilisateurs sont généralement associés à un centre de gestion et utilisent uniquement les documents propres à des modules spécifiques de ce centre.  

Pour configurer cela, vous devez affecter des centres de gestion à des utilisateurs dans trois modules : Achats, Ventes et Gestion des services.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration utilisateur**, puis choisissez le lien associé.  
2. Sur la page **Configuration des utilisateurs**, sélectionnez l'utilisateur auquel vous souhaitez affecter un centre de gestion. Si l'utilisateur ne figure pas dans la liste, saisissez un code utilisateur dans le champ **Code utilisateur**.  
3. Dans le champ **Filtre centre gestion vente**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées aux ventes.  
4. Dans le champ **Filtre centre gestion achat**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées aux achats.  
5. Dans le champ **Filtre centre gestion service**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées à la gestion des services.  

> [!NOTE]  
> Les utilisateurs peuvent afficher uniquement les documents reportés liés à leur propre centre de responsabilité. Cependant, ils peuvent afficher toutes les écritures et accéder à d’autres documents reportés à partir des écritures.

## <a name="see-related-microsoft-trainingtrainingmodulesset-up-responsibility-centers" />Voir la [formation Microsoft](/training/modules/set-up-responsibility-centers/) associée

## <a name="see-also" />Voir aussi .

[Configuration de stock](inventory-setup-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Définir une stratégie de report des factures pour les utilisateurs](admin-setup-invoice-posting-policy.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
