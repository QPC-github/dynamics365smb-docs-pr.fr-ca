---
title: "Procédure : utiliser les périodes d'inventaire | Microsoft Docs"
description: "Vous pouvez contrôler le délai de report des modifications de l'inventaire en définissant des périodes d'inventaire."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: inventory, periods
ms.date: 08/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 8f9c289f4fef06ef0b684dd7176630d29b2fc5d3
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-work-with-inventory-periods"></a>Procédure : utiliser les périodes inventaire
Les périodes d'inventaire sont des périodes au cours desquelles vous pouvez reporter des modifications d'inventaire. Une période d'inventaire est définie par la date à laquelle elle se termine (date fin). Lorsque vous fermez une période d'inventaire, vous ne pouvez pas reporter de modifications d'inventaire, qu'elles soient prévues ou facturées, avant cette date fin. Vous ne pouvez pas reporter de nouvelles valeurs dans l'inventaire avant la date de fin. Si vous avez des écritures du grand livre d'articles ouvertes dans la période fermée, ce qui signifie des quantités positives qui n'ont pas encore été affectées sur des transactions sortantes, vous pouvez encore affecter des quantités sortantes sur ces écritures, même si la période est fermée.  

Les sections suivantes décrivent comment :  

* Créer des périodes inventaire.  
* Fermer des périodes d'inventaire.  
* Rouvrir des périodes inventaire.  

## <a name="to-create-an-inventory-period"></a>Pour créer une période d'inventaire  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Périodes d'inventaire**, puis sélectionnez le lien associé.  
2. Créez une ligne.  
3. Dans le champ **Date fin**, entrez la dernière date que vous voulez définir pour la période inventaire. Une fois la période fermée, vous ne pouvez plus reporter de modifications d'inventaire antérieures à cette date.  
4. Saisissez un nom descriptif dans le champ **Nom**. Cliquez sur le bouton **OK**.  

## <a name="closing-inventory-periods"></a>Fermeture de périodes d'inventaire  
Le champ **Clôturé** indique si la période inventaire est clôturée ou non sur des modifications de valeur de stock. Vous ne pouvez pas modifier ce champ.  

Vous pouvez fermer toute période d'inventaire, pour autant que les conditions suivantes soient vraies :  

* Il n'y a pas d'écritures du grand livre d'articles sortantes ouvertes (inventaire négatif) dans cette période.  
* Le coût de tous les articles a été ajusté à l'aide du traitement par lots **Ajuster coût écritures article**.  

Cela signifie que toutes les quantités de transaction sortante, telles que celles des documents de vente, transferts sortants, factures vente, retours achat ou notes de crédit achat doivent être affectées à la quantité en inventaire.  

### <a name="to-close-an-inventory-period"></a>Pour fermer une période d'inventaire  
1. Avant de clôturer une période inventaire, exécutez le traitement par lot **Ajuster coût écritures article** pour vous assurer que tous les ajustements des coûts sont validés. Sur l'onglet **Actions**, dans le groupe **Fonctions**, choisissez **Ajuster coût écritures article**.  

     Exécutez l'état **Clôturer période inventaire – Test** pour déterminer s'il y a des écritures article sortant ouvertes dans la période inventaire ou des articles dont le coût n'a pas encore été ajusté.  
2. Choisissez l'action **Fermer la période d'inventaire - Test**.  

     Exécutez le traitement en lot **Reporter le coût de l'inventaire au grand livre** pour vous assurer que tous les coûts sont reportés dans le grand livre.  
3. Cliquez sur l'action **Reporter inventaire en grand livre**.  
4. Ouvrez la fenêtre **Périodes d'inventaire** et sélectionnez la période d'inventaire que vous voulez fermer.  
5. Choisissez l'action **Fermer la période**. Une fois la période d'inventaire fermée, vous ne pouvez pas reporter de modifications d'inventaire avant la date de fin. Le coût de tous les articles doit être ajusté avec le traitement par lots **Ajuster coût écritures article** avant la clôture de la période inventaire.  
6. Choisissez le bouton **Oui** pour confirmer la clôture de la période, ou choisissez **Non** pour annuler la clôture.  
7. La période d'inventaire est fermée et un message de confirmation est affiché une fois l'opération terminée.  

## <a name="reopening-inventory-periods"></a>Réouverture de périodes inventaire  
Une fois la période d'inventaire fermée, vous ne pouvez plus la supprimer. En revanche, vous pouvez la rouvrir si vous voulez autoriser son report avant la date fin. La réouverture d'une période rouvre également toutes les périodes inventaire dont la date fin est postérieure à la fin de la période que vous rouvrez.  

### <a name="to-reopen-an-inventory-period"></a>Pour rouvrir une période d'inventaire  
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Périodes inventaire**, puis sélectionnez le lien connexe.  
2. Sélectionnez la période d'inventaire que vous voulez rouvrir.  
3. Sélectionnez l'action de la période **Rouvrir période**. Confirmez que vous voulez réouvrir la période.  
4. Toutes les périodes inventaire dont la date fin est postérieure à la fin de la période sélectionnée sont réouvertes.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : périodes inventaire](design-details-inventory-periods.md)  
[Finance](finance.md)  
[Stocks](inventory-manage-inventory.md)  
[Utilisation de Financials](ui-work-product.md)
