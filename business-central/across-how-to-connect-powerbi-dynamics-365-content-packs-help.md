---
title: "Procédure de connexion de Power BI à Business Central | Microsoft Docs"
description: "Il est facile d'obtenir des informations exploitables, de la veille économique et des KPI de vos données Business Central grâce à Power BI et aux packs de contenu Business Central."
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 04/03/2018
ms.author: solsen
redirect_url: admin-powerbi
ms.translationtype: HT
ms.sourcegitcommit: ad1b888d475c0523c5a905e804a3f89ab4531b28
ms.openlocfilehash: 0196bff5dedb878884fd3d6e0208022faa968dfd
ms.contentlocale: fr-ca
ms.lasthandoff: 05/17/2018

---
# <a name="connecting-power-bi-to-dynamics-365-business-central-content-packs"></a>Connexion de Power BI aux packs de contenu Dynamics 365 Business Central
Il est facile d'obtenir des informations exploitables de vos données [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft grâce à Power BI et aux packs de contenu [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft. Power BI extrait vos données, puis génère un tableau de bord prêt à l'emploi et des rapports basés sur ces données.

Remarque : vous devez disposer d'un compte valide avec Dynamics 365 et avec Power BI. En outre, vous devez télécharger [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) si vous souhaitez créer vos propres rapports Power BI. Les packs de contenu Power BI nécessitent des autorisations vers les tables d'où sont extraites les données. Vous trouverez plus d'informations sur les besoins ci-dessous.  

## <a name="how-to-connect"></a>Pour vous connecter
1. Sélectionnez **Extraire les données** en bas du volet de navigation gauche.  
![Naviguer pour obtenir des données](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-get-data.png)

Vous pouvez également démarrer à partir de Dynamics 365 Business Edition. Dans le Tableau de bord, accédez à **Sélection de rapport** dans le composant Tableau de bord Power BI. Sélectionnez **Service** ou **Mon organisation** dans le ruban. Lorsque l'une de ces actions est sélectionnée, vous arrivez dans la galerie Organisation de Power BI ou dans la bibliothèque des services de Power BI, qui sera également filtrée pour afficher uniquement les packs de contenu associés à [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)].

2. Dans la zone **Services**, sélectionnez **Extraire**. Une fenêtre s'ouvre alors, elle contient **AppSource** et **Applications pour applications Power BI**.  
![Choisir des packs de contenu à partir des services en ligne](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-online-services-get.png)
3. Sélectionnez **Applications** dans l'onglet **Applications pour applications Power BI** et choisissez le pack de contenu **Microsoft Dynamics 365 Business Central** à utiliser, puis cliquez sur **Obtenir maintenant**.  
![Sélectionner Dynamics 365 Business Central et sélectionner Obtenir maintenant](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-dynamics365-for-financials-get-it-now.png)
4. Quand on vous le demande, indiquez le nom de *votre compagnie* dans [!INCLUDE[d365fin_md](includes/d365fin_long_md.md)]. Il ne s'agit pas du nom complet. Le nom de la compagnie se trouve sur la page Compagnies dans votre instance [!INCLUDE[d365fin_md](includes/d365fin_long_md.md)]. 
![Sélectionner Dynamics 365 Business Central et sélectionner Obtenir maintenant](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-connect-to-d365-finance-and-operations-crm.png)
5. Une fois connecté, un tableau de bord, un rapport et un ensemble de données sont automatiquement chargés dans votre espace de travail Power BI. Une fois terminé, les mosaïques sont mises à jour avec les données de votre compagnie [!INCLUDE[d365fin_md](includes/d365fin_long_md.md)].
![Sélectionner Dynamics 365 Business Central et sélectionner Obtenir maintenant](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-workspace-dashboard-report-dataset.png)

## <a name="what-now"></a>Et ensuite ?

- Cliquez sur [poser une question dans la zone Q&R](https://docs.microsoft.com/en-us/power-bi/service-q-and-a) en haut du tableau de bord.
- [Modifiez les mosaïques](https://docs.microsoft.com/en-us/power-bi/service-dashboard-edit-tile) du tableau de bord.  
- [Sélectionnez une mosaïque](https://docs.microsoft.com/en-us/power-bi/service-dashboard-tiles) pour ouvrir le rapport sous-jacent.  
- Même si votre ensemble de données est programmé pour être actualisé quotidiennement, vous pouvez modifier le calendrier de l'actualisation ou essayer de l'actualiser à la demande en sélectionnant **Actualiser maintenant**.

## <a name="system-requirements"></a>Configuration système requise
Pour importer les données [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] dans Power BI, vous devez disposer des autorisations sur les services Web utilisés pour récupérer les données. Les services Web obligatoires pour chaque pack de contenu incluent :

## <a name="role-center-reports"></a>Rapports du Tableau de bord

**Microsoft Dynamics 365 Business Central – CRM**
- Opportunités ventes
- Modèle Excel Afficher compagnie
- Étiquettes de rapport Power BI

**Microsoft Dynamics 365 Business Central – Finance**
- PowerBIFinance
- Modèle Excel Afficher compagnie
- Étiquettes de rapport Power BI

**Microsoft Dynamics 365 Business Central – Jobs**
- Liste des projets
- Lignes de planification de projet
- Lignes de tâche de projet
- Étiquettes de rapport Power BI
- Modèle Excel Afficher compagnie

**Microsoft Dynamics 365 Business Central - Sales**
- Tableau de bord ventes
- Modèle Excel Afficher compagnie
- Étiquettes de rapport Power BI

## <a name="list-page-reports"></a>Rapports Page de liste 

**Microsoft Dynamics 365 Business Central – Customers List**
- Ventes d'articles par client
- Liste des achats d'articles Power BI
- Liste des ventes d'articles Power BI
- Tableau de bord ventes
- Liste des clients Power BI
- ExcelTemplateViewCompany
- Étiquettes de rapport Power BI 

**Microsoft Dynamics 365 Business Central - General Ledger Entries List**
- Liste des montants Power BI GL
- Montant budgété Power BI GL
- ExcelTemplateViewCompany
- Étiquettes de rapport Power BI

**Microsoft Dynamics 365 Business Central – Items List**
- Ventes d'articles par client
- Liste des achats d'articles Power BI
- Liste des ventes d'articles Power BI
- Tableau de bord ventes
- ExcelTemplateViewCompany
- Étiquettes de rapport Power BI

**Microsoft Dynamics 365 Business Central – Jobs List**
- Liste des projets Power BI
- ExcelTemplateViewCompany
- Étiquettes de rapport Power BI

**Microsoft Dynamics 365 Business Central – Purchase Invoices List**
- Liste des achats Power BI
- ExcelTemplateViewCompany
- Étiquettes de rapport Power BI

**Microsoft Dynamics 365 Business Central – Sales Orders List**
- Liste des ventes Power BI
- ExcelTemplateViewCompany
- Étiquettes de rapport Power BI


**Microsoft Dynamics 365 Business Central – Vendors List**
- Liste des achats d'articles Power BI
- Liste des ventes d'articles Power BI
- Liste des fournisseurs Power BI
- ExcelTemplateViewCompany
- Étiquettes de rapport Power BI

## <a name="web-services"></a>Services web
Pour trouver facilement les services Web, il suffit de les chercher dans [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. Dans la liste, assurez-vous que la case Publier est cochée pour les services Web répertoriés ci-dessus.

## <a name="troubleshooting"></a>Dépannage
Le tableau de bord Power BI s'appuie sur les services Web publiés qui sont répertoriés ci-dessus. Il affichera les données de la compagnie de démonstration ou de votre propre compagnie si vous importez les données de votre solution financière actuelle. Toutefois, si une erreur se produit, cette section fournit une solution de rechange pour les problèmes les plus courants.

### <a name="incorrect-company-name"></a>Nom de compagnie incorrect  
Une erreur courante consiste à entrer le nom d'affichage de la compagnie au lieu de son nom. Pour trouver le nom de la compagnie, cherchez dans **Compagnies**. Utilisez ensuite le champ **Nom** au moment de saisir le nom de votre compagnie.

### <a name="incorrect-user-name-and-password"></a>Nom d'utilisateur et mot de passe incorrects  
Le nom d'utilisateur et le mot de passe utilisés pour la connexion sont identiques à ceux utilisés pour la connexion à votre compte Microsoft Office 365.  

Les packs de contenu nécessitent également que vous ayez un compte [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft. Une fois les informations d'identification saisies, tous les abonnés [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft accessibles seront détectés automatiquement. Si vous n'avez pas de compte [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Microsoft sous licence ou d'essai, vous recevrez un message d'erreur.

### <a name="the-key-didnt-match-any-rows-in-the-table"></a>La clé ne correspond à aucune ligne de la table
Si vous entrez un nom de compagnie non valide pendant le processus de connexion, le message d'erreur suivant « La clé ne correspond à aucune ligne de la table » risque de s'afficher. Indiquez le nom de compagnie correct, puis reconnectez-vous.

## <a name="see-also"></a>Voir aussi
[Mise en route de Power BI](https://docs.microsoft.com/en-us/power-bi/service-get-started)  
[Power BI - Concepts de base](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts)  
[Veille économique](bi.md)  
[Mise en route](product-get-started.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finance](finance.md)  
[Configuration du rapport [!INCLUDE[d365fin](includes/d365fin_md.md)] dans Power BI](across-how-use-financials-data-source-powerbi.md)  
