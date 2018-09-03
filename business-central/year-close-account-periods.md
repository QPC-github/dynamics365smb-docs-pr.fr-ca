---
title: "Fermer des périodes comptables pour un exercice financier | Microsoft Docs"
description: "Décrit comment fermer les périodes comptables de l'exercice financier."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 06/02/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 23a9cd7a8a7f579f63937ac4fc28e6d4958f3f9a
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="close-accounting-periods"></a>Fermer des périodes comptables
Lorsqu'un exercice financier est terminé, vous devez fermer les périodes qui le composent.

## <a name="to-close-accounting-periods"></a>Pour fermer des périodes comptables
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Périodes comptables**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Périodes comptables**, sélectionnez l'action **Clôturer exercice**.

    Si plusieurs exercices financiers sont ouverts, le plus ancien est automatiquement sélectionné pour la fermeture. Un message identifiant l'exercice qu'il compte fermer s'affiche et indique les conséquences de la fermeture.
3. Pour clôturer l'exercice, cliquez sur **Oui**.

L'exercice comptable est désormais clôturé, et les champs **Fermé** et **Verrouillage date** sont sélectionnés pour toutes les périodes de l'exercice. Vous ne pouvez pas rouvrir l'exercice comptable ni supprimer la coche des champs **Fermé** et **Verrouillage date**.

> [!NOTE]  
>   Vous ne pouvez pas fermer un exercice financier avant d'en avoir créé un nouveau. Sachez que lorsqu'un exercice financier est fermé, vous ne pouvez pas modifier la date début de l'exercice financier suivant.

Même si un exercice financier a été fermé, vous pouvez toujours y reporter des écritures. Dans ce cas, les écritures sont marquées comme validées dans un exercice comptable clôturé et le champ **Ecr. exercice précédent** est activé.

Une fois qu'un exercice financier a été fermé, vous devez fermer les comptes d'état des résultats et transférer les résultats de l'exercice sur un compte du bilan. Vous pouvez répéter cette opération chaque fois que vous effectuez un report dans l'exercice financier fermé.

## <a name="see-also"></a>Voir aussi
[Clôture plans](year-close-books.md)  
[Reporter l'écriture de fermeture d'exercice](year-how-post-year-end-close-entry.md)  
[Ouvrir un nouvel exercice financier](finance-how-open-new-fiscal-year.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
