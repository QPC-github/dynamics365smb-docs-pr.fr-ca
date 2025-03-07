---
title: Spécification d’une imprimante par défaut
description: En savoir plus sur les différentes façons de configurer les imprimantes qui seront utilisées par défaut pour les travaux d′impression.
author: jswymer
ms.topic: how-to
ms.reviewer: na
ms.service: dynamics365-business-central
ms.custom: bap-template
ms.search.keywords: 'online printing, email printing, cloud printing, Universal Print'
ms.search.form: '2650, 2750, 2752, 2753, 2754, 8900,'
ms.date: 02/09/2023
ms.author: jswymer
---
# <a name="a-namedefaultaspecify-a-default-printer" /><a name="default"></a>Spécification d’une imprimante par défaut

Une fois les imprimantes configurées dans Business Central, vous pouvez ensuite spécifier l’imprimante que vous souhaitez utiliser par défaut. Il existe plusieurs façons de spécifier les imprimantes qui seront utilisées par défaut pour les rapports et autres travaux d′impression. Une imprimante par défaut est utile si vous utilisez différents rapports nécessitant différentes imprimantes en raison de leur placement dans la compagnie ou de leurs capacités d’impression.

> [!IMPORTANT]
> Les seules imprimantes que vous pouvez spécifier par défaut sont **Imprimer vers PDF Microsoft** et les imprimantes nuage qui ont déjà été configurées pour être utilisées dans Business Central, comme les imprimantes par courriel et les imprimantes Universal Print. Les imprimantes en nuage sont généralement configurées par un administrateur. Pour plus d’informations, voir [Configuration et gestion de l’imprimante](admin-printer-setup-overview.md).   

## <a name="set-a-printer-as-a-default-printer-for-all-print-jobs" />Définir une imprimante comme imprimante par défaut pour tous les travaux d'impression

La page **Gestion des imprimantes** vous permet de configurer une imprimante comme imprimante par défaut pour tous les travaux d′impression. Vous pouvez spécifier l'imprimante par défaut pour vous uniquement ou pour tous les utilisateurs.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Gestion des imprimantes**, puis sélectionnez le lien associé.

    > [!TIP]
    > Vous pouvez également ouvrir la page **Gestion des imprimantes** de la page **Sélections d'imprimantes** en choisissant **Gestion des imprimantes**.  
2. Sur la page **Gestion des imprimantes**, sélectionnez une imprimante dans la liste, choisissez **Gérer**, puis choisi **Définir comme imprimante par défaut** ou bien **Définir comme imprimante par défaut pour tous les utilisateurs**.

> [!NOTE]
> La configuration d′une imprimante par défaut à partir de la **Gestion des imprimantes** ajoutera une entrée dans les **Sélections d′imprimantes**.

## <a name="set-a-default-printer-for-specific-reports" />Définir une imprimante par défaut pour des rapports spécifiques

La page **Sélections d′imprimantes** vous permet de spécifier l′imprimante qu′un rapport utilisera par défaut. Les imprimantes par défaut sont définies sur la base d'un compte utilisateur. Vous pouvez définir une imprimante par défaut pour vous-même, un autre utilisateur ou tous les utilisateurs.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Sélections d’imprimantes**, puis sélectionnez le lien associé. Sinon, sur la page **Gestion des imprimantes**, sélectionnez une imprimante, puis l’action **Sélections d’imprimantes**.
2. Choisissez l'action **Nouveau** pour ajouter une sélection d'imprimante pour un rapport spécifique.
3. Renseignez les champs selon vos besoins.

Le rapport spécifié est désormais configuré pour être imprimé sur l'imprimante sélectionnée par défaut.

> [!NOTE]
> Lorsque vous imprimez le rapport en question, vous pouvez en sélectionner un autre à l′aide du champ **Impression** sur la page de demande.

> [!NOTE]
> Si vous ne configurez pas un rapport pour une imprimante spécifique sur la page **Sélections d’imprimantes**, il est imprimé sur l’imprimante par défaut de la compagnie, comme défini sur la page **Gestion des imprimantes**.

Vous ou l'administrateur pouvez également utiliser la page **Sélections d'imprimantes** pour définir d'autres variantes d'impression pour les utilisateurs et les rapports. Le tableau suivant décrit la combinaison de valeurs nécessaires pour spécifier d'autres configurations d’impression pour un rapport.

|À                                                 |Définir les valeurs suivantes                                             |
|---------------------------------------------------|---------------------------------------------------------------------|
|Imprimer un rapport sur une imprimante spécifique pour tous les utilisateurs |Spécifiez une valeur dans les champs **Code rapport** et **Nom de l'imprimante** et ne renseignez pas le champ **Code utilisateur**.|
|Imprimer tous les rapports sur une imprimante spécifique pour un utilisateur spécifique|Spécifiez une valeur dans les champs **Code utilisateur** et **Nom de l'imprimante** et ne renseignez pas le champ **Code rapport**. Cette entrée fait la même chose que l'action **Définir comme imprimante par défaut** sur la page **Gestion d'impression**.|
|Définir l’imprimante par défaut pour tous les rapports de tous les utilisateurs|Spécifiez une valeur dans le champ **Nom de l'imprimante** et ne renseignez pas les champs **Code utilisateur** et **Code rapport**. Cette entrée fait la même chose que l'action **Définir comme imprimante par défaut pour tous les utilisateurs** sur la page **Gestion d'impression**.|
|Imprimer un rapport spécifique sur l'imprimante par défaut de l'utilisateur|Spécifiez une valeur dans le champ **Code rapport** et ne renseignez pas les champs **Nom de l'imprimante** et **Code utilisateur**.|
|Imprimer un rapport spécifique sur une imprimante spécifique pour un utilisateur spécifique|Spécifiez une valeur dans les trois champs.|

> [!NOTE]
> Des sélections d’imprimantes plus spécifiques prévalent sur des sélections d’imprimantes plus générales. Par exemple, une sélection d'imprimante ayant des valeurs dans les champs **Code utilisateur**, **Code rapport** et **Nom de l'imprimante** prévaut sur une sélection d’imprimante ayant des entrées vides dans le champ **Code utilisateur** ou **Code rapport**.

## <a name="choosing-the-printer-when-running-a-report" />Choix de l’imprimante pendant l’exécution d’un rapport

Au lieu d’utiliser l’imprimante par défaut lors de l’exécution d’un rapport, vous pouvez remplacer ce paramètre à partir de la page de demande. Choisissez simplement l’imprimante que vous souhaitez utiliser pour cette invocation du rapport dans le menu déroulant **Imprimante**.

## <a name="sizing-print-jobs" />Dimensionnement des travaux d’impression

L'impression dans le nuage est conçue pour des documents de taille raisonnable. La plupart des services en nuage, y compris PrintNode et HP ePrint, ont une limite de 10 Mo par tâche. Si vous devez imprimer des rapports plus volumineux, vous devrez peut-être les diviser en plusieurs impressions.

[Formation Microsoft](/training/modules/change-documents-dynamics-365-business-central/)

## <a name="see-also" />Voir aussi

[Gestion de l’impression](admin-printer-setup-overview.md)  
[Configuration d’imprimantes à impression universelle](admin-printer-setup-universal-print.md)  
[Configurer des imprimantes par courriel](admin-printer-setup-email.md)  
[Impression d'un rapport](ui-work-report.md#PrintReport)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exécuter des traitements en lot](ui-how-run-batch-jobs.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
