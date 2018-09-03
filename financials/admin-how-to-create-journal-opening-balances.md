---
title: "Procédure de création de soldes ouverts journal | Microsoft Docs"
description: "Business Central inclut plusieurs traitements en lot qui sont fournis pour aider au transfert des soldes de compte hérités vers une compagnie nouvellement configurée. Vous pouvez facilement transférer ces données avec des reports de journal."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: be45ed1de52c92722d801da344163fdffc2a9073
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-journal-opening-balances"></a>Créer des soldes ouverts journal
[!INCLUDE[d365fin](includes/d365fin_md.md)] inclut plusieurs traitements par lots qui sont livrés pour aider au transfert des soldes de compte hérité vers une société nouvellement configurée. Vous pouvez facilement transférer ces données avec le journal clients, le journal fournisseurs, le journal articles ou le journal GL.

La première étape consiste à créer un package de configuration incluant les tables de configuration pour ces journaux. La procédure suivante est basée sur l’hypothèse que cette étape est terminée. Pour plus d'informations, voir [Définir une configuration de compagnie](admin-set-up-company-configuration.md). Cette procédure explique les étapes suivantes, comme le lettrage du package qui est fourni par un partenaire.  

Avant de commencer, vérifiez que vous vous trouvez sur la page du tableau de bord Responsable de l'implémentation de RapidStart Services, car elle fournit le contexte correct pour votre travail de configuration. Pour plus d'informations, voir [Modification des paramètres de base](ui-change-basic-settings.md).

## <a name="to-apply-the-entries-in-a-journal-to-a-new-company"></a>Pour affecter les écritures d'un journal à une compagnie  
1. Configurez une nouvelle compagnie et appliquez-lui un package de configuration. Pour plus d'informations, voir [Configurer une compagnie avec l’assistant RapidStart](admin-how-to-configure-a-company-with-the-rapidstart-wizard.md).  

    La nouvelle compagnie ne contient pas d’informations sur les soldes ouverts journal.  

2. Ouvrez la feuille configuration et importez les données existantes à propos des clients, des articles, des fournisseurs et du grand livre. Pour plus d'informations, voir [Migrer des données client](admin-migrate-customer-data.md).  
3. Choisissez, par exemple, l'action **Créer lignes feuille compta**.  
4. Renseignez le raccourci **Options** de la manière appropriée, puis définissez les filtres selon vos besoins. Par exemple, dans le champ **Modèle feuille**, entrez un nom.  
5. Cliquez sur le bouton **OK**. Les enregistrements se trouvent maintenant dans le journal, mais les montants sont vides.  
6. Exportez la table journal vers Excel, puis entrez manuellement le report et les informations de compte de solde à partir des données héritées.
7. Importez et appliquez les informations de table dans la nouvelle compagnie. Les lignes journal sont prêtes pour le report.  
8. Dans la feuille configuration, sélectionnez la table ligne journal, puis sélectionnez l'action **Données de base de données**.  
9. Examinez les informations, puis sélectionnez l'action **Reporter**.  
10. Répétez les étapes pour importer et reporter les autres soldes ouverts.  

## <a name="see-also"></a>Voir aussi  
[Appliquer des configurations à de nouvelles compagnies](admin-apply-configuration-to-new-companies.md)  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
