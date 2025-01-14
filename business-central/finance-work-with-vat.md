---
title: "Procédure\_: utiliser la TVA sur les ventes et les achats"
description: 'Cette rubrique décrit les différentes manières de travailler avec la TVA à la fois manuellement et avec la configuration automatique, pour vous aider à respecter les réglementations spécifiques à chaque pays.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'VAT, sales, purchases'
ms.search.form: '7, 118, 130, 142, 459, 460, 525'
ms.date: 06/16/2021
ms.author: bholtorf
---
# <a name="work-with-vat-on-sales-and-purchases" />Utiliser la TVA sur les ventes et les achats

Si votre pays ou votre région vous oblige à calculer et déclarer la taxe sur la valeur ajoutée (TVA) sur les transactions vente et achat, vous pouvez configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour calculer la TVA. Pour plus d'informations, voir [Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md).

Il existe, cependant, certaines tâches associées à la TVA que vous pouvez effectuer manuellement. Par exemple, vous devrez peut-être corriger un montant reporté si vous découvrez qu'un fournisseur utilise un mode d'arrondissement différent.  

> [!TIP]
> Vous pouvez laisser [!INCLUDE[prod_short](includes/prod_short.md)] valider les numéros d’identification intracommunautaire et d’autres informations compagnie lorsque vous créez ou mettez à jour des documents. Pour plus d’informations, consultez [Valider des numéros d’identification intracommunautaire](finance-how-validate-vat-registration-number.md).

## <a name="calculating-and-displaying-vat-amounts-on-sales-and-purchase-documents" />Calcul et affichage des montants de TVA dans des documents achat et vente

Lorsque vous sélectionnez un numéro d'article dans le champ **N°** sur un document vente ou achat, [!INCLUDE[prod_short](includes/prod_short.md)] remplit les champs **Prix unitaire** et **Montant ligne**. Le prix unitaire provient de la fiche **Article** ou des prix article autorisés pour l'article et le client. [!INCLUDE[prod_short](includes/prod_short.md)] calcule le montant ligne lorsque vous entrez une quantité pour la ligne.  

Si vous souhaitez que les prix unitaires et les montants ligne incluent la TVA, par exemple, si vous vendez au détail à des particuliers, cochez la case **Prix TTC** sur le document. Pour plus d’informations, voir [Inclure ou exclure la TVA dans les prix et les montants ligne](#including-or-excluding-vat-in-prices-and-line-amounts). 

Vous pouvez calculer et afficher des montants TVA dans des documents achat et vente de façon différente, en fonction du type de client ou de fournisseur avec lequel vous traitez. Vous pouvez également changer manuellement le montant TVA calculé, par exemple pour qu’il corresponde au montant TVA calculé par le fournisseur sur une transaction donnée.

### <a name="including-or-excluding-vat-in-prices-and-line-amounts" />Inclure ou exclure la TVA dans les prix et les montants ligne

Si vous cochez la case **Prix TTC** sur un document vente, les champs **Prix unitaire** et **Montant ligne** incluront la TVA. Par défaut, les valeurs de ces champs n’incluent pas la TVA. Les noms des champs indiquent si les prix incluent la TVA.  

Vous pouvez configurer les paramètres par défaut de **Prix TTC** pour tous les documents vente relatifs à un client dans le champ **Prix TTC** sur la fiche **Client**. Vous pouvez également configurer des prix article pour inclure ou exclure la TVA. En règle générale, les prix indiqués sur la fiche article n’incluent pas la TVA. 

Le tableau suivant montre comment l'application calcule les montants de prix unitaire pour un document vente lorsque vous n'avez pas configuré de prix sur la page **Prix vente** :  

|**Le prix inclut le champ TVA sur la fiche client.**|**Champ Prix TTC**|**Action exécutée**|  
|-----------------------------------------------|----------------------------------------------------|--------------------------|  
|Non activé|Non activé|Le champ **Prix unitaire** de la fiche article est copié dans le champ **Prix unitaire HT** dans les lignes vente.|  
|Non activé|Activé|L'application calcule le montant de TVA par unité et l'ajoute au **Prix unitaire** sur la fiche article. Ce prix unitaire total est entré dans le champ **Prix unitaire TTC** dans les lignes vente.|  
|Activé|Non activé|L’application calcule le montant TVA inclus dans le champ **Prix unitaire** sur la **Fiche article** à l’aide du pourcentage de TVA par rapport aux champs Gpe report marché TVA (prix) et Groupe de report produit TVA. Le **prix unitaire** sur la fiche article, moins le montant de la TVA, est ensuite saisi dans le champ **Prix unitaire HT** dans les lignes de vente. Pour plus d’informations, voir [Utilisation des groupes de report marché TVA et des groupes prix client](finance-work-with-vat.md#using-vat-business-posting-groups-and-customer-price-groups).|  
|Activé|Activé|Le champ **Prix unitaire** de la fiche article est copié dans le champ **Prix unitaire TTC** dans les lignes vente.|

#### <a name="using-vat-business-posting-groups-and-customer-price-groups" />Utilisation des groupes de report marché TVA et des groupes prix client

Si vous souhaitez que les prix incluent la TVA, vous pouvez utiliser des groupes de report marché TVA pour calculer le montant en fonction de la configuration report TVA pour le groupe. Pour plus d’informations, voir [Configurer des groupes de report marché TVA](finance-setup-vat.md#set-up-vat-business-posting-groups).

En fonction de ce que vous souhaitez faire, vous pouvez affecter un groupe de report marché TVA aux documents client ou vente des manières suivantes :

* Pour utiliser le même taux de TVA pour tous les clients, vous pouvez choisir un groupe dans le champ **Groupe de report marché TVA (Prix)** sur la page **Configuration ventes**.
* Pour utiliser un taux de TVA pour un client spécifique, vous pouvez choisir un groupe dans le champ **Groupe de report marché TVA (Prix)** sur la page **Fiche client**. 
* Pour utiliser un taux de TVA pour un groupe de clients spécifique, vous pouvez choisir un groupe dans le champ **Groupe de report marché TVA (Prix)** sur la page **Groupe prix client**. Par exemple, cela s’avère utile lorsque vous souhaitez qu’un prix s’applique à tous les clients d’une certaine région géographique ou d’un secteur spécifique.
* Sur tous les documents vente dans le champ **Groupe de report marché TVA**. Le montant TVA spécifié pour le groupe est utilisé uniquement pour le document sur lequel vous travaillez actuellement.

> [!NOTE]
> Si vous ne spécifiez pas de groupe dans le champ **Groupe de report marché TVA (Prix)**, la TVA ne sera pas incluse dans les prix.

#### <a name="examples" />Exemples

Des facteurs tels que le pays ou la région dans lesquels vous vendez, ou le type de secteurs auxquels vous vendez, peuvent avoir un impact sur le montant de la TVA que vous devez comptabiliser. Par exemple, un restaurant peut facturer 6 % de TVA pour les repas consommés sur place et 17 % pour les plats à emporter. Pour ce faire, vous créez un groupe de report marché TVA (prix) pour la restauration sur place et un autre pour les plats à emporter.

## <a name="working-with-vat-date" />Utilisation de la date de TVA

### <a name="vat-date-in-documents" />Date de TVA dans les documents

Lorsque vous créez des documents de vente ou d’achat, la **Date de TVA** est basée sur le paramètre du champ **Date de TVA par défaut** sur la page **Configuration du grand livre**. Cette valeur par défaut peut être la même que **Date de report** ou **Date du document**. Si vous avez besoin d’une autre date de TVA, vous pouvez modifier manuellement la valeur dans le champ **Date de TVA**. Lorsque vous reportez le document, la **Date de TVA** apparaît sur le document de report et sur les écritures TVA et GL.

> [!NOTE]
> Si le champ **Date TVA** n’est pas disponible sur vos documents ou journaux, cela signifie que **Ne pas utiliser la fonctionnalité de date TVA** est sélectionné dans le champ **Utilisation de la date TVA** sur la page **Configuration du grand livre**.  

> [!IMPORTANT]
> Si vous configurez **Contrôler période TVA** dans la **Configuration du grand livre** comme **Bloquer le report dans une période fermée** ou **Bloquer le report dans une période fermée et avertir pour la période libérée**, vous ne pouvez reporter de document ou de journal que si la date du champ **Date TVA** n’est pas dans une période fermée dans les **Périodes de retour TVA**. Même si la période dans **Périodes de retour de TVA** est ouverte, vous pouvez recevoir un avertissement basé sur l’**État du retour TVA** et la configuration dans **Contrôler période TVA**.

> [!IMPORTANT]
> Vous pouvez empêcher ou autoriser la publication de la **Date TVA** pour une plage de données spécifique, en utilisant les champs **Début période report** et **Fin période report** dans la **Configuration du grand livre** et la **Configuration de l'utilisateur**.  

> [!NOTE]
> Si vous laissez vide la **Date TVA**, [!INCLUDE [prod_short](includes/prod_short.md)] utilisera votre paramètre par défaut **Date TVA par défaut** dans la **Configuration du grand livre** comme une **Date TVA** dans la transaction reportée.  

### <a name="modifying-the-vat-date-in-posted-entries" />Modification de la date TVA dans les écritures reportées

Si nécessaire, vous pouvez modifier la date TVA des documents reportés. Pour modifier la date dans le champ **Date TVA** pour les documents reportés, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures TVA**, puis choisissez le lien associé. 
2. Trouvez l’entrée avec une date de TVA incorrecte.  
3. Sélectionnez l’action **Modifier la liste** et entrez la date correcte dans le champ **Date TVA**.  
4. Lorsque vous fermez la page, la date de TVA change dans les **Écritures GL** associées et dans le document reporté.  

> [!NOTE]
> Vous pouvez modifier le champ **Date TVA** dans les **Écritures TVA** uniquement si votre date actuelle ne figure pas dans une période de retour TVA fermée. Même si la période dans le champ **Périodes de retour TVA** est ouverte, vous pouvez recevoir un avertissement basé sur l’**État du retour TVA**.  

> [!NOTE]
> Si votre document comporte plusieurs **Écritures TVA**, il vous suffit de modifier la valeur dans le champ **Date TVA** dans une écriture associée au document. Pour assurer la cohérence des écritures, [!INCLUDE[prod_short](includes/prod_short.md)] modifie automatiquement la date de TVA dans les écritures TVA liées à cette transaction. [!INCLUDE [prod_short](includes/prod_short.md)] mettra à jour la **Date TVA** dans les autres tables (écritures comptables et documents), mais uniquement en rapport avec cette transaction.  

## <a name="correcting-vat-amounts-manually-on-sales-and-purchase-documents" />Correction manuelle des montants de TVA dans des documents achat et vente

Vous pouvez apporter des corrections à des écritures TVA reportées afin de pouvoir modifier les montants TVA totaux vente ou achat sans changer la base TVA. Par exemple, si vous recevez une facture d’un fournisseur avec un montant TVA incorrect.  

Même si vous avez peut-être configuré une ou plusieurs combinaisons pour traiter la TVA à l'importation, vous devez configurer au moins un groupe de report produit TVA. Par exemple, vous pouvez l'appeler **CORRECT** à des fins de correction, à moins que vous puissiez utiliser le même compte général dans le champ **Compte TVA achat** sur la ligne des paramètres de comptabilisation TVA. Pour plus d'informations, voir [Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md).

Si un escompte de paiement a été calculé en fonction d’un montant de facture TTC, vous remboursez la partie escompte de paiement du montant TVA lorsque l’escompte de paiement est accordé. Remarque : vous devez activer le champ **Ajust. pour esc. paiement** à la fois dans la configuration du grand livre en général et dans la configuration du report TVA, pour des combinaisons particulières d'un groupe de report de marché TVA et d'un groupe de report de produit TVA.  

### <a name="to-set-the-system-up-for-manual-vat-entry-in-sales-documents" />Pour configurer le système pour la saisie manuelle de la TVA dans les documents de vente
La section suivante explique comment activer les modifications manuelles de la TVA sur les documents de vente. Les étapes sont similaires sur la page **Configuration achats et à payer**.

1. Sur la page **Configuration du grand livre**, spécifiez une **Différence TVA max. autorisée** entre le montant calculé par l'application et le montant calculé manuellement.  
2. Dans la page **Paramètres ventes**, activez le champ **Autoriser différence TVA**.  

### <a name="to-adjust-vat-for-a-sales-document" />Pour ajuster la TVA pour un document vente

1. Ouvrez le document de vente approprié.  
2. Sélectionnez l'action **Statistiques**.  
3. Dans l'organisateur **Facturation**, choisissez la valeur dans le champ **Nbre de lignes fiscales**.
4. Modifiez le champ **Montant TVA**.   

> [!NOTE]  
> Le montant de TVA total de la facture et l'identificateur TVA s'affichent dans les lignes. Vous pouvez ajuster les montants manuellement dans le champ **Montant TVA** des lignes correspondant à chaque identifiant TVA. Lorsque vous modifiez la valeur du champ **Montant TVA**, l'application vérifie que vous n'avez pas modifié la TVA d'une valeur supérieure à celle du montant spécifié comme différence maximale autorisée. Si le montant se situe en dehors de la plage **Différence TVA max. autorisée**, un avertissement s'affiche, indiquant la différence maximale autorisée. Vous ne pouvez pas poursuivre tant que le montant n'est pas ajusté conformément aux paramètres acceptables. Cliquez sur **OK** , puis entrez un autre **Montant TVA** s'inscrivant dans la plage autorisée. Si la différence TVA est inférieure ou égale à la différence maximale autorisée, la TVA est répartie de façon proportionnelle entre les lignes document ayant le même identificateur TVA.  

## <a name="calculating-vat-manually-using-journals" />Calcul manuel de la TVA à l’aide de journaux
Vous pouvez également ajuster les montants TVA dans les journaux généraux, vente et achat. Par exemple, vous devrez peut-être le faire lorsque vous entrez une facture fournisseur dans votre journal et qu'il y a une différence entre le montant de TVA calculé par [!INCLUDE[prod_short](includes/prod_short.md)] et le montant de TVA figurant sur la facture que vous avez reçue du fournisseur.  

### <a name="to-set-the-system-up-for-manual-vat-entry-in-a-general-journals" />Pour configurer le système pour la saisie manuelle de la TVA dans les journaux généraux
Vous devez suivre les étapes suivantes avant de saisir manuellement la TVA dans un journal général.  

1. Sur la page **Configuration du grand livre**, spécifiez une **Différence TVA max. autorisée** entre le montant calculé par l'application et le montant calculé manuellement.  
2. Sur la page **Modèles journal général**, cochez la case **Autoriser différence TVA** pour la journal appropriée.  

### <a name="to-set-the-system-up-for-manual-vat-entry-in-a-sales-and-purchase-journals" />Pour configurer le système pour la saisie manuelle de la TVA dans les journaux vente et achat

Vous devez suivre les étapes suivantes avant de saisir manuellement la TVA dans un journal vente et achat.

1. Sur la page **Configuration achats et à payer**, cochez la case **Autoriser différence TVA**.  
2. Répétez l'étape 1 pour la page **Configuration ventes & à recevoir**.
3. Après avoir effectué la configuration décrite ci-avant, vous pouvez ajuster la valeur du champ **Montant TVA** de la ligne journal général ou du champ **Montant TVA contrepartie** de la ligne journal achat ou vente. [!INCLUDE[prod_short](includes/prod_short.md)] vérifie que la différence n'est pas supérieure à la valeur maximale spécifiée.  

> [!NOTE]  
> Si la différence est supérieure, un avertissement s'affiche, indiquant la différence maximale autorisée. Pour continuer, vous devez ajuster le montant. Sélectionnez **OK**, puis entrez un montant compris dans la plage autorisée. Si la différence de TVA est inférieure ou égale à la valeur maximale autorisée, [!INCLUDE[prod_short](includes/prod_short.md)] affiche la différence dans le champ **Différence TVA**.  

## <a name="posting-import-vat-with-purchase-invoices" />Reporter la TVA à l'importation dans les factures achat
Au lieu d'utiliser des journaux comptabilité pour reporter une facture TVA importation, vous pouvez utiliser une facture achat.  

### <a name="to-set-up-purchasing-for-posting-import-vat-invoices" />Pour configurer les achats pour le report des factures TVA à l'importation

1. Paramétrer une fiche fournisseur pour l'administration d'importation qui vous envoie la facture TVA à l'importation. Les champs **Groupe compta. marché** et **Groupe compta. marché TVA** doivent être configurés de la même manière que le compte général pour la TVA à l'importation.  
2. Créez un **Groupe compta. produit** pour la TVA importation et paramétrez un **Gpe compta. produit TVA défaut** (TVA importation) pour le **Groupe compta. produit** lié.  
3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Plan comptable**, puis choisissez le lien associé.  
4. Sélectionnez le compte GL de TVA à l'importation, puis choisissez l'action **Modifier**.  
5. Sur le raccourci **Validation**, sélectionnez la configuration **Groupe compta. produit** pour importer la TVA. [!INCLUDE[prod_short](includes/prod_short.md)] renseigne automatiquement le champ **Groupe compta. produit TVA**.  
6. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du report général**, puis choisissez le lien associé.  
7. Créez une combinaison de **Groupe de report de marché** pour l'administration fiscale et de **Groupe de report de produit** pour la TVA d'importation. Pour cette nouvelle combinaison, dans le champ **Compte achat**, sélectionnez le compte du grand livre de la TVA à l'importation.  

### <a name="to-create-a-new-invoice-for-the-import-authority-vendor-once-you-have-completed-the-setup" />Pour créer une facture pour le fournisseur de l'administration d'importation, une fois la configuration terminée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures achat**, puis sélectionnez le lien associé.  
2. Créez une facture achat.  
3. Dans le champ **N° fournisseur**, sélectionnez le fournisseur de l'administration d'importation, puis cliquez sur **OK**.  
4. Sur la ligne achat, dans le champ **Type**, sélectionnez **Compte du grand livre** et dans le champ **N°**, sélectionnez le compte du grand livre TVA à l'importation.  
5. Dans le champ **Quantité**, tapez **1**.  
6. Dans le champ **Coût unitaire direct HT**, indiquez le montant de la TVA.  
7. Reportez la facture.  

## <a name="processing-certificates-of-supply" />Traitement des certificats d’approvisionnement

Lorsque vous vendez des biens à un client dans un autre pays/une autre région de l'UE, vous devez envoyer au client un certificat d'approvisionnement que le client doit signer et vous renvoyer. Les procédures suivantes servent à traiter les certificats d'approvisionnement pour des livraisons vente, mais les mêmes phases s'appliquent aux livraisons service des articles, ainsi qu'aux livraisons retour aux fournisseurs.  

### <a name="to-view-certificate-of-supply-details" />Pour afficher les détails d'un certificat d'approvisionnement
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraisons vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la livraison vente appropriée à un client dans un autre pays/une autre région de l'UE.  
3. Sélectionnez **Détails certificat d'approvisionnement**.  
4. Par défaut, si la case **Certificat d'approvisionnement requis** est cochée pour la configuration du groupe de report TVA pour le client, le champ **État** est défini sur **Requis**. Vous pouvez mettre à jour le champ pour indiquer si le client a retourné le certificat.  

> [!Note]  
>  Si la configuration de groupes comptabilisation TVA n'a pas la case **Certificat d'approvisionnement requis** cochée, alors un enregistrement est créé et le champ **Statut** est défini sur **Non applicable**. Vous pouvez mettre à jour le champ pour tenir compte des informations d'état correctes. Vous pouvez modifier manuellement le statut de **Non applicable** en **Requis**, et de **Requis** en **Non applicable** selon vos besoins.  

   Lorsque vous mettez à jour le champ **Statut** sur **Requis**, **Reçu** ou **Non reçu**, un certificat est créé.  

> [!TIP]  
>  Vous pouvez utiliser la page **Certificats d'approvisionnement** pour obtenir une vue d'état de toutes les livraisons reportées pour lesquelles un certificat d'approvisionnement a été créé.  

5. Sélectionnez **Imprimer le certificat d'approvisionnement**.  

> [!Note]  
>  Vous pouvez afficher un aperçu ou imprimer le document. Lorsque vous choisissez **Imprimer le certificat d'approvisionnement** et que vous imprimez le document, la case à cocher **Imprimé** est automatiquement sélectionnée. En outre, s'il n'est pas déjà renseigné, le statut du certificat est mis à jour sur **Requis**. Si nécessaire, vous incluez le certificat imprimé avec la livraison.  

### <a name="to-print-a-certificate-of-supply" />Pour imprimer un certificat d'approvisionnement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraisons vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la livraison vente appropriée à un client dans un autre pays/une autre région de l'UE.  
3. Sélectionnez l'action **Imprimer le certificat d'approvisionnement**.  

> [!NOTE]  
>  Sinon, vous pouvez imprimer un certificat à partir de la page **Certificat d'approvisionnement**.  

4. Pour inclure des informations des lignes dans le document expédition sur le certificat d'approvisionnement, sélectionnez la case à cocher **Imprimer détails de ligne**.  
5. Cochez la case **Créer des certificats d'approvisionnement s'ils n'ont pas encore été créés** pour que [!INCLUDE[prod_short](includes/prod_short.md)] crée des certificats pour les livraisons reportées qui n'en ont pas au moment de l'exécution. Lorsque vous cochez la case, de nouveaux certificats sont créés pour toutes les livraisons reportées qui n'ont pas de certificats compris dans la plage sélectionnée.  
6. Par défaut, les paramètres de filtre concernent le document livraison que vous avez sélectionné. Renseignez les informations de filtre pour sélectionner un certificat d'approvisionnement spécifique à imprimer.  
7. Dans la page **Certificat d'approvisionnement**, sélectionnez l'action **Imprimer** pour imprimer le rapport ou l'action **Aperçu** pour l'afficher à l'écran.  

> [!Note]  
> Le champ **État Certificat d'approvisionnement** et le champ **Imprimé** sont mis à jour pour la livraison sur la page **Certificats d'approvisionnement**.  

8. Envoyez le certificat d'approvisionnement imprimé au client pour signature.  

### <a name="to-update-the-status-of-a-certificate-of-supply-for-a-shipment" />Pour mettre à jour l'état d'un certificat d'approvisionnement pour une livraison

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraisons vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la livraison vente appropriée à un client dans un autre pays/une autre région de l'UE.  
3. Dans le champ **Statut**, sélectionnez l'option appropriée.  

   Si le client a retourné le certificat d'approvisionnement signé, choisissez **Reçu**. Le champ **Date de réception** est mis à jour. Par défaut, la date de réception est configurée sur la date de travail actuelle.  

   Vous pouvez modifier la date pour tenir compte de la date à laquelle vous avez reçu le certificat d'approvisionnement signé du client. Vous pouvez également ajouter un lien vers le certificat signé à l'aide des liaisons standard de [!INCLUDE[prod_short](includes/prod_short.md)].  

   Si le client ne retourne pas le certificat d'approvisionnement signé, choisissez **Non reçu**. Vous devez envoyer au client une nouvelle facture qui inclut la TVA, parce que la facture initiale ne sera pas acceptée par l'administration fiscale.  

Pour afficher un groupe de certificats, vous commencez à partir de la page **Certificats d'approvisionnement**, puis mettez à jour les informations concernant l'état des certificats en attente à mesure que vous les recevez de la part de vos clients. Ceci peut être utile si vous souhaitez rechercher tous les certificats ayant un certain statut, par exemple, **Requis**, si vous souhaitez mettre à jour leur statut en **Non reçu**.  

### <a name="to-update-the-status-of-a-group-of-certificates-of-supply" />Pour mettre à jour l'état d'un groupe de certificats d'approvisionnement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Certificats d’approvisionnement**, puis sélectionnez le lien associé.  
2. Filtrez le champ **Statut** sur la valeur que vous souhaitez afin de créer la liste des certificats que vous souhaitez gérer.  
3. Pour mettre les informations d'état à jour, sélectionnez **Modifier la liste**.  
4. Dans le champ **Statut**, sélectionnez l'option appropriée.  

   Si le client a retourné le certificat d'approvisionnement signé, choisissez **Reçu**. Le champ **Date de réception** est mis à jour. Par défaut, la date de réception est configurée sur la date de travail actuelle.  

   Vous pouvez modifier la date pour tenir compte de la date à laquelle vous avez reçu le certificat d'approvisionnement signé. Vous pouvez également ajouter un lien vers le certificat signé à l'aide des liaisons de document standard de [!INCLUDE[prod_short](includes/prod_short.md)].  

> [!NOTE]
> Vous ne pouvez pas créer un nouveau certificat d'approvisionnement sur la page **Certificat d'approvisionnement** lorsque vous y accédez à l'aide de cette procédure. Pour créer un certificat pour une livraison qui n'a pas été configurée pour en exiger, ouvrez la livraison vente reportée et utilisez l'une des deux procédures décrites ci-dessus :  
>
> * Pour créer manuellement un certificat d'approvisionnement.  
> * Pour imprimer un certificat d'approvisionnement.

## <a name="see-related-microsoft-trainingtrainingpathsprocess-vat-dynamics-365-business-central" />Voir la [formation Microsoft](/training/paths/process-vat-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi

[Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée](finance-setup-vat.md)  
[Déclarer la TVA à une autorité fiscale](finance-how-report-vat.md)  
[Valider un numéro d'identification intracommunautaire](finance-how-validate-vat-registration-number.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
