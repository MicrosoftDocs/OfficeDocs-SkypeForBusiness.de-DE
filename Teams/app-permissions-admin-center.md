---
title: Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie von Apps angeforderte Berechtigungen anzeigen und Apps die Administratorzustimmung erteilen, auf der Seite "Apps verwalten" im Microsoft Teams Admin Center.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54fbd67fffa666e7f07719305075be264f077976
ms.sourcegitcommit: f3c380f745af4c3aaa2720234860b45696a0c333
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2022
ms.locfileid: "63442271"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center

Auf der Seite ["Apps verwalten](manage-apps.md)" im Microsoft Teams Admin Center können Sie alle Teams Apps für Ihre Organisation anzeigen und verwalten. Sie können beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps im App Store Ihrer Organisation genehmigen oder hochladen, Apps auf Organisationsebene blockieren oder zulassen und organisationsweite App-Einstellungen verwalten.

Hier können Sie auch organisationsweite Administratorzustimmungen für Apps erteilen, die Berechtigungen für den Zugriff auf Daten anfordern und Berechtigungen für ressourcenspezifische Zustimmungen (Resource-Specific Consent, RSC) für Apps anzeigen.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Organisationsweite Administratorzustimmung für eine App erteilen

Wenn Sie ein globaler Administrator sind, können Sie Apps, die Berechtigungen im Namen aller Benutzer in Ihrer Organisation anfordern, überprüfen und deren Zustimmung erteilen. Sie tun dies, damit Benutzer die von der App angeforderten Berechtigungen beim Starten der App nicht überprüfen und akzeptieren müssen. Abhängig von den [Zustimmungseinstellungen](/azure/active-directory/manage-apps/configure-user-consent) des Benutzers in Azure Active Directory (Azure AD) können einige Benutzer apps, die auf Unternehmensdaten zugreifen, möglicherweise nicht zustimmen.

Beispiele für von Apps angeforderte Berechtigungen sind die Möglichkeit, in einem Team gespeicherte Informationen zu lesen, das Profil eines Benutzers zu lesen und eine E-Mail im Namen von Benutzern zu senden. Weitere Informationen finden Sie [unter Berechtigungen und Zustimmung im Microsoft Identity Platform Endpunkt](/azure/active-directory/develop/v2-permissions-and-consent).

Die Spalte **"Berechtigungen"** gibt an, ob eine App über Berechtigungen verfügt, die zustimmungsbedürftig sind. Für jede in Azure AD registrierte App mit Berechtigungen, die zustimmungsbedürftig sind, wird ein Link "**Details anzeigen**" angezeigt. Beachten Sie, dass dies nur für benutzerdefinierte Apps und Drittanbieter-Apps gilt. Dieser Link wird nicht angezeigt, oder Sie müssen die Administratorzustimmung für von Microsoft veröffentlichte Apps erteilen.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot der Spalte &quot;Berechtigungen&quot; auf der Seite &quot;Apps verwalten&quot;.":::

Führen Sie die folgenden Schritte aus, um einer App eine organisationsweite Zustimmung zu erteilen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie einen der folgenden Schritte aus:
    - Suchen Sie nach der gewünschten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann die Registerkarte **"Berechtigungen** " aus.
    - Sortieren Sie die Spalte **"Berechtigungen"** in absteigender Reihenfolge, um die App zu finden, und wählen Sie dann " **Details anzeigen"** aus. Auf diese Weise gelangen Sie zur Registerkarte **"Berechtigungen** " der App-Detailseite.

3. Wählen Sie unter **organisationsweite Berechtigungen** **"Berechtigungen überprüfen" und "Zustimmung" aus**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot der organisationsweiten Berechtigungen auf der Registerkarte &quot;Berechtigungen&quot; für eine App.":::

    Sie müssen ein globaler Administrator sein, um dies zu tun. Diese Option steht Teams Dienstadministratoren nicht zur Verfügung.

4. Überprüfen Sie auf der Registerkarte **"Berechtigungen** " die von der App angeforderten Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot der von einer App angeforderten Berechtigungen.":::

    > [!IMPORTANT]
    > Wenn Sie einer App eine organisationsweite Zustimmung erteilen, kann die App auf die Daten Ihrer Organisation zugreifen. Überprüfen Sie sorgfältig die von der App angeforderten Berechtigungen, bevor Sie ihre Zustimmung erteilen.
5. Wenn Sie mit den von der App angeforderten Berechtigungen einverstanden sind, klicken Sie auf **"Annehmen** ", um die Zustimmung zu erteilen. Ein Banner wird vorübergehend oben auf der Seite angezeigt, um Sie darüber zu informieren, dass die angeforderten Berechtigungen für die App erteilt wurden. Die App hat jetzt Zugriff auf die angegebenen Ressourcen für alle Benutzer in Ihrer Organisation, und niemand sonst wird aufgefordert, die Berechtigungen zu überprüfen.

Nachdem Sie die Berechtigungen akzeptiert haben, wird unter **"Organisationsweite Berechtigungen"** auf der Seite "App-Details" eine Meldung angezeigt, in der Sie wissen, dass die Zustimmung erteilt wurde. Wenn Sie Details zu den Berechtigungen der App anzeigen möchten, klicken Sie auf den **Link Azure Active Directory**, um zur Seite der App im Azure AD Portal zu wechseln.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Screenshot der Meldung, die angezeigt wird, wenn die Zustimmung erteilt wurde.":::

Wenn Benutzer in Ihrer Organisation die Zustimmung erteilen dürfen und einem oder mehreren Benutzern die Zustimmung zu einer bestimmten App erteilt wurde, wird auch die gleiche Meldung angezeigt, um Sie darüber zu informieren, dass die Zustimmung erteilt wurde, und den Azure Active Directory Link zur Seite der App im Azure AD Portal.

> [!NOTE]
> Obwohl die Option **"Berechtigungen und Zustimmung überprüfen**" für Teams Dienstadministratoren nicht verfügbar ist und sie keine organisationsweite Administratorzustimmung für Apps erteilen können, können Teams Dienstadministratoren den Inhalt auf der Registerkarte **"Berechtigungen**" für eine App anzeigen. Beispielsweise kann ein Teams-Dienstadministrator auf den **Link Azure Active Directory** klicken, um Details zu App-Berechtigungen im Azure AD Portal anzuzeigen.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Anzeigen ressourcenspezifischer Zustimmungsberechtigungen einer App

Mit RSC-Berechtigungen können Teambesitzer einer App die Zustimmung erteilen, auf die Daten eines Teams zuzugreifen und diese zu ändern. RSC-Berechtigungen sind präzise, Teams-spezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Beispiele für RSC-Berechtigungen sind die Möglichkeit, Kanäle zu erstellen und zu löschen, die Einstellungen für ein Team abzurufen und Kanalregisterkarten zu erstellen und zu entfernen.

RSC-Berechtigungen sind im App-Manifest und nicht in Azure AD definiert. Sie erteilen rsc-Berechtigungen ihre Zustimmung, wenn Sie die App zu einem Team hinzufügen. Weitere Informationen finden Sie unter [Ressourcenspezifische Zustimmung (RESOURCE-Specific Consent, RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Globale Administratoren und Teams Dienstadministrator können rsc-Berechtigungen für eine App auf der Registerkarte **"Berechtigungen**" der Seite "App-Details" anzeigen.

Führen Sie die folgenden Schritte aus, um RSC-Berechtigungen für eine App anzuzeigen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Suchen Sie nach der gewünschten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann die Registerkarte **"Berechtigungen** " aus.
3. Überprüfen Sie unter **Microsoft Graph ressourcenspezifischen Zustimmungsberechtigungen (RESOURCE-Specific Consent, RSC)** die von der App angeforderten RSC-Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="Screenshot der RSC-Berechtigungen für eine App.":::

## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Der Link "Details anzeigen" wird in der Spalte "Berechtigungen" für einige Drittanbieter-Apps, die Berechtigungen anfordern, nicht angezeigt.

Derzeit ist die Möglichkeit, Berechtigungen zu überprüfen und die Zustimmung zu erteilen, nicht für alle Apps von Drittanbietern verfügbar, die in Azure AD registriert sind, die Berechtigungen anfordern. Anstelle des Links **"Details anzeigen**" wird die Spalte **"Berechtigungen"** angezeigt **--**. Wir arbeiten mit ISVs zusammen, um dieses Feature für ihre Apps zu aktivieren.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Berechtigungen und Zustimmung im Microsoft Identity Platform Endpunkt](/azure/active-directory/develop/v2-permissions-and-consent)
- [Ressourcenspezifische Zustimmung in Teams](resource-specific-consent.md)
- [Ressourcenspezifische Zustimmung (Resource Specific Consent, RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navigieren im Teams App-Lebenszyklus](https://aka.ms/PR132) (Ignite 2020-Sitzung)
