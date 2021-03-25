---
title: Ressourcenspezifische Zustimmung in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die Einstellungen, die Sie konfigurieren müssen, um zu steuern, ob Teambesitzer in Ihrer Organisation Apps zustimmen können.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7b9379db7760fa8ef03440c24b93cb0223b4bee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117623"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Ressourcenspezifische Zustimmung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Mit der ressourcenspezifischen Zustimmung in Microsoft Teams können Teambesitzer Apps die Zustimmung zum Zugriff auf Teamdaten erteilen. Beispiele für diesen Zugriff sind die Möglichkeit, Kanalnachrichten zu lesen, Kanäle zu erstellen und zu löschen sowie Kanalregisterkarten zu erstellen und zu entfernen.

Als Administrator steuern Sie, ob Teambesitzer in Ihrer Organisation ihre Zustimmung über Einstellungen erteilen können, die Sie mithilfe des Azure Active Directory (Azure AD)-PowerShell-Moduls oder des Azure-Portals und des Microsoft Teams Admin Centers konfigurieren.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Festlegen, ob Teambesitzer Apps zustimmen können

Hier sind die Einstellungen, die Sie festlegen müssen, um zu steuern, ob Teambesitzer Apps zustimmen können. Überprüfen Sie unbedingt alle folgenden Einstellungen.

### <a name="settings-in-azure-ad"></a>Einstellungen in Azure AD

Die folgenden beiden Einstellungen bestimmen, ob Teambesitzer Apps zustimmen können.

> [!IMPORTANT]
> Das Ändern dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, für die bereits die Zustimmung erteilt wurde. Wenn Sie diese Einstellungen beispielsweise so konfigurieren, dass Teambesitzer die Zustimmung nicht erteilen können, werden durch diese Änderungen keine Datenzugriffe entfernt, die bereits gewährt wurden.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Die Einstellung "Benutzer können zustimmen, dass Apps auf Unternehmensdaten in ihrem Auftrag zugreifen"

Mit dieser Einstellung wird bestimmt, ob Benutzer in Ihrer Organisation Apps in ihrem Auftrag zustimmen können. Damit Teambesitzer ihre Zustimmung erteilen können, muss diese Einstellung auf Ja **festgelegt sein.** Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Wechseln Sie im Azure-Portal zu **Unternehmensanwendungen**  >  **Benutzereinstellungen**.
2. Legen **Sie unter Unternehmensanwendungen** den Satz **Benutzer können** auf Apps, die in ihrem Auftrag auf Unternehmensdaten zugreifen, auf **Nein** oder **Ja festgelegt.**

Sie können diese Einstellung auch mithilfe von PowerShell verwalten. Weitere Informationen finden Sie unter [Konfigurieren von Benutzerinhalten für Anwendungen.](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>Die Einstellung "EnableGroupSpecificConsent"

Mit dieser Einstellung wird bestimmt, ob Benutzer in Ihrer Organisation den Apps zustimmen können, die auf Unternehmensdaten für die Gruppen zugreifen, die sie besitzen. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung erteilen können. Schritte zum Verwalten dieser Einstellung mithilfe von PowerShell finden Sie unter Konfigurieren der Zustimmung des Gruppenbesitzers für Apps, [die auf Gruppendaten zugreifen.](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Einstellungen im Microsoft Teams Admin Center

Zusätzlich zu den Einstellungen in Azure AD bestimmen organisationsweite App-Einstellungen auf der Seite [](manage-apps.md#allow-and-block-apps) Apps verwalten, [](teams-app-permission-policies.md) ob eine App auf der Seite Apps verwalten blockiert oder zulässig ist, und die dem Teambesitzer zugewiesene [App-Berechtigungsrichtlinie](manage-apps.md#manage-org-wide-app-settings) bestimmt, ob ein Teambesitzer die Zustimmung erteilen kann. [](manage-apps.md)

> [!IMPORTANT]
> Das Ändern dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, für die bereits die Zustimmung erteilt wurde. Wenn Sie z. B. Apps von Drittanbietern organisationsweit deaktivieren oder bestimmte Apps blockieren, um zu verhindern, dass Teambesitzer ihre Zustimmung erteilen, werden durch diese Änderungen keine Datenzugriffe entfernt, die bereits gewährt wurden.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Einstellung "Apps von Drittanbietern zulassen" in organisationsweiten App-Einstellungen

Diese organisationsweite App-Einstellung steuert, ob Benutzer in Ihrer Organisation Apps von Drittanbietern verwenden können. Diese Einstellung muss aktiviert sein, damit Teambesitzer die Zustimmung erteilen können. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams-Apps** Apps verwalten, und klicken Sie dann  >  auf **Organisationsweite App-Einstellungen.**
2. Deaktivieren oder aktivieren Sie **unter Apps** von Drittanbietern die App **"Apps von Drittanbietern zulassen".**

    ![Screenshot der Einstellung "Apps von Drittanbietern in Teams zulassen"](media/resource-specific-consent-org-wide-setting.png)

Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Zulassen oder Blockieren der App auf Organisationsebene

Wenn Sie eine App auf [](manage-apps.md#allow-and-block-apps) der Seite Apps verwalten blockieren oder zulassen, ist diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig. Teambesitzer können einer App nur zustimmen, wenn die App zulässig ist. Gehen Sie wie folgt vor, um eine App auf Organisationsebene zu erlauben oder zu blockieren:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Wählen Sie auf der Seite Apps verwalten die App aus, und klicken Sie dann auf **Blockieren,** um sie zu blockieren, oder klicken Sie auf **Zulassen,** um sie zu erlauben.

    ![Screenshot der blockierten Apps in organisationsweiten Einstellungen](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Dem Teambesitzer zugewiesene App-Berechtigungsrichtlinie

Teambesitzer können Apps nur zustimmen, dass sie mit ihrer App-Berechtigungsrichtlinie ausgeführt werden können. Gehen Sie wie folgt vor, um die Einem Teambesitzer zugewiesene App-Berechtigungsrichtlinie ein- und zu verwalten:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**.
2. Doppelklicken Sie auf den Anzeigenamen des Teambesitzers, und klicken Sie dann auf **Richtlinien.**
3. Die dem Teambesitzer zugewiesene Richtlinie wird unter **App-Berechtigungsrichtlinie aufgeführt.**
    - Wenn Sie eine andere Richtlinie zuweisen möchten, klicken Sie **auf Bearbeiten**, und wählen Sie dann die Richtlinie aus, die Sie zuweisen möchten.
    - Wenn Sie die Einstellungen der Richtlinie bearbeiten möchten, die dem Teambesitzer zugewiesen ist, klicken Sie auf den Richtliniennamen, und nehmen Sie dann die von Ihnen vorgenommenen Änderungen vor.  

## <a name="uploading-custom-apps"></a>Hochladen benutzerdefinierter Apps

Beim Hochladen einer benutzerdefinierten App (auch als Querladen bezeichnet), die eine ressourcenspezifische Zustimmung verwendet, muss die App aus dem Mandanten stammen, in dem sie installiert wird. Anders ausgedrückt: Die Azure AD-App-Registrierung muss von diesem Mandanten kommen. Globale Administratoren sind von dieser Einschränkung ausgenommen und können benutzerdefinierte Apps aus jedem Mandanten hochladen, entweder direkt in ein Team (Querladen) oder in den Katalog der Mandanten-App.

## <a name="related-topics"></a>Verwandte Themen

- [Verfügbare RSC-Berechtigungen](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)