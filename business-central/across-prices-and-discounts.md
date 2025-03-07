---
title: Configurer les prix et les escomptes
description: Décrit comment définir des ententes de prix et d’escompte standard et spéciaux pour les ventes et les achats.
author: brentholtorf
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'price, pricing, discount, discounting, rebate, sale, purchase, invoice'
ms.search.form: '459, 460, 7001, 7011, 7015, 7016, 7017, 7018'
ms.date: 04/01/2021
ms.author: bholtorf
---
# <a name="set-up-prices-and-discounts" />Configurer les prix et les escomptes

> [!NOTE]
> Dans la deuxième vague de lancement de 2020, nous avons libéré des processus rationalisés pour la configuration et la gestion des prix et des escomptes. Si vous êtes un nouveau client utilisant cette version, vous utilisez la nouvelle expérience. Si vous êtes un client existant, l’utilisation ou non de la nouvelle expérience dépend du fait que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes** sur la page **Gestion des fonctionnalités**. Pour plus d’informations, consultez [Activer les fonctionnalités à venir à l’avance](/dynamics365/business-central/dev-itpro/administration/feature-management).

Les stratégies de prix et d’escompte pour l’achat et la vente d’articles et de services sont des outils fondamentaux pour les entreprises prospères. Une fois que vous avez configuré les articles et services que votre compagnie achète et vend, vous pouvez définir ce que vous payez ou facturez pour eux, et ces montants seront automatiquement ajoutés aux documents vente et achat. 

## <a name="setting-up-prices-and-discounts" />Configuration des prix et des escomptes

Avant de créer des listes de prix, vous devez définir vos stratégies de tarification et d’escompte sur les pages **Configuration ventes** et **Configuration achats**.

Vous ne pouvez pas configurer les deux types d’escomptes suivants :

| Type d'escompte | Description |
| --- | --- |
| **Remise ligne** |Montant d’escompte accordé pour les lignes sur les documents vente et achat. En règle générale, les escomptes ligne sont basés sur une combinaison de client, d’article, de quantité minimale, d’unité de mesure  ou de période que vous définissez pour les ventes et les achats sur les pages **Configuration ventes** et **Configuration achats**.|
| **Remise facture** |Pourcentage d’escompte qui est soustrait du total du document achat et vente si la somme de toutes les lignes du document dépasse un montant minimal donné. |

Dans la mesure où les prix de vente et les escomptes de ligne de vente sont basés sur une combinaison article/client, vous pouvez également mettre en œuvre cette configuration à partir de la page article de l’article auquel les règles et valeurs s’appliquent.

> [!TIP]  
> Si un article ne doit jamais être vendu avec un escompte, laissez les champs d’escompte de la page article vides, et n’incluez pas l’article dans une quelconque configuration d’escompte ligne.

## <a name="about-price-lists" />À propos des listes de prix

Les listes de prix sont flexibles et vous permettent de spécifier le partenaire commercial ou l’activité auquel elles s’appliquent. Par exemple, vous pouvez configurer une liste de prix qui s’applique à tous les fournisseurs et clients, ou proposer des escomptes ou des prix spéciaux pour chaque partenaire commercial, peut-être en fonction d’une quantité minimale sur les documents d’achat ou de vente, ou d’une certaine combinaison client, article, quantité minimale, unité de mesure ou périodes de temps. Les prix et escomptes que vous définissez sont automatiquement affectés aux documents d’achat et de vente. 

## <a name="set-up-prices" />Configurer les prix

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. 

#### [Expérience actuelle](#tab/current-experience)  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Choisissez le client, puis sélectionnez l’action **Prix**.
3. Renseignez les champs de la ligne selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Renseignez une ligne pour chaque combinaison qui accorde un prix de vente spécial au client.

#### [Nouvelle expérience](#tab/new-experience)  

Vous pouvez ajouter des articles et des services manuellement pour chaque ligne, ou vous pouvez utiliser l’action **Proposer lignes** pour créer de nouveaux prix pour les articles sélectionnés, les groupes escomptes article, les ressources et d’autres types de produits. Si vous choisissez **Proposer lignes**, sur la page **Lignes de prix - Créer un nouveau** vous pouvez utiliser des filtres pour sélectionner les articles ou les services à inclure dans la liste de prix. Vous pouvez également indiquer s’il faut prendre en compte une quantité minimale lors du calcul des prix, le facteur d’ajustement à appliquer pour les nouvelles lignes de liste de prix et la méthode d’arrondissement à appliquer aux prix. 

Par défaut, l’état des nouvelles listes de prix est **Brouillon**. Lorsque vous êtes prêt à commencer à utiliser la liste, vous pouvez remplacer l’état par **Actif**.

Pour consulter les listes de prix et les prix qui s’appliquent à des clients ou fournisseurs spécifiques, sur les pages **Client** ou **Fournisseur**, choisissez l’action **Listes de prix vente** ou **Listes de prix achat**. Pour les articles et les ressources, vous pouvez afficher les lignes de liste de prix en choisissant **Prix de vente** ou **Prix d’achat** sur les pages **Article** et **Ressource**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Choisissez le client, puis sélectionnez l’action **Listes prix vente**. 
3. Sélectionnez **Nouveau** pour créer une liste prix vente.
4. Sur les raccourcis **Général** et **Taxes**, complétez les champs, comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Pour ajouter des éléments à la liste, effectuez l’une des opérations suivantes :
   * Pour ajouter de nombreux éléments, choisissez **Proposer lignes**, puis entrez des critères de filtre pour spécifier les types d’éléments à ajouter. Si vous le souhaitez, vous pouvez également saisir des paramètres supplémentaires pour les articles spécifiques à la liste de prix. Si nécessaire, vous pouvez les modifier ultérieurement.
   * Pour copier des articles d’une autre liste de prix, choisissez **Copier lignes**, puis choisissez la liste de prix à copier.
   * Pour ajouter des éléments manuellement, dans le champ **Type de produit**, choisissez le type de produit auquel la liste de prix est destinée. En fonction de votre sélection, renseignez les champs restants selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Pour commencer à utiliser la liste de prix, dans le champ **État**, choisissez **Actif**.  

---

## <a name="to-set-up-a-sales-line-discount-for-a-customer" />Pour définir un escompte de ligne vente pour un client

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. 

#### [Expérience actuelle](#tab/current-experience/)  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Ouvrez la fiche client appropriée, puis sélectionnez l'action **Remises ligne**.
3. Renseignez les champs de la ligne selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Renseignez une ligne pour chaque combinaison qui accorde une remise ligne vente au client.

> [!Note]
> Lorsque vous ouvrez les pages **Prix de vente** et **Escomptes de ligne de vente** à partir d’un client spécifique, les champs **Filtre type vente** et **Filtre code vente** sont définis pour le client et ne peuvent pas être modifiés ou supprimés.
>
> Pour configurer des prix ou des escomptes ligne pour tous les clients, un groupe de prix client ou une promotion, vous devez ouvrir les pages à partir d’une fiche article. Sinon, pour les prix de vente, utilisez la page **Feuille prix vente**. Pour plus d'informations, voir [Mettre à jour en bloc des prix d'articles](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).  

#### [Nouvelle expérience](#tab/new-experience/)  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Choisissez le client, puis sélectionnez l’action **Listes prix vente**.
3. Ouvrez la liste de prix pour laquelle vous souhaitez spécifier l’escompte ligne.
4. Activez le bouton bascule **Autoriser escompte ligne**.
5. Créez une nouvelle ligne ou choisissez une ligne existante, puis remplissez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Dans le champ **Définit**, choisissez soit **Prix et escompte**, ou juste **Escompte**. 
7. Dans le champ **% escompte ligne**, spécifiez le pourcentage escompte.

   > [!TIP]
   > Si vous modifiez une ligne existante, vous pouvez filtrer les lignes en choisissant l’option appropriée dans le champ **Afficher les colonnes pour**.

---

## <a name="work-with-invoice-discounts-and-service-charges" />Utiliser des escomptes facture et des frais forfaitaires

Lorsque vous utilisez des escomptes de facture, la valeur du montant de la facture détermine celle de l'escompte accordé. Dans la page **Escomptes facture**, vous pouvez également ajouter des frais forfaitaires aux factures supérieures à un montant donné.  <!--The Invoice Discounts page is hard to find.-->

Pour pouvoir utiliser les escomptes facture avec les ventes, vous devez saisir certaines informations dans l'application. Vous devez décider quels clients bénéficieront de ce type d’escompte et les pourcentages escompte que vous utiliserez.  

Sur la page **Configuration des ventes et des comptes à recevoir**, vous pouvez spécifier si les escomptes facture doivent être calculés automatiquement.  

Pour chaque client, vous pouvez indiquer si vous accordez des remises facture si la condition est remplie (si le montant facture est suffisamment élevé). Vous pouvez définir les conditions pour l'escompte facture en devise locale pour les clients nationaux et en devise étrangère pour les clients étrangers.  

Vous pouvez associer les pourcentages escompte à des montants de facture spécifiques sur la page **Escomptes facture**. Vous pouvez entrer autant de pourcentages que nécessaire. Chaque client peut avoir sa propre page, ou vous pouvez lier plusieurs clients à la même page.  

En plus du pourcentage d'escompte (ou à sa place), vous pouvez lier un montant de frais forfaitaires au montant d'une facture.  

> [!TIP]  
> Avant de commencer à saisir ces informations, il est judicieux de préparer au préalable votre structure d’escompte, de sorte qu’il soit plus facile de voir quels clients associer à la même page d’escompte facture. Pour plus d’informations sur les escomptes sur les ventes, voir [Configurer des escomptes pour vos clients](/training/modules/customer-discounts-dynamics-365-business-central/index).

### <a name="to-set-up-an-invoice-discount-for-a-customer" />Pour configurer un escompte facture pour un client

Après avoir décidé des clients pouvant faire l’objet d’escomptes facture, entrez le code escompte facture dans les fiches client et configurez les conditions de chaque code.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Ouvrez la page client d’un client pouvant faire l’objet d’escomptes facture.
3. Dans le champ **Code remise facture**, sélectionnez un code pour les conditions de remise facture appropriées à utiliser pour calculer les remises facture pour le client. <!--Looks like I can only choose customers in this list-->

> [!NOTE]  
> Les codes escompte facture sont représentés par les fiches client existantes. Cela vous permet d'affecter rapidement les conditions d'escompte facture aux clients en sélectionnant le nom d'autres clients qui bénéficient des mêmes conditions.

Configurez de nouvelles conditions d'escompte facture pour les ventes.

1. Sur la page **Clients**, sélectionnez l’action **Escomptes facture**. La page **Escomptes facture client** s'ouvre.
2. Dans le champ **Code devise**, indiquez le code d'une devise à laquelle s'appliquent les conditions de remise facture. Laissez le champ vierge si vous souhaitez configurer des conditions d'escompte facture en USD.
3. Dans le champ **Montant minimum**, entrez le montant minimal qu'une facture doit présenter pour faire l'objet de la remise.
4. Dans le champ **% remise**, entrez la remise facture sous la forme d'un pourcentage du montant de la facture.
5. Répétez les étapes 5 à 7 pour chaque devise pour laquelle le client recevra un escompte facture différent.

L'escompte facture est désormais configuré et affecté au client concerné. Lorsque vous sélectionnez le code client dans le champ **Code remise facture** dans d'autres fiches client, la même remise facture est affecté à ces clients.

## <a name="to-copy-sales-prices" />Pour copier des prix de vente

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. 

#### [Expérience actuelle](#tab/current-experience/)  

Pour copier des prix de vente, comme les prix appliqués à un client et qui doivent être appliqués à tout un groupe de clients, vous devez lancer le traitement par lots **Suggérer prix vente**. traitement en lot sur la page **Feuille prix vente**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille de calcul de prix de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Suggérer prix vente**    
3. Sur le raccourci **Prix vente**, renseignez les champs **Type vente** et **Code vente** avec les prix de vente d'origine à copier.  
4. Dans la partie supérieure de la page de demande, indiquez dans les champs **Type vente** et **Code vente** le type et le nom sous lesquels vous souhaitez copier les prix de vente.  
5. Pour que le traitement en lot crée des prix, cochez la case **Créer nouveaux prix**.  
6. Choisissez le bouton **OK** pour renseigner les lignes de la page **Feuille prix vente** avec les nouveaux prix proposés, en précisant qu'ils sont applicables au type vente sélectionné.  

   > [!NOTE]  
   > Ce traitement en lot crée uniquement des propositions ; il n'effectue pas les modifications proposées. Si les propositions vous conviennent et que vous souhaitez les appliquer, c'est-à-dire les insérer sur la page **Prix vente**, choisissez l'action **Implémenter des modifications de prix**, sur la page **Feuille prix vente**.

#### [Nouvelle expérience](#tab/new-experience/)  

L’état de la liste de prix doit être **Brouillon**. 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Listes de prix de vente**, puis sélectionnez le lien associé. 
2. Choisissez la liste de prix à copier, puis choisissez **Copier les lignes**.
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > Vous ne pouvez pas avoir deux lignes ayant les mêmes paramètres mais des prix différents. Si cela se produit, un message s’affiche lorsque vous activez une liste de prix. Vous pouvez choisir le prix à utiliser en ouvrant la liste et en supprimant le prix incorrect.  
  
---

## <a name="to-bulk-update-item-prices" />Pour mettre à jour en bloc des prix d'articles

Ces étapes diffèrent selon que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes**. 

#### [Expérience actuelle](#tab/current-experience/)

Si vous souhaitez mettre à jour en bloc des prix article, tels que l'augmentation de tous les prix article par un certain pourcentage, vous devez exécuter **Suggérer prix article**. traitement en lot. Vous pouvez rechercher un lien vers le traitement en lot sur la page **Feuille prix vente**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille de calcul de prix de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Suggérer prix article**    
3. Sur le raccourci **Article**, renseignez le champ **N°**, ou **Groupe de report inventaire** ou d'autres champs avec les prix article d'origine à mettre à jour.  
4. Dans la partie supérieure de la page de demande, indiquez dans les champs **Type vente** et **Code vente** le type et le nom sous lesquels vous souhaitez copier les prix de vente.
5. Si vous souhaitez que le traitement en lot ajuste automatiquement les prix article proposés, saisissez l'ajustement dans le champ **Facteur ajustement**. Par exemple, vous devez entrer 1,15 dans **Facteur appliqué** pour une augmentation de 15 % des prix unitaires.  
6. Pour que le traitement par lots crée des prix, sélectionnez le champ **Créer nouveaux prix**.  
7. Choisissez le bouton **OK** pour renseigner les lignes de la page **Feuille prix vente** avec les nouveaux prix proposés, en précisant qu'ils sont applicables au l'**article** sélectionné.  

> [!NOTE]
> Ce traitement en lot crée uniquement des propositions ; il n'effectue pas les modifications proposées. Si les propositions vous conviennent et que vous souhaitez les appliquer, c'est-à-dire les insérer dans la table **Prix vente**, vous pouvez utiliser le traitement en lot **Implémenter nouveaux prix**, accessible via l'onglet **Actions**, dans le groupe **Fonctions**, sur la page **Feuille prix vente**.

#### [Nouvelle expérience](#tab/new-experience/)

Pour mettre à jour les prix de plusieurs articles, vous devez créer une nouvelle liste de prix, puis copier les lignes d’une liste de prix existante. Lorsque vous copiez les lignes, vous pouvez utiliser des filtres pour spécifier les éléments à copier, et vous pouvez spécifier un nombre entier ou décimal dans le champ **Facteur appliqué** pour augmenter ou diminuer les prix. L’état de la liste de prix doit être **Brouillon**. Si nécessaire, vous pouvez alors désactiver l’ancienne liste de prix.

> [!NOTE]
> Vous ne pouvez pas avoir deux lignes ayant les mêmes paramètres mais des prix différents. Si cela se produit, un message s’affiche lorsque vous activez une liste de prix. Vous pouvez choisir le prix à utiliser en ouvrant la liste et en supprimant le prix incorrect.  

---

## <a name="calculating-the-best-price" />Calcul du meilleur prix

Lorsque vous avez enregistré des prix spéciaux et des escomptes ligne pour les ventes et les achats, [!INCLUDE[d365fin](includes/d365fin_md.md)] s’assure que votre profit pour l’article est toujours optimal en calculant automatiquement le meilleur prix dans les documents achat et vente, sur le projet et les lignes journal article. Pour plus d'informations, voir [Calcul du meilleur prix](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

## <a name="see-related-microsoft-trainingtrainingmodulescustomer-discounts-dynamics-365-business-central" />Voir la [formation Microsoft](/training/modules/customer-discounts-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Définition des ventes](sales-setup-sales.md)  
[Ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
