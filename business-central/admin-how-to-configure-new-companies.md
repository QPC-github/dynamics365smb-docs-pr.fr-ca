---
title: "Procédure de configuration de nouvelles compagnies | Microsoft Docs"
description: "Vous pouvez configurer et personnaliser une nouvelle compagnie que vous avez créée. Pour détailler votre implémentation, vous procédez en trois phases pour terminer votre configuration."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: b9e701f102f1a2fc7ccbd4882dfec37f65cfe3b7
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="configure-new-companies"></a>Configurer de nouvelles compagnies
Pour configurer une nouvelle compagnie dans votre implémentation de la solution, vous suivez habituellement trois phases. Dans la première phase, vous importez le package configuration, un fichier .rapidstart avec les informations de configuration. Dans la deuxième phase, vous modifiez les informations de configuration, puis vous les appliquez à votre nouvelle compagnie. Dans la phase finale, vous vérifiez et corrigez les erreurs.  

Les procédures suivantes supposent que vous avez créé et enregistré un colis configuration. Pour plus d’informations, voir [Préparer un package configuration](admin-how-to-prepare-a-configuration-package.md).  

Les procédures suivantes supposent que vous avez initialisé et ouvert votre nouvelle compagnie et que vous utilisez le tableau de bord Responsable de l'implémentation de RapidStart Services.

## <a name="to-import-a-configuration-package"></a>Pour importer un colis configuration  
1. Ouvrez la nouvelle compagnie dans la base de données [!INCLUDE[d365fin](includes/d365fin_md.md)].  
2. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Packages configuration**, puis sélectionnez le lien associé.  
3. Sélectionnez l'action **Importer package**.  
4. Accédez à l'emplacement où vous avez enregistré le fichier du package de configuration .rapidstart, puis sélectionnez le bouton **Ouvrir**.  
5. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Informations compagnie**, puis sélectionnez le lien associé. Entrez les informations sur la compagnie dans la fiche Informations compagnie. Incluez des informations, telles que les coordonnées bancaires. Vous pouvez également fournir un logo pour la compagnie.  

Toutes les tables que vous avez désignées pour les inclure à la nouvelle compagnie sont importées. À ce stade, vous pouvez appliquer les données de package dans la base de données, ou ajuster et modifier les données de table pour répondre aux spécifications du client.  

## <a name="to-apply-package-data"></a>Pour appliquer les données de package  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille configuration**, puis sélectionnez le lien associé.  
2. Sélectionnez une table pour laquelle vous souhaitez modifier les données, puis sélectionnez l'action **Appliquer données**. Cliquez sur le bouton **Oui** pour confirmer l'affectation.
3. Pour confirmer que les données se trouvent maintenant dans la base de données et que l’affectation a réussi, revenez à la fenêtre **Feuille config** et sélectionnez l'action **Données base de données**.  

> [!NOTE]  
>  Une fois les données appliquées, vous pouvez uniquement les visualiser dans la base de données. Elles ne se trouvent plus dans le colis.  

## <a name="to-modify-and-apply-package-data"></a>Pour modifier et appliquer les données de package  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille configuration**, puis sélectionnez le lien associé.  
2. Sélectionnez une table pour laquelle vous souhaitez modifier les données, puis sélectionnez l'action **Données package**.  
3. Dans la fenêtre **Enregistrements package config.**, effectuez vos modifications. Par exemple, vous pouvez supprimer des options qui ne s’appliquent pas.  
4. Sélectionnez l'action **Appliquer données**, puis le bouton **OK**.  
5. Pour confirmer que les données se trouvent maintenant dans la base de données et que l’affectation a réussi, revenez à la fenêtre **Feuille config** et sélectionnez l'action **Données base de données**.  

## <a name="to-locate-and-identify-a-configuration-error"></a>Pour trouver et identifier une erreur de configuration  
Il existe certains types d’erreurs qui surviennent lorsque vous appliquez des données à une base de données. L’erreur la plus commune est que les tables associées requises ne soient pas incluses. Vous corrigez ces erreurs dans la feuille de configuration.

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Packages configuration**, puis sélectionnez le lien associé.  
2. Sélectionnez le package que vous souhaitez examiner, puis sélectionnez l'action **Modifier**.  

    Toute table présentant des erreurs est mise en surbrillance. Le nombre d’erreurs de colis est affiché dans le champ **Nombre d’erreurs de colis**.  

3. Choisissez le champ **Nombre erreurs package** pour ouvrir la fenêtre **Enregistrements package config.**, qui répertorie les enregistrements contenant des erreurs.  

### <a name="to-fix-an-error"></a>Pour corriger une erreur  
1. Ouvrez la compagnie basée sur votre package de configuration.  
2. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille configuration**, puis sélectionnez le lien associé.  
3. Corrigez les erreurs, par exemple ajoutez des tables liées manquantes à la feuille.  
4. Ajoutez les tables au colis configuration existant, ou créez un colis qui contient uniquement les nouvelles tables. Pour plus d’informations, voir [Préparer un package configuration](admin-how-to-prepare-a-configuration-package.md).  
5. Rouvrez la nouvelle compagnie pour laquelle vous implémentez la configuration.  
6. Importez le colis configuration.  

    > [!NOTE]  
    >  Si vous importez le même colis à nouveau, vous pouvez remplacer toutes les modifications des données que vous avez déjà apportées. Pour ce motif, vous pouvez ajouter toutes les nouvelles tables dans un nouveau package, et les importer.  

7. Appliquez les données dans la base de données, comme décrit dans la section « Pour modifier et appliquer les données de package ».

## <a name="see-also"></a>Voir aussi  
[Appliquer des configurations à de nouvelles compagnies](admin-apply-configuration-to-new-companies.md)  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
