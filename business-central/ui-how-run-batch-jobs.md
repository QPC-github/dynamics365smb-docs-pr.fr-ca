---
title: Exécuter des traitements en lot et des objets XMLport
description: 'Vous exécutez des traitements en lot pour traiter les données et mettre à jour les informations, par exemple, pour élaborer des activités de comptabilité périodiques ou effectuer des calculs.'
author: SusanneWindfeldPedersen
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'task, process'
ms.search.form: '672, 676, 682'
ms.date: 04/01/2021
ms.author: solsen
---
# <a name="run-batch-jobs-and-xmlports" />Exécuter des traitements en lot et des objets XMLport

Un traitement par lots est une routine qui traite les données par lots, par exemple le traitement par lots **Ajuster taux de change**. Il existe des traitements en lot qui exécutent des activités de comptabilité périodiques, comme la fermeture de l'état des résultats à la fin d'un exercice financier. De nombreux traitements en lot exécutent des calculs, tels que le calcul des frais financiers, l'ajustement du taux de change et le calcul des prix unitaires.

Un traitement en lot est similaire à un rapport, sauf qu'il utilise les résultats obtenus pour mettre à jour les informations directement plutôt que d'imprimer les résultats.

Vous pouvez programmer l'exécution d'un traitement en lot. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

## <a name="to-run-a-batch-job" />Pour exécuter un traitement en lot
1. Pour ouvrir la page de demande du traitement en lot concerné, sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez le nom du traitement en lot, puis choisissez le lien associé.
2. Si un raccourci **Options** est disponible pour le traitement par lots, renseignez-en les champs pour déterminer les tâches effectuées par le traitement par lots.
3. La page peut inclure un ou plusieurs raccourcis avec des filtres que vous pouvez utiliser pour limiter les données incluses dans le traitement en lot. Pour cela, entrez des critères dans les filtres suggérés ou ajoutez des filtres supplémentaires.
4. Pour démarrer le traitement en lot, cliquez sur le bouton **OK**.

## <a name="see-also" />Voir aussi
[Tri, recherche et filtrage de listes](ui-enter-criteria-filters.md)  
[Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
