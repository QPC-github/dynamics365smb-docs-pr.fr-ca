---
title: "Créer une facture vente ou un document de vente | Microsoft Docs"
description: "Décrit comment créer une facture vente, un document de vente ou, enregistrer votre entente avec un client pour vendre des produits à des conditions spécifiques."
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bill, sale, invoice, order
ms.date: 04/30/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 046a42582dc66368fded90a4bb45add71a95d979
ms.openlocfilehash: 97116be5c1a0fbbef2564120ac95030f488aafbc
ms.contentlocale: fr-ca
ms.lasthandoff: 07/02/2018

---
# <a name="invoice-sales"></a>Facturer des ventes
Vous créez une facture vente ou un document de vente pour enregistrer votre entente avec un client pour vendre certains produits selon certaines méthodes de livraison et de paiement.  

Dans certains scénarios, vous devez utiliser un document de vente au lieu d'une facture vente :  

* Si vous devez livrer uniquement une partie d'une quantité de commande, par exemple, si la quantité totale n'est pas disponible.  
* Si vous vendez des articles que votre fournisseur fournit directement à votre client (une livraison directe). Pour plus d'informations, voir [Effectuer des livraisons directes](sales-how-drop-shipment.md).  

Pour tous les autres aspects, les commandes vente et les factures vente fonctionnent de la même manière. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).

Vous pouvez négocier avec le client en créant d'abord un devis, que vous pouvez convertir en facture vente lorsque vous êtes d'accord sur la vente. Pour plus d'informations, voir [Créer des devis](sales-how-make-offers.md).

Si le client décide d'acheter, vous reportez la facture vente pour créer les écritures quantité et valeur associées. Lorsque vous reportez la facture vente, vous pouvez également envoyer par courriel le document en pièce jointe au format PDF. Vous pouvez faire en sorte que le corps du message soit prérempli avec un résumé des informations de facturation et de paiement, par exemple un lien vers Paypal. Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md).

Dans les environnements d'entreprise où le client paie un certain temps après la livraison, conformément aux conditions de paiement, une facture vente reportée reste ouverte (impayée) jusqu'à ce que le département Comptabilité client vérifie la réception du paiement et affecte le paiement à la facture vente reportée. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).

Dans les environnements d'entreprise où le client paie immédiatement, par exemple par PayPal ou en espèces, le paiement est enregistré immédiatement lorsque vous reportez la facture vente, c'est-à-dire la facture vente reportée est fermée comme entièrement affectée. Vous sélectionnez la méthode appropriée dans le champ **Code mode de paiement** du document de vente. Voir l'étape 8. Pour les paiements électroniques, tels que PayPal, vous devez également renseigner le champ **Service de paiement**. Pour plus d'informations, voir [Activer les paiements client via les services de paiement](sales-how-enable-payment-service-extensions.md).

Vous pouvez même créer des factures à paiement direct pour les clients non enregistrés en configurant une fiche « client en espèces », vers laquelle vous pointez sur la facture vente. Pour plus d'informations, reportez-vous à [Configurer des clients effectuant un achat au comptoir](finance-how-to-set-up-cash-customers.md).  

Vous pouvez facilement corriger ou annuler une facture vente reportée avant qu'elle ne soit payée. Cela est utile, par exemple, si vous souhaitez corriger une erreur de saisie, ou si le client demande une modification tôt dans le processus de commande. Pour plus d'informations, voir [Corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md). Si la facture vente reportée est payée, vous devez créer une note de crédit vente pour inverser la vente. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md).

Les articles peuvent être des articles en inventaire et des services, représentés par le type **Inventaire** ou **Service** sur la fiche article. Le processus de facture vente est identique pour les deux types d'article. Pour plus d'informations, voir [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).

Vous pouvez remplir les champs relatifs au client sur la facture vente de deux façons selon que le client est déjà enregistré ou non. Reportez-vous aux étapes 2 et 3 de la procédure ci-dessous.

## <a name="to-create-a-sales-invoice"></a>Pour créer une facture vente :
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Factures vente**, puis sélectionnez le lien connexe.  
2. Dans le champ **Client**, entrez le nom d'un client existant.

   D'autres champs de la fenêtre **Facture vente** contiennent des informations standard sur le client sélectionné. Si le client n'est pas enregistré, procédez comme suit :
3. Dans le champ **Client**, entrez le nom du nouveau client.
4. Dans la boîte de dialogue d'enregistrement du nouveau client, cliquez sur le bouton **Oui**.
5. Dans la fenêtre **Sélectionnez un modèle pour un nouveau client**, sélectionnez un modèle sur lequel baser la nouvelle fiche client, puis cliquez sur le bouton **OK**.
6. Une nouvelle fiche client affiche des informations sur le modèle client sélectionné. Renseignez les champs restants. Pour plus d'informations, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).  
7. Lorsque vous avez terminé la fiche client, cliquez sur le bouton **OK** pour revenir à la fenêtre **Facture vente**.

   Plusieurs champs de la facture vente sont désormais renseignés avec les informations que vous avez spécifiées sur la nouvelle fiche client.  
8. Renseignez les champs restants de la fenêtre **Facture vente**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > Si vous autorisez le client à payer immédiatement, par exemple, en liquide ou par PayPal, renseignez le champ **Code mode de règlement**. Le paiement est ensuite enregistré dès que vous reportez la facture vente. Si vous sélectionnez ESPÈCES, le paiement est enregistré dans un compte de contrepartie spécifié.

    Vous êtes maintenant prêt à renseigner les lignes facture vente pour les produits que vous vendez au client ou pour toute transaction avec le client que vous souhaitez enregistrer dans un compte du grand livre.   

    Si vous avez défini des lignes vente récurrentes pour le client, tel qu'un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la commande par l'intermédiaire de l'action **Extraire les lignes vente récurrentes**.  
9. Sous le raccourci **Lignes**, dans le champ **Type**, sélectionnez le type de produit, de frais ou de transaction à valider pour le client avec la ligne vente.
10. Dans le champ **N°**, sélectionnez un enregistrement à valider en fonction de la valeur du champ **Type**.

    Laissez le champ **N°** vide dans les cas suivants :

    * Si la ligne est destinée à un commentaire. Saisissez le commentaire dans le champ **Description**.
    * Si la ligne est destinée à un article non stocké. Sélectionnez l'action **Sélectionner articles non stockés**. Pour en savoir plus, voir [Utiliser des articles non stockés](inventory-how-work-nonstock-items.md).

11. Dans le champ **Quantité**, entrez le nombre d'unités du produit, de frais ou de la transaction que la ligne enregistre pour le client.  

    > [!NOTE]  
    >   Si l'article est de type **Service** ou si le champ **Type** contient **Ressource**, la quantité est une unité de temps, par exemple heures, comme indiqué dans le champ **Code unité de mesure** de la ligne.  

    La valeur du champ **Montant ligne** est calculée comme suit : *Prix unitaire* x *Quantité*.  

    Le prix et les montants ligne sont affichés avec ou sans la taxe de vente en fonction de la valeur que vous avez sélectionnée dans le champ **Prix incluant les taxes** de la fiche client.  
12. Si vous souhaitez accorder une remise, saisissez un pourcentage dans le champ **% remise ligne**. La valeur du champ **Montant ligne** est mise à jour en conséquence.  

    Si des prix article spéciaux sont définis sur le raccourci **Prix vente et remises ligne vente** dans la fiche client ou article, le prix et le montant de la ligne vente sont automatiquement mis à jour si les critères de prix convenus sont réunis. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).  
13. Répétez les étapes 9 à 12 pour chaque produit ou frais que vous souhaitez facturer au client.  

    Les totaux sous les lignes sont calculés automatiquement au fur et à mesure que vous créez ou modifiez des lignes.  
14. Dans le champ **Montant remise facture**, entrez un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC**.

    Si vous avez défini des remises facture pour le client, le pourcentage spécifié est automatiquement inséré dans le champ **% remise facture** si les critères sont réunis, et le montant associé est inséré dans le champ **Montant remise facture sans TVA**. Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).  
15. Lorsque les lignes facture vente sont renseignées, sélectionnez l'action **Valider et envoyer**.  

La boîte de dialogue **Valider et envoyer la confirmation** s'ouvre et indique le mode de réception de documents par défaut du client. Vous pouvez modifier le mode d'envoi en cliquant sur le bouton de recherche pour le champ **Envoyer le document à**. Pour plus d'informations, reportez vous à [Configurer des profils d'envoi de documents](sales-how-setup-document-send-profiles.md).

Les écritures article et client associées sont à présent créées dans votre système, et la facture vente est sortie en tant que document au format PDF. La facture vente est supprimée de la liste des factures vente et remplacée par un nouveau document dans la liste des factures vente reportées.

## <a name="see-also"></a>Voir aussi
[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Stock](inventory-manage-inventory.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Facturation en vrac à partir de Microsoft Bookings dans Business Central](finance-bookings.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
