---
title: Anzeigen von App-Berechtigungen und Erteilen der Administratorzusberechtigung im Microsoft Teams Admin Center
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie die von Apps angeforderten Berechtigungen anzeigen und den Apps auf der Seite "Apps verwalten" im Microsoft Teams Admin Center die Administratorzusberechtigung erteilen.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec41760a7edd7de52d15995f39365b300cd797e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827535"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Anzeigen von App-Berechtigungen und Erteilen der Administratorzusberechtigung im Microsoft Teams Admin Center

Auf [der Seite "Apps](manage-apps.md) verwalten" im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. Sie können z. B. den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps im App Store Ihrer Organisation genehmigen oder hochladen, Apps auf Organisationsebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch organisationsweite Administratorzusendberechtigungen für Apps erteilen, die Berechtigungen für den Zugriff auf Daten anfordern und ressourcenspezifische Zustimmungsberechtigungen (RSC) für Apps anzeigen.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Erteilen der organisationsweiten Administratorzusendung für eine App

Wenn Sie ein globaler Administrator sind, können Sie Apps, die Berechtigungen für alle Benutzer in Ihrer Organisation anfordern, eine Überprüfung und Zustimmung erteilen. Dadurch müssen benutzer beim Starten der App die von der App angeforderten Berechtigungen nicht überprüfen und akzeptieren. Außerdem ist es einigen Benutzern je nach den Zustimmungseinstellungen [des](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) Benutzers in Azure Active Directory (Azure AD) möglicherweise nicht gestattet, Apps, die auf Unternehmensdaten zugreifen, die Zustimmung zu erteilen.

Beispiele für von Apps angeforderte Berechtigungen sind die Möglichkeit, in einem Team gespeicherte Informationen zu lesen, das Profil eines Benutzers zu lesen und eine E-Mail im Auftrag von Benutzern zu senden. Weitere Informationen finden Sie unter ["Berechtigungen und Zustimmung" am Endpunkt der Microsoft-Identitätsplattform.](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) 

In **der Spalte** "Berechtigungen" wird angegeben, ob eine App über Berechtigungen verfügt, für die eine Zustimmung erforderlich ist. Es wird ein Link **"Details** anzeigen" für jede app angezeigt, die in Azure AD registriert ist und über Berechtigungen verfügt, die eine Zustimmung benötigen. Beachten Sie, dass dies nur für benutzerdefinierte Apps und Apps von Drittanbietern gilt. Dieser Link wird nicht angezeigt, oder Sie müssen dem Administrator die Zustimmung von Apps erteilen, die von Microsoft veröffentlicht wurden.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot der Spalte "Berechtigungen" auf der Seite "Apps verwalten"":::

Führen Sie die folgenden Schritte aus, um einer App organisationsweite Zustimmung zu erteilen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Führen Sie einen der folgenden Schritte aus:
    - Suchen Sie nach der App, klicken Sie auf den App-Namen, um zur Detailseite der App zu wechseln, und wählen Sie dann die Registerkarte **"Berechtigungen"** aus.
    - Sortieren Sie **die Spalte "Berechtigungen"** in absteigender Reihenfolge, um die App zu finden, und wählen Sie dann **"Details anzeigen" aus.** Dadurch gelangen Sie zur **Registerkarte** "Berechtigungen" der Seite mit den App-Details.

3. Wählen **Sie unter "Organisationsweite Berechtigungen"** die Option **"Berechtigungen überprüfen" aus, und stimmen Sie zu.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot der organisationsweiten Berechtigungen auf der Registerkarte "Berechtigungen" für eine App":::

    Dazu müssen Sie ein globaler Administrator sein. Diese Option ist für Teamdienstadministratoren nicht verfügbar.

4. Überprüfen Sie **auf der Registerkarte** "Berechtigungen" die von der App angeforderten Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot der von einer App angeforderten Berechtigungen":::

    > [!IMPORTANT]
    > Wenn Sie eine organisationsweite Zustimmung für eine App erteilen, kann die App auf die Daten Ihrer Organisation zugreifen. Überprüfen Sie sorgfältig die von der App angeforderten Berechtigungen, bevor Sie die Zustimmung erteilen.
5. Wenn Sie den von der App  angeforderten Berechtigungen zustimmen, klicken Sie auf "Zustimmen", um die Zustimmung zu erteilen. Ein Banner wird vorübergehend oben auf der Seite angezeigt, um Sie darauf zu ver warnen, dass die angeforderten Berechtigungen für die App gewährt wurden. Die App hat jetzt Zugriff auf die angegebenen Ressourcen für alle Benutzer in Ihrer Organisation, und niemand wird aufgefordert, die Berechtigungen zu überprüfen.

Nachdem Sie die Berechtigungen akzeptiert haben, wird auf der Seite mit den **App-Details unter "Organisationsweite** Berechtigungen" eine Meldung angezeigt, in der Sie darauf hindeten, dass die Zustimmung erteilt wurde. Um Details zu den Berechtigungen der App anzuzeigen, klicken Sie auf den **Azure Active Directory-Link,** um zur Seite der App im Azure AD-Portal zu wechseln.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Screenshot der Meldung, die angezeigt wird, wenn die Zustimmung erteilt wurde":::

Wenn Benutzer in Ihrer Organisation die Zustimmung erteilen dürfen und ein oder mehrere Benutzer einer bestimmten App die Zustimmung erteilt haben, wird ihnen dieselbe Meldung angezeigt, um Sie darüber zu in verbindung zu halten, dass die Zustimmung erteilt wurde, und der Azure Active Directory-Link zu der Seite der App im Azure AD-Portal.

> [!NOTE]
> Obwohl die  Option "Berechtigungen und Zustimmung überprüfen" für Teamdienstadministratoren nicht verfügbar ist und sie Apps keine organisationsweite Administratorzusberechtigung erteilen können, können Teamdienstadministratoren die Inhalte auf der Registerkarte "Berechtigungen" für eine App anzeigen.  Beispielsweise kann ein Teams-Dienstadministrator auf den **Azure Active Directory-Link** klicken, um Details zu den Berechtigungen der App im Azure -AD-Portal anzuzeigen. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Anzeigen ressourcenspezifischer Zustimmungsberechtigungen für eine App

Mit der Berechtigung "RSC" können Teambesitzer einer App die Zustimmung zum Zugreifen auf und Ändern von Teamdaten erteilen. RsC-Berechtigungen sind granulare, Teams-spezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Beispiele für RsC-Berechtigungen sind das Erstellen und Löschen von Kanälen, das Erhalten der Einstellungen für ein Team und das Erstellen und Entfernen von Kanalregisterkarten. 

Die Berechtigungen für RSC werden im App-Manifest und nicht in Azure AD definiert. Wenn Sie die App zu einem Team hinzufügen, erteilen Sie die Zustimmung zu RSC-Berechtigungen. Weitere Informationen finden Sie unter ["Ressourcenspezifische Zustimmung" (RSC).](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Globale Administratoren und Der Dienstadministrator von Teams können  auf der Registerkarte "Berechtigungen" der Detailseite der App die Berechtigungen für eine App anzeigen. 

Führen Sie die folgenden Schritte aus, um die Berechtigung "RSC" für eine App anzeigen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Suchen Sie nach der App, klicken Sie auf den App-Namen, um zur Detailseite der App zu wechseln, und wählen Sie dann die Registerkarte **"Berechtigungen"** aus.
3. Überprüfen **Sie unter "Ressourcenspezifische Microsoft Graph-Zustimmung(RSC)"-Berechtigungen** die rsC-Berechtigungen, die von der App angefordert werden.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Screenshot der RsC-Berechtigungen für eine App":::

## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Der Link "Details anzeigen" wird für einige Apps von Drittanbietern, die Berechtigungen anfordern, nicht in der Spalte "Berechtigungen" angezeigt.

Derzeit ist die Möglichkeit zum Überprüfen von Berechtigungen und Erteilen der Zustimmung nicht für alle in Azure AD registrierten Apps von Drittanbietern verfügbar, die Berechtigungen anfordern. Statt des Links **"Details anzeigen"** wird die Spalte **--** **"Berechtigungen"** angezeigt. Wir arbeiten mit isVs zusammen, um dieses Feature für ihre Apps zu aktivieren.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Berechtigungen und Zustimmung im Endpunkt der Microsoft-Identitätsplattform](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Ressourcenspezifische Zustimmung in Teams](resource-specific-consent.md)
- [Ressourcenspezifische Zustimmung (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navigieren im Lebenszyklus der Teams-App](https://aka.ms/PR132) (Ignite 2020-Sitzung)


