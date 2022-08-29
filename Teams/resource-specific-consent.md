---
title: Ressourcenspezifische Zustimmung in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die Einstellungen, die Sie konfigurieren müssen, um zu steuern, ob Teambesitzer in Ihrer Organisation ihre Zustimmung Apps erteilen können.
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb96b6130ce87d8d1453f6ea4ee40af2bb84050d
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396466"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Ressourcenspezifische Zustimmung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Mit der ressourcenspezifischen Zustimmung in Microsoft Teams können Teambesitzer Apps ihre Zustimmung zum Zugriff auf Teamdaten erteilen. Beispiele für diesen Zugriff sind die Möglichkeit, Kanalnachrichten zu lesen, Kanäle zu erstellen und zu löschen sowie Kanalregisterkarten zu erstellen und zu entfernen.

Als Administrator steuern Sie, ob Teambesitzer in Ihrer Organisation ihre Zustimmung über Einstellungen erteilen können, die Sie mithilfe des PowerShell-Moduls von Azure Active Directory (Azure AD) oder das Azure-Portal und das Microsoft Teams Admin Center konfigurieren.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Festlegen, ob Teambesitzer Apps ihre Zustimmung erteilen können

Dies sind die Einstellungen, die Sie festlegen müssen, um zu steuern, ob Teambesitzer Apps ihre Zustimmung erteilen können. Überprüfen Sie unbedingt alle der folgenden Einstellungen.

### <a name="settings-in-azure-active-directory-portal"></a>Einstellungen im Azure Active Directory-Portal

Die folgenden beiden Einstellungen bestimmen, ob Teambesitzer Apps ihre Zustimmung erteilen können.

> [!IMPORTANT]
> Das Ändern dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, denen bereits die Zustimmung erteilt wurde. Wenn Sie diese Einstellungen beispielsweise so konfigurieren, dass Teambesitzer ihre Zustimmung nicht geben können, wird durch diese Änderungen der bereits gewährte Datenzugriff nicht entfernt.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Die Einstellung „Benutzer können Anwendungen zustimmen, die in ihrem Namen auf Firmendaten zugreifen“

Diese Einstellung steuert, ob Benutzer in Ihrer Organisation Apps in ihrem Namen zustimmen können. Damit Teambesitzer ihre Zustimmung erteilen können, muss diese Einstellung auf **Ja** festgelegt werden. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Wechseln Sie im Azure-Portal zu **Unternehmensanwendungen** > **Benutzereinstellungen**.
2. Legen Sie unter **Unternehmensanwendungen** die Einstellung **Benutzer können Anwendungen zustimmen, die in ihrem Namen auf Firmendaten zugreifen** auf **Nein** oder **Ja** fest.

Sie können diese Einstellung auch mithilfe von PowerShell verwalten. Weitere Informationen finden Sie unter [Konfigurieren von Benutzerinhalten in Anwendungen](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Die Einstellung „EnableGroupSpecificConsent“

Diese Einstellung steuert, ob Benutzer in Ihrer Organisation Apps die Zustimmung erteilen können, die für die Gruppen, deren Besitzer sie sind, auf Unternehmensdaten zugreifen. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung geben können. Schritte zum Verwalten dieser Einstellung mithilfe von PowerShell finden Sie unter [Konfigurieren der Zustimmung des Gruppenbesitzers für Apps, die auf Gruppendaten zugreifen](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Einstellungen im Microsoft Teams Admin Center

Zusätzlich zu den Einstellungen in Azure AD, bestimmen [organisationsweite App-Einstellungen](manage-apps.md#manage-org-wide-app-settings) auf der Seite [Apps verwalten](manage-apps.md), ob eine App auf der Seite [Apps verwalten](manage-apps.md#allow-and-block-apps) blockiert oder zugelassen wird, und die [App-Berechtigungsrichtlinie](teams-app-permission-policies.md), die dem Teambesitzer zugewiesen ist, bestimmt, ob ein Teambesitzer seine Zustimmung erteilen kann.

> [!IMPORTANT]
> Das Ändern dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, denen bereits die Zustimmung erteilt wurde. Wenn Sie beispielsweise Drittanbieter-Apps organisationsweit deaktivieren oder bestimmte Apps blockieren, um zu verhindern, dass Teambesitzer ihre Zustimmung geben, wird durch diese Änderungen der bereits gewährte Datenzugriff nicht entfernt.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Die Einstellung „Drittanbieter-Apps zulassen“ in organisationsweiten App-Einstellungen

Diese organisationsweite App-Einstellung steuert, ob Benutzer in Ihrer Organisation Drittanbieter-Apps verwenden können. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung geben können. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Wählen Sie **organisationsweite App-Einstellungen** und unter **Drittanbieter-Apps** die Option " **Apps von Drittanbietern zulassen**" aus, oder aktivieren Sie sie.

    ![Screenshot der Einstellung „Drittanbieter-Apps in Teams zulassen“](media/resource-specific-consent-org-wide-setting.png)

Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Zulassen oder Blockieren der App auf Organisationsebene

Wenn Sie eine App auf der Seite [Apps verwalten](manage-apps.md#allow-and-block-apps) blockieren oder zulassen, wird diese App für alle Benutzer in Ihrer Organisation blockiert bzw. zugelassen. Teambesitzer können einer App nur Zustimmung erteilen, wenn die App zulässig ist. Gehen Sie wie folgt vor, um eine App auf Organisationsebene zuzulassen oder zu blockieren:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Wählen Sie auf der Seite "Apps verwalten" die App aus, und wählen Sie dann " **Blockieren** " aus, um sie zu blockieren, oder wählen Sie **"Zulassen** " aus, um sie zuzulassen.

    ![Screenshot der blockierten Apps in organisationsweiten Einstellungen](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>App-Berechtigungsrichtlinie, die dem Teambesitzer zugewiesen ist

Teambesitzer können nur Apps Zustimmung erteilen, die sie gemäß ihrer App-Berechtigungsrichtlinie ausführen können. Gehen Sie wie folgt vor, um die App-Berechtigungsrichtlinie anzuzeigen und zu verwalten, die einem Teambesitzer zugewiesen ist:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**.
1. Doppelklicken Sie auf den Anzeigenamen des Teambesitzers, und wählen Sie dann **"Richtlinien"** aus.
1. Die dem Teambesitzer zugewiesene Richtlinie wird unter **App-Berechtigungsrichtlinie** aufgeführt.
    - Wenn Sie eine andere Richtlinie zuweisen möchten, wählen Sie **"Bearbeiten"** und dann die Richtlinie aus, die Sie zuweisen möchten.
    - Um die Einstellungen der Richtlinie zu bearbeiten, die dem Teambesitzer zugewiesen ist, wählen Sie den Richtliniennamen aus, und nehmen Sie dann die gewünschten Änderungen vor.  

## <a name="upload-custom-apps"></a>Hochladen benutzerdefinierter Apps

Beim Hochladen einer benutzerdefinierten App (wird auch als Querladen bezeichnet), die die ressourcenspezifische Zustimmung nutzt, muss die App von dem Mandanten stammen, auf dem sie installiert wird. Anders ausgedrückt: Die Azure AD-App-Registrierung muss von diesem Mandanten stammen. Globale Administratoren sind von dieser Einschränkung ausgenommen und können benutzerdefinierte Apps von jedem Mandanten hochladen, entweder direkt für ein Team (Querladen) oder in den Mandanten-App-Katalog.

## <a name="related-articles"></a>Verwandte Artikel

- [Verfügbare RSC-Berechtigungen](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Verwalten Sie Ihre Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
