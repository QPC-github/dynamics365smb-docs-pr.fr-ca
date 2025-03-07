---
title: Programmer des projets à exécuter automatiquement
description: Découvrez comment utiliser les entrées de la file d’attente des tâches pour exécuter des rapports et des codeunits.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: conceptual
ms.date: 03/20/2023
ms.custom: bap-template
ms.search.form: '672, 673, 674, 671'
---
# <a name="use-job-queues-to-schedule-tasks" />Utiliser des files d'attente des travaux pour programmer des tâches

Utiliser la page **Écritures file d’attente des travaux** permet aux utilisateurs de programmer et d’exécuter des rapports et codeunits spécifiques. Vous pouvez définir des projets à exécuter une fois, ou sur une base récurrente. Par exemple, vous souhaiterez peut-être exécuter le rapport **Statistiques vente * représentant** sur une base hebdomadaire, pour suivre les ventes par représentant chaque semaine, ou exécuter le codeunit **Déléguer les demandes d’approbation** quotidiennement, pour empêcher les documents de s’empiler ou de bloquer le flux de travail.

La page Écritures file d'attente des travaux répertorie tous les projets existants. Si vous ajoutez une nouvelle écriture de file d’attente de travaux que vous souhaitez exécuter sur un calendrier, vous devez fournir certaines informations. Par exemple :

* Le type d’objet à exécuter, tel qu’un rapport ou une codeunit. Vous devez être autorisé à exécuter le rapport ou la codeunit en question.
* Le nom et le code objet de l’objet.
* Les paramètres pour spécifier le comportement de la file d’attente des travaux. Par exemple, vous pouvez ajouter un paramètre pour envoyer uniquement des documents de vente reportés.
* Quand et à quelle fréquence l’écriture de la file d’attente des travaux sera exécutée.

> [!IMPORTANT]  
> Si vous bénéficiez de l’ensemble d’autorisations SUPER qui est fourni avec [!INCLUDE[prod_short](includes/prod_short.md)], vous disposez des autorisations pour exécuter tous les objets inclus dans votre licence. Si vous disposez du rôle Administrateur délégué, vous pouvez créer et programmer des écritures de file d’attente de travaux, mais seuls les administrateurs et les utilisateurs sous licence peuvent les exécuter. Les utilisateurs disposant de la licence Appareil ne peuvent pas créer ni exécuter d’écritures file d’attente des travaux.

Une fois les files d'attente des travaux configurées et en cours d'exécution, l'état peut être modifié comme suit au cours de chaque période récurrente :

* **En attente**  
* **Prêt**  
* **En cours**  
* **Erreur**  
* **Terminé**  

Une fois qu’un travail s’est terminé correctement, il est supprimé de la liste d’écritures file d’attente des travaux, sauf en cas de projet récurrent. Pour les travaux récurrents, le champ **Heure de début (au plus tôt)** est ajusté pour afficher la prochaine heure d’exécution du projet.  

## <a name="monitor-status-or-errors-in-the-job-queue" />Surveiller l’état ou les erreurs dans la file d’attente des travaux

Les données générées par la file d’attente des travaux sont stockées, de sorte que vous pouvez résoudre les erreurs.  

Pour chaque entrée de file d'attente des travaux, vous pouvez afficher et modifier l’état. Lorsque vous créez une écriture file d'attente des travaux, son état est défini sur **En attente**. Vous pouvez définir l'état sur **Prêt** et revenir à **En attente**, par exemple. Sinon, les informations d'état sont mises à jour automatiquement.

Le tableau suivant décrit les valeurs du champ **État**.

| état | Désignation |
|--|--|
| Prêt | L’écriture file d’attente des travaux est prête à être exécutée. |
| En cours | L’écriture file d’attente des travaux est en cours. Ce champ est mis à jour lors de l’exécution de la file d’attente des travaux. |
| En suspens | L’état par défaut de l’écriture file d’attente des travaux lorsqu’elle est créée. Choisissez **Attribuer l'état Prêt** pour modifier l'état sur **Prêt**. Choisissez l’action **Définir sur Suspendu** pour rétablir l’état sur **En attente**. |
| Erreur | Un problème est survenu. Choisissez **Afficher erreur** pour afficher le message d’erreur. |
| PROD FINIS | L’écriture file d’attente des travaux est complète. |

> [!Tip]  
> Les écriture de la file d’attente des tâches cessent de s’exécuter en cas d’erreur. Par exemple, cela peut être un problème lorsqu'une entrée se connecte à un service externe, tel qu'un flux bancaire. Si le service est temporairement indisponible et que l’entrée de la file d’attente des travaux ne peut pas se connecter, l’entrée affichera une erreur et cessera de s’exécuter. Vous devrez redémarrer manuellement l’entrée de la file d’attente des travaux. Cependant, les champs **Nombre maximal de tentatives** et **Délai de réexécution (sec.)** peuvent vous aider à éviter cette situation. Le champ **Nombre maximal de tentatives** vous permet de spécifier combien de fois l’entrée de la file d’attente des travaux peut échouer avant qu’elle n’arrête d’essayer de s’exécuter. Le champ **Délai de réexécution (sec.)** vous permet de spécifier la durée, en secondes, entre les tentatives. La combinaison de ces deux champs peut maintenir l’entrée de la file d’attente des travaux en cours d’exécution jusqu’à ce que le service externe soit disponible.

### <a name="to-view-status-for-any-job" />Pour visualiser l'état de tous les travaux

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures file d’attente des travaux**, puis sélectionnez le lien associé.
2. Sur la page **Écritures file d'attente des travaux**, sélectionnez une écriture file d'attente des travaux, puis sélectionnez l'action **Écritures journal**.  

> [!TIP]
> Pour une analyse plus approfondie basée sur la télémétrie, utilisez Application Insights dans Microsoft Azure pour voir l’état des écritures file d’attente. Pour en savoir plus sur la télémétrie, accédez à [Surveillance et analyse de la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) et [Analyse de la télémétrie de la trace du cycle de vie des files d’attente de travaux](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

## <a name="view-scheduled-tasks" />Afficher les tâches programmées

La page **Tâches programmées** dans [!INCLUDE [prod_short](includes/prod_short.md)] indique quelles tâches sont prêtes à être exécutées dans la file d'attente des travaux. La page affiche également des informations sur la compagnie dans laquelle chaque tâche est configurée pour s’exécuter. Cependant, seules les tâches marquées comme appartenant à l’environnement actuel peuvent s’exécuter.  

Par exemple, toutes les tâches programmées s’arrêtent si la compagnie se trouve dans un environnement qui est une copie d’un autre environnement. Utilisez la page **Tâches programmées** pour définir les tâches comme prêtes à être exécutées dans la file d'attente des travaux.  

> [!NOTE]
> Les administrateurs internes et les utilisateurs sous licence peuvent programmer l’exécution des tâches. Les administrateurs délégués peuvent configurer et programmer des tâches à exécuter, mais seuls les utilisateurs sous licence peuvent les exécuter.

## <a name="the-my-job-queue-part" />Composant Ma file d’attente des travaux

Le composant **Ma file d’attente des travaux** sur votre Tableau de bord répertorie les écritures file d’attente des travaux que vous avez commencées, mais qui ne sont pas terminées. Par défaut, le composant n’est pas affiché, mais vous pouvez l’ajouter à votre tableau de bord. Pour plus d’informations sur la personnalisation, consultez [Personnaliser votre espace de travail](ui-personalization-user.md).  

Le composant affiche les informations suivantes :

* Quels documents ayant votre code dans le champ **Code utilisateur affecté** sont en cours de traitement ou en attente, y compris ceux reportés à l’arrière-plan. 
* S’il y a eu une erreur lors du report d’un document ou dans l’entrée de la file d’attente des travaux. 

Le composant Ma file d’attente des travaux permet également d’annuler une report de document.

### <a name="to-view-an-error-from-the-my-job-queue-part" />Pour afficher une erreur dans le composant Ma file d'attente des travaux

1. Sur une écriture ayant l'état **Erreur**, sélectionnez l'action **Afficher erreur**.
2. Examinez le message d’erreur et résolvez le problème.

## <a name="examples-of-what-you-can-schedule-using-job-queue-entries" />Exemples de ce que vous pouvez programmer à l’aide des écritures de la file d’attente des travaux

### <a name="schedule-reports" />Programmer des rapports

Vous pouvez programmer un rapport ou un traitement en lot pour qu'il s'exécute à une date et une heure spécifiques. Les rapports ou les traitements en lot programmés sont entrés dans la file d'attente des travaux et traités au moment programmé, comme les autres projets. Vous devez choisir l’option **Programmer** après avoir choisi l’action **Envoyer à**, puis vous devez entrer des informations telles que l’imprimante, l’heure et la date, et la récurrence.  

Pour en savoir plus sur la planification, accédez à [Planifier l’exécution d’un rapport](ui-work-report.md#ScheduleReport)

### <a name="schedule-synchronization-between-includeprodshortincludesprodshortmd-and-includeprodshortincludescdslongmdmd" />Programmer la synchronisation entre [!INCLUDE[prod_short](includes/prod_short.md)] et [!INCLUDE[prod_short](includes/cds_long_md.md)]

Si vous avez intégré [!INCLUDE[prod_short](includes/prod_short.md)] avec [!INCLUDE[prod_short](includes/cds_long_md.md)], la file d’attente des travaux vous permet de programmer à quel moment synchroniser les données. Selon la direction et les règles que vous avez définies, l’entrée de la file d’attente des tâches peut créer des enregistrements dans une application pour faire correspondre les enregistrements dans l’autre. Un bon exemple est lorsque vous enregistrez un contact dans [!INCLUDE[crm_md](includes/crm_md.md)], l’entrée de la file d’attente peut configurer ce contact pour vous dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour en savoir plus sur la planification, voir [Planification d’une synchronisation entre Business Central et Dynamics 365 Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

### <a name="schedule-when-to-post-sales-and-purchase-orders" />Programmer le moment de report des commande vente et des bons de commande

Vous pouvez utiliser les entrées de la file d’attente des travaux pour programmer l’exécution des processus métier en arrière-plan. Par exemple, les tâches en arrière-plan sont utiles quand plusieurs utilisateurs valident des documents de vente en même temps, mais qu’une seule commande peut être traitée à la fois. Pour en savoir plus sur la publication en arrière-plan, accédez à [Pour configurer la publication en arrière-plan avec des files d’attente de travaux](ui-batch-posting.md#to-set-up-background-posting-with-job-queues).

## <a name="handle-job-queue-entry-issues" />Gérer les problèmes d’écritures dans la file d’attente des tâches

Si une écriture de la file d’attente des travaux affiche une erreur, votre première option pour résoudre le problème consiste à redémarrer l’entrée de la file d’attente des travaux. Vous pouvez définir l’état de l’entrée de la file d’attente des travaux sur **En attente**, puis sur **Prêt**, ou simplement la redémarrer.

Si un redémarrage n’aide pas, le problème peut être dans le code. Vous pouvez trouver le propriétaire (également appelé *éditeur*) du code dans la trace de la pile AL dans le journal de la file d’attente des travaux. Si l’erreur provient d’une application/extension, contactez votre partenaire Microsoft. Si l’erreur provient d’une application Microsoft, ouvrez une demande de support auprès de Microsoft.

Si vous contactez votre partenaire Microsoft ou Microsoft pour obtenir de l’aide, fournissez les informations suivantes :

* Le code de l’exécution d’une écriture file d’attente des projets où l’erreur s’est produite
* L’horodatage du moment où l’erreur s’est produite
* Votre fuseau horaire

> [!TIP]
> Selon que votre [!INCLUDE [prod_short](includes/prod_short.md)] est antérieur ou ultérieur à la version 22.1, rassemblez les informations de la manière suivante :
>
> * Pour les versions antérieures, fournissez une capture d’écran de la page **Écritures journal file d’attente des travaux**.
> * Pour les versions ultérieures, utilisez l’action **Copier les détails** sur la page Écritures journal file d’attente des travaux pour copier les informations (Code de la file d’attente des travaux, horodatage et votre fuseau horaire).

## <a name="monitor-the-job-queue-with-telemetry" />Surveiller la file d’attente des travaux avec la télémétrie

Les administrateurs peuvent utiliser [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview) pour recueillir et analyser la télémétrie qui vous permet d’identifier les problèmes. Pour en savoir plus sur la télémétrie, accédez à [Surveillance et analyse de la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) et [Analyse de la télémétrie de la trace du cycle de vie des files d’attente de travaux](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

La télémétrie permet aux administrateurs de configurer des alertes sur les problèmes de file d’attente des tâches qui envoient un SMS, un courriel ou un message dans Teams si quelque chose ne va pas. Pour en savoir plus sur ces alertes, accédez à [Alerte sur la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-alert).

## <a name="see-also" />Voir aussi

[Administration](admin-setup-and-administration.md)  
[Configuration de Business Central](setup.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Analyse de la télémétrie de suivi du cycle de vie de la file d'attente des travaux](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace)  
[Alerte sur la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-alert)

[!INCLUDE[footer-include](includes/footer-banner.md)]
