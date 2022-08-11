---
title: Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie auf der Seite "Apps verwalten" im Microsoft Teams-Administrationszentrum die von Apps angeforderten Berechtigungen anzeigen und den Apps eine Admin-Zustimmung erteilen.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5bd84ce2fa19fc7a9aa823250fa77f1980055f0
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299054"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center

Auf der Seite [Apps verwalten](manage-apps.md) im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. Beispielsweise können Sie den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps genehmigen oder in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen und organisationsweite App-Einstellungen verwalten.

Hier können Sie außerdem Apps, die Berechtigungen für den Zugriff auf Daten anfordern, organisationsweite Administratorzustimmung erteilen, sowie ressourcenspezifische Zustimmungsberechtigungen (Resource-Specific Consent, RSC) für Apps anzeigen.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Erteilen der organisationsweiten Administratorzustimmung für eine App

Als globaler Administrator können Sie Apps, die Berechtigungen im Namen aller Benutzer in Ihrer Organisation anfordern, überprüfen und ihre Zustimmung erteilen. Sie tun dies, damit Benutzer die von der App angeforderten Berechtigungen nicht überprüfen und akzeptieren müssen, wenn sie die App starten. Je nach den [Zustimmungseinstellungen](/azure/active-directory/manage-apps/configure-user-consent) des Benutzers in Azure Active Directory (Azure AD) dürfen einige Benutzer möglicherweise keine Zustimmung für Anwendungen erteilen, die auf Unternehmensdaten zugreifen.

Beispiele für Berechtigungen, die von Apps angefordert werden, sind die Möglichkeit, in einem Team gespeicherte Informationen zu lesen, das Profil eines Benutzers zu lesen und eine E-Mail im Namen des Nutzers zu senden. Weitere Informationen finden Sie unter [Berechtigungen und Zustimmung im Microsoft Identity Platform-Endpunkt](/azure/active-directory/develop/v2-permissions-and-consent).

Die Spalte **Berechtigungen** gibt an, ob eine App über Berechtigungen verfügt, die zustimmungsbedürftig sind. Für jede App, die in Azure AD registriert ist und über Berechtigungen verfügt, die eine Zustimmung benötigen, wird ein Link **Details anzeigen** angezeigt. Beachten Sie, dass dies nur für benutzerdefinierte und Drittanbieter-Anwendungen gilt. Der Link ist für von Microsoft bereitgestellte Apps nicht verfügbar. Außerdem ist eine Zustimmung durch Administratoren für solche Apps nicht notwendig.

Führen Sie die folgenden Schritte aus, um einer App organisationsweite Berechtigungen zu erteilen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Führen Sie einen der folgenden Schritte aus:
    * Suchen Sie nach der gewünschten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu gelangen, und wählen Sie dann die Registerkarte **Berechtigungen** aus.
    * Sortieren Sie die Spalte **Berechtigungen** in absteigender Reihenfolge, um die App zu finden, und wählen Sie dann **Details anzeigen** aus. Auf diese Weise gelangen Sie zur Registerkarte **Berechtigungen** der Seite mit den App-Details.

1. Wählen Sie unter **Organisationsweite Berechtigungen** die Option **Berechtigungen überprüfen und zustimmen** aus.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot der organisationsweiten Berechtigungen auf der Registerkarte „Berechtigungen“ für eine App.":::

    Sie müssen ein globaler Administrator sein, um dies zu tun. Diese Option ist für Microsoft Teams-Dienstadministratoren nicht verfügbar.

1. Überprüfen Sie auf der Registerkarte **Berechtigungen** die von der App angeforderten Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot der von einer App angeforderten Berechtigungen.":::

    > [!IMPORTANT]
    > Wenn Sie einer App eine organisationsweite Zustimmung erteilen, kann die App auf die Daten Ihrer Organisation zugreifen. Überprüfen Sie sorgfältig die von der App angeforderten Berechtigungen, bevor Sie ihre Zustimmung erteilen.

1. Wenn Sie mit den von der App angeforderten Berechtigungen einverstanden sind, klicken Sie auf **Annehmen**, um die Zustimmung zu erteilen. Oben auf der Seite wird nun kurz ein Banner angezeigt, um Sie darüber zu informieren, dass die angeforderten Berechtigungen für die App erteilt wurden. Die App hat jetzt Zugriff auf die angegebenen Ressourcen für alle Benutzer in Ihrer Organisation, und niemand sonst wird aufgefordert, die Berechtigungen zu überprüfen.

Nachdem Sie die Berechtigungen angenommen haben, wird auf der Seite mit den App-Details unter **Organisationsweite Berechtigungen** eine Meldung angezeigt, um Sie darüber zu informieren, dass die Zustimmung erteilt wurde. Um Details zu den Berechtigungen der App anzuzeigen, klicken Sie auf den **Azure Active Directory**-Link, um zur Seite der App im Azure AD-Portal zu wechseln.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Screenshot der Nachricht, die bei Zustimmungserteilung angezeigt wird.":::

Wenn Benutzer in Ihrer Organisation die Zustimmung erteilen dürfen und einem oder mehreren Benutzern die Zustimmung zu einer bestimmten App erteilt wurde, wird auch die gleiche Nachricht angezeigt, um Sie darüber zu informieren, dass die Zustimmung erteilt wurde, und den Azure Active Directory-Link zur App-Seite im Azure AD-Portal.

> [!NOTE]
> Obwohl die Option **Berechtigungen und Zustimmung überprüfen** für Teams-Dienstadministratoren nicht verfügbar ist und sie keine organisationsweite Administratoreinwilligung für Apps erteilen können, können Teams-Dienstadministratoren den Inhalt auf der Registerkarte **Berechtigungen** für eine App anzeigen. Beispielsweise kann ein Teams-Dienstadministrator auf den **Azure Active Directory-Link** klicken, um Details zu App-Berechtigungen im Azure AD-Portal anzuzeigen.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Anzeigen ressourcenspezifischer Zustimmungsberechtigungen einer App

RSC-Berechtigungen ermöglichen es Teambesitzern, einer App die Zustimmung für den Zugriff auf die Daten eines Teams zu erteilen und diese zu ändern. RSC-Berechtigungen sind detaillierte Teams-spezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Beispiele für RSC-Berechtigungen sind die Möglichkeit, Kanäle zu erstellen und zu löschen, die Einstellungen für ein Team abzurufen und Kanalregisterkarten zu erstellen und zu entfernen.

RSC-Berechtigungen sind im App-Manifest und nicht in Azure AD definiert. Sie erteilen RSC-Berechtigungen Ihre Zustimmung, wenn Sie die App zu einem Team hinzufügen. Weitere Informationen finden Sie unter [Ressourcenspezifische Zustimmung (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent).

Globale Administratoren und Teams-Dienstadministratoren können RSC-Berechtigungen für eine App auf der Registerkarte **Berechtigungen** auf der Seite "App-Details" anzeigen.

Gehen Sie folgendermaßen vor, um die RSC-Berechtigungen für eine Anwendung anzuzeigen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
1. Suchen Sie nach der gewünschten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu gelangen, und wählen Sie dann die Registerkarte **Berechtigungen** aus.
1. Überprüfen Sie unter **Microsoft Graph ressourcenspezifischen Zustimmungsberechtigungen (RSC)** die von der App angeforderten RSC-Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="Screenshot der RSC-Berechtigungen für eine App.":::

## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Der Link "Details anzeigen" wird in der Spalte "Berechtigungen" für einige Drittanbieter-Apps, die Berechtigungen anfordern, nicht angezeigt.

Die Möglichkeit, Berechtigungen zu überprüfen und die Zustimmung zu erteilen, ist nicht für alle Drittanbieter-Apps verfügbar. In der Regel werden die Drittanbieter-Apps in Azure Active Directory registriert, wenn die Apps Berechtigungen anfordern. Anstelle des Links **Details anzeigen** sehen Sie `--` in der Spalte **Berechtigungen**.

## <a name="related-articles"></a>Verwandte Artikel

* [Verwalten Sie Ihre Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Berechtigungen und Zustimmung im Microsoft Identity Platform-Endpunkt](/azure/active-directory/develop/v2-permissions-and-consent)
* [Ressourcenspezifische Zustimmung in Teams](resource-specific-consent.md)
* [Ressourcenspezifische Zustimmung (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Navigieren im Lebenszyklus der Teams-App](https://aka.ms/PR132) (Ignite 2020-Sitzung)
