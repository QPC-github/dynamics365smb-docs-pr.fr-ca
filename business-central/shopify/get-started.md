---
title: Mise en route du connecteur pour Shopify
description: Premières étapes lors de la configuration de la connexion entre Business Central et Shopify
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.reviewer: solsen
ms.search.form: 30100, 30101, 30102, 30103, 30104, 30135,
author: AndreiPanko
ms.author: andreipa
ms.openlocfilehash: e59dd0dcf757fbcf76d4068756adfe7bc9475f54
ms.sourcegitcommit: 38b1272947f64a473de910fe81ad97db5213e6c3
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 08/29/2022
ms.locfileid: "9361566"
---
# <a name="get-started-with-the-shopify-connector"></a>Mise en route du connecteur Shopify

Connectez votre magasin Shopify (ou vos magasins) avec [!INCLUDE [prod_short](../includes/prod_short.md)] et optimisez la productivité de votre entreprise. Gérez et affichez les informations de votre entreprise et de votre magasin Shopify comme une seule unité. 

Le connecteur Shopify prend en charge les capacités suivantes :

- Prise en charge de plusieurs magasins Shopify  

  - Chaque magasin a sa propre configuration, y compris un ensemble de produits, d’emplacements utilisés pour calculer l'inventaire et des listes de prix.  
- Synchronisation bidirectionnelle d’articles ou de produits  

  - Le connecteur synchronisera les images, les variantes article, les codes-barres, les références fournisseur, les textes étendus et les balises.  
  -    Exportez les attribut article dans Shopify.  
  -    Utilisez les groupes prix client et les escomptes sélectionnés pour définir les prix exportés vers Shopify.  
  -    Décidez si les articles peuvent être créés automatiquement ou n’autorisez que les mises à jour des produits existants.  
- Synchronisation des niveaux d'inventaire  

  -    Choisissez certains ou tous les emplacements disponibles dans [!INCLUDE [prod_short](../includes/prod_short.md)].  
  -    Mettez à jour les niveaux d'inventaire sur plusieurs emplacements dans Shopify.  
- Synchronisation bidirectionnelle des clients  

  -    Mappez intelligemment les clients par téléphone et courriel.  
  -    Utilisez des modèles spécifiques au pays lors de la création de clients, ce qui permet de garantir que les paramètres fiscaux sont corrects.  
- Importer des commandes depuis Shopify  

  -    Lors de l’importation, vous pouvez créer automatiquement des clients dans [!INCLUDE [prod_short](../includes/prod_short.md)] ou décider de gérer les clients dans Shopify.  
  -    Incluez les commandes créées dans d’autres canaux, tels que Shopify PDV ou Amazon.  
  -    Frais d’expédition, cartes-cadeaux, pourboires, modes d’expédition et de paiement, transactions et risque de fraude.  
  - Recevez des informations de paiement de Shopify Payments.  
- Suivi facile des informations d’exécution  

  -    Choisissez éventuellement d’écrire des informations de suivi des articles à partir de [!INCLUDE [prod_short](../includes/prod_short.md)] dans Shopify.  

Pour utiliser Shopify avec [!INCLUDE [prod_short](../includes/prod_short.md)], vous devez d’abord effectuer quelques actions. Cet article sert de guide pour terminer l’intégration de votre magasin Shopify avec [!INCLUDE [prod_short](../includes/prod_short.md)].

## <a name="prerequisites-for-shopify"></a>Conditions préalables pour Shopify

Vous devez disposer :

- D’un compte Shopify
- D’une boutique en ligne Shopify

Pour créer un compte Shopify ou vous inscrire à un essai gratuit de 14 jours, accédez à [Shopify](https://www.shopify.com/). Pour plus d’informations sur la création et la personnalisation de votre boutique en ligne, voir le[Centre d’aide de Shopify](https://help.shopify.com/).
  
D’autres canaux de vente sont pris en charge, par exemple, le PDV Shopify.

### <a name="recommended-settings"></a>Paramètres recommandés

- Désactivez **Archiver automatiquement la commande** dans la section **Traitement des commandes** des paramètres [**Validation**](https://www.shopify.com/admin/settings/checkout) dans l’**administration Shopify**.

Pour en savoir plus sur les paramètres Shopify pour les scénarios de démonstration et d’essai, voir [Scénarios de test et de formation](/dynamics365/business-central/dev-itpro/administration/admin-shopify-connector#preparation).

## <a name="prerequisites-for-business-central"></a>Conditions préalables pour Business Central

- Assurez-vous que l’application **[Shopify Connector](https://go.microsoft.com/fwlink/?linkid=2196238)** est installée.

L’application est préinstallée pour toutes les nouvelles inscriptions et tous les essais. En savoir plus sur l’installation d’applications à partir de la place de marché dans [Installation et désinstallation des extensions](../ui-extensions-install-uninstall.md#install). Suivez les étapes ci-dessous si vous n’avez pas [!INCLUDE[prod_short](../includes/prod_short.md)].

## <a name="installing-the-dynamics-365-business-central-app-to-your-shopify-online-store"></a>Installation de l’application **Dynamics 365 Business Central** pour votre boutique en ligne Shopify

Pour le [!INCLUDE[prod_short](../includes/prod_short.md)] existant, cette étape est facultative et peut être ignorée.

1. Localisez l’application [Dynamics 365 Business Central](https://apps.shopify.com/dynamics-365-business-central) sur l’[AppStore Shopify](https://apps.shopify.com/)
2. Cliquez sur le bouton **Ajouter des applications**. Si vous y êtes invité, connectez-vous à votre compte Shopify. Sélectionnez la boutique en ligne souhaitée si vous en avez plusieurs.
3. Après avoir passé en revue la confidentialité et les autorisations, choisissez le bouton **Installer l’application**.
  Vous pouvez trouver et ouvrir l’application **Dynamics 365 Business Central** installée dans la section **Applications** dans l’encadré **Adinistrateur Shopify**.
4. Choisissez **S’inscrire maintenant** pour commencer l’essai [!INCLUDE[prod_short](../includes/prod_short.md)] ou **Se connecter** si vous avez déjà [!INCLUDE[prod_short](../includes/prod_short.md)]. Vous serez redirigé vers votre [!INCLUDE[prod_short](../includes/prod_short.md)] sur [Business Central](https://businesscentral.dynamics.com).
5. Les étapes suivantes doivent avoir lieu dans [!INCLUDE[prod_short](../includes/prod_short.md)].

## <a name="connecting-business-central-to-the-shopify-online-store"></a>Connexion de Business Central à la boutique en ligne Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasin Shopify** et choisissez le lien associé.
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Code**, saisissez le code voulu.  
4. Dans le champ **URL Shopify**, tapez l’URL de votre boutique en ligne, qui doit être connectée. Utilisez le format suivant : `https://{shop}.myshopify.com/`.
5. Activez la bascule **Activé**, lisez et acceptez les conditions générales.
6. Si vous y êtes invité, connectez-vous à votre compte Shopify, passez en revue la confidentialité et les autorisations, puis cliquez sur le bouton **Installer l’application**.

Répétez les étapes 2 à 6 pour toutes les boutiques en ligne que vous voulez connecter.

### <a name="next-steps"></a>Étapes suivantes

Votre boutique en ligne est désormais connectée à [!INCLUDE[prod_short](../includes/prod_short.md)]. Dans les étapes suivantes, vous allez définir comment et quoi synchroniser.

- [Synchroniser les articles](synchronize-items.md)
- [Synchroniser les clients](synchronize-customers.md)
- [Synchroniser les commandes](synchronize-orders.md)

## <a name="see-also"></a>Voir aussi

[Scénarios de test et de formation](/dynamics365/business-central/dev-itpro/administration/admin-shopify-connector).
