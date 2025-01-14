---
title: Rapprocher des paiements clients avec le journal des encaissements ou à partir des écritures client
description: Décrit comment affecter des règlements ou des remboursements client dans une ou plusieurs écritures client ouvertes. Cela fait partie du rapprochement des paiements des clients.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'payment process, cash receipt'
ms.search.form: '25, 255'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="reconcile-customer-payments-with-the-cash-receipt-journal-or-from-customer-ledger-entries" />Rapprocher des paiements clients avec le journal des encaissements ou à partir des écritures client

Lorsque vous recevez un règlement en espèces d’un client ou que vous effectuez un remboursement, vous pouvez affecter le paiement ou le remboursement pour fermer une ou plusieurs écritures débit ou crédit. Vous pouvez indiquer le montant à affecter. Par exemple, vous pouvez affecter des paiements partiels à des écritures client. La fermeture des écritures client garantit que les statistiques clients, les relevés bancaires et les frais financiers, etc. sont à jour.

> [!TIP]  
>   Sur la page **Écritures client**, le rouge signifie que le paiement associé a dépassé sa date d'échéance. Si les paiements échus deviennent un problème, nous pouvons vous aider à minimiser leur fréquence. Vous pouvez activer l'extension **Prévisions des retards de paiement**, qui utilise un modèle prédictif que nous avons généré dans Azure Machine Learning pour prévoir les délais de paiement. Ces prévisions vous permettent de réduire les créances ouvertes et d'ajuster votre stratégie de collectes. Par exemple, si un retard de paiement est prévu, vous pouvez ajuster les conditions de paiement ou le mode de règlement du client. Pour plus d'informations, consultez [Prévisions de retard de paiement](ui-extensions-late-payment-prediction.md).  

Vous pouvez affecter les écritures client de plusieurs manières :

* En entrant des informations sur les pages dédiées :
    * La page **Journal rapprochement paiement**. Pour plus d'informations, reportez-vous à [Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md).
    * La page **Enregistrement de paiement**. Pour plus d'informations, voir [Rapprocher les paiements client dans une liste des documents vente échus](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md).
    * Le **journal des encaissements**. Cette option est décrite ci-dessous.
* En renseignant le champ **N° doc. référence** sur les documents note de crédit vente. Cette option est décrite ci-dessous.
* Grâce à l'action **Définir Code référence** d'une écriture client. Cette option est décrite ci-dessous.
* En utilisant l’action **Affecter écritures** sur la page **Dépôt bancaire**, puis en saisissant le numéro de facture dans le champ **Définir Code référence**. Pour plus d’informations, voir [Créer des dépôts bancaires](bank-create-bank-deposits.md).

> [!NOTE]  
>   Si le champ **Méthode d'affectation** de la fiche client contient **Au plus ancien**, les paiements sont affectés à l'écriture crédit ouverte la plus ancienne, sauf si vous spécifiez une écriture manuellement. Si la méthode d'affectation est **Manuel**, vous devez toujours affecter les écritures manuellement.

## <a name="to-fill-and-post-a-cash-receipt-journal" />Pour renseigner et reporter un journal des encaissements
Un journal des encaissements est un type de journal général. Vous pouvez l’utiliser pour reporter les transactions sur les comptes généraux, bancaires, client, fournisseur et immobilisation. Vous pouvez affecter le règlement sur une ou plusieurs écritures débit lorsque vous reportez le règlement. Vous pouvez également affecter à partir des écritures reportées ultérieurement.
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal des encaissements**, puis choisissez le lien associé.
2. Sélectionnez **Modifier journal**.
3. Sélectionnez le nom de traitement par lots souhaité dans le champ **Nom de la feuille**.
4. Renseignez le champ **Date comptabilisation**.  
5. Dans le champ **Type document**, sélectionnez **Paiement**.

    Le champ **N° document** contient les séries de numéros affectées au lot.  
6. Utilisez le champ **N° doc. externe** pour stocker un identificateur, tel que le numéro de chèque du client.
7. Dans le champ **Type compte**, sélectionnez **Client**.
8. Dans le champ **N° compte**, sélectionnez le compte du grand livre approprié.
9. Si vous souhaitez reporter l'affectation en même temps que le journal, suivez l'un des exemples ci-dessous.
10. Dans le champ **Type compte contrepartie**, sélectionnez **Compte général** pour les règlements et **Compte bancaire** pour les autres paiements.
11. Dans le champ **N° compte de contrepartie**, sélectionnez le compte caisse pour les paiements en espèces ou le compte bancaire approprié pour d'autres paiements.
12. Reportez le journal.

## <a name="to-apply-a-payment-to-a-single-customer-ledger-entry" />Pour affecter un paiement à une seule écriture client
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal des encaissements** et choisissez le lien associé.
2. Sélectionnez **Modifier journal**.
3. Dans la première ligne journal, saisissez les informations appropriées sur l'écriture à affecter.
4. Dans le champ **Type document**, entrez **Paiement**.
5. Dans le champ **Type compte**, entrez **Client**.
6. Dans le champ **Type compte contrepartie**, entrez **Compte bancaire.**
7. Dans le champ **N° doc. référence**, sélectionnez le champ permettant d'ouvrir la page **Affecter écritures client**.
8. Sur la page **Affecter écritures client**, sélectionnez l'écriture à laquelle affecter le paiement.
9. Dans le champ **Montant à lettrer**, entrez le montant à lettrer à l'écriture. Si vous n’entrez aucun montant, le montant maximal est affecté.

    Au bas de la page **Affecter écritures client**, vous voyez le montant spécifique dans le champ **Montant affecté** et constatez si l'affectation est équilibrée.  
10. Choisissez le bouton **OK**. La page **Journal des encaissements** affiche désormais l’écriture des champs **Type doc. référence** et **N° doc. référence**.
11. Reportez le journal des encaissements.

## <a name="to-apply-a-payment-to-multiple-customer-ledger-entries" />Pour affecter un paiement à plusieurs écritures client
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal des encaissements**, puis choisissez le lien associé.
2. Sélectionnez **Modifier journal**.
3. Dans la première ligne journal, saisissez les informations appropriées sur l'écriture à affecter.
4. Dans le champ **Type document**, entrez **Paiement**.
5. Dans le champ **Type compte**, entrez **Client**.
6. Dans le champ **Type compte contrepartie**, entrez **Compte bancaire.**
7. Dans le champ **Montant**, entrez le paiement complet sous forme de montant négatif.
8. Pour lettrer le paiement avec plusieurs écritures comptables client lors de la validation, sélectionnez l'action **Lettrer écritures**.  
9. Sélectionnez les lignes correspondant aux écritures avec lesquelles l'écriture lettrage doit être lettrée, puis sélectionnez l'action **Lettrer**.  
10. Sur chaque ligne du champ **Montant à lettrer**, entrez le montant que vous souhaitez lettrer à l'écriture. Si vous n’entrez aucun montant, le montant maximal est affecté.

    Au bas de la page **Affecter écritures client**, vous voyez le montant spécifique dans le champ **Montant affecté** et constatez si l'affectation est équilibrée.  
11. Cliquez sur le bouton **OK**.
12. Reportez le journal des encaissements.

## <a name="to-apply-a-credit-memo-to-a-single-customer-ledger-entry" />Pour affecter une note de crédit à une seule écriture client
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit vente**, puis sélectionnez le lien associé.
2. Ouvrez la note de crédit vente souhaitée.
3. Pour affecter la note de crédit à une seule écriture client lors du report, dans le champ **N° doc. affecté à**, sélectionnez l'écriture à laquelle affecter le paiement.
4. Sur la ligne du champ **Montant à lettrer**, entrez le montant à lettrer avec l'écriture.  

    Si vous n’entrez aucun montant, l’application affecte automatiquement le montant maximal. Au bas de la page **Affecter écritures client**, vous voyez le montant spécifique dans le champ **Montant affecté** et constatez si l'affectation est équilibrée.    
5. Cliquez sur le bouton **OK**. La page **Note de crédit** affiche désormais l'écriture que vous avez saisie dans les champs **Type doc. référence** et **N° doc. référence**. Et le montant de la note de crédit à reporter, escomptes de paiement éventuels déduits.
6. Reportez la note de crédit.

## <a name="to-apply-a-credit-memo-to-multiple-customer-ledger-entries" />Pour affecter une note de crédit à plusieurs écritures client
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit vente**, puis sélectionnez le lien associé.
2. Ouvrez la note de crédit vente souhaitée.
3. Pour lettrer l'avoir avec plusieurs écritures comptables client lors de la validation, sélectionnez l'action **Lettrer écritures**.
4. Sélectionnez les lignes correspondant aux écritures avec lesquelles l'écriture lettrage doit être lettrée, puis sélectionnez l'action **Lettrer**.
5. Sur chaque ligne du champ **Montant à lettrer**, entrez le montant que vous souhaitez lettrer à l'écriture. Si vous n’entrez aucun montant, le montant maximal est affecté.  

    Au bas de la page **Affecter écritures client**, vous voyez le montant spécifique dans le champ **Montant affecté** et constatez si l'affectation est équilibrée.  
6. Cliquez sur le bouton **OK**. La page **Note de crédit vente** affiche désormais le montant de la note de crédit à reporter, escomptes de paiement éventuels déduits.
7. Reportez la note de crédit.

## <a name="to-apply-posted-customer-ledger-entries" />Pour affecter des écritures client reportées
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Ouvrez la fiche du client possédant les écritures que vous souhaitez affecter.
3. Sélectionnez l'action **Écritures comptables**, puis sélectionnez la ligne où figure l'écriture qui sera l'écriture lettrage.
4. Sélectionnez l'action **Lettrer écritures**. La page **Affecter écritures client** s'ouvre et affiche les écritures ouvertes de ce client.
5. Sélectionnez les lignes correspondant aux écritures avec lesquelles l'écriture lettrage doit être lettrée, puis sélectionnez l'action **Lettrer**.  
6. Pour chaque ligne du champ **Montant à lettrer**, entrez le montant que vous souhaitez lettrer à l'écriture. Si vous n’entrez aucun montant, le montant maximal est affecté.  

    Au bas de la page **Affecter écritures client**, vous voyez le montant spécifique dans le champ **Montant affecté**.  
7. Sélectionnez l'action **Valider le lettrage**. La page **Reporter l'affectation** s'ouvre et affiche le numéro de document de l'écriture affectation et la date de report de l'écriture ayant la date de report la plus récente.  
8. Cliquez sur **OK** pour valider le lettrage.

    Si le lettrage validé génère des écritures comptables client lettrées, ces écritures comptables ne sont plus activées dans le champ **Ouvert**.    
9. Pour voir les écritures, sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé. Accédez à la fiche du client approprié pour afficher les écritures.  

Dans la liste écritures, sur la ligne contenant l’écriture totalement affectée, vous constatez que la case **Ouvert** n’est pas cochée.  

> [!NOTE]  
>   Une fois que vous avez sélectionné une écriture de la page **Affecter écritures client** ou plusieurs écritures avec le **Code référence**, le champ **Montant affecté** de la ligne journal contient la somme des montants restants des écritures reportées que vous avez sélectionnées, cela à moins que le champ ne soit déjà renseigné. Si vous sélectionnez **Au plus ancien** dans le champ **Mode de lettrage** sur la fiche client, le lettrage intervient automatiquement.

## <a name="to-apply-customer-ledger-entries-in-different-currencies-to-one-another" />Pour affecter des écritures client en devises différentes à une autre
Si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez toujours affecter la facture au paiement.  

Prenons un exemple. Vous affectez une écriture (Écriture 1) dans une devise avec une autre écriture (Écriture 2) dans une autre devise. La date de report de l’Écriture 1 est utilisée pour trouver le taux de change adéquat et convertir les montants de l’Écriture 2. Le taux de change se trouve sur la page **Taux de change devise**.  

L'affectation d'écritures client en devises différentes doit être activée. Pour plus d'informations, voir [Activer l'affectation des écritures en devises différentes](finance-how-enable-application-ledger-entries-different-currencies.md).  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal règlements**, puis choisissez le lien associé.
2. Ouvrez le journal que vous souhaitez, puis renseignez la première ligne vide du journal à l'aide d'un code devise.
3. Sélectionnez l'action **Lettrer écritures**.
4. Sélectionnez la ligne comportant l'écriture à lettrer avec l'écriture de la feuille règlement. Sélectionnez ensuite l'action **Lettrer**, puis sélectionnez l'écriture sur laquelle le lettrage doit être effectué.
5. Cliquez sur le bouton **OK** pour revenir à la feuille règlement.
6. Reportez le journal ventes.  

> [!IMPORTANT]  
>   Lorsque vous affectez des écritures dans des devises différentes, les écritures sont converties en USD. Bien que le taux de change des deux devises concernées soit fixe, comme entre le USD et l'EUR, leur conversion en USD peut donner un petit montant résiduel. Le programme reporte ces petits montants résiduels en tant que gains et pertes dans le compte défini dans les champs **Cpte gains constatés** ou **Cpte pertes constatées** de la page **Devises**. La valeur du champ **Montant (USD)** est également ajustée sur les écritures comptables fournisseur.  

## <a name="to-correct-an-application-of-customer-entries" />Pour corriger une affectation d'écritures
Lorsque vous corrigez une affectation, des écritures de correction sont créées et reportées pour toutes les écritures. Les écritures de correction sont les mêmes que les originales mais elles ont un signe opposé dans le champ **Montant**. Les écritures de correction incluent toutes les écritures du grand livre issues de l’affectation. Par exemple, l’escompte de paiement et les pertes et gains en devise. Les écritures qui sont fermées par l'affectation sont rouvertes.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Ouvrez la fiche client appropriée.
3. Sélectionnez l'action **Écritures comptables**.
4. Sélectionnez l'écriture comptable appropriée, puis sélectionnez l'action **Délettrer les écritures**.
5. Sinon, sélectionnez l'action **Écritures comptables détaillées**.
6. Sélectionnez l'écriture de lettrage appropriée, puis sélectionnez l'action **Délettrer les écritures**.
7. Renseignez les champs de l'en-tête, puis sélectionnez l'action **Délettrer**.  

> [!IMPORTANT]  
>   Si une écriture a été affectée par plusieurs écritures d'affectation, vous devez commencer par annuler l'affectation de la dernière écriture.  

## <a name="see-also" />Voir aussi
[Gestion des comptes client](receivables-manage-receivables.md)  
[Vente](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
