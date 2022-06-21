---
title: Ressourcenspezifische Zustimmung in Microsoft Teams
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die Einstellungen, die Sie konfigurieren müssen, um zu steuern, ob Teams-Besitzer in Ihrer Organisation Apps zustimmen können.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5ef3f94c511dfe86ab7b153bfa8dd3ea1a04fa
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190496"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Ressourcenspezifische Zustimmung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Mit der ressourcenspezifischen Zustimmung in Microsoft Teams können Teambesitzer Apps den Zugriff auf Teamdaten zustimmen. Beispiele für diesen Zugriff sind die Möglichkeit, Kanalnachrichten zu lesen, Kanäle zu erstellen und zu löschen sowie Kanalregisterkarten zu erstellen und zu entfernen.

Als Administrator steuern Sie, ob Teambesitzer in Ihrer Organisation ihre Zustimmung über Einstellungen erteilen können, die Sie mithilfe des Azure Active Directory (Azure AD)-PowerShell-Moduls oder des Azure-Portal und des Microsoft Teams Admin Centers konfigurieren.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Festlegen, ob Teambesitzer Apps zustimmen können

Hier sind die Einstellungen, die Sie festlegen müssen, um zu steuern, ob Teambesitzer Apps zustimmen können. Überprüfen Sie unbedingt alle folgenden Einstellungen.

### <a name="settings-in-azure-ad"></a>Einstellungen in Azure AD

Die folgenden beiden Einstellungen bestimmen, ob Teambesitzer Apps zustimmen können.

> [!IMPORTANT]
> Das Ändern einer dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, denen bereits die Zustimmung erteilt wurde. Wenn Sie z. B. diese Einstellungen so konfigurieren, dass Teambesitzer nicht ihre Zustimmung geben, wird durch diese Änderungen der datenzugriff, der bereits gewährt wurde, nicht entfernt.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Die Einstellung "Benutzer können Apps zustimmen, die in ihrem Auftrag auf Unternehmensdaten zugreifen"

Diese Einstellung steuert, ob Benutzer in Ihrer Organisation Apps in ihrem Auftrag zustimmen können. Damit Teambesitzer ihre Zustimmung erteilen können, muss diese Einstellung auf **"Ja**" festgelegt sein. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Wechseln Sie in der Azure-Portal zu **den Benutzereinstellungen Enterprise Anwendungen** > .
2. Legen Sie unter **Enterprise Anwendungen** fest, dass **Benutzer Apps zustimmen können, die in ihrem Namen auf Unternehmensdaten zugreifen**, auf **"Nein**" oder "**Ja**".

Sie können diese Einstellung auch mithilfe von PowerShell verwalten. Weitere Informationen finden Sie unter [Konfigurieren von Benutzerinhalten für Anwendungen](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Die Einstellung "EnableGroupSpecificConsent"

Diese Einstellung steuert, ob Benutzer in Ihrer Organisation Apps zustimmen können, die auf Unternehmensdaten für die Gruppen zugreifen können, die sie besitzen. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung geben können. Schritte zum Verwalten dieser Einstellung mithilfe von PowerShell finden Sie unter [Konfigurieren der Zustimmung des Gruppenbesitzers für Apps, die auf Gruppendaten zugreifen](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Einstellungen im Microsoft Teams Admin Center

Zusätzlich zu den Einstellungen in Azure AD bestimmen [organisationsweite App-Einstellungen](manage-apps.md#manage-org-wide-app-settings) auf der Seite " [Apps verwalten](manage-apps.md) ", ob eine App auf der Seite " [Apps verwalten](manage-apps.md#allow-and-block-apps) " blockiert oder zulässig ist, und die [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) , die dem Teambesitzer zugewiesen ist, ob ein Teambesitzer seine Zustimmung erteilen kann.

> [!IMPORTANT]
> Das Ändern einer dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, denen bereits die Zustimmung erteilt wurde. Wenn Sie beispielsweise Apps von Drittanbietern organisationsweit deaktivieren oder bestimmte Apps blockieren, um zu verhindern, dass Teambesitzer ihre Zustimmung geben, entfernen diese Änderungen keinen Datenzugriff, der bereits gewährt wurde.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Die Einstellung "Apps von Drittanbietern zulassen" in organisationsweiten App-Einstellungen

Diese organisationsweite App-Einstellung steuert, ob Benutzer in Ihrer Organisation Apps von Drittanbietern verwenden können. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung geben können. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **Teams Apps** > **verwalten**, und klicken Sie dann auf **Organisationsweite App-Einstellungen**.
2. Deaktivieren oder aktivieren Sie unter **Drittanbieter-Apps** **"Apps von Drittanbietern zulassen**".

    ![Screenshot der Einstellung "Apps von Drittanbietern in Teams zulassen"](media/resource-specific-consent-org-wide-setting.png)

Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Zulassen oder Blockieren der App auf Organisationsebene

Wenn Sie eine App auf der Seite " [Apps verwalten"](manage-apps.md#allow-and-block-apps) blockieren oder zulassen, ist diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig. Teambesitzer können einer App nur zustimmen, wenn die App zulässig ist. Gehen Sie wie folgt vor, um eine App auf Organisationsebene zuzulassen oder zu blockieren:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Wählen Sie auf der Seite "Apps verwalten" die App aus, und klicken Sie dann auf **"Blockieren** ", um sie zu blockieren, oder klicken Sie auf **"Zulassen** ", um sie zuzulassen.

    ![Screenshot der blockierten Apps in organisationsweiten Einstellungen.](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>App-Berechtigungsrichtlinie, die dem Teambesitzer zugewiesen ist

Teambesitzer können Apps nur zustimmen, dass ihre App-Berechtigungsrichtlinie die Ausführung zulässt. Gehen Sie wie folgt vor, um die App-Berechtigungsrichtlinie anzuzeigen und zu verwalten, die einem Teambesitzer zugewiesen ist:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**.
2. Doppelklicken Sie auf den Anzeigenamen des Teambesitzers, und klicken Sie dann auf **"Richtlinien"**.
3. Die dem Teambesitzer zugewiesene Richtlinie wird unter der **App-Berechtigungsrichtlinie** aufgeführt.
    - Um eine andere Richtlinie zuzuweisen, klicken Sie auf **"Bearbeiten"**, und wählen Sie dann die Richtlinie aus, die Sie zuweisen möchten.
    - Um die Einstellungen der Richtlinie zu bearbeiten, die dem Teambesitzer zugewiesen ist, klicken Sie auf den Richtliniennamen, und nehmen Sie dann die gewünschten Änderungen vor.  

## <a name="uploading-custom-apps"></a>Hochladen benutzerdefinierter Apps

Beim Hochladen einer benutzerdefinierten App (auch als Querladen bezeichnet), die ressourcenspezifische Zustimmung verwendet, muss die App vom Mandanten stammen, auf dem sie installiert wird. Mit anderen Worten, die Azure AD-App-Registrierung muss von diesem Mandanten stammen. Globale Administratoren sind von dieser Einschränkung ausgenommen und können benutzerdefinierte Apps von jedem Mandanten hochladen, entweder direkt in ein Team (Querladen) oder in den Mandanten-App-Katalog.

## <a name="related-topics"></a>Verwandte Themen

- [Verfügbare RSC-Berechtigungen](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
