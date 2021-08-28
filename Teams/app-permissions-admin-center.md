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
description: Erfahren Sie, wie Sie von Apps angeforderte Berechtigungen anzeigen und den Apps auf der Seite "Apps verwalten" im Microsoft Teams Admin Center die Administratorzusberechtigung erteilen.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e4875eca0c7a9848d7676be77e4677de45cf8db
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580239"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Anzeigen von App-Berechtigungen und Erteilen der Administratorzusberechtigung im Microsoft Teams Admin Center

Auf [der Seite Apps](manage-apps.md) verwalten im Microsoft Teams Admin Center können Sie alle Ihre Teams für Ihre Organisation anzeigen und verwalten. So können Sie beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps im App Store Ihrer Organisation genehmigen oder hochladen, Apps auf Organisationsebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch organisationsweite Administratorzusberechtigungen für Apps erteilen, die Berechtigungen für den Zugriff auf Daten anfordern und ressourcenspezifische Zustimmungsberechtigungen (RSC) für Apps anzeigen.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Erteilen der organisationsweiten Administratorzusendung für eine App

Wenn Sie ein globaler Administrator sind, können Sie Apps, die Berechtigungen für alle Benutzer in Ihrer Organisation anfordern, eine Überprüfung und Zustimmung erteilen. Dadurch müssen Benutzer die von der App angeforderten Berechtigungen beim Starten der App nicht überprüfen und akzeptieren. Darüber hinaus ist es einigen Benutzern [je](/azure/active-directory/manage-apps/configure-user-consent) nach den Einstellungen für die Zustimmung des Benutzers in Azure Active Directory (Azure AD) möglicherweise nicht gestattet, Apps, die auf Unternehmensdaten zugreifen, die Zustimmung zu erteilen.

Beispiele für von Apps angeforderte Berechtigungen sind die Möglichkeit, in einem Team gespeicherte Informationen zu lesen, das Profil eines Benutzers zu lesen und eine E-Mail im Auftrag von Benutzern zu senden. Weitere Informationen finden Sie unter [Berechtigungen und Zustimmung im Microsoft Identity Platform Endpunkt.](/azure/active-directory/develop/v2-permissions-and-consent) 

In **der Spalte** Berechtigungen wird angegeben, ob eine App Über Berechtigungen verfügt, für die eine Zustimmung erforderlich ist. Es wird ein Link **Details** anzeigen für jede app angezeigt, die in Azure AD registriert ist und über Berechtigungen verfügt, die eine Zustimmung benötigen. Beachten Sie, dass dies nur für benutzerdefinierte Apps und Apps von Drittanbietern gilt. Dieser Link wird nicht angezeigt, oder Sie müssen die Zustimmung des Administrator für Apps erteilen, die von Microsoft veröffentlicht wurden.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot der Spalte "Berechtigungen" auf der Seite "Apps verwalten"":::

Führen Sie die folgenden Schritte aus, um einer App organisationsweite Zustimmung zu erteilen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie einen der folgenden Schritte aus:
    - Suchen Sie nach der gesuchten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann die **Registerkarte Berechtigungen** aus.
    - Sortieren Sie **die Spalte Berechtigungen** in absteigender Reihenfolge, um die App zu finden, und wählen Sie dann Details anzeigen **aus.** Dadurch gelangen Sie zur **Registerkarte** Berechtigungen der App-Detailseite.

3. Wählen **Sie unter Organisationsweite Berechtigungen** die Option Berechtigungen überprüfen und Zustimmung **aus.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot von organisationsweiten Berechtigungen auf der Registerkarte "Berechtigungen" für eine App":::

    Sie müssen ein globaler Administrator sein, um dies zu tun. Diese Option steht für Administratoren Teams Diensts nicht zur Verfügung.

4. Überprüfen Sie **auf der** Registerkarte Berechtigungen die von der App angeforderten Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot der von einer App angeforderten Berechtigungen":::

    > [!IMPORTANT]
    > Wenn Sie einer App organisationsweite Zustimmung erteilen, kann die App auf die Daten Ihrer Organisation zugreifen. Überprüfen Sie die von der App angeforderten Berechtigungen sorgfältig, bevor Sie ihre Zustimmung erteilen.
5. Wenn Sie den von der App angeforderten Berechtigungen zustimmen, klicken Sie **auf** Akzeptieren, um die Zustimmung zu erteilen. Vorübergehend wird am oberen Rand der Seite ein Banner angezeigt, um Sie darauf hin zu machen, dass die angeforderten Berechtigungen für die App gewährt wurden. Die App hat jetzt Zugriff auf die angegebenen Ressourcen für alle Benutzer in Ihrer Organisation, und niemand wird aufgefordert, die Berechtigungen zu überprüfen.

Nachdem Sie die Berechtigungen akzeptiert haben, wird auf der Seite mit den **App-Details** unter Organisationsweite Berechtigungen eine Meldung angezeigt, mit der Sie wissen, dass die Zustimmung erteilt wurde. Um Details zu den Berechtigungen der App anzuzeigen, klicken Sie auf den **Link Azure Active Directory,** um zur Seite der App im Azure AD-Portal zu wechseln.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Screenshot der Nachricht, die angezeigt wird, wenn die Zustimmung erteilt wurde":::

Wenn Benutzer in Ihrer Organisation Ihre Zustimmung erteilen dürfen und ein oder mehrere Benutzer einer bestimmten App die Zustimmung erteilt haben, wird ihnen dieselbe Meldung angezeigt, um Sie darüber zu in Verbindung zu halten, dass die Zustimmung erteilt wurde, und der Link Azure Active Directory zur Seite der App im Azure AD-Portal wird angezeigt.

> [!NOTE]
> Obwohl die  Option Berechtigungen und Zustimmung überprüfen für Teams-Dienstadministratoren nicht verfügbar ist und sie Apps keine organisationsweite Administratorzusberechtigung erteilen können,  können Teams-Dienstadministratoren die Inhalte auf der Registerkarte Berechtigungen für eine App anzeigen. Beispielsweise kann ein Teams-Dienstadministrator auf  den Link Azure Active Directory klicken, um Details zu App-Berechtigungen im Azure AD-Portal anzuzeigen. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Anzeigen ressourcenspezifischer Zustimmungsberechtigungen für eine App

Mit RSC-Berechtigungen können Teambesitzer einer App die Zustimmung zum Zugreifen auf und Ändern von Teamdaten erteilen. RSC-Berechtigungen sind granular und Teams Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Beispiele für RSC-Berechtigungen sind das Erstellen und Löschen von Kanälen, das Erhalten der Einstellungen für ein Team und das Erstellen und Entfernen von Kanalregisterkarten. 

RSC-Berechtigungen werden im App-Manifest und nicht in Azure AD definiert. Sie erteilen die Zustimmung zu RSC-Berechtigungen, wenn Sie die App zu einem Team hinzufügen. Weitere Informationen finden Sie unter [Ressourcenspezifische Zustimmung (RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Globale Administratoren und Teams Dienstadministratoren können RSC-Berechtigungen  für eine App auf der Registerkarte Berechtigungen auf der Seite mit den App-Details anzeigen. 

Führen Sie die folgenden Schritte aus, um RSC-Berechtigungen für eine App anzeigen zu können:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Suchen Sie nach der gesuchten App, klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann die **Registerkarte Berechtigungen** aus.
3. Überprüfen Sie unter Microsoft Graph Ressourcenspezifische Zustimmung **(RSC)-Berechtigungen** die von der App angeforderten RSC-Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Screenshot der RSC-Berechtigungen für eine App":::

## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Der Link "Details anzeigen" wird bei einigen Drittanbieter-Apps, die Berechtigungen anfordern, in der Spalte Berechtigungen nicht angezeigt.

Derzeit ist die Möglichkeit zum Überprüfen von Berechtigungen und Erteilen der Zustimmung nicht für alle in Azure AD registrierten Drittanbieter-Apps verfügbar, die Berechtigungen anfordern. Statt des **Links Details anzeigen** wird die Spalte Berechtigungen **--** angezeigt.  Wir arbeiten mit isVs zusammen, um dieses Feature für ihre Apps zu aktivieren.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Berechtigungen und Zustimmung im Microsoft Identity Platform-Endpunkt](/azure/active-directory/develop/v2-permissions-and-consent)
- [Ressourcenspezifische Zustimmung in Teams](resource-specific-consent.md)
- [Ressourcenspezifische Zustimmung (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navigieren im Teams App-Lebenszyklus](https://aka.ms/PR132) (Ignite 2020-Sitzung)