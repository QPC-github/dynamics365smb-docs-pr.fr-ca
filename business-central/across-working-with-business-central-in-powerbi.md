---
title: "Utiliser les données Business\_Central dans Power BI| Microsoft Docs"
description: "Obtenir des informations, des informations décisionnelles et des indicateurs de performance clés à partir de vos données Business\_Central à l’aide de Power BI."
author: jswymer
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'account schedule, analysis, reporting, financial report, business intelligence, KPI'
ms.date: 09/07/2022
ms.author: jswymer
---
# <a name="work-with-include-prodshortincludesprodshortmd-data-in-power-bi" />Utiliser des données [!INCLUDE [prod_short](includes/prod_short.md)] dans Power BI

Dans cet article, vous découvrirez quelques notions de base sur l’utilisation des rapports et des tableaux de bord dans Power BI qui utilisent [!INCLUDE [prod_short](includes/prod_short.md)] comme source de données. L’article traite de certains aspects qui vous aideront à démarrer en tant qu’utilisateur [!INCLUDE[prod_short](includes/prod_short.md)]. Pour obtenir des instructions générales et des instructions sur l’utilisation Power BI, voir [Documentation Power BI pour les consommateurs](/power-bi/consumer).

## <a name="get-ready" />Mise en route

Inscrivez-vous au service Power BI. Si vous ne vous êtes pas encore inscrit, accédez à [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Lorsque vous vous inscrivez, utilisez une adresse de courriel professionnelle et un mot de passe.

## <a name="get-started" />Démarrer

Une fois que vous avez un compte Power BI, vous pouvez vous connecter à [https://powerbi.microsoft.com/](https://powerbi.microsoft.com/).

Le service Power BI héberge tous les rapports dont vous disposez. Pour voir le rapport, sélectionnez **Mon espace de travail** > **Rapports**. Ensuite, sélectionnez simplement le rapport que vous souhaitez afficher.

Avec [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, vous aurez automatiquement un ensemble de rapports par défaut sur votre espace de travail. Si vous souhaitez créer vos propres rapports, vous pouvez utiliser Power BI Desktop pour créer des rapports, puis les publier dans votre espace de travail. Pour plus d’informations, consultez [Familiarisation avec la création de rapports dans Power BI Desktop pour afficher les données [!INCLUDE [prod_long](includes/prod_long.md)]](across-how-use-financials-data-source-powerbi.md).

[!INCLUDE[note-multicompany-reports](includes/note-multicompany-reports.md)]

Si vous utilisez [!INCLUDE[prod_short](includes/prod_short.md)] sur site, vous devrez repartir de zéro en utilisant Power BI Desktop. En option, les rapports Power BI peuvent être distribués sous forme de fichiers que vous pouvez télécharger.

## <a name="get-the-latest-data" />Obtenir les dernières données

Chaque rapport Power BI est basé sur un ensemble de données qui obtient des données des sources [!INCLUDE[prod_short](includes/prod_short.md)]. Vous voulez vous assurer que les données de vos rapports Power BI sont à jour avec les données dans [!INCLUDE[prod_short](includes/prod_short.md)]. C’est ce qu’on appelle l’*actualisation*.  En fonction de la configuration de votre organisation Power BI, l’actualisation risque de ne pas se faire automatiquement. Il existe deux façons d’actualiser les données : manuellement ou en planifiant une actualisation. L’actualisation manuelle est effectuée à la demande, si nécessaire. Avec l’actualisation programmée, actualisez automatiquement à des intervalles de temps définis.

### <a name="refresh-manually" />Actualiser manuellement

Dans le volet de navigation, sous **Ensembles de données**, sélectionnez **Plus d’options (...)** à côté de l’ensemble de données, puis sélectionnez **Actualiser maintenant**.

### <a name="schedule-a-refresh" />Programmer une actualisation

Dans le volet de navigation, sous Ensembles de données, sélectionnez Plus d’options (...) à côté de l’ensemble de données, puis sélectionnez **Programmer l'actualisation**. Renseignez les informations sous la section **Programmer l’actualisation**, et sélectionnez **Appliquer**.

Pour plus d’informations, voir [Configurer une actualisation programmée](/power-bi/connect-data/refresh-scheduled-refresh).

## <a name="a-nameuploadaupload-reports-from-files" /><a name="upload"></a>Télécharger des rapports à partir de fichiers

Les rapports Power BI peuvent être distribués entre les utilisateurs sous forme de fichiers .pbix. Si vous disposez d’un fichier .pbix, vous pouvez télécharger le fichier dans un espace de travail. Pour télécharger un rapport, procédez comme suit :

1. Dans votre nouvel espace de travail, sélectionnez **Obtenir des données**.

2. Dans la zone Fichiers, sélectionnez **Extraire**.

3. Sélectionner **Fichier local**, accédez à l’emplacement où vous avez enregistré le fichier et sélectionnez **Ouvrir**.

Pour plus d’informations, consultez [Télécharger le rapport vers le service](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

> [!NOTE]
> Pour télécharger un rapport, vous devez disposer d’un espace de travail de [capacité premium](/power-bi/service-premium-what-is). Pour plus d’informations, voir [Gestion des capacités premium](/power-bi/admin/service-premium-capacity-manage). 

> [!TIP]
> Si vous utilisez [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, vous pouvez également télécharger un rapport depuis [!INCLUDE[prod_short](includes/prod_short.md)]. Pour plus d’informations, consultez [Utiliser les rapports Power BI dans [!INCLUDE [prod_short](includes/prod_short.md)] - Télécharger des rapports](across-working-with-powerbi.md#upload).

## <a name="a-nameshareashare-reports-with-others" /><a name="share"></a>Partager des rapports avec d’autres

Une fois qu’un rapport est dans votre espace de travail, vous pouvez le partager avec d’autres personnes de votre organisation.

Pour partager un rapport, dans une liste de rapports ou dans un rapport ouvert, sélectionnez **Partager**. Dans le volet **Partager le rapport**, entrez les adresses de courriel complètes des personnes ou des groupes de distribution avec qui vous souhaitez le partager. Suivez les instructions à l’écran pour terminer le partage. Pour plus d’informations, consultez [Partager un tableau de bord ou un rapport](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

> [!NOTE]
> Vous devez disposer d'une [Licence Power BI Pro](/power-bi/service-features-license-type), tout comme les personnes avec qui vous effectuez le partage. Le contenu doit se trouver dans un espace de travail dans une [Capacité Premium](/power-bi/service-premium-what-is). Pour en savoir plus, consultez [Moyens de partager votre travail dans Power BI](/power-bi/service-how-to-collaborate-distribute-dashboards-reports).

## <a name="see-related-microsoft-trainingtrainingmodulesconfigure-powerbi-excel-dynamics-365-business-centralindex" />Voir la [formation Microsoft](/training/modules/configure-powerbi-excel-dynamics-365-business-central/index) associée

## <a name="see-also" />Voir aussi

[Business Central et Power BI](admin-powerbi.md)  
[Création de rapports Power BI pour afficher les données [!INCLUDE [prod_long](includes/prod_long.md)]](across-how-use-financials-data-source-powerbi.md)  
[Vue d’ensemble Architecture et composante d’intégration Power BI pour [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Utiliser les rapports Power BI dans [!INCLUDE [prod_short](includes/prod_short.md)]](across-working-with-powerbi.md)  
[Power BI pour les consommateurs](/power-bi/consumer/end-user-consumer)  
[Le « nouveau look » du service Power BI](/power-bi/service-new-look)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Documentation Power BI](/power-bi/)  
[Veille économique](bi.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power Apps](across-how-use-financials-data-source-powerapps.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] dans Power Automate](across-how-use-financials-data-source-flow.md)  




[!INCLUDE[footer-include](includes/footer-banner.md)]
