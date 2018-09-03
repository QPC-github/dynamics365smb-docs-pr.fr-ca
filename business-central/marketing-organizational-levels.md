---
title: "Configurer des niveaux hiérarchiques pour les contacts| Microsoft Docs"
description: "Vous pouvez définir un niveau hiérarchique et l'affecter à vos contacts pour indiquer leur position au sein de leur compagnie, par exemple, la direction générale."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, client, prospect
ms.date: 06/06/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 974133ffb0324cf6bc3ed37436adb9fb237f5e4d
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-organizational-levels-for-contact-persons"></a>Configurer des niveaux hiérarchiques pour les personnes contact
Vous pouvez utiliser les niveaux hiérarchiques sur vos contacts pour spécifier leur position au sein de la compagnie, par exemple, la direction générale. Vous pouvez utiliser ces informations lors de la saisie de données sur vos contacts.

L'utilisation de niveaux hiérarchiques sur les contacts est un processus en deux étapes. Tout d'abord, vous définissez le code de niveau hiérarchique. Vous ne devez effectuer cette étape qu'une seule fois pour niveau hiérarchique. Une fois que vous disposez d'un code de niveau hiérarchique, vous pouvez commencer à affecter ce code aux personnes contact.

## <a name="to-define-an-organizational-level-code"></a>Pour définir un code de niveau hiérarchique
Le code de niveau hiérarchique définit le type ou la catégorie du niveau hiérarchique, par exemple PDG ou DF. Vous pouvez disposer de plusieurs codes de niveau hiérarchique. Pour définir le niveau hiérarchique, vous utilisez la fenêtre **Niveaux organisationnels**.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Niveaux organisationnels**, puis sélectionnez le lien connexe.
2. Sélectionnez l'action **Nouveau**, et entrez un code et une description. Vous pouvez saisir pour le code un maximum de 11 caractères, et toute combinaison de chiffres et des lettres.

## <a name="to-assign-organizational-levels-to-a-contact-person"></a>Pour affecter des niveaux hiérarchiques à une personne contact
Vous pouvez affecter des niveaux hiérarchiques à des personnes contact uniquement, mais pas aux compagnies contact. Vous ne pouvez affecter qu'un niveau hiérarchique par contact.

1. Ouvrez le contact.
2. Dans le champ **Niveaux organisationnels**, sélectionnez le code à affecter.

Une fois que vous avez affecté des niveaux hiérarchiques à vos contacts, vous pouvez utiliser ces données pour créer des segments.

Une fois que vous avez affecté des responsabilités à vos contacts, vous pouvez utiliser ces informations pour sélectionner des contacts pour vos segments. Pour plus d'informations, reportez-vous à [Ajouter des contacts à des segments](marketing-add-contact-segment.md).

## <a name="see-also"></a>Voir aussi
[Création de sociétés contact](marketing-create-contact-companies.md)  
[Création de personnes contact](marketing-create-contact-persons.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
