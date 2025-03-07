---
title: Enregistrer les prix de vente spéciaux et les escomptes
description: Décrit comment définir et appliquer des ententes de tarification et d'escompte pour les documents vente.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: ivkoleti
ms.topic: how-to
ms.date: 06/13/2023
ms.custom: bap-template
ms.search.keywords: 'special price, alternate price, pricing'
ms.search.form: '7022, 7024'
---

# Enregistrer les prix de vente spéciaux et les escomptes

> [!NOTE]
> Dans la 2e vague de lancement de 2020, nous avons lancé de nouveaux processus rationnalisés pour la configuration et la gestion des prix et des escomptes. Si vous êtes un nouveau client utilisant la dernière version, vous utilisez la nouvelle expérience. Si vous êtes un client existant, l’utilisation ou non de la nouvelle expérience dépend du fait que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes** dans **Gestion des fonctionnalités**. En savoir plus sur [Activer les fonctionnalités à venir à l’avance](/dynamics365/business-central/dev-itpro/administration/feature-management) dans le contenu de l’administration.

[!INCLUDE[prod_short](includes/prod_short.md)] prend en charge diverses stratégies de tarification, telles que :

* Modèles à prix unique où un article est toujours vendu au même prix.
* Ententes de prix spéciales avec des clients spécifiques ou des groupes de clients.
* Promotions lorsqu’une vente répond aux critères d’une offre spéciale. Par exemple, vous pouvez avoir les critères suivants pour une commande :

  * Elle répond à une quantité minimale
  * Elle est antérieure à une certaine date
  * Elle inclut un certain type d’article  

Pour utiliser un modèle de tarification de base, il vous suffit de spécifier un prix unitaire lorsque vous configurez un article ou une ressource. Ce prix sera toujours utilisé sur les documents vente. Pour les modèles plus avancés, par exemple, lorsque vous proposez des prix spéciaux pour une promotion de vente, vous pouvez spécifier des critères sur la page **Prix de vente**. Vous pouvez proposer des prix spéciaux basés sur une combinaison des informations suivantes :  

* Client
* Article ;
* Unité de mesure
* Quantité minimale
* Dates qui définissent la période pour laquelle les prix sont valables.

Après avoir défini des prix spéciaux, [!INCLUDE[prod_short](includes/prod_short.md)] peut calculer les meilleurs prix sur les documents vente et achat, et sur les lignes de travail et les journaux articles. En savoir plus sur [Calcul du meilleur prix](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

Pour les escomptes vente, vous pouvez configurer deux types différents :

| Type d'escompte | Désignation |
| --- | --- |
| **Escompte ligne vente** |Ajoutez un montant utilisé sur les lignes vente s’il existe une certaine combinaison de client, d’article, de quantité minimale, d’unité de mesure ou de date de début et date de fin. Ce type fonctionne de la même manière que pour les prix de vente. |
| **Escompte facture** |Pourcentage d’escompte qui est soustrait du total du document vente si la somme de toutes les lignes du document dépasse un montant minimal donné. |

> [!TIP]  
> Si un article ne doit jamais être vendu avec un escompte, laissez les champs d’escompte de la page article vides, et n’incluez pas l’article dans une quelconque configuration d’escompte ligne.

## Pour définir un prix de vente pour un client

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. Si la mise à jour des fonctionnalités n’est pas activée, suivez les étapes de l’onglet Expérience actuelle. 

#### [Expérience actuelle](#tab/current-experience/)

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Clients**, puis sélectionnez le lien associé.
2. Choisissez le client, puis sélectionnez l’action **Prix**.
3. Renseignez les champs de la ligne selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Renseignez une ligne pour chaque combinaison qui accorde un prix de vente spécial au client.

#### [Nouvelle expérience](#tab/new-experience/)  

Par défaut, l’état des nouvelles listes de prix est **Brouillon**. Les projets de tarifs ne sont pas inclus dans les calculs de prix. Lorsque vous avez terminé d’ajouter des lignes et que vous souhaitez commencer à utiliser les prix, remplacez l'état par **Actif**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Clients**, puis sélectionnez le lien associé.
2. Choisissez le client, puis sélectionnez l’action **Listes prix vente**. 
3. Sélectionnez **Nouveau** pour créer une liste prix vente.
4. Sur les raccourcis **Général** et **Taxes**, complétez les champs, comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Pour ajouter des éléments à la liste, effectuez l’une des opérations suivantes :
   * Pour ajouter de nombreux éléments, choisissez **Proposer lignes**, puis entrez des critères de filtre pour spécifier les types d’éléments à ajouter. Si vous le souhaitez, vous pouvez saisir des paramètres supplémentaires pour les articles spécifiques à la liste de prix. Si nécessaire, vous pouvez modifier ces paramètres ultérieurement.
   * Pour copier des articles d’une autre liste de prix, choisissez **Copier lignes**, puis choisissez la liste de prix à copier.
   * Pour ajouter des éléments manuellement, dans la grille, dans le champ **Type de produit**, choisissez le type de produit auquel la liste de prix est destinée. En fonction de votre sélection, renseignez les champs restants selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Pour commencer à utiliser la liste de prix, dans le champ **État**, choisissez **Actif**.  

---

## Utilisation des tarifs de vente et d’achat

> [!NOTE]
> L’utilisation des tarifs nécessite que votre administrateur ait activé la mise à jour de la fonctionnalité **Nouvelle expérience de prix de vente** dans **Gestion des fonctionnalités**. En savoir plus sur [Activer les fonctionnalités à venir à l’avance](/dynamics365/business-central/dev-itpro/administration/feature-management) dans le contenu de l’administration.

La nouvelle expérience de tarification des ventes est en grande partie similaire à l’expérience actuelle, mais il existe quelques différences. Ces différences sont décrites dans les sections suivantes.

**Type d’application** et **N° doc. référence.** vous permettent de choisir à quoi des tarifs s’appliqueront, par exemple au groupe prix client ou au client. À l’aide du champ **Afficher les colonnes pour**, vous pouvez afficher ou masquer les colonnes pertinentes pour la définition des prix, des escomptes ou des prix et escomptes.

### Conversion des prix existants lorsque vous activez la mise à jour de la fonctionnalité de tarification

Lorsque vous activez la mise à jour de la fonctionnalité **Nouvelle expérience de prix de vente** sur la page **Gestion des fonctionnalités**, le guide **Mise à jour des données de fonctionnalité** s’ouvre. Utilisez le bouton de basculement **Utiliser les prix par défaut** comme suit :

* Si vous souhaitez utiliser tous les prix sur une seule page, activez-le. Les prix existants seront convertis en une liste de prix par défaut pour chacun des documents suivants :

  * Ventes
  * Achats
  * Ventes projet
  * Achats projet

  Vous pouvez modifier tous les prix pour ces zones sur la page **Feuille prix**. Les listes de prix par défaut seront définies sur les pages **Configuration ventes**, **Configuration achats** et **Configuration projets**.

> [!NOTE]
> Si les prix sont définis uniquement sur les fiches d’articles ou de ressources, les tarifs par défaut ne seront pas renseignés avec ces prix au moment de la mise à jour des données de fonctionnalité. Cependant, vous pouvez ouvrir l’une des listes de prix par défaut ou la page **Feuille prix** et utiliser l’action **Proposer lignes** pour ajouter les prix fixés sur les fiches article ou ressource.

* Pour utiliser les tarifs vente, désactivez-le. Les prix existants sont convertis en une nouvelle liste de prix pour chacun combinaison des éléments suivants :

  * Client
  * Groupe de clients ou promotion
  * Dates de début et de fin
  * Devises

Si vous disposez de plusieurs combinaisons, vous aurez plusieurs listes de prix.

Si vous avez déjà activé la nouvelle expérience de tarification, vous pouvez créer manuellement des tarifs par défaut ou spécifier une liste de prix existante par défaut. Pour définir une liste de prix existante par défaut, activez le bouton de basculement **Autoriser la mise à jour des valeurs par défaut** sur la liste de prix. Ensuite, sur les pages **Configuration ventes**, **Configuration achats** ou **Configuration projets**, définissez les tarifs comme valeurs par défaut.

### Modification des tarifs actifs

Pour permettre aux utilisateurs de modifier les prix sur les listes de prix actives pour les articles, les ressources, les clients, les fournisseurs ou d’autres entités qui utilisent la tarification, activez le bouton de basculement **Autoriser la modification du prix actif** sur les pages **Configuration ventes** et **Configuration achats**.

Quand le bouton de basculement **Autoriser la modification du prix actif** est désactivé, pour mettre à jour les prix dans une liste de prix, vous devez remplacer l'état de la liste de prix par **Brouillon**, effectuer votre modification, puis réactiver la liste de prix.

La page **Vue d’ensemble des prix** fournit un aperçu de tous les prix dans tous les tarifs. Vous pouvez définir des filtres pour affiner la liste des prix que vous souhaitez modifier ou ajouter. Après avoir modifié les prix, vous devez utiliser l’action **Vérifier les lignes** pour vérifier les prix par rapport à d’autres lignes de tarifs. La vérification des prix permet d’éviter les doublons et l’ambiguïté lors du calcul des prix.

> [!NOTE]
> Lorsque vous modifiez une ligne dans une liste de prix active, l'état de la ligne devient **Brouillon** et la ligne ne sera pas prise en compte dans les calculs de prix tant que vous n’aurez pas utilisé l’action **Vérifier les lignes**. Après avoir vérifié le prix, l'état de la ligne devient **Actif** et il sera pris en compte dans les calculs de prix.

Pour ajouter de nouveaux prix, sur la page **Vue d’ensemble des prix**, utilisez l’action **Ajouter de nouvelles lignes**. La page **Feuille prix** s’ouvre et vous pouvez ajouter des lignes de prix en les suggérant en fonction de critères, en les copiant à partir d’autres listes de prix ou en les saisissant manuellement. Ensuite, vous pouvez utiliser l’action **Implémenter nouveaux prix** pour comparer les nouveaux prix à d’autres tarifs afin d’éviter les doublons et l’ambiguïté lors du calcul des prix.

#### Créer des lignes de prix de vente basées sur le prix unitaire

1. Sur la page **Feuille prix**, sélectionnez l’action **Proposer lignes**.
2. Sur la page **Lignes de prix - Créer un nouveau**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Sur le champ **Filtre produit**, définissez des filtres pour le **Type de produit** sélectionné.
4. Choisir le champ **Valeurs par défaut** pour spécifier des paramètres tels que :
   * À quelles entités les tarifs seront attribués.
   * Dates de validité du prix.
   * Code devise.
   * Filtre type montant qui définit les colonnes affichées sur les lignes de la liste de prix.
5. Cliquez sur **OK**. De nouvelles lignes sont ajoutées à la page **Feuille de prix** avec les paramètres sélectionnés et les prix unitaires des fiches articles.
6. Modifiez les lignes créées avec les nouveaux prix unitaires ou escomptes. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### Créer des lignes de prix de vente basées sur les tarifs existants

1. Sur la page **Feuille prix**, sélectionnez l’action **Copier les lignes**.
2. Sur la page **Lignes de prix - Copier existante**, sélectionnez une liste de prix existante sur le champ **À partir des tarifs**.
3. Sur le champ **Filtre ligne prix**, définissez des filtres pour les produits de la liste de prix sélectionnée.
4. Choisir le champ **Valeurs par défaut** pour spécifier des paramètres tels que :
   * À quelles entités les tarifs seront attribués.
   * Dates de validité du prix.
   * Code devise.
   * Filtre type montant qui définit les colonnes affichées sur les lignes de la liste de prix.
5. Renseignez les autres champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Cliquez sur **OK**. De nouvelles lignes sont ajoutées à la page **Feuille prix** avec les paramètres sélectionnés.
7. Modifiez les lignes créées avec les nouveaux prix unitaires ou escomptes. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Pour copier des prix de vente

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. Si la mise à jour des fonctionnalités n’est pas activée, suivez les étapes de l’onglet Expérience actuelle.

#### [Expérience actuelle](#tab/current-experience/)  

Pour copier des prix de vente, comme les prix appliqués à un client et qui doivent être appliqués à tout un groupe de clients, vous devez lancer le traitement par lots **Suggérer prix vente**. traitement en lot sur la page **Feuille prix vente**.  

1. Choisissez l’icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Feuille prix vente**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Suggérer prix vente**    
3. Sur le raccourci **Prix vente**, renseignez les champs **Type vente** et **Code vente** avec les prix de vente d'origine à copier.  
4. Dans la partie supérieure de la page de demande, indiquez dans les champs **Type vente** et **Code vente** le type et le nom sous lesquels vous souhaitez copier les prix de vente.  
5. Pour que le traitement par lots crée des prix, activez la case à cocher **Créer nouveaux prix**.  
6. Cliquez sur le bouton **OK** pour renseigner les lignes de la page **Feuille prix vente** avec les nouveaux prix proposés, en précisant qu’ils sont applicables au type vente sélectionné.  

   > [!NOTE]  
   > Ce traitement en lot crée uniquement des propositions ; il n'effectue pas les modifications proposées. Si les propositions vous conviennent et que vous souhaitez les appliquer, c'est-à-dire les insérer sur la page **Prix vente**, choisissez l'action **Implémenter des modifications de prix**, sur la page **Feuille prix vente**.

#### [Nouvelle expérience](#tab/new-experience/)  

Vous pouvez préciser les réglages que les tarifs utiliseront :

* Utilisez les paramètres de l’en-tête de la liste que vous copiez.
* Utilisez les paramètres à partir de la liste vers laquelle vous effectuez la copie. Pour utiliser les paramètres de la liste de prix dans laquelle vous copiez les prix, activez **Utiliser les valeurs par défaut de la cible**.

1. Choisissez l’icône ![ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Listes prix vente**, puis choisissez le lien associé.
2. Choisissez la liste de prix à copier, puis choisissez **Copier les lignes**.
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > Vous ne pouvez pas avoir deux articles qui ont les mêmes paramètres mais des prix différents. Si cela se produit, un message s’affiche lorsque vous activez la liste de prix. Vous pouvez choisir le prix à utiliser en ouvrant la liste et en supprimant le prix incorrect.  
  
---

## Pour mettre à jour en bloc des prix d'articles

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. Si la mise à jour des fonctionnalités n’est pas activée, suivez les étapes de l’onglet Expérience actuelle.

#### [Expérience actuelle](#tab/current-experience/)

Pour mettre à jour en bloc des prix article, tels que l’augmentation de tous les prix article par un certain pourcentage, vous pouvez renseigner la page Feuille prix vente à l’aide des traitements en lot suivants :

* **Suggérer un prix de vente sur la feuille de travail** suggère des modifications de deux manières :

  * En appliquant un facteur d’ajustement aux prix de vente existants.
  * En copiant les ententes de prix de vente existants vers d’autres clients, groupes de prix client ou promotions de vente.

* **Suggérer un prix d'article sur la feuille de travail** suggère des modifications de deux manières :

  * En appliquant un facteur d’ajustement aux prix de vente existants sur les fiches article.
  * En suggérant des prix pour de nouvelles combinaisons de devises, d’unités de mesure, etc.

  Ce traitement par lots ne change pas les tarifs sur les articles.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Feuille prix vente**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Suggérer prix article**    
3. Sur le raccourci **Article**, renseignez le champ **N°**, ou **Groupe de report inventaire** ou d’autres champs avec les prix article d’origine à mettre à jour.  
4. Dans la partie supérieure de la page de demande, indiquez dans les champs **Type vente** et **Code vente** le type et le nom sous lesquels vous souhaitez copier les prix de vente.
5. Si vous souhaitez que le traitement en lot ajuste automatiquement les prix article proposés, saisissez l’ajustement dans le champ **Facteur ajustement**. Par exemple, vous devez entrer 1,15 dans **Facteur appliqué** pour une augmentation de 15 % des prix unitaires.  
6. Pour que le traitement en lot crée des prix, activez le bouton de basculement **Créer prix**.  
7. Cliquez sur le bouton **OK** pour remplir les lignes sur la page **Feuille prix vente** avec les nouveaux prix suggérés.
8. Pour mettre en œuvre les suggestions, utilisez l’action **Implémenter nouveaux prix**. Le traitement en lot crée des suggestions mais ne les implémente pas. 

#### [Nouvelle expérience](#tab/new-experience/)

Pour mettre à jour les prix de plusieurs articles, vous devez créer une nouvelle liste de prix, puis copier les lignes d’une liste de prix existante. Lorsque vous copiez les lignes, vous pouvez utiliser des filtres pour spécifier les éléments à copier, et vous pouvez spécifier un nombre entier ou décimal dans le champ **Facteur appliqué** pour augmenter ou diminuer les prix. L’état de la liste de prix doit être **Brouillon**. Si nécessaire, vous pouvez alors désactiver l’ancienne liste de prix.

> [!NOTE]
> Vous ne pouvez pas avoir deux lignes qui ont les mêmes paramètres mais des prix différents. Si cela se produit, un message s’affiche lorsque vous activez une liste de prix. Vous pouvez choisir le prix à utiliser en ouvrant la liste et en supprimant le prix incorrect.  

---

## Calcul du meilleur prix

Après avoir enregistré des prix spéciaux et des escomptes ligne pour les ventes et les achats, [!INCLUDE[prod_short](includes/prod_short.md)] calcule le meilleur prix sur les documents vente et achat, et sur les lignes journal article et projet.

Le meilleur prix est le prix le plus bas avec l'escompte de ligne le plus élevé autorisé à une date donnée. [!INCLUDE[prod_short](includes/prod_short.md)] calcule les meilleurs prix lorsqu’il ajoute les prix unitaires et les pourcentages d'escompte de ligne sur les lignes document et journal.

> [!NOTE]  
> Voici une description du calcul du meilleur prix pour la vente. Pour les achats, le calcul est similaire, mais se base sur les paramètres disponibles. Par exemple, les groupes escomptes article ne sont pas pris en charge pour l’achat.

1. [!INCLUDE[prod_short](includes/prod_short.md)] vérifie la combinaison client facturé et article, et calcule le prix unitaire applicable et le pourcentage escompte de ligne à l’aide des critères suivants :

    * Ce client a-t-il une entente pour des prix ou des escomptes ou appartient-il à un groupe bénéficiant d'un telle entente?
    * L'article ou le groupe escompte article sur la ligne est-il inclus dans l'une ou l'autre de ces ententes prix/escompte?
    * La date se trouve-t-elle dans la plage de date de début et de fin de l’accord tarifaire/d’escompte? Pour les factures et les avoirs, il s’agit de la date figurant sur le champ **Date de report** dans l’en-tête du document. Pour tous les autres documents, il s’agit de la date indiquée dans le champ **Date de commande** sur leurs en-têtes.
    * Un code unité de mesure de mesure est-il spécifié? Si c’est le cas, [!INCLUDE[prod_short](includes/prod_short.md)] recherche des prix/escomptes possédant le même code unité de mesure, et des prix/escomptes sans code unité de mesure.

2. [!INCLUDE[prod_short](includes/prod_short.md)] vérifie si des ententes de prix/escompte s’appliquent aux informations de la ligne document ou journal. Il insère ensuite le prix unitaire applicable et le pourcentage d'escompte de ligne en utilisant les critères suivants :

    * Existe-t-il une quantité minimum à respecter dans l'entente de prix/escompte?
    * Existe-t-il une exigence en matière de devise à respecter dans l'entente de prix/escompte? Si c'est le cas, le prix le plus bas et l'escompte ligne le plus élevé pour cette devise sont insérés, même si la devise locale permettrait d'offrir un meilleur prix. S’il n’existe aucune entente de prix/escompte dans le code devise indiqué, [!INCLUDE[prod_short](includes/prod_short.md)] insère le prix le plus bas et l'escompte de ligne le plus élevé dans la devise locale.

Si aucun prix spécial ne peut être calculé pour l'article de la ligne, alors soit le coût unitaire direct, soit le prix unitaire à partir de la fiche article est inséré.

## Escomptes facture vente et frais forfaitaires

Lorsque vous utilisez des escomptes facture, le montant total de la facture détermine celui de l'escompte accordé. Sur la page **Escomptes facture client**, vous pouvez également ajouter des frais de service aux factures supérieures à un montant donné.  

Pour pouvoir utiliser les escomptes facture avec les ventes, vous devez spécifier certaines informations. Vous devez décider ce qui suit :  

* les clients qui se verront accorder ce type d'escompte ;  
* les pourcentages d'escompte à appliquer.  

Sur la page **Configuration ventes**, activez le bouton de basculement **Calculer escompte facture** pour que les escomptes facture soient calculés automatiquement.  

Vous pouvez spécifier si vous proposerez des escomptes facture dès lors qu’une facture remplit certains critères pour chaque client. Par exemple, si le montant de la facture est suffisamment important. Les escomptes facture peuvent être définis en devise locales pour les clients nationaux ou en devise étrangère pour les clients étrangers.  

Vous pouvez associer les pourcentages d'escompte à des montants de facture spécifiques sur la page **Escomptes facture client** pour chaque client. Vous pouvez entrer le nombre de pourcentages de votre choix. Chaque client peut avoir sa propre page, ou vous pouvez lier plusieurs clients à la même page.  

En plus du pourcentage d'escompte (ou à sa place), vous pouvez lier un montant de frais forfaitaires au montant d’une facture.  

> [!TIP]  
> Avant de saisir ces informations dans le programme, il est conseillé de préparer la structure de l'escompte à utiliser. La structure vous permet de déterminer plus facilement les clients pouvant être liés à la même page d'escompte facture. Plus le nombre de pages à configurer est faible, plus vous pouvez saisir rapidement les informations de base.

Pour la formation sur les escomptes sur les ventes, voir [Configurer des escomptes pour vos clients](/training/modules/customer-discounts-dynamics-365-business-central/index).

### Calcul d’escomptes facture pour des ventes

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## Pour définir un escompte de ligne vente pour un client

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. Si la mise à jour des fonctionnalités n’est pas activée, suivez les étapes de l’onglet Expérience actuelle.

#### [Expérience actuelle](#tab/current-experience/)  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Clients**, puis sélectionnez le lien associé.
2. Ouvrez la fiche client appropriée, puis sélectionnez l’action **Escomptes ligne**.
3. Renseignez les champs de la ligne selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Renseignez une ligne pour chaque combinaison qui accorde un escompte ligne vente au client.

> [!NOTE]
> Lorsque vous ouvrez les pages **Prix de vente** et **Escomptes ligne vente** à partir d’un client spécifique, les champs **Filtre type vente** et **Filtre code vente** sont définis pour le client et ne peuvent pas être modifiés ou supprimés.
>
> Pour configurer des prix ou des escomptes ligne pour tous les clients, un groupe de prix client ou une promotion, vous devez ouvrir les pages à partir d’une fiche article. Sinon, pour les prix de vente, utilisez la page **Feuille prix vente**. Pour en savoir plus, voir [Mettre à jour en bloc des prix d’articles](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).  

#### [Nouvelle expérience](#tab/new-experience/)  

1. Choisissez l’icône ![en forme d’ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Clients**, puis sélectionnez le lien associé.
2. Choisissez le client, puis sélectionnez l’action **Listes prix vente**.
3. Ouvrez la liste de prix pour laquelle vous souhaitez spécifier l’escompte ligne.
4. Créez une nouvelle ligne ou choisissez une ligne existante, puis remplissez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Dans le champ **Définit**, choisissez soit **Prix et escompte**, ou juste **Escompte**. 
6. Dans le champ **% escompte ligne**, spécifiez le pourcentage escompte.

    > [!TIP]
    > Si vous modifiez une ligne existante, vous pouvez filtrer les lignes en choisissant l’option appropriée dans le champ **Afficher les colonnes pour**.

    > [!NOTE]  
    > Les codes escompte facture sont représentés par les fiches client existantes. Cela vous permet d'affecter rapidement les conditions d'escompte facture aux clients en sélectionnant le nom d'autres clients qui bénéficient des mêmes conditions. Pour configurer des conditions d’escompte sur facture spécifiques au client, définissez le champ **Code escompte facture** sur le code client du client, puis passez à l’étape suivante.

---

## Pour configurer un escompte facture pour un client

Après avoir décidé quels clients peuvent faire l’objet d'escomptes facture, entrez le code escompte facture sur les pages Fiche client. Ensuite, configurez les conditions pour chaque code.

1. Choisissez l’icône ![en forme d’ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Clients**, puis sélectionnez le lien associé.
2. Ouvrez la page client d’un client pouvant faire l’objet d’escomptes facture.
3. Dans le champ **Code escompte facture**, sélectionnez un code pour les conditions d’escompte facture appropriées à utiliser pour calculer les escomptes facture pour le client.

> [!NOTE]  
> Les codes escompte facture sont représentés par les fiches client existantes. Cela vous permet d'affecter rapidement les conditions d'escompte facture aux clients en sélectionnant le nom d'autres clients qui bénéficient des mêmes conditions.

Configurez de nouvelles conditions d'escompte facture vente.

1. Sur la page **Clients**, sélectionnez l’action **Escomptes facture**. La page **Escomptes facture client** s'ouvre.
2. Dans le champ **Code devise**, indiquez le code d’une devise à laquelle s’appliquent les conditions d’escompte facture. Laissez le champ vierge si vous souhaitez configurer des conditions d'escompte facture en USD.
3. Dans le champ **Montant minimum**, entrez le montant minimal qu’une facture doit présenter pour faire l’objet de l’escompte.
4. Dans le champ **% escompte**, entrez l’escompte facture sous la forme d’un pourcentage du montant de la facture.
5. Répétez les étapes 5 à 7 pour chaque devise pour laquelle le client recevra un escompte facture différent.

## Voir la [formation Microsoft](/training/modules/manage-sales-prices-dynamics-365-business-central/index) associée

## Voir aussi .

[Définition des ventes](sales-setup-sales.md)  
[Ventes](sales-manage-sales.md)  
[Configuration de groupes tarifs client](sales-how-to-set-up-customer-price-groups.md)  
[Configuration des groupes escomptes client](sales-how-to-set-up-customer-discount-groups.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
