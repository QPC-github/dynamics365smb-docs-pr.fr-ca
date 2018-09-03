---
title: "Exporter vos données Business Central vers Excel| Microsoft Docs"
description: "Vous pouvez exporter vos rapports financiers et vos données de veille économique de Business Central vers Excel, ou ouvrir vos données dans Excel."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, reporting, financial report, business intelligence, BI, Excel
ms.date: 06/02/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: e3917573a912a4e51416c4e926443c87513728fe
ms.openlocfilehash: 3bd7442582fe13809ea04d1f298b7aecbf9b45ed
ms.contentlocale: fr-ca
ms.lasthandoff: 06/01/2018

---
# <a name="exporting-your-business-data-to-excel"></a>Exportation de vos données métier vers Excel
Si vous souhaitez travailler avec vos données à partir de [!INCLUDE[d365fin](includes/d365fin_md.md)] dans Excel, vous pouvez ouvrir toutes les listes et les utiliser dans Excel. De même, si vous souhaitez annuler votre abonnement à [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez exporter vos données vers Excel afin de pouvoir les transférer par la suite.

## <a name="opening-lists-in-excel"></a>Ouverture de listes dans Excel
Vous pouvez ouvrir des données dans Excel à partir de n'importe quel journal, liste ou feuille de calcul. Il vous suffit d'ouvrir la page que vous souhaitez, puis de cliquer sur **Ouvrir dans Excel**. Par exemple, ouvrez la liste des clients (recherchez **Clients**), puis sélectionnez **Ouvrir dans Excel**. Votre navigateur vous invite alors à ouvrir ou à enregistrer le classeur Excel généré.  

Chaque liste inclut un certain nombre de colonnes, et l'exportation vers Excel inclut toutes les colonnes qui sont dans votre vue actuelle. Si vous souhaitez ajouter ou supprimer des colonnes avant d'ouvrir la liste dans Excel, il vous suffit simplement d'ouvrir le menu contextuel de n'importe quelle colonne et d'indiquer ensuite les colonnes que vous souhaitez visualiser. Cette liste de colonnes est différente de la plupart des listes, et elle reflète la structure de la base de données où vos données sont enregistrées. Si vous ne connaissez pas le type de données d'une certaine colonne, vous pouvez l'ajouter à votre affichage, puis décider de la supprimer à nouveau.  

## <a name="exporting-data-to-other-finance-systems"></a>Exportation de données vers d'autres systèmes financiers
Si vous décidez d'annuler votre abonnement à [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez exporter vos données vers Excel et les transférer ensuite dans votre système financier suivant.  

Bien entendu, vous pouvez exporter toutes les pages, mais il peut y en avoir trop. Vous devez donc exporter les principales pages suivantes, et penser à ajouter toutes les colonnes comme décrit précédemment :  

* Plan comptable  
* Clients  
* Fournisseurs  
* Banques  
* Articles  

Si vous souhaitez exporter toutes vos transactions financières également, le volume de données est alors très important et l'exportation prend alors souvent plusieurs minutes. Les transactions financières sont affichées dans la page **Écritures comptables**.  

Nous recommandons également d'exporter des données à partir des pages suivantes :  

* Écritures client  
* Détails écritures fournisseur  
* Écritures du grand livre de compte bancaire  
* Écritures article  
* Config. paramètres report  
* Groupes de report du client  
* Groupes de report du fournisseur  
* Groupes comptabilisation stock  
* Groupe de report banque  
* Budgets GL  
* Écritures budget  
* Devis  
* Factures vente  
* Factures achat  
* Contacts  
* Représentants  

> [!NOTE]  
>   Si vous avez défini plusieurs sociétés dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez exporter les données appropriées de chaque société.

## <a name="see-also"></a>Voir aussi
[Annuler pour votre abonnement [!INCLUDE[d365fin](includes/d365fin_md.md)]](admin-cancel.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Finances](finance.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
