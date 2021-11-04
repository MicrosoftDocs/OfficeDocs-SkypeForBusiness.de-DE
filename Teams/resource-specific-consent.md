---
title: Ressourcenspezifische Zustimmung in Microsoft Teams
author: cichur
ms.author: v-mahoffman
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die Einstellungen, die Sie konfigurieren müssen, um zu steuern, ob Teambesitzer in Ihrer Organisation Apps zustimmen können.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f12acd7d99f8ab841f47ca84bc677f104cc0f164
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740231"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Ressourcenspezifische Zustimmung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Mit der ressourcenspezifischen Zustimmung in Microsoft Teams Teambesitzern die Zustimmung von Apps für den Zugriff auf Teamdaten erteilt. Beispiele für einen solchen Zugriff sind die Möglichkeit, Kanalnachrichten zu lesen, Kanäle zu erstellen und zu löschen sowie Kanalregisterkarten zu erstellen und zu entfernen.

Als Administrator steuern Sie, ob Teambesitzer in Ihrer Organisation über Einstellungen, die Sie mithilfe des Azure Active Directory(Azure AD) PowerShell-Moduls oder des Azure-Portals und des Microsoft Teams Admin Centers konfigurieren, ihre Zustimmung geben können.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Festlegen, ob Teambesitzer Apps die Zustimmung erteilen können

Hier sind die Einstellungen, die Sie festlegen müssen, um zu steuern, ob Teambesitzer Apps die Zustimmung erteilen können. Überprüfen Sie unbedingt alle folgenden Einstellungen.

### <a name="settings-in-azure-ad"></a>Einstellungen in Azure AD

Die folgenden beiden Einstellungen bestimmen, ob Teambesitzer Apps die Zustimmung erteilen können.

> [!IMPORTANT]
> Eine Änderung dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, für die bereits die Zustimmung erteilt wurde. Wenn Sie diese Einstellungen beispielsweise so konfigurieren, dass Teambesitzer nicht ihre Zustimmung geben, wird durch diese Änderungen kein bereits gewährter Datenzugriff entfernt.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Die Einstellung "Benutzer können apps den Zugriff auf Unternehmensdaten in ihrem Auftrag zustimmen"

Diese Einstellung steuert, ob Benutzer in Ihrer Organisation Apps in ihrem Namen zustimmen können. Damit Teambesitzer ihre Zustimmung geben können, muss diese Einstellung auf Ja **festgelegt sein.** Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Wechseln Sie im Azure-Portal zu **Enterprise**  >  **Benutzereinstellungen**.
2. Legen **Enterprise unter Enterprise-Anwendungen** die Gruppe Benutzer können Apps den Zugriff auf Unternehmensdaten **in** ihrem Namen zustimmen auf **Nein** oder **Ja.**

Sie können diese Einstellung auch mithilfe von PowerShell verwalten. Weitere Informationen finden Sie unter [Konfigurieren von Benutzerinhalten für Anwendungen.](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>Die Einstellung "EnableGroupSpecificConsent"

Mit dieser Einstellung wird kontrolliert, ob Benutzer in Ihrer Organisation Apps den Zugriff auf Unternehmensdaten für die Gruppen, die sie besitzen, zustimmen können. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung erteilen können. Schritte zum Verwalten dieser Einstellung mithilfe von PowerShell finden Sie unter Konfigurieren der Zustimmung des Gruppenbesitzers für Apps, [die auf Gruppendaten zugreifen.](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Einstellungen im Microsoft Teams Admin Center

Zusätzlich zu den Einstellungen in Azure AD bestimmen organisationsweite [](manage-apps.md) App-Einstellungen auf der Seite "Apps [](manage-apps.md#allow-and-block-apps) verwalten", ob [](teams-app-permission-policies.md) eine App auf der Seite "Apps verwalten" blockiert oder zulässig ist, und die dem Teambesitzer zugewiesene [App-Berechtigungsrichtlinie](manage-apps.md#manage-org-wide-app-settings) bestimmt, ob ein Teambesitzer seine Zustimmung erteilen kann.

> [!IMPORTANT]
> Eine Änderung dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, für die bereits die Zustimmung erteilt wurde. Wenn Sie beispielsweise Apps von Drittanbietern organisationsweit deaktivieren oder bestimmte Apps blockieren, um zu verhindern, dass Teambesitzer ihre Zustimmung geben, werden durch diese Änderungen nicht bereits gewährte Datenzugriffe entfernt.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Die Einstellung "Drittanbieter-Apps zulassen" in den organisationsweiten App-Einstellungen

Diese organisationsweite App-Einstellung steuert, ob Benutzer in Ihrer Organisation Apps von Drittanbietern verwenden können. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung erteilen können. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Teams Apps** Apps verwalten , und klicken Sie dann auf  >   **Organisationsweite App-Einstellungen**.
2. Deaktivieren **oder aktivieren Sie unter Apps** von Drittanbietern die App Von Drittanbietern **zulassen.**

    ![Screenshot der Einstellung "Drittanbieter-Apps in Teams zulassen"](media/resource-specific-consent-org-wide-setting.png)

Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Zulassen oder Blockieren der App auf Organisationsebene

Wenn Sie eine App auf [](manage-apps.md#allow-and-block-apps) der Seite Apps verwalten blockieren oder zulassen, wird diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig. Teambesitzer können einer App nur zustimmen, wenn die App zulässig ist. Gehen Sie wie folgt vor, um eine App auf Organisationsebene zu erlauben oder zu blockieren:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Wählen Sie auf der Seite Apps verwalten  die App aus, und klicken Sie dann auf Blockieren, um sie zu blockieren, oder klicken **Sie** auf Zulassen, um sie zu erlauben.

    ![Screenshot der blockierten Apps in organisationsweiten Einstellungen](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Dem Teambesitzer zugewiesene App-Berechtigungsrichtlinie

Teambesitzer können nur Apps ihre Zustimmung erteilen, dass sie mit ihrer App-Berechtigungsrichtlinie ausgeführt werden dürfen. Gehen Sie wie folgt vor, um die einem Teambesitzer zugewiesene App-Berechtigungsrichtlinie anzeigen und verwalten zu können:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**.
2. Doppelklicken Sie auf den Anzeigenamen des Teambesitzers, und klicken Sie dann auf **Richtlinien**.
3. Die dem Teambesitzer zugewiesene Richtlinie wird unter **App-Berechtigungsrichtlinie aufgeführt.**
    - Wenn Sie eine andere Richtlinie zuweisen möchten, klicken Sie **auf Bearbeiten**, und wählen Sie dann die Richtlinie aus, die Sie zuweisen möchten.
    - Um die Einstellungen der Richtlinie zu bearbeiten, die dem Teambesitzer zugewiesen ist, klicken Sie auf den Namen der Richtlinie, und nehmen Sie dann die von Ihnen vorgenommenen Änderungen vor.  

## <a name="uploading-custom-apps"></a>Hochladen benutzerdefinierter Apps

Wenn Sie eine benutzerdefinierte App (auch Querladen bekannt) hochladen, für die eine ressourcenspezifische Zustimmung verwendet wird, muss die App vom Mandanten stammen, auf dem sie installiert wird. Anders ausgedrückt: Die Registrierung Azure AD App muss von diesem Mandanten sein. Globale Administratoren sind von dieser Einschränkung ausgenommen und können benutzerdefinierte Apps von jedem beliebigen Mandanten hochladen, entweder direkt in ein Team (Querladen) oder in den Mandanten-App-Katalog.

## <a name="related-topics"></a>Verwandte Themen

- [Verfügbare RSC-Berechtigungen](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)