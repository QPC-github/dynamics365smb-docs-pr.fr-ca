---
title: "Gestion de l’intégration de Microsoft Teams avec Business\_Central | Microsoft Docs"
description: Gérez l’intégration Business Central avec Microsoft Teams.
author: jswymer
ms.topic: overview
ms.search.keywords: 'Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork'
ms.date: 02/03/2023
ms.author: jswymer
ms.reviewer: jswymer
ms.custom: bap-template
ms.service: dynamics365-business-central
---

# <a name="managing-microsoft-teams-integration-with-include-prodshortincludesprodshortmd" />Gestion de l’intégration de Microsoft Teams à [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE [online_only](includes/online_only.md)]

Cet article fournit un aperçu de ce que vous pouvez faire en tant qu’administrateur pour contrôler l’intégration de Microsoft Teams avec [!INCLUDE [prod_short](includes/prod_short.md)].

## <a name="in-microsoft-teams" />Dans Microsoft Teams

### <a name="minimum-requirements" />Configuration minimale requise

Cette section décrit la configuration minimale requise pour les fonctionnalités de l’application [!INCLUDE [prod_short](includes/prod_short.md)] pour travailler dans Teams.

- Licences requises

    L’application [!INCLUDE[prod_short](includes/prod_short.md)] nécessite une licence Teams via un abonnement Microsoft 365 Business ou Enterprise. Les abonnements Teams autonomes tels que Microsoft Teams (gratuit) ou Microsoft Teams Essentials ne sont pas pris en charge.

    La plupart des fonctionnalités de l’application [!INCLUDE[prod_short](includes/prod_short.md)] pour Teams nécessite également une licence [!INCLUDE [prod_short](includes/prod_short.md)], comme indiqué dans le tableau suivant.

    |Quoi|Licence [!INCLUDE [prod_short](includes/prod_short.md)]|
    |----|---|
    |Recherche de contacts [!INCLUDE [prod_short](includes/prod_short.md)].|![coche](media/check.png "coche")|
    |Coller un lien vers un enregistrement [!INCLUDE [prod_short](includes/prod_short.md)] dans une conversation et l’envoyer sous forme de fiche.|![coche](media/check.png "coche")|
    |Partager un lien entre une page dans [!INCLUDE [prod_short](includes/prod_short.md)] et une conversation Teams.|![coche](media/check.png "coche")|
    |Afficher une fiche d’un enregistrement [!INCLUDE [prod_short](includes/prod_short.md)] dans une conversation.||
    |Afficher plus de détails d’une fiche pour un enregistrement [!INCLUDE [prod_short](includes/prod_short.md)] dans une conversation.|![coche](media/check.png "coche")|
    |Ouvrir un lien de page dans [!INCLUDE [prod_short](includes/prod_short.md)] à partir d’une conversation.|![coche](media/check.png "coche")|

- Autoriser les aperçus d’URL

    Le paramètre de stratégie **Autoriser les aperçus d’URL** doit être activé. Sinon, une fiche ne peut pas être générée pour les liens [!INCLUDE [prod_short](includes/prod_short.md)] collés dans une conversation Teams. Pour plus d’informations sur ce paramètre, consultez [Gérer les stratégies de messagerie dans Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="managing-the-include-prodshortincludesprodshortmd-app-optional" />Gestion de l’application [!INCLUDE [prod_short](includes/prod_short.md)] (facultatif)

En tant qu’administrateur Teams, vous pouvez gérer toutes les applications de votre organisation, y compris l’application [!INCLUDE [prod_short](includes/prod_short.md)]. Vous pouvez approuver ou installer l’application [!INCLUDE [prod_short](includes/prod_short.md)] pour votre organisation, empêcher l’utilisateur d’installer l’application, etc.

Pour plus d’informations, consultez les articles suivants dans la documentation Microsoft Teams :

- [Gérer vos applications dans le centre d’administration Microsoft Teams](/MicrosoftTeams/manage-apps)
- [Gérer les stratégie de configuration des applications dans Microsoft Teams](/microsoftteams/teams-app-setup-policies)

## <a name="in-include-prodshortincludesprodshortmd" />Dans [!INCLUDE [prod_short](includes/prod_short.md)]

### <a name="minimum-requirements" />Configuration minimale requise

- Version de [!INCLUDE [prod_short](includes/prod_short.md)] :

    1re vague de lancement 2021 de [!INCLUDE [prod_short](includes/prod_short.md)] ou ultérieure. L’intégration de Teams n’est prise en charge que pour [!INCLUDE [prod_short](includes/prod_short.md)] en ligne ; pas en local.

- Le codeunit **2718 Fournisseur résumé page** est publié en tant que service web :

    Ce codeunit est publié en tant que service web par défaut. Le codeunit fait partie de l’application système [!INCLUDE [prod_short](includes/prod_short.md)]. Il est utilisé pour obtenir les données de champ pour une page [!INCLUDE [prod_short](includes/prod_short.md)] ajoutée à une conversation Teams. Pour plus d’informations sur la publication des services Web, voir [Publier un service Web](across-how-publish-web-service.md).

- <a name="permissions"></a>Autorisations utilisateur :

    Pour la plupart, la Recherche contact, les pages et les données que les utilisateurs peuvent afficher et modifier dans une conversation Teams sont contrôlées par leurs autorisations dans [!INCLUDE [prod_short](includes/prod_short.md)].

    - Pour rechercher des contacts, les utilisateurs doivent disposer au moins d'une autorisation de lecture sur le tableau **Contacts**. 
    - Pour coller un lien [!INCLUDE [prod_short](includes/prod_short.md)] dans une conversation Teams et le faire développer dans une fiche, les utilisateurs doivent avoir au moins une autorisation de lecture sur la page et ses données.
    - Une fois qu’une fiche est soumise à une conversation, tout utilisateur participant à cette conversation peut afficher cette fiche sans autorisation de [!INCLUDE [prod_short](includes/prod_short.md)].
    - Pour afficher plus de détails sur une fiche ou ouvrir l’enregistrement dans [!INCLUDE [prod_short](includes/prod_short.md)], les utilisateurs doivent avoir une autorisation de lecture sur la page et ses données.
    - Pour modifier les données, l’utilisateur doit modifier les autorisations.
    
    Pour plus d’informations sur les autorisations, voir [Attribuer des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md).

## <a name="installing-the-business-central-app-by-using-centralized-deployment" />Installation de l’application Business Central à l’aide du déploiement centralisé

Le centre d’administration Microsoft Teams est l’endroit où vous configurez les stratégies de configuration de l’application Teams pour l’organisation. Dans le centre d’administration Teams, vous pouvez utiliser la fonctionnalité de déploiement centralisé pour installer automatiquement l’application Business Central dans Teams pour tous les utilisateurs de votre organisation, des groupes spécifiques ou des utilisateurs individuels.

> [!NOTE]
> Pour configurer le déploiement centralisé, votre compte Teams doit avoir le rôle **Administrateur du service Teams** ou le rôle **Administrateur global**.

1. Dans Business Central, sélectionnez ![la loupe qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Déploiement centralisé de l’application Teams**, puis sélectionnez le lien associé. Ou sélectionnez [ici](https://businesscentral.dynamics.com/?page=1833) pour ouvrir la page directement.
2. Lire les informations sur la page **Configurer l’application Business Central pour teams**, puis sélectionnez **Suivant** quand vous êtes prêt.
3. Ouvrez le [Centre d’administration Teams](https://go.microsoft.com/fwlink/?linkid=2163970), et procédez comme suit.
    1. Accédez à **Applications teams** > **Stratégies de configuration**.
    2. Créez une nouvelle stratégie ou sélectionnez celle que vous souhaitez utiliser pour installer l’application Business Central, puis sélectionnez **Ajouter des applications**.
    3. Dans la page **Ajouter des applications installées**, recherchez et sélectionnez **Business Central**.
    4. Choisissez **Ajouter**.

       Business Central doit maintenant apparaître sous **Applications installées** pour la stratégie.
    5. Configurez davantage de paramètres le cas échéant, puis choisissez **Enregistrer**.

    Pour plus d’informations sur les stratégies de configuration dans Teams, consultez [Gérer les règles de configuration d’application dans Microsoft Teams](/MicrosoftTeams/teams-app-setup-policies) dans la documentation Teams.
4. Revenez à **Déploiement centralisé de l’application Teams** dans Business Central et sélectionnez **Terminé**.

> [!IMPORTANT]
> L’application de la stratégie de configuration de l’application et le déploiement de l’application auprès des utilisateurs peuvent prendre jusqu’à 24 heures.

## <a name="managing-privacy-and-compliance" />Gestion de la confidentialité et de la conformité

Microsoft Teams fournit des contrôles étendus pour la conformité et la gestion des données sensibles ou personnellement identifiables&mdash; y compris les données ajoutées aux chats et aux canaux par l’application [!INCLUDE [prod_short](includes/prod_short.md)].

### <a name="understanding-where-include-prodshortincludesprodshortmd-cards-are-stored" />Comprendre où les fiches [!INCLUDE [prod_short](includes/prod_short.md)] sont stockées

Une fois qu’une fiche est envoyée à une discussion instantanée, la fiche et les champs affichés sur la fiche sont copiés dans Teams. Ces informations sont soumises aux stratégies Teams de votre organisation, telles que les stratégies de conservation des données. Lors de l’affichage des détails de la fiche, aucune des données de la fenêtre de détails n’est stockée dans Teams. Les données restent stockées dans [!INCLUDE [prod_short](includes/prod_short.md)] et ne seront récupérées par Teams que lorsque l’utilisateur choisit d’afficher les détails. 

- Pour en savoir plus sur l’emplacement de stockage de ces données par Teams, consultez [Emplacement des données au format Microsoft Teams](/microsoftteams/location-of-data-in-teams).
- Pour en savoir plus sur les stratégies de rétention dans Teams, voir [Stratégies de rétention dans Microsoft Teams](/microsoftteams/retention-policies).

### <a name="restricting-sharing-of-cards" />Restriction du partage des fiches

Vous empêchez des utilisateurs ou groupes spécifiques d’envoyer des fiches à des discussions instantanées ou des canaux en définissant des **Aperçus d’URL**. Pour plus d’informations sur ce paramètre, consultez [Gérer les stratégies de messagerie dans Teams](/microsoftteams/messaging-policies-in-teams). 

Vous pouvez également utiliser des barrières d’information pour empêcher des individus ou des groupes de communiquer entre eux. Pour en savoir plus, consultez [Barrières d’information dans Microsoft Teams](/microsoftteams/information-barriers-in-teams).

Les fonctionnalités de prévention de la perte de données dans le centre de sécurité et de conformité Microsoft 365 ne peuvent pas être appliquées spécifiquement aux fiches. Mais ils peuvent être appliqués aux messages de discussion contenant les fiches. <!-- To track upcoming advanced features that include enabling DLP for cards, see [https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093).-->

### <a name="responding-to-data-requests" />Répondre aux demandes de données

Vous autorisez les membres de l’équipe et les propriétaires d’équipe à supprimer les messages contenant des cartes sensibles en configurant des stratégies de messagerie, telles que : **Les propriétaires peuvent supprimer les messages envoyés** et **Les utilisateurs peuvent supprimer les messages envoyés**. Pour plus d’informations, consultez [Gérer les stratégies de messagerie dans Teams](/microsoftteams/messaging-policies-in-teams).

Les fonctionnalités de recherche de contenu et de conformité à eDiscovery dans le centre de sécurité et de conformité Microsoft 365 peuvent également être appliquées aux fiches.

Parce que les données de la fiche dans Teams sont une copie des données dans [!INCLUDE [prod_short](includes/prod_short.md)], vous pouvez aussi utiliser les fonctionnalités [!INCLUDE [prod_short](includes/prod_short.md)] pour exporter les données d’un client si demandé. Pour plus d’informations sur la confidentialité dans [!INCLUDE [prod_short](includes/prod_short.md)], voir [FAQ sur la confidentialité pour les clients Business Central](/dynamics365/business-central/dev-itpro/security/privacyfaq).

## <a name="show-or-hide-record-data-on-cards" />Afficher ou masquer les données d’enregistrement sur les fiches

Lorsqu’un enregistrement est partagé avec d’autres personnes dans une conversation ou un canal Teams, une fiche avec des champs contenant des données sur l’enregistrement s’affiche. Tous les destinataires peuvent afficher ces données (ou le résumé de l’enregistrement) par défaut, quelles que soient leur licence ou leurs autorisations dans Business Central. Si vous êtes un administrateur, vous pouvez utiliser le guide de configuration assistée **Configuration de la fiche** pour masquer le résumé de l’enregistrement afin qu’il n’apparaisse pas sur les fiches dans Teams. Masquer le résumé de l’enregistrement supprime tous les champs et images, mais continue d’afficher le bouton **Détails** et d’autres informations non liées à l’enregistrement sur la fiche.

|Résumé de l’enregistrement activé|Résumé de l’enregistrement désactivé|
|-|-|
|![Image qui montre une fiche dans Teams lorsque le résumé de l’enregistrement est activé.](media/card-settings-example-on.png)|![Image qui montre une fiche dans Teams lorsque le résumé de l’enregistrement est désactivé.](media/card-settings-example-off.png)|

Vous configurez le paramètre par environnement. Ainsi, lorsque vous activez ou désactivez le résumé de l’enregistrement, cela affecte toutes les compagnies de l’environnement.

1. Dans Business Central, ouvrez l’environnement que vous souhaitez modifier.

   > [!TIP]
   > Pour changer d’environnement, sélectionnez <kbd>Ctrl</kbd>+<kbd>O</kbd>.
2. Sélectionnez l’icône en forme ![de loupe qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Paramètres de la fiche**, puis choisissez le lien associé. <!--Or, select [here](https://businesscentral.dynamics.com/?page=1833) to open the page directly.-->
3. Lisez les informations sur les **Paramètres de la fiche**, puis choisissez **Suivant** lorsque vous êtes prêt.
4. Sur la page **Visibilité des données**, activez le commutateur **Afficher le résumé de l’enregistrement** pour afficher les données sur les fiches ou désactivez-les pour cacher les données.
5. Sélectionnez **Suivant** et suivez les instructions pour terminer le guide de configuration.

## <a name="see-also" />Voir aussi

[Vue d’ensemble de l’intégration [!INCLUDE [prod_short](includes/prod_short.md)] et Microsoft Teams ](across-teams-overview.md)  
[Installer l’application [!INCLUDE [prod_short](includes/prod_short.md)] pour Microsoft Teams](across-install-app-for-teams.md)  
[FAQ Teams](teams-faq.md)  
[Dépannage dans Teams](admin-teams-troubleshooting.md)  
[Développement pour l’intégration de Teams](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## <a name="includeprodshortincludesfreetrialmdmd" />[!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]
