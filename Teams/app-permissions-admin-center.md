---
title: Anzeigen von App-Berechtigungen und Erteilen der Administrator zustimmung im Microsoft Teams Admin Center
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie von Apps angeforderte Berechtigungen anzeigen und den Administratoren die Zustimmung für Apps auf der Seite Apps verwalten im Microsoft Teams Admin Center erteilen.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2833a548ccf66b327d9feb71155f1ed33a671f1c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094657"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Anzeigen von App-Berechtigungen und Erteilen der Administrator zustimmung im Microsoft Teams Admin Center

Auf [der Seite](manage-apps.md) "Apps verwalten" im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. So können Sie beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps im App Store Ihrer Organisation genehmigen oder hochladen, Apps auf Organisationsebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch organisationsweite Administratorberechtigungen für Apps erteilen, die Berechtigungen für den Zugriff auf Daten anfordern und ressourcenspezifische Zustimmungsberechtigungen für Apps anzeigen.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Organisationsweite Administrator zustimmung für eine App erteilen

Wenn Sie ein globaler Administrator sind, können Sie Apps, die Berechtigungen für alle Benutzer in Ihrer Organisation anfordern, eine Überprüfung und Zustimmung erteilen. Sie tun dies, damit Benutzer die von der App beim Starten der App angeforderten Berechtigungen nicht überprüfen und akzeptieren müssen. Abhängig von den Zustimmungseinstellungen des Benutzers [in](/azure/active-directory/manage-apps/configure-user-consent) Azure Active Directory (Azure AD) ist es einigen Benutzern möglicherweise nicht gestattet, Apps, die auf Unternehmensdaten zugreifen, die Zustimmung zu erteilen.

Beispiele für von Apps angeforderte Berechtigungen sind die Möglichkeit, in einem Team gespeicherte Informationen zu lesen, das Profil eines Benutzers zu lesen und eine E-Mail im Auftrag der Benutzer zu senden. Weitere Informationen finden Sie unter [Berechtigungen und Zustimmung im Endpunkt der Microsoft-Identitätsplattform.](/azure/active-directory/develop/v2-permissions-and-consent) 

In **der Spalte** Berechtigungen wird angegeben, ob eine App über Berechtigungen verfügt, die einer Zustimmung bedarf. Es wird ein Link **Details** anzeigen für jede App angezeigt, die in Azure AD registriert ist und über Berechtigungen verfügt, für die eine Zustimmung erforderlich ist. Beachten Sie, dass dies nur für benutzerdefinierte Apps und Apps von Drittanbietern gilt. Dieser Link wird nicht angezeigt, oder Sie müssen die Zustimmung des Administrator für apps erteilen, die von Microsoft veröffentlicht wurden.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot der Spalte "Berechtigungen" auf der Seite "Apps verwalten"":::

Führen Sie die folgenden Schritte aus, um einer App organisationsweite Zustimmung zu erteilen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie einen der folgenden Schritte aus:
    - Suchen Sie nach der gesuchten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann die Registerkarte **Berechtigungen** aus.
    - Sortieren Sie **die Spalte Berechtigungen** in absteigender Reihenfolge, um die App zu finden, und wählen Sie dann Details anzeigen **aus.** Dadurch gelangen Sie zur **Registerkarte** Berechtigungen auf der Seite mit den App-Details.

3. Wählen **Sie unter Organisationsweite Berechtigungen** die Option Berechtigungen überprüfen und Zustimmung **aus.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot der organisationsweiten Berechtigungen auf der Registerkarte Berechtigungen für eine App":::

    Dazu müssen Sie ein globaler Administrator sein. Diese Option ist für Teams-Dienstadministratoren nicht verfügbar.

4. Überprüfen Sie **auf der** Registerkarte Berechtigungen die von der App angeforderten Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot der von einer App angeforderten Berechtigungen":::

    > [!IMPORTANT]
    > Wenn Sie einer App organisationsweite Zustimmung erteilen, kann die App auf die Daten Ihrer Organisation zugreifen. Überprüfen Sie die von der App angeforderten Berechtigungen sorgfältig, bevor Sie die Zustimmung erteilen.
5. Wenn Sie mit den von der App angeforderten Berechtigungen einverstanden sind, klicken Sie **auf Akzeptieren,** um die Zustimmung zu erteilen. Am oberen Rand der Seite wird vorübergehend ein Banner angezeigt, damit Sie wissen, dass die angeforderten Berechtigungen für die App erteilt wurden. Die App hat jetzt Zugriff auf die angegebenen Ressourcen für alle Benutzer in Ihrer Organisation, und niemand sonst wird aufgefordert, die Berechtigungen zu überprüfen.

Nachdem Sie die Berechtigungen akzeptiert haben, wird auf der Seite mit den **App-Details** unter Organisationsweite Berechtigungen eine Meldung angezeigt, in der Sie wissen möchten, dass die Zustimmung erteilt wurde. Wenn Sie Details zu den Berechtigungen der App anzeigen möchten, klicken Sie auf den **Azure Active Directory-Link,** um zur Seite der App im Azure AD-Portal zu wechseln.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Screenshot der Meldung, die angezeigt wird, wenn die Zustimmung erteilt wurde":::

Wenn Benutzer in Ihrer Organisation die Zustimmung erteilen dürfen und ein oder mehrere Benutzer einer bestimmten App die Zustimmung erteilt haben, wird auch dieselbe Meldung angezeigt, in der Sie darüber in Verbindung mit dem Azure Active Directory-Link zur Seite der App im Azure AD-Portal gelangen.

> [!NOTE]
> Obwohl die  Option Berechtigungen und Zustimmung überprüfen für Teams-Dienstadministratoren nicht verfügbar ist und sie apps keine organisationsweite Administrator zustimmung  erteilen können, können Teams-Dienstadministratoren den Inhalt auf der Registerkarte Berechtigungen für eine App anzeigen. Beispielsweise kann ein Teams-Dienstadministrator auf den **Azure Active Directory-Link** klicken, um Details zu Den App-Berechtigungen im Azure AD-Portal anzuzeigen. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Anzeigen ressourcenspezifischer Zustimmungsberechtigungen einer App

Mit den RSC-Berechtigungen können Teambesitzer die Zustimmung für eine App erteilen, um auf die Daten eines Teams zu zugreifen und diese zu ändern. RsC-Berechtigungen sind granulare, teamsspezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Beispiele für RSC-Berechtigungen sind die Möglichkeit, Kanäle zu erstellen und zu löschen, die Einstellungen für ein Team zu erhalten sowie Kanalregisterkarten zu erstellen und zu entfernen. 

RSC-Berechtigungen werden im App-Manifest und nicht in Azure AD definiert. Sie stimmen den RSC-Berechtigungen zu, wenn Sie die App zu einem Team hinzufügen. Weitere Informationen finden Sie unter [Ressourcenspezifische Zustimmung (RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Globale Administratoren und Teams-Dienstadministratoren können rsC-Berechtigungen für eine App auf der Registerkarte **Berechtigungen** auf der Seite "App-Details" anzeigen. 

Zum Anzeigen von RSC-Berechtigungen für eine App führen Sie die folgenden Schritte aus:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Suchen Sie nach der gesuchten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann die Registerkarte **Berechtigungen** aus.
3. Überprüfen **Sie unter Microsoft Graph resource-specific consent (RSC)** die von der App angeforderten RSC-Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Screenshot der RSC-Berechtigungen für eine App":::

## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Der Link "Details anzeigen" wird in der Spalte Berechtigungen für einige Apps von Drittanbietern, die Berechtigungen anfordern, nicht angezeigt.

Derzeit ist die Möglichkeit zum Überprüfen von Berechtigungen und Zum Erteilen der Zustimmung nicht für alle in Azure AD registrierten Drittanbieter-Apps verfügbar, die Berechtigungen anfordern. Anstelle des Links **Details anzeigen** wird die Spalte Berechtigungen **--** angezeigt.  Wir arbeiten mit ISVs zusammen, um dieses Feature für ihre Apps zu aktivieren.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Berechtigungen und Zustimmung im Endpunkt der Microsoft-Identitätsplattform](/azure/active-directory/develop/v2-permissions-and-consent)
- [Ressourcenspezifische Zustimmung in Teams](resource-specific-consent.md)
- [Ressourcenspezifische Zustimmung (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navigieren im Lebenszyklus der Teams-App](https://aka.ms/PR132) (Ignite 2020-Sitzung)