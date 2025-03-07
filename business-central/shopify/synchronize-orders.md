---
title: Synchroniser et exécuter les documents de vente
description: Configurer et exécuter l’importation et le traitement des documents de vente à partir de Shopify.
ms.date: 06/06/2023
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: '30110, 30111, 30112, 30113, 30114, 30115, 30121, 30122, 30123, 30128, 30129,'
author: andreipa
ms.author: andreipa
ms.reviewer: bholtorf
---

# Synchroniser et exécuter les documents de vente

Cet article décrit les paramètres et les étapes à effectuer pour synchroniser et exécuter les documents de vente avec Shopify dans [!INCLUDE[prod_short](../includes/prod_short.md)].

## Définir l’importation des commandes sur la Fiche magasin Shopify

Saisissez un **Code devise** si la boutique en ligne utilise une devise différente de la devise locale ($). La devise spécifiée doit avoir des taux de change configurés. Si votre boutique en ligne utilise la même devise que [!INCLUDE[prod_short](../includes/prod_short.md)], laissez le champ vide. 

Vous pouvez voir la devise du magasin dans les paramètres [Détails du magasin](https://www.shopify.com/admin/settings/general) dans votre Admin Shopify. Shopify peut être configuré pour accepter différentes devises, cependant, les commandes importées dans [!INCLUDE[prod_short](../includes/prod_short.md)] utilisent la devise du magasin.

Une commande Shopify classique peut inclure des coûts en plus du sous-total, comme les frais d’expédition ou, s’ils sont activés, les pourboires. Ces montants sont reportés directement dans le compte du grand livre que vous souhaitez utiliser pour des types de transactions spécifiques :

* **Compte frais d’expédition**
* **Compte carte cadeau vendu** ; en savoir plus dans la rubrique [Carte cadeau](synchronize-orders.md#gift-cards)
* **Compte de pourboires**  

Activez **Créer automatiquement des commandes** pour créer automatiquement des documents vente dans [!INCLUDE[prod_short](../includes/prod_short.md)] après l’importation de la commande Shopify.

Si vous souhaitez libérer automatiquement un document de vente, activez le bouton bascule **Libérer automatiquement les documents de vente**.

Le document de vente dans [!INCLUDE[prod_short](../includes/prod_short.md)] génère un lien vers la commande Shopify, et vous pouvez ajouter un champ qui n’est pas déjà affiché sur la page. Pour en savoir plus sur l’ajout d’un champ, accédez à [Commencer à personnaliser une page via la bannière **Personnalisation**](../ui-personalization-user.md#to-start-personalizing-a-page-through-the-personalizing-banner). Si vous sélectionnez le champ **N° commande sur n° ligne doc. Shopify**, ces informations sont répétées dans les ligne vente de type **Commentaire**.

Dans le champ **Priorité zone recouvrement**, vous pouvez définir la priorité en matière de sélection du code zone recouvrement sur les adresses dans la commande. La commande Shopify importée contient des informations sur les taxes. Les taxes sont recalculées lorsque vous créez le document de vente, il est donc important que les paramètres de TVA/taxe soient corrects dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Pour plus d’informations sur les taxes, voir [Configurer les taxes pour la connexion Shopify](setup-taxes.md).

Précisez comment vous traiterez les retours et les remboursements :

* **Vide** spécifie que vous n’importez pas et ne traitez pas les retours et les remboursements.
* **Importer uniquement** indique que vous importez des informations, mais vous créerez manuellement la note de crédit correspondante.
* **Créer automatiquement une note de crédit** spécifie que vous importez des informations et [!INCLUDE[prod_short](../includes/prod_short.md)] crée automatiquement les notes de crédit. Cette option nécessite que vous activiez le bouton à bascule **Créer automatiquement un document de vente**.

Spécifiez un emplacement pour les retours et des comptes du grand livre pour les remboursements de marchandises et autres remboursements.

* **Articles non réapprovisionnés du compte de remboursement** : indique un n° compte du grand livre pour les articles pour lesquels vous ne souhaitez pas avoir de correction d’inventaire.
* **Compte de remboursement** : indique un compte du grand livre pour la différence entre le montant total remboursé et le montant total des articles.

En savoir plus sur [Retours et remboursements](synchronize-orders.md#returns-and-refunds)

### Mappage des méthodes de livraison

Le **Code méthode de livraison** pour les documents vente importés de Shopify peut être renseigné automatiquement. Vous devez configurer le **Mappage méthodes de livraison**.

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez définir le mappage pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Mappage méthodes de livraison**. Cela crée automatiquement les enregistrements des conditions de livraison définis dans les paramètres [**Expédition**](https://www.shopify.com/admin/settings/payments) dans l’**administration Shopify**.
4. Dans le champ **Nom**, vous affichez le nom de la condition de livraison de Shopify.
5. Saisissez le **Code méthode de livraison** avec la méthode de livraison correspondante dans [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]  
> Si plusieurs frais d’expédition sont associés à un document de vente, un seul est sélectionné comme la méthode de livraison et affecté au document vente.

### Cartographie des emplacements

Le mappage de l’emplacement est requis à trois fins :

* Pour en savoir plus sur la façon de synchroniser l'inventaire, voir [Synchroniser l'inventaire sur Shopify](synchronize-items.md#sync-inventory-to-shopify)
* Pour remplir le **Code d’emplacement** pour les documents de vente importés de Shopify. C’est important lorsque le bouton à bascule **Emplacement Obligatoire** est activé dans la fiche **Configuration inventaire**, sinon vous ne pourrez pas créer de documents vente.
* Pour mettre à jour la commande Shopify avec les informations d’exécution basées sur la page **Livraison vente reportée**.

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez configurer le mappage des emplacements pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Emplacements** pour ouvrir les **Emplacements des magasins Shopify**.
4. Sélectionnez l’action **Obtenir les emplacements Shopify** pour importer tous les emplacements définis dans Shopify. Ils se trouvent dans les paramètres [**Emplacements**](https://www.shopify.com/admin/settings/locations) du volet **Administration Shopify**. Notez que l’emplacement marqué comme *Par défaut* sera utilisé lors de l’importation de commandes Shopify non remplies.
5. Entrez le **Code d’emplacement par défaut** avec l’emplacement correspondant dans [!INCLUDE[prod_short](../includes/prod_short.md)].

## Exécuter la synchronisation des commandes

La procédure suivante décrit comment importer et mettre à jour les documents de vente.

> [!NOTE]  
> Les commandes archivées dans Shopify ne peuvent pas être importées. Désactivez l’option **Archiver automatiquement la commande** dans la section **Traitement des commandes** des paramètres **Validation** dans le volet **Administration Shopify** pour vérifier que toutes les commandes sont importées dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Pour importer des commandes archivées, utilisez l’action **Désarchiver les commandes** dans la page [Commandes](https://www.shopify.com/admin/orders) du volet  **Administration Shopify**.

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez importer des commandes pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Commandes**.
4. Sélectionnez l’action **Synchroniser les commandes à partir de Shopify**.
5. Définissez des filtres sur les commandes si nécessaire. Par exemple, vous pouvez importer les commandes entièrement payées ou celles présentant un faible niveau de risque.

> [!NOTE]  
> Lors du filtrage par balise, vous devez utiliser les jetons de filtre `@` et `*`. Par exemple, si vous souhaitez importer des commandes contenant *tag1*, utilisez `@*tag1*`. `@` assurera que le résultat ne respecte pas la casse, tandis que `*` recherche des commandes avec plusieurs balises.

6. Cliquez sur le bouton **OK**.

Sinon, vous pouvez rechercher le traitement en lot **Synchroniser les commandes à partir de Shopify**.

Vous pouvez programmer la tâche pour qu’elle soit exécutée automatiquement. En savoir plus dans la section [Programmer des tâches récurrentes](background.md#to-schedule-recurring-tasks).

## Passer en revue les commandes importées

Une fois l’importation terminée, vous pouvez explorer la commande Shopify et trouver toutes les informations associées comme les transactions de paiement, les frais d’expédition, le niveau de risque, les attributs et balises de commande ou les exécutions, si la commande a déjà été exécutée dans Shopify. Vous pouvez également voir les confirmations de commande envoyées au client en sélectionnant l’action **Page d'état Shopify**.

> [!NOTE]  
> Vous pouvez accéder directement à la fenêtre **Commandes Shopify** pour afficher les commandes dont l'état est défini sur *Ouvert* dans tous les magasins. Pour consulter les commandes terminées, vous devez ouvrir la page **Commandes Shopify** à partir de la fenêtre **Fiche magasin Shopify** spécifique.

## Créer des documents vente dans Business Central

Si le bouton à bascule **Créer automatiquement des commandes** est activée sur la **Fiche magasin Shopify**, [!INCLUDE[prod_short](../includes/prod_short.md)] tente de créer un document vente après l’importation de la commande. Si des problèmes tels qu’un client ou un produit manquant surviennent, vous devrez les résoudre, puis créer à nouveau le document de vente.

### Pour créer des documents vente

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez synchroniser les commandes pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Commandes**.
4. Sélectionnez la commande pour laquelle vous voulez créer un document vente et sélectionnez l’action **Créer documents vente**.
5. Choisissez **Oui**.

Si la commande Shopify exige une exécution, un **document de vente** est créé. Pour les commandes Shopify exécutées, telles que les commandes qui ne contiennent qu’une carte-cadeau ou qui sont déjà traitées dans Shopify, une **Facture vente** est créée.

Un document vente est maintenant créé et peut être géré en utilisant les fonctionnalités standard de [!INCLUDE[prod_short](../includes/prod_short.md)].

### Gérer les clients manquants

Si vos paramètres empêchent la création automatique d’un client et qu’un client existant approprié est introuvable, vous devez attribuer un client à la commande Shopify manuellement. Il explique plusieurs méthodes pour y parvenir :

* Vous pouvez attribuer le **N° débiteur** et **N° client facturé** directement dans la page **Commandes Shopify** en choisissant un client dans la liste des clients existants.
* Vous pouvez sélectionner un code modèle client, puis créer et affecter le client par l’action **Créer un client** dans la page **Commandes Shopify**. Remarquez que le client Shopify doit avoir au moins une adresse. Les commandes créées via le canal de vente du PDV Shopify manquent souvent de détails d’adresse.
* Vous pouvez mapper un client existant avec le **Client Shopify** existant dans la fenêtre **Clients Shopify**, puis sélectionner l’action **Trouver le mappage** dans la page **Commandes Shopify**.

### Comment le connecteur choisit le client à utiliser

La fonction *Importer la commande à partir de Shopify* tente de sélectionner le client dans l’ordre suivant :

1. Si le **N° client par défaut** est défini dans **Modèle client Shopify** pour le **Code pays/région destinataire**, puis le **N° client par défaut** est utilisé quels que soient les paramètres dans les champs **Importation client à partir de Shopify** et **Type de mappage client**. En savoir plus sur [Modèle client par pays](synchronize-customers.md#customer-template-per-country).
2. Si le champ **Importation client à partir de Shopify** est défini sur *Aucun* et le champ **N° client par défaut** est défini sur la page **Fiche magasin Shopify**, alors le **N° client par défaut** est utilisé.

Les étapes suivantes dépendent du champ **Type de mappage client**.

* **Toujours prendre le client par défaut**, puis le connecteur utilise le client défini dans le champ **N° client par défaut** dans la page **Fiche magasin Shopify**.
* **Par courriel/téléphone**, le connecteur tente d’abord de trouver le client existant par code, puis par courriel, puis par téléphone. Si le client est introuvable, le connecteur crée un client.
* **Par informations de facturation**, le connecteur tente d’abord de trouver le client existant par code, puis par adresse facturation. Si le client est introuvable, le connecteur crée un client.

> [!NOTE]  
> Le connecteur utilise les informations de l’adresse facturation et crée le client facturé dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Le débiteur correspond au client facturé.

### Différentes règles de traitement des commandes

Vous souhaiterez peut-être traiter les commandes différemment en fonction d’une règle. Par exemple, les commandes provenant d’un canal de vente spécifique, comme le point de vente, doivent utiliser le client par défaut, mais vous souhaitez que votre boutique en ligne ait de vraies informations sur le client.

Une façon de répondre à cette exigence consiste à créer une fiche Shopify Shop supplémentaire et à utiliser des filtres dans la page de demande **Synchroniser des commandes à partir de Shopify** .

Exemple : vous avez une boutique en ligne ainsi qu’un PDV Shopify. Pour votre PDV, vous souhaitez utiliser un client fixe, mais pour votre boutique en ligne, vous souhaitez créer des clients dans [!INCLUDE[prod_short](../includes/prod_short.md)]. La procédure suivante répertorie les étapes de haut niveau. Pour en savoir plus, consultez les articles d’aide correspondants.

1. Créez une boutique Shopify appelée *MAGASIN* et associez-la à votre compte Shopify.
2. Configurez la synchronisation article/produit pour que ce magasin gère les informations produit.
3. Spécifiez que les clients sont importés avec les commandes. Le connecteur doit trouver des clients en recherchant leur adresse de courriel. S’il ne trouve pas d’adresse, il utilise le modèle de client pour créer un client.
4. Créez une boutique Shopify appelée *PDV* et associez-la au même compte Shopify.
6. Assurez-vous que la synchronisation article/produit est désactivée.
7. Sélectionnez le connecteur qui utilise le client par défaut.
8. Créez une entrée de file d’attente de tâches récurrentes pour le rapport 30104 **Synchroniser les commandes à partir de Shopify**. Sélectionnez **MAGASIN** dans le champ **Code magasin Shopify** et utilisez des filtres pour saisir toutes les commandes sauf celles qui passent par le canal de vente PDV crée. Par exemple, **<>Point de vente**
9. Créez une entrée de file d’attente de tâches récurrentes pour le rapport 30104 **Synchroniser les commandes à partir de Shopify**. Sélectionnez **PDV** dans le champ **Code magasin Shopify** et utilisez des filtres pour saisir les commandes générées par le canal de vente PDV. Par exemple, **Point de vente**.

Chaque file d’attente importe et traite les commandes dans les filtres définis et utilise les règles de la fiche magasin Shopify correspondante. Par exemple, elles créent des commandes de point de vente pour le client par défaut.

>![Important] Pour éviter les conflits lors du traitement des commandes, n’oubliez pas d’utiliser la même catégorie de file d’attente pour les deux entrées de file d’attente.

### Impact des modifications des commandes

Dans Shopify :

|Modifier|Impact pour la commande déjà importée|Impact pour la commande importée pour la première fois|
|------|-----------|-----------|
|Modifier l’emplacement d’exécution | L’emplacement d’origine est dans les lignes | L’emplacement d’exécution est synchronisé avec [!INCLUDE[prod_short](../includes/prod_short.md)].|
|Modifier une commande et accroître sa quantité| L’en-tête de la commande et les tableaux supplémentaires seront mis à jour dans [!INCLUDE[prod_short](../includes/prod_short.md)], les lignes ne le seront pas.| La commande importée utilise la nouvelle quantité|
|Modifier une commande et réduire sa quantité| L’en-tête de la commande et les tableaux supplémentaires seront mis à jour dans [!INCLUDE[prod_short](../includes/prod_short.md)], les lignes ne le seront pas.| La commande importée utilise la quantité d’origine, le champ Quantité réalisable contient une nouvelle valeur.|
|Modifier une commande et supprimer un article existant | L’en-tête de la commande et les tableaux supplémentaires seront mis à jour dans [!INCLUDE[prod_short](../includes/prod_short.md)], les lignes ne le seront pas.| L’article supprimé est toujours importé, le champ Quantité réalisable contient la valeur zéro. |
|Modifier une commande et ajouter un nouvel article | L’en-tête de la commande sera mis à jour, pas les lignes. | Les articles originaux et ajoutés sont importés. |
|Traiter la commande : remplir, mettre à jour les informations de paiement | L’en-tête de la commande est mis à jour, pas les lignes. |Le changement n’a aucun impact sur la façon dont la commande est importée.|
|Annuler une commande | L’en-tête de la commande est mis à jour, pas les lignes. |La commande annulée n’est pas importée |

Dans [!INCLUDE[prod_short](../includes/prod_short.md)] :

|Modifier|Impact|
|------|-----------|
|Remplacez l’emplacement par un autre emplacement, mappé sur les emplacements Shopify. Reportez la livraison. | La commande est marquée comme exécutée. L’emplacement d’origine est utilisé. |
|Remplacez l’emplacement par un autre emplacement, non mappé sur les emplacements Shopify. Reportez la livraison. | Le traitement ne sera pas synchronisé avec Shopify. |
|Réduisez la quantité. Reportez la livraison. | La commande Shopify est marquée comme partiellement exécutée. |
|Augmentez la quantité. Reportez la livraison. | Le traitement ne sera pas synchronisé avec Shopify. |
|Ajoutez un nouvel article. Reportez la livraison. | La commande Shopify est marquée comme exécutée. Les lignes ne sont pas mises à jour. |

## Synchroniser les livraisons avec Shopify

Lorsqu’un document de vente créé à partir d’une commande Shopify est livré, vous pouvez synchroniser les livraisons avec Shopify.

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Synchroniser livraisons avec Shopify**, puis sélectionnez le lien associé.
2. Définissez les filtres sur les livraisons si nécessaire. Par exemple, vous pouvez mettre à jour une livraison reportée à une date donnée.
3. Cliquez sur le bouton **OK**.

La commande dans Shopify est marquée comme exécutée. Le client reçoit automatiquement un courriel ou un SMS d’avis de livraison. Si un agent de livraison et un code de suivi sont spécifiés sur la livraison, les informations de suivi sont indiquées dans le courriel.

Sinon, utilisez l’action **Synchroniser les livraisons** sur les pages Documents de vente Shopify ou Magasin Shopify.

Vous pouvez programmer la tâche pour qu’elle soit exécutée de manière automatisée. En savoir plus dans la section [Programmer des tâches récurrentes](background.md#to-schedule-recurring-tasks).

>[!Important]
>L’emplacement, y compris l’emplacement vide, défini dans la ligne de livraison reportée doit avoir un enregistrement correspondant dans l’emplacement Shopify. Sinon, cette ligne ne sera pas renvoyée à Shopify. En savoir plus sur le [Mappage d’emplacement](synchronize-orders.md#location-mapping).

N’oubliez pas d’exécuter **Synchroniser les commandes à partir de Shopify** pour mettre à jour l'état d’exécution d'une commande dans [!INCLUDE[prod_short](../includes/prod_short.md)]. La fonctionnalité du connecteur archive également les commandes entièrement payées et exécutées à la fois dans Shopify et dans [!INCLUDE[prod_short](../includes/prod_short.md)] si les conditions sont remplies.

### Agents de livraison et URL de suivi

Si le document **Livraison vente reportée** contient le **Code agent de livraison** et/ou le **N° de suivi du colis**, ces informations seront envoyées à Shopify et au client dans le courriel de confirmation de livraison.

La compagnie de suivi est renseignée dans l'ordre suivant (du plus élevé au plus faible), en fonction de l’enregistrement de l'agent de livraison :

* **Compagnie de suivi Shopify**
* **Nom**
* **Code**

Si le champ **URL de suivi des colis** est renseigné pour l’enregistrement de l'agent de livraison, la confirmation de livraison contiendra aussi une URL de suivi.

## Retours et remboursements

Dans une intégration entre Shopify et [!INCLUDE[prod_short](../includes/prod_short.md)], il est important de pouvoir synchroniser autant de données métier que possible. Cela facilite la mise à jour de vos niveaux de financement et d’inventaire dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Les données que vous pouvez synchroniser incluent les retours et les remboursements qui ont été enregistrés dans Administrateur Shopify ou PDV Shopify.

Les retours et les remboursements sont importés avec leurs commandes associées si vous avez activé le type de traitement sur la fiche magasin Shopify.

Les retours sont importés à des fins d’information uniquement. Aucune logique de traitement ne leur est associée.

Les transactions financières et, si nécessaire, les transactions d’inventaire sont traitées via des remboursements. Les remboursements peuvent inclure des produits ou simplement des montants, par exemple, si un marchand a décidé de compenser les frais d’expédition ou un autre montant.
Vous pouvez créer des notes de crédit vente pour les remboursements. Les avoirs peuvent avoir les types de lignes suivants :

|Type|N°|Commentaire|
|-|-|-|
|Compte du grand livre|Compte carte cadeau vendu| À utiliser pour les remboursements liés aux cartes-cadeaux.|
|Compte du grand livre|Articles non-stockés du compte de remboursement | Utilisez pour les remboursements associés à des produits qui n’ont pas été réapprovisionnés. |
|Article |Nombre d'articles| Utilisez pour les remboursements associés à des produits qui ont été réapprovisionnés. Valable pour les remboursements directs ou les remboursements liés aux remboursements. Le code d’emplacement sur la ligne de crédit plus est défini en fonction de la valeur sélectionnée pour l’emplacement de retour.|
|Compte du grand livre| Compte de remboursement | Utilisez pour d’autres montants remboursés qui ne sont pas associés à des produits ou à des cartes-cadeaux. Par exemple, des pourboires, ou si vous avez indiqué manuellement un montant à rembourser dans Shopify. |

>[!Note]
>L’emplacement de retour, y compris les emplacements vides, définis dans la **Fiche emplacement Shopify** sont utilisés sur la note de crédit créée. Le système ignore les emplacements d’origine des commandes ou des expéditions.

## Cartes cadeaux

Dans le magasin Shopify, vous pouvez vendre des cartes cadeaux, qui peuvent être utilisées pour acheter des produits.

En matière de cartes cadeaux, il est important de saisir une valeur dans le champ **Compte carte cadeau vendu** dans la fenêtre **Fiche magasin Shopify**. La carte cadeau vendue est synchronisée avec les commandes en cours. Une carte cadeau appliquée est également importée avec la commande, mais en tant que transaction. Notez que la carte cadeau ne diminue pas le montant à facturer.

Pour examiner les cartes cadeaux appliquées et émises, sélectionnez l’icône ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Cartes cadeaux**, puis choisissez le lien associé.

## Voir aussi .

[Mise en route du connecteur pour Shopify](get-started.md)  
