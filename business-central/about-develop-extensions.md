---
title: "Personnaliser Dynamics 365 Business Central | Microsoft Docs"
description: "Concevoir, présenter et promouvoir vos applications et extensions pour Business Central."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize
ms.date: 04/12/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 2286b728a464943841b192031cfea13644441013
ms.openlocfilehash: 69f660f8a19bd1fd9cb39a79d5be7977e68d3a47
ms.contentlocale: fr-ca
ms.lasthandoff: 06/28/2018

---
# <a name="extending-included365finlongincludesd365finlongmdmd"></a>Extension de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]
Microsoft [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] est une solution de gestion d'entreprise qui aide les compagnies à connecter leurs finances, ventes, services et opérations pour rationnaliser les processus d'entreprise, améliorer les interactions avec le client et prendre de meilleures décisions. [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] est accessible dans le cloud et aux utilisateurs sur différents types d'appareils, et est mis à jour régulièrement. Cette plate-forme d'entreprise moderne vous permet de personnaliser, d'étendre et de créer facilement et rapidement des applications en fonction de vos besoins spécifiques, avec peu ou pas de développement de code.  

Il existe de nombreux avantages à utiliser [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] comme plateforme pour les constructeurs d'applications, notamment :

* Prise en main en toute confiance grâce à une expérience d'intégration transparente 
* Utilisation des services Go-To-Market de Microsoft
* Personnalisation de votre page de liste d'applications 
* Communication directe avec les décisionnaires et ciblage d'un plus grand nombre de clients
* Amélioration de la valeur commerciale et augmentation du volume des transactions avec les clients existants et nouveaux
* Faites-en plus avec une plate-forme qui fournit une expérience moderne et offre une évolutivité  
* Accès à des informations exploitables sur les performances de vos listings via le portail Cloud Partner ou le processus de publication de l'application Office
* Associée à des applications professionnelles intelligentes telles que PowerApps, Flow, Power BI, Cortana Intelligence et bien d'autres encore  

Importez vos services [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] dans Microsoft AppSource en tant que : 

**Applications individuelles** – pour apporter votre expertise du secteur sur le marché.  
**Offre groupée de services de consultation** – pour apporter une offre groupée d'engagements prêts à l'emploi sur le marché.

Les nouveaux outils de développement vous permettent de créer des extensions pour les utilisateurs [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]. Si vous souhaitez vous familiariser avec les nouveaux outils ou en savoir plus sur les extensions 2.0, consultez [aka.ms/GetStartedWithApps](http://aka.ms/GetStartedWithApps).  

Vous trouverez des informations sur les applications et les services de consultation actuellement disponibles sur [Microsoft AppSource](https://appsource.microsoft.com/en-us/marketplace/consulting-services?country=US&page=1).

Pour aider les utilisateurs à démarrer rapidement, Microsoft a ajouté à AppSource un catalogue d'offres de services de consultation pour les solutions basées sur [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], Power BI et PowerApps. En savoir plus sur les [Services de consultation](/dynamics-nav/developer/readiness/readiness-consulting).

## <a name="choosing-which-services-to-offer-with-included365finlongincludesd365finlongmdmd"></a>Choix des services à offrir avec [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] 

### <a name="integrate-a-3rd-party-solution"></a>Intégrer une solution tierce
[!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] propose plusieurs API prêtes à l'emploi pour les [applications connectées](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-connect-apps) pour faciliter l'intégration entre votre service et [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]. Vous pouvez regrouper vos services avec une version [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] et offrir une expérience intégrée à vos clients. En savoir plus l'[Intégration d'une solution tierce](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-thirdparty-solution).

### <a name="development-of-a-vertical-solution"></a>Développement d'une solution verticale
Créez un application spécialisée dans un secteur d'activité spécifique. Avec une [application intégrée](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-embed-apps), vous pouvez étendre et personnaliser l'application [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] existante et enrichir l'expérience de l'utilisateur final avec une fonctionnalité spécifique au secteur d'activité en utilisant les outils de développement nouveaux et modernes et les extensions version 2.0. En savoir plus sur le [Développement d'une solution verticale](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-vertical).

### <a name="development-of-a-horizontal-solution"></a>Développement d'une solution horizontale
Étendez l'expérience et les capacités de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] en créant une [application complémentaire](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-add-on-apps) qui s'intègre dans l'expérience utilisateur de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]. Créez une interface basée sur le mode de transfert de vos données entre [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] et vos services. En savoir plus sur le [Développement d'une solution horizontale](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-horizontal). 

### <a name="development-of-a-localization-solution"></a>Développement d'une solution de localisation
Conformez-vous aux capacités réglementaires locales pour [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], qui adapte les zones fonctionnelles aux exigences du marché local et au [Service de traduction de Dynamics 365](/dynamics365/unified-operations/dev-itpro/lifecycle-services/translation-service-overview). Alignez les capacités de base des exigences légales locales et étendez les fonctionnalités existantes pour soutenir la concurrence sur le marché local. En savoir plus sur le [Développement d'une solution de localisation](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-localization).

### <a name="reseller-solution"></a>Solution de revendeur
Comme chaque entreprise est unique, la [Personnalisation des abonnés](/dynamics-nav/developer/readiness/readiness-customizing-tenants) vous permet de mettre en correspondance la manière dont vous utilisez vos processus rationnalisés et votre terminologie avec la manière dont vos employés ou services communiquent et collaborent. En outre, vous pouvez choisir de revendre et d'adapter [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] aux besoins de vos clients en fournissant des [Services de consultation](/dynamics-nav/developer/readiness/readiness-consulting). Vous pouvez également utiliser Microsoft Flow, Power Apps et Power BI pour créer des [Flux de travail personnalisés](/dynamics-nav/developer/readiness/readiness-no-code), des applications et des rapports d'analyse sans avoir à écrire de code. En savoir plus sur le [Revendeur Dynamics 365 (VAR)](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-reseller). 

## <a name="where-do-i-learn-more"></a>Informations utiles
Pour plus d'informations sur les offres de services de consultation de Microsoft AppSource, sélectionnez les liens suivants : 

[Offres de services de consultation de AppSource](https://appsource.microsoft.com/en-us/marketplace/consulting-services?country=US&page=1)  
[Éligibilité des partenaires](https://smp-cdn-prod.azureedge.net/documents/Microsoft%20AppSource%20Partner%20Listing%20Guidelines.pdf)  
[Formulaire de nomination des partenaires](https://appsource.microsoft.com/en-us/partners/list-consulting-service)  

## <a name="the-ready-to-go-program"></a>Programme Ready to Go
Le programme Ready to Go est conçu à vous aider à importer vos offres Microsoft [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] dans Microsoft Appsource. Le programme contient : 

- [Apprentissage en ligne](http://aka.ms/ReadyToGoOnlineLearning)
- [Formation et ateliers](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-ready-to-go#the-ready-to-go-coaching)
- [Plateforme Microsoft Collaborate](http://aka.ms/Collaborate)

Pour plus d'informations sur la création d'une offre [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], consultez les détails du [Programme Ready to Go](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-ready-to-go). Si vous avez des questions ou des commentaires concernant le programme **Ready to Go**, vous pouvez [nous contacter](mailto:dyn365bep@microsoft.com). 

## <a name="see-also"></a>Voir aussi
[Mise en route](product-get-started.md)  
[Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions](ui-extensions.md)  
[https://appsource.microsoft.com](https://appsource.microsoft.com/en-us/marketplace/apps?product=dynamics-365-for-financials&page=1)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
 
