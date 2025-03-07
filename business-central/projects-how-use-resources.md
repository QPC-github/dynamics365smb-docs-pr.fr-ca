---
title: Enregistrer et ajuster l’utilisation et les prix des ressources
description: 'Décrit la manière dont vous pouvez enregistrer l''utilisation ou la consommation ressource associée à un projet, de garder la trace et de gérer les coûts, les prix, ainsi que les types de travaux.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'project management, capacity, staff'
ms.search.form: '201,206, 207, 271, 493'
ms.date: 03/08/2023
ms.author: edupont
---
# <a name="use-resources-for-jobs" />Utiliser des ressources pour des projets

Vous devez enregistrer l'utilisation des ressources dans le journal projet pour suivre les coûts et les prix, ainsi que les types de travaux associés aux projets. Pour plus d'informations, voir [Enregistrer l'utilisation pour les projets](projects-how-record-job-usage.md).

> [!NOTE]
> Vous pouvez également acheter des ressources externes, par exemple pour facturer un fournisseur pour le travail livré. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).

Vous pouvez aussi reporter l'utilisation d'une ressource dans un journal ressource. Les écritures reportées dans un journal ressource n'ont aucune incidence sur le grand livre.

## <a name="to-assign-resources-to-jobs" />Pour affecter des ressources aux projets

Vous pouvez affecter des ressources aux projets en créant des lignes planification projet pour le projet. Pour plus d'informations, voir [Créer des projets](projects-how-create-jobs.md).

## <a name="to-record-resource-usage-for-a-job" />Pour enregistrer l'utilisation des ressources pour un projet

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux projet**, puis choisissez le lien associé.
2. Ouvrez le lot journal projet approprié, puis complétez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Lorsque la feuille est renseignée, cliquez sur **Valider**.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="to-adjust-resource-prices" />Pour ajuster le prix des ressources

Si vous souhaitez modifier le coût ou le prix d'un grand nombre de ressources, vous pouvez utiliser un traitement en lot.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ajuster coûts/prix ressource**, puis sélectionnez le lien associé.
2. Renseignez les autres champs selon vos besoins, puis cliquez sur le bouton **OK**.

> [!NOTE]  
> Ce traitement en lot ne crée pas et n'ajuste pas les nouveaux coûts ou prix des ressources. Il modifie uniquement le contenu du champ de la fiche ressource correspondant au champ **Champ à modifier** que vous avez sélectionné dans le traitement par lots. L'ajustement s'appliquant immédiatement aux ressources, vérifiez les facteurs d'ajustement avant de lancer le traitement en lot.

## <a name="to-get-resource-price-change-suggestions-based-on-existing-alternate-prices" />Pour obtenir des propositions de modification des prix ressource basées sur les prix secondaires existants

Si vous avez déjà configuré d'autres prix pour un certain nombre de ressources, vous pouvez utiliser un traitement en lot pour configurer d'autres prix ressource.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Nouv. prix ressource proposés**, puis choisissez le lien associé.
2. Sélectionnez l'action **Prop. modif. prix ress. (prix)**, puis renseignez les champs selon vos besoins.
3. Cliquez sur le bouton **OK**.  
4. Lorsque le traitement en lot est terminé, la page **Nouv. prix ressource proposés** affiche les résultats du traitement en lot.

## <a name="to-get-resource-price-change-suggestions-based-on-standard-prices" />Pour obtenir des propositions de modification des prix ressource basées sur les prix standard :

Si vous souhaitez configurer plusieurs autres prix ressource sur la base des prix standard des fiches ressource, vous pouvez utiliser un traitement en lot.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Nouv. prix ressource proposés**, puis choisissez le lien associé.
2. Sélectionnez l'action **Prop. modif. prix ress. (ress)**, puis renseignez les champs selon vos besoins.  
3. Cliquez sur le bouton **OK**.  
4. Lorsque le traitement en lot est terminé, ouvrez la page **Nouv. prix ressource proposés** pour visualiser les résultats du traitement en lot.

## <a name="to-get-resource-price-change-suggestions-based-on-alternate-prices" />Pour obtenir des propositions de modification des prix ressource basées sur les prix standard

Si vous avez déjà configuré d'autres prix pour un certain nombre de ressources, vous pouvez utiliser un traitement en lot pour configurer d'autres prix ressource.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Prop. modif. prix ress. (prix)**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins.
3. Cliquez sur le bouton **OK**.  
4. Lorsque le traitement en lot est terminé, ouvrez la page **Nouv. prix ressource proposés** pour visualiser les résultats du traitement en lot.

## <a name="see-also" />Voir aussi

[Gestion de projets](projects-manage-projects.md)  
[Finance](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)         
[Ventes](sales-manage-sales.md)     
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
