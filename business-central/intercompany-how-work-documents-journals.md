---
title: Reporter des documents et journaux intercompagnies | Microsoft Docs
description: Utiliser des documents intercompagnies pour reporter des transactions avec vos partenaires intercompagnies.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 06/07/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: e73c2dd0533aade4aa6225c9d2f385baaea3cfd1
ms.openlocfilehash: ab05b9d596af65936d81c649fbace0f250efe076
ms.contentlocale: fr-ca
ms.lasthandoff: 06/11/2018

---
# <a name="work-with-intercompany-documents-and-journals"></a>Utiliser les documents et les journaux intersociétés
Les documents ou journaux intercompagnies permettent de reporter les transactions effectuées avec vos partenaires intercompagnies. Lorsque vous reportez un document ou une ligne journal intercompagnie dans votre compagnie, le programme crée le document ou la ligne journal correspondante dans votre boîte d'envoi intercompagnie : vous pouvez le transmettre au partenaire concerné. Celui-ci peut ensuite reporter la transaction correspondante dans sa compagnie sans avoir à entrer à nouveau les données.

Pour les documents achat et vente, le code partenaire intercompagnie du client ou du fournisseur concerné garantit que toutes les commandes et factures générées en relation avec les transactions avec ces compagnies produisent des documents correspondants dans la compagnie partenaire. Il en résulte un équilibrage correct des comptes.

Dans le cas des lignes journal général intercompagnies, vous ne devez pas spécifier les comptes pour un ensemble de livres particulier, mais simplement fournir l'identification de la compagnie concernée. Les lignes journal général intercompagnie correspondantes sont alors créées dans la compagnie partenaire, ce qui entraîne l'équilibrage des livres des deux compagnies impliquées dans une transaction.

## <a name="to-fill-in-and-send-an-intercompany-sales-order"></a>Pour renseigner et envoyer un document de vente intercompagnie
Vous pouvez envoyer les documents de vente et les bons de commande, ainsi que les retours avant qu'ils soient reportés. En revanche, l'envoi des factures et notes de crédit est impossible tant qu'elles ne sont pas reportées.

La procédure suivante explique comment renseigner et envoyer un document de vente intercompagnie. La même procédure s'applique aux bons de commande intercompagnie et aux retours, ainsi qu'aux factures et notes de crédit intercompagnie reportés.  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.  
2. Sélectionnez **Nouveau** pour créer un document de vente. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Vérifiez que le client est un partenaire intercompagnie.
5. Pour envoyer le document de vente avant de le reporter, choisissez l'action **Envoi document de vente IC**.

> [!NOTE]
> Si vous effectuez l'étape 4, le document de vente est déplacé vers votre boîte d'envoi intercompagnies, d'où vous pouvez l'envoyer ultérieurement. Pour plus d'informations, voir [Gérer la boîte de réception et la boîte d'envoi intersociétés](intercompany-how-manage-intercompany-inbox.md).

## <a name="to-fill-in-and-post-an-intercompany-journal"></a>Pour renseigner et reporter un journal intercompagnie
Lorsque vous reportez une ligne journal général intercompagnie dans votre compagnie, le programme crée une ligne journal correspondante dans votre boîte d'envoi intercompagnie : vous pouvez la transmettre au partenaire concerné. Celui-ci peut ensuite reporter la transaction correspondante dans sa compagnie sans avoir à entrer à nouveau les données.

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journaux généraux intercompagnies**, puis sélectionnez le lien associé.  
2. Ouvrez le lot journal approprié. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Renseignez les champs selon vos besoins.
4. Dans le champ **N° compte G/L du partenaire IC**, saisissez le numéro du compte du grand livre intercompagnie sur lequel le montant sera reporté dans la compagnie de votre partenaire.

    > [!NOTE]
    > Ce champ doit être renseigné avec une ligne dont l'un des champs **N° compte** ou  **N° compte de solde** contient un compte bancaire ou un compte du grand livre.  
5. Sélectionnez l'action **Valider**.

Les écritures associées sont reportées dans votre compagnie et un journal avec les écritures correspondantes est créé dans votre boîte d'envoi intercompagnie ; vous pouvez l'envoyer à votre partenaire. Pour plus d'informations, voir [Gérer la boîte de réception et la boîte d'envoi intersociétés](intercompany-how-manage-intercompany-inbox.md).

## <a name="see-also"></a>Voir aussi
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
