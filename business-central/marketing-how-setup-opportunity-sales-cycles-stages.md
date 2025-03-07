---
title: Configurer des cycles de vente opportunité et des phases de cycle
description: 'Décrit comment définir des phases de ventes, à partir du contact initial jusqu''à la fermeture, créer un cycle de vente et l''affecter aux opportunités dans Business Central.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'relationship, prospect'
ms.search.forms: '5122, 5121, 5120, 5175, 5119, 5098, 5096'
ms.date: 05/27/2022
ms.author: jswymer
---
# <a name="set-up-opportunity-sales-cycles-and-cycle-stages" />Configurer des cycles de vente opportunité et des phases de cycle

Avant d’utiliser les opportunités de vente, vous devez configurer les cycles de vente et les phases correspondantes. Un cycle de vente est composé d'une série d'étapes allant du contact initial à la fermeture d'une vente. Pour chaque phase, vous définissez les exigences à respecter, par exemple exiger un devis, avant qu’une opportunité puisse accéder à la phase suivante. Vous pouvez également spécifier si une phase peut être ignorée. Vous pouvez créer autant de cycles de vente que nécessaire. Vous pouvez configurer autant de phases de cycle de vente que nécessaire dans un cycle de vente.

Pour utiliser des cycles de vente opportunité, vous devez configurer le cycle de vente, définir les différentes phases du cycle, puis affecter le cycle à des opportunités. L'affectation de l'activité ou des tâches correspondantes à l'opportunité peut également faire partie de la configuration d'un cycle de vente.

Cet article décrit également comment configurer des tâches et les activités, et comment affecter des tâches aux activités. Pour plus d'informations, voir [Pour configurer des activités avec des tâches](marketing-how-setup-opportunity-sales-cycles-stages.md#to-set-up-activities-with-tasks).

## <a name="to-set-up-opportunity-sales-cycle-codes" />Pour configurer des cycles de vente opportunité

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Cycles vente**, puis sélectionnez le lien associé. La page **Cycles de vente** s'affiche, et répertorie tous les cycles de vente existants.
2. Sélectionnez l'action **Nouveau**, puis renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Répétez ces étapes pour chaque cycle de vente à configurer. Une fois les cycles de vente opportunité configurés, vous pouvez définir les différentes étapes de chaque cycle.

## <a name="to-define-opportunity-sales-cycle-stages" />Pour définir les étapes du cycle de vente opportunité

1. Sur la page **Cycles de vente**, sélectionnez le cycle de vente opportunité pour lequel vous souhaitez définir des phases, puis sélectionnez l'action **Phases**. La page **Phases du cycle de vente** s'affiche.
2. Sélectionnez l'action **Nouveau** pour intégrer une nouvelle étape dans le cycle de vente.

Répétez ces étapes pour définir toutes les étapes du cycle de vente.

## <a name="to-assign-stage-cycles-to-opportunities" />Pour affecter des cycles de phase à des opportunités

Après avoir ajouté le cycle d'étapes opportunité, vous pouvez commencer à ajouter des opportunités de vente, puis affecter le cycle d'étapes aux opportunités en définissant le champ **Code cycle de vente**. Pour plus d'informations, voir [Créer des opportunités de vente](marketing-how-create-opportunities.md).

## <a name="to-set-up-activities-with-tasks" />Pour configurer des activités avec des tâches

Vous pouvez combiner plusieurs tâches, par exemple les tâches qui représentent chacune une étape, dans les activités. Les tâches d'activité sont liées entre elles par une formule de date. Vous pouvez affecter des activités aux opportunités, aux représentants ou aux contacts.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Activités**, puis choisissez le lien associé.
2. Sélectionnez l'action **Nouveau**, puis renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
3. Sur le raccourci **Lignes**, renseignez les champs nécessaires pour définir une ou plusieurs tâches dans l'activité.

## <a name="to-assign-tasks-or-activities-of-tasks-to-opportunities" />Pour affecter des tâches ou des activités de tâches liées aux opportunités

Lorsque vous avez créé une tâche, vous pouvez l'affecter à une opportunité de vente et affecter ainsi l'activité à laquelle la tâche appartient.

> [!NOTE]
> Vous ne pouvez pas créer de tâches de type *Réunion* dans [!INCLUDE [prod_short](includes/prod_short.md)] en ligne. La fonctionnalité nécessite l’accès à un déploiement sur site.

La procédure suivante explique comment affecter des tâches d’activité à des opportunités. Les étapes sont similaires lorsque vous affectez des tâches aux représentants et aux contacts.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Opportunités**, puis choisissez le lien associé.
2. Sélectionnez une opportunité, puis cliquez sur **Tâches**.
3. Sur la page **Liste des tâches**, sélectionnez l'action **Créer Tâche**.
4. Sur la page **Créer Tâche**, renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

    > [!TIP]
    > Comme vous pouvez le constater dans le champ **Opportunité**, la tâche est automatiquement affectée à l’opportunité correspondante.
5. Cliquez sur le bouton **OK**.
6. Sur la page **Liste des tâches**, sélectionnez la nouvelle tâche, puis sélectionner l'action **Affecter activités**.
7. Sur la page **Affecter activités**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

## <a name="see-also" />Voir aussi

[Traitement des opportunités de vente](marketing-processing-sales-opportunities.md)  
[Vente](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
