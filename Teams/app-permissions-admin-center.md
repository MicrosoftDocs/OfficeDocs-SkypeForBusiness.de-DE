---
title: Anzeigen von App-Berechtigungen und erteilen der Zustimmung des Administrators im Microsoft Teams Admin Center
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie von apps angeforderte Berechtigungen anzeigen und Apps auf der Seite "Apps verwalten" des Microsoft Teams admin Centers die Zustimmung des Administrators erteilen.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814611"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Anzeigen von App-Berechtigungen und erteilen der Zustimmung des Administrators im Microsoft Teams Admin Center

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Auf der Seite " [apps verwalten](manage-apps.md) " im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. So können Sie beispielsweise den Status und die Eigenschaften von apps auf Organisationsebene anzeigen, neue benutzerdefinierte apps im App Store Ihrer Organisation genehmigen oder hochladen, Apps auf org-Ebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch apps, die Berechtigungen für den Zugriff auf Daten anfordern und die Berechtigungen für die ressourcenspezifische Zustimmung (RSC) für apps anzeigen, die organisationsweite Zustimmung des Administrators erteilen.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Erteilen einer organisationsweiten Administrator Zustimmung zu einer APP

Als Administrator können Sie apps, die Berechtigungen für alle Benutzer in Ihrer Organisation anfordern, überprüfen und deren Zustimmung erteilen. Sie tun dies, damit Benutzer die von der APP angeforderten Berechtigungen nicht überprüfen und akzeptieren müssen, wenn Sie die app starten. Je nach den [Zustimmungs Einstellungen](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) des Benutzers in Azure Active Directory (Azure AD) ist es einigen Benutzern möglicherweise nicht gestattet, apps zu genehmigen, die auf Unternehmensdaten zugreifen.

Beispiele für von apps angeforderte Berechtigungen sind die Möglichkeit, in einem Team gespeicherte Informationen zu lesen, das Profil eines Benutzers zu lesen und eine e-Mail im Auftrag der Benutzer zu senden. Weitere Informationen finden Sie unter [Berechtigungen und Zustimmung im Microsoft Identity Platform-Endpunkt](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent). 

Sie müssen ein globaler Administrator sein, um einer App eine organisationsweite Zustimmung zu erteilen. Die Spalte " **Berechtigungen** " gibt an, ob eine APP Berechtigungen hat, für die eine Genehmigung erforderlich ist. Für jede APP, die in Azure AD registriert ist, wird ein Link " **Details anzeigen** " angezeigt, der Berechtigungen enthält, für die eine Genehmigung erforderlich ist. Beachten Sie, dass dies nur für benutzerdefinierte apps und apps von Drittanbietern gilt. Dieser Link wird nicht angezeigt, oder Sie müssen die Zustimmung des Administrators für von Microsoft veröffentlichte apps erteilen.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot der Spalte "Berechtigungen" auf der Seite "Apps verwalten"":::

Führen Sie die folgenden Schritte aus, um einer App eine organisationsweite Zustimmung zu erteilen:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.
2. Führen Sie einen der folgenden Schritte aus:
    - Suchen Sie nach der gewünschten APP, klicken Sie auf den Namen der APP, um zur Seite App-Details zu wechseln, und wählen Sie dann die Registerkarte **Berechtigungen** aus.
    - Sortieren Sie die Spalte **Berechtigungen** in absteigender Reihenfolge, um die APP zu finden, und wählen Sie dann **Details anzeigen**aus. Dadurch gelangen Sie auf die Registerkarte **Berechtigungen** auf der Seite App-Details.

3. Wählen Sie unter **organisationsweite Berechtigungen**die Option **Berechtigungen und Zustimmung überprüfen**aus. Sie müssen ein globaler Administrator sein, um dies zu tun. Diese Option steht für Teams-Dienstadministratoren nicht zur Verfügung.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot der organisationsweiten Berechtigungen auf der Registerkarte "Berechtigungen" für eine APP":::

4. Überprüfen Sie auf der Registerkarte **Berechtigungen** die von der APP angeforderten Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot der von einer APP angeforderten Berechtigungen":::

    > [!IMPORTANT]
    > Durch das Erteilen einer organisationsweiten Zustimmung zu einer APP kann die APP auf die Daten Ihrer Organisation zugreifen. Überprüfen Sie sorgfältig die von der APP angeforderten Berechtigungen, bevor Sie die Zustimmung erteilen.
5. Wenn Sie mit den von der APP angeforderten Berechtigungen einverstanden sind, klicken Sie auf **annehmen** , um die Zustimmung zu erteilen. Oben auf der Seite wird vorübergehend ein Banner eingeblendet, in dem Sie darüber informiert werden, dass die angeforderte Berechtigung für die APP gewährt wurde. Die APP hat nun Zugriff auf die angegebenen Ressourcen für alle Benutzer in Ihrer Organisation, und niemand sonst wird aufgefordert, die Berechtigungen zu überprüfen.

Nachdem Sie die Berechtigungen akzeptiert haben, wird auf der Seite APP **-Details unter organisationsweite Berechtigungen** eine Meldung angezeigt, in der Sie darüber informiert werden, dass die Genehmigung erteilt wurde. Wenn Sie Details zu den Berechtigungen der App anzeigen möchten, klicken Sie auf den **Azure Active Directory** -Link, um zur Seite der APP im Azure AD-Portal zu wechseln.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Screenshot der Nachricht, die angezeigt wird, wenn die Genehmigung erteilt wurde":::

Wenn Benutzern in Ihrer Organisation die Genehmigung erteilt werden kann und wenn ein oder mehrere Benutzer der Zustimmung zu einer bestimmten app zugestimmt haben, wird nur die Meldung angezeigt, in der Sie wissen, dass die Genehmigung erteilt wurde, und der Azure Active Directory-Link. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Anzeigen der ressourcenspezifischen Genehmigungsberechtigungen einer APP

Mit RSC-Berechtigungen können Teambesitzer die Zustimmung einer APP für den Zugriff auf die Daten eines Teams erteilen und diese ändern. RSC-Berechtigungen sind granulare, Teams-spezifische Berechtigungen, die definieren, was eine app in einem bestimmten Team tun kann. Beispiele für RSC-Berechtigungen sind die Möglichkeit, Kanäle zu erstellen und zu löschen, die Einstellungen für ein Team abzurufen und Kanal Registerkarten zu erstellen und zu entfernen. RSC-Berechtigungen werden im App-Manifest und nicht in Azure AD definiert.

Sie erteilen die Zustimmung zu RSC-Berechtigungen, wenn Sie die APP einem Team hinzufügen. Weitere Informationen finden Sie unter [ressourcenspezifische Zustimmung (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) und [ressourcenspezifische Zustimmung in Teams](resource-specific-consent.md).

Globale Administratoren und Teams können vom Dienstadministrator die RSC-Berechtigungen anzeigen. Führen Sie die folgenden Schritte aus, um die RSC-Berechtigungen für eine APP anzuzeigen:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.
2. Suchen Sie nach der gewünschten APP, klicken Sie auf den Namen der APP, um zur Seite App-Details zu wechseln, und wählen Sie dann die Registerkarte **Berechtigungen** aus.
3. Überprüfen Sie unter **Microsoft Graph-Berechtigungen für ressourcenspezifische Zustimmung (RSC)** die von der APP angeforderten RSC-Berechtigungen.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Screenshot der RSC-Berechtigungen für eine APP":::

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Berechtigungen und Zustimmung im Microsoft Identity Platform-Endpunkt](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Ressourcenspezifische Zustimmung in Teams](resource-specific-consent.md)
- [Ressourcenspezifische Zustimmung (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


