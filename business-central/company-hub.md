---
title: Gérer le travail entre plusieurs compagnies dans le Hub Entreprise
description: En savoir plus sur le Hub Entreprise Dynamics 365 Business Central que vous utilisez pour gérer votre travail dans plusieurs compagnies.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: accountant, accounting, financial report
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 7ed69f86a941a216ef948488d3756c06f298549d
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3927782"
---
# <a name="manage-work-across-multiple-companies-in-the-company-hub"></a>Gérer le travail entre plusieurs compagnies dans le Hub Entreprise

Certaines personnes travaillent dans plusieurs compagnies [!INCLUDE [prodshort](includes/prodshort.md)], et certaines travaillent également dans plusieurs organisations, comme des comptables externes, ou des employés et des gestionnaires d'entreprises ayant plusieurs filiales. Pour ces utilisateurs, et bien d’autres, le Hub Entreprise sert de page de destination pour gérer le travail dans les différents environnements dans lesquels ils travaillent, entre les compagnies, les environnements et les régions.  

Vous pouvez accéder au hub Entreprise en passant au rôle **Hub Entreprise** dans Mes paramètres, ou en ouvrant la page **Hub Entreprise** . Vous pouvez faire le même travail aux deux endroits, mais les actions sont placées légèrement différemment dans les menus.  

## <a name="company-hub-home-page"></a>Page d’accueil du Hub Entreprise

Si vous utilisez le rôle de **Hub Entreprise** , votre page d’accueil affiche une liste des compagnies auxquelles vous avez accès, y compris des informations sur les données des points clés d’intérêt et des liens pour ouvrir chaque compagnie. Vous pouvez personnaliser le tableau de bord pour afficher les points de données que vous souhaitez voir en ajoutant ou supprimant des colonnes. Par exemple, vous souhaitez peut-être visualiser les taxes dues, le nombre de documents vente ouverts que possède chaque compagnie, ou le nombre de factures achat dues la semaine suivante. Vous pouvez configurer la vue à votre convenance. Si vous avez ajouté de nombreuses compagnies, vous pouvez utiliser des filtres pour trier votre affichage.  

Choisissez l’action **Hub Entreprise** pour ouvrir le Hub Entreprise, où vous pouvez travailler plus étroitement avec chaque compagnie.  

> [!TIP]
> Pour accéder à une compagnie spécifique dans [!INCLUDE [prodshort](includes/prodshort.md)], choisissez le nom de la compagnie ou choisissez l’élément de menu **Accéder à la compagnie** , vous êtes connecté automatiquement dans un nouvel onglet de navigateur.

:::image type="content" source="media/company-hub-company-list-actions.png" alt-text="Actions pour une compagnie répertoriée dans le Hub Entreprise":::

Vous pouvez ajouter de nouvelles compagnies, par exemple lorsque vous obtenez un nouveau client ou lorsque votre société ajoute une nouvelle filiale. Pour plus d’informations, voir [Ajouter des compagnies à votre Hub Entreprise](company-hub-add-company.md).  

> [!TIP]
> Afin d’actualiser les données dans le Hub Entreprise, vous devez avoir accès aux données des compagnies dont les données proviennent.

<!--## Company details

In the **Company Hub** page, you can see more information about each company by choosing the name of the company that you want to learn more about. This opens the **Company Details** pane, where you can see additional information, such as the following:  

* Cash account balances  
* Cash flow forecast  
* Overdue purchase invoices  
* Overdue sales invoices  

> [!TIP]
> You can launch predefined Excel workbooks from the **Reports** tab in the ribbon. These Excel workbooks are designed as ready-to-print key financial statements and reports, but you can also modify them to fit your needs. For more information, see [Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md).  

Otherwise, close the details pane and continue to the next company.  -->

## <a name="assigned-tasks"></a>Tâches affectées

Dans le [!INCLUDE [prodshort](includes/prodshort.md)], vous pouvez affecter des tâches à vous-même et à d’autres utilisateurs, et d’autres utilisateurs peuvent vous affecter des tâches. Le Hub Entreprise vous fournit un aperçu des tâches affectées à chaque client, et vous pouvez également accéder à une liste de toutes les tâches affectées en choisissant **Mes tâches utilisateur** sur la page **Accueil** .  

<!--In the client company, you also have cues that call out tasks assigned to you in this particular client.  -->

### <a name="my-user-tasks"></a>Mes tâches utilisateur

La liste **Mes tâches utilisateur** vous permet de planifier votre journée en affichant plus d’informations sur les tâches qui vous sont affectées dans toutes vos compagnies.  

Vous pouvez effectuer un tri par date d'échéance, par exemple, ou tout autre type de données vous permettant de planifier votre journée. Par défaut, la liste affiche toutes les tâches qui vous sont affectées, mais vous pouvez définir des filtres pour afficher uniquement les tâches qui sont marquées comme ayant une priorité élevée, par exemple.  

Pour sélectionner une tâche, il suffit de cliquer dessus dans la liste des tâches utilisateur en attente. Dans le ruban, le lien **Atteindre l'élément de tâche** ouvre la page sur laquelle vous pouvez effectuer le travail.  

Lorsque vous avez terminé une tâche, marquez-la simplement comme terminée.  

Pour plus d’informations sur les compagnies et les environnements, voir [Liens d’environnements](company-hub-add-company.md#environment-links).  

## <a name="access-the-company-hub"></a>Accéder au Hub Entreprise

Pour accéder au Hub Entreprise, vous devez avoir accès via le groupe d’utilisateurs *HUB ENTREPRISE D365* ou via l’ensemble d’autorisations *HUB ENTREPRISE D365* . Vous devez également avoir accès aux compagnies répertoriées dans votre Hub Entreprise, ce qui signifie que vous devez être un utilisateur de ces compagnies. Pour plus d’informations, voir [Créer des utilisateurs conformément aux licences](ui-how-users-permissions.md).  

> [!IMPORTANT]
> Le Hub Entreprise est une liste à l’échelle de la compagnie, de sorte que tout utilisateur qui a accès au Hub Entreprise pourra voir toutes les compagnies de son propre abonné [!INCLUDE [prodshort](includes/prodshort.md)] et tous les indicateurs de performance clés des compagnies auxquelles il a accès.

Si vous ne parvenez pas à trouver le Hub Entreprise et que vous savez que vous y avez obtenu l’accès, vérifiez auprès de votre administrateur si le Hub Entreprise est répertorié dans la page **Gestion des extensions** . Pour plus d'informations, voir [Personnalisation de Business Central à l'aide d'extensions](ui-extensions.md).  

## <a name="set-up-the-company-hub"></a>Configurer le Hub Entreprise

Pour commencer à utiliser le Hub Entreprise, vous devez ajouter une ou plusieurs compagnies à votre tableau de bord. Pour plus d’informations, voir [Ajouter des compagnies à votre Hub Entreprise](company-hub-add-company.md).  

Mais pour ajouter une compagnie, vous devez avoir accès à une ou plusieurs instances de [!INCLUDE [prodshort](includes/prodshort.md)] en plus de la compagnie dans laquelle vous utilisez le Hub Entreprise.  

Par exemple, si vous êtes comptable, vos clients peuvent vous inviter à leur [!INCLUDE [prodshort](includes/prodshort.md)]. Pour plus d’informations, voir [Inviter votre comptable externe dans votre Business Central](finance-accounting.md#inviteaccountant).  

Les administrateurs peuvent utiliser le même guide de configuration assistée pour vous ajouter à leur [!INCLUDE [prodshort](includes/prodshort.md)], ou ils peuvent vous ajouter au compte Azure AD dans le centre d’administration Microsoft 365. Pour en savoir plus, voir [Gérer les utilisateurs et les groupes](/microsoft-365/admin/add-users/?view=o365-worldwide&preserve-view=true).  

## <a name="see-also"></a>Voir aussi

[Ajouter des compagnies à votre Hub Entreprise](company-hub-add-company.md)  
[Expériences de comptables dans Business Central](finance-accounting.md)  
[Hub Entreprise pour l’extension Business Central](ui-extensions-company-hub.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  