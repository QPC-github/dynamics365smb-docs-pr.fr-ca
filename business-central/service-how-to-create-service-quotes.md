---
title: "Procédure : créer des devis service | Microsoft Docs"
description: "Utilisez la fenêtre **Devis service** pour créer des documents dans lesquels vous saisissez des informations sur un service, tel que réparation et maintenance, pour des articles de service à la demande du client. Vous pouvez utiliser un devis service comme brouillon d'une commande service, et convertir le devis en commande."
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
ms.openlocfilehash: 91928287d24c2b6199ea243bdc00e48e136adcfd
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-service-quotes"></a>Pour créer des devis service
Vous pouvez considérer les devis service comme la base des commandes service. En réalité, ils sont quasiment identiques. Tous deux contiennent des informations, telles que l'identité du client, le type de commande, l'article nécessitant une maintenance, les informations de facturation et d'expédition et les informations sur la tâche de service réelle.
 
Vous pouvez utiliser un devis service comme brouillon d'une commande service, et convertir le devis en commande.  
  
## <a name="to-create-a-service-quote"></a>Pour créer un devis service  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Devis de service**, puis sélectionnez le lien associé.  
2. Créez un devis service.  
3. Dans le champ **N°**, saisissez le numéro du devis service. Si vous avez configuré une souche de numéros pour les devis service dans la fenêtre **Paramètres Gestion des services,** vous pouvez appuyer sur Entrée pour renseigner le numéro devis service suivant.  
4. Dans le champ **N° client**,  sélectionnez le client approprié dans la liste.  

  > [!Note]  
  >  Les champs de client sont automatiquement renseignés avec les informations de la fiche **Client**. Si une fiche **Client** n'existe pas pour le client et que vous avez configuré un modèle client, vous pouvez créer le client à partir du devis service. Renseignez les champs appropriés, puis choisissez l'action **Créer client**.  
  
5. Selon les paramètres du raccourci **Champs obligatoires** de la fenêtre **Config. gestion des services**, vous pouvez être amené à renseigner le champ **Type commande service** et le champ **Code représentant**.  
6. Renseignez les lignes article de service.  
7. Enregistrez les coûts estimés dans les lignes service.  
  
## <a name="see-also"></a>Voir aussi  
[Créer commande service](service-how-to-create-service-orders.md)  
[Travailler sur des tâches service](service-how-to-work-on-service-tasks.md)  

 