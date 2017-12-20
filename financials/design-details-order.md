---
title: "Détails de conception - Commande | Microsoft Docs"
description: "Cette rubrique fournit des informations sur les liens commande-à-commande dans un environnement de fabrication à la commande."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, order
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 24f5c56e9e148128d83593757d820fa62686403e
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-order"></a>Détails de conception : commande
Dans un environnement de fabrication à la commande, un article est acheté ou produit pour couvrir exclusivement une demande spécifique. Généralement, il se rapporte aux articles A, et la motivation pour choisir cette méthode de réapprovisionnement de commande peut être que la demande n'est pas fréquente, le délai de production est insignifiant ou les attributs requis varient.  
  
Le programme crée un lien commande à commande, qui agit en tant que connexion préliminaire entre l'approvisionnement, une commande d'approvisionnement ou un inventaire, et la demande qu'il va traiter.  
  
Outre l'utilisation de la méthode de commande, le lien commande à commande peut s'appliquer lors de la planification, comme suit :  
  
* Lors de l'utilisation de la méthode de fabrication Prod. pour commande pour créer des bons de production de type multiniveau ou projet (la production avait besoin de composantes sur le même bon de production).  
* Lors de l'utilisation de la fonction Planification document de vente pour créer un bon de production à partir d'un document de vente.  
  
Même si une compagnie manufacturière se considère comme un environnement de fabrication à la commande, il peut être préférable d'utiliser une méthode de réapprovisionnement Lot pour lot si les articles sont des standards purs sans variation au niveau des attributs. Par conséquent, le système utilise l'inventaire non planifié et additionne uniquement les documents de vente ayant la même date de livraison ou faisant partie d'une plage de temps définie.  
  
## <a name="order-to-order-links-and-past-due-dates"></a>Liens commande à commande et dates d'échéance passées  
Contrairement à la plupart des ensembles approvisionnement-demande, les commandes liées avec des dates d'échéance antérieures à la date début de la planification sont entièrement planifiées par le système. La raison commerciale de cette exception est que les ensembles spécifiques approvisionnement-demande doivent être synchronisés jusqu'à l'exécution. Pour plus d'informations sur la zone gelée qui s'applique à la plupart des types de demande-approvisionnement, voir [Détails de conception : traiter les commandes avant la date début de la planification](design-details-dealing-with-orders-before-the-planning-starting-date.md).  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md)   
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)