---
title: "Procédure de configuration des heures de travail et des heures de service | Microsoft Docs"
description: "Vous pouvez spécifier les heures de travail service habituelles de votre compagnie. Ces heures de service sont utilisées pour calculer la date et l'heure de réponse des commandes et des devis service, et envoyer des alertes relatives au délai de réponse."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: fefde17c8e8063b7b1f373196bab29ff1caec452
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-work-hours-and-service-hours"></a>Configurer des heures de travail et des heures de service
Généralement, un système de gestion de services suit les heures ressource et les états commande service afin de prévoir les besoins en charges de travail et en service. [!INCLUDE[d365fin](includes/d365fin_md.md)] intègre des outils que vous pouvez personnaliser afin d'enregistrer ce type d'informations.  
  
Après avoir défini les heures de service par défaut de votre compagnie, vous pouvez calculer les temps de réponse aux commandes service ou envoyer des attentions ou des alertes lors de la réception d'appels de service. La fonctionnalité d'alerte est implémentée conjointement au planificateur de traitements.   
  
Lorsque vous travaillez sur une commande service, vous pouvez mettre à jour son état afin de surveiller la progression. L'état commande service reflète l'état réparation de tous les articles de service de la commande service. Pour plus d'informations, voir [Description des commandes service et de l'état réparation](service-order-repair-status.md). 

## <a name="to-set-up-default-service-hours"></a>Pour configurer des heures de service par défaut  
La fenêtre **Heures de service par défaut** permet de configurer les heures de travail service habituelles de votre société. Ces heures de service sont utilisées pour calculer la date et l'heure de réponse des commandes et des devis service, et envoyer des alertes relatives au délai de réponse. Les heures de service par défaut sont utilisées pour les contrats de service si vous ne spécifiez pas d'heures de service spéciales pour un contrat.  
  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Heures de service par défaut**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
  
> [!IMPORTANT]  
>  Si vous laissez les lignes de la fenêtre **Heures de service par défaut** vides, la valeur par défaut est 24 heures, valable uniquement pour les jours ouvrés du calendrier.  
  
## <a name="to-set-up-work-hour-templates"></a>Pour configurer des modèles heure de travail
Vous pouvez utiliser la fenêtre **Modèle heure de travail** pour configurer des modèles contenant les heures de travail habituelles de votre compagnie. Par exemple, vous pouvez créer des modèles pour les techniciens à temps plein et à temps partiel. Vous pouvez utiliser des modèles heure de travail lorsque vous ajoutez de la capacité à des ressources.  
  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modèles des heures de travail**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
  
> [!Note]
> Une fois que vous avez saisi les heures de travail pour chaque jour, la valeur du champ **Total par semaine** est calculée automatiquement.  

## <a name="to-set-up-contract-specific-service-hours"></a>Pour configurer des heures de service propres à un contrat  
Vous pouvez utiliser la fenêtre **Heures de service** pour configurer des heures de service spécifiques pour le client propriétaire du contrat de service. Les heures de service sont utilisées pour calculer la date et le délai de réponse pour les commandes service et les devis qui appartiennent au contrat de service.  
  
Si vous ne configurez pas d'heures de service spécifiques pour le contrat de service, les heures de service par défaut des contrats de service sont utilisées.  
  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Contrats de service**, puis sélectionnez le lien associé.  
2. Ouvrez le contrat de service pour lequel vous voulez configurer des heures de service spécifiques, puis sélectionnez **Heures de service**.  
4. Pour configurer des heures de service en fonction des heures de service par défaut, sélectionnez l'action **Copier heures de service par défaut**.  
5. Modifiez les champs des écritures heures de service. Insérez ou supprimer des écritures pour configurer les heures de service du contrat. Les champs **Jour**, **Heure début** et **Heure fin** sont obligatoires pour chaque ligne.  
6. Si vous souhaitez que les heures de service soient valables à partir d'une date spécifique, renseignez le champ **Date début**.  
7. Si vous souhaitez que les heures de service soient valables les jours fériés, activez le champ **Valable les jours fériés**.  

## <a name="see-also"></a>Voir aussi  
[Description de l'état d'affectation et de l'état réparation](service-allocation-status-and-repair-status.md)  
[Paramétrage de la gestion des services](service-setup-service.md)  
[Description des commandes service et de l'état réparation](service-order-repair-status.md)  
