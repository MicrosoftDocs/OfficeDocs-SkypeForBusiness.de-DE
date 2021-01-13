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
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815675"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Ressourcenspezifische Zustimmung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Mit der ressourcenspezifischen Zustimmung in Microsoft Teams können Teambesitzer Apps die Zustimmung für den Zugriff auf Teamdaten erteilen. Beispiele für einen solchen Zugriff sind das Lesen von Kanalnachrichten, das Erstellen und Löschen von Kanälen sowie das Erstellen und Entfernen von Kanalregisterkarten.

Als Administrator steuern Sie, ob Teambesitzer in Ihrer Organisation mithilfe von Einstellungen, die Sie mithilfe des Azure Active Directory (Azure AD)-PowerShell-Moduls oder des Azure-Portals und des Microsoft Teams Admin Centers konfigurieren, ihre Zustimmung geben können.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Festlegen, ob Teambesitzer Apps die Zustimmung erteilen können

Hier sind die Einstellungen, die Sie festlegen müssen, um zu steuern, ob Teambesitzer Apps die Zustimmung erteilen können. Überprüfen Sie unbedingt alle folgenden Einstellungen.

### <a name="settings-in-azure-ad"></a>Einstellungen in Azure AD

Die folgenden beiden Einstellungen bestimmen, ob Teambesitzer Apps die Zustimmung erteilen können.

> [!IMPORTANT]
> Eine Änderung dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, für die bereits die Zustimmung erteilt wurde. Wenn Sie diese Einstellungen beispielsweise so konfigurieren, dass Teambesitzer nicht ihre Zustimmung erteilen, wird durch diese Änderungen kein bereits gewährter Datenzugriff entfernt.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Die Einstellung "Benutzer können Apps zustimmen, die auf Unternehmensdaten in ihrem Auftrag zugreifen"

Diese Einstellung steuert, ob Benutzer in Ihrer Organisation Apps in ihrem Namen zustimmen können. Damit Teambesitzer ihre Zustimmung geben können, muss diese Einstellung auf "Ja" **festgelegt sein.** Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Wechseln Sie im Azure-Portal zu **"Unternehmensanwendungen" unter**  >  **"Benutzereinstellungen".**
2. Legen **Sie unter "Unternehmensanwendungen"** die Zustimmung für apps, die auf Unternehmensdaten **in** ihrem Namen zugreifen, mit **"Nein"** oder "Ja" **sicher.**

Sie können diese Einstellung auch mithilfe von PowerShell verwalten. Weitere Informationen finden Sie unter ["Konfigurieren von Benutzerinhalten für Anwendungen".](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>Die Einstellung "EnableGroupSpecificConsent"

Diese Einstellung steuert, ob Benutzer in Ihrer Organisation Apps zustimmen können, die auf Unternehmensdaten für die Gruppen zugreifen, die sie besitzen. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung erteilen können. Schritte zum Verwalten dieser Einstellung mithilfe von PowerShell finden Sie unter "Konfigurieren der Zustimmung des Gruppenbesitzers für Apps, [die auf Gruppendaten zugreifen".](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Einstellungen im Microsoft Teams Admin Center

Zusätzlich zu den Einstellungen in Azure AD bestimmen [](manage-apps.md) organisationsweite App-Einstellungen auf der Seite [](manage-apps.md#allow-and-block-apps) "Apps verwalten", ob eine App auf der Seite "Apps verwalten" blockiert oder zulässig ist, und die dem Teambesitzer zugewiesene [App-Berechtigungsrichtlinie,](manage-apps.md#manage-org-wide-app-settings) ob ein Teambesitzer seine Zustimmung geben kann. [](teams-app-permission-policies.md)

> [!IMPORTANT]
> Eine Änderung dieser Einstellungen wirkt sich nicht auf den Datenzugriff für Apps aus, für die bereits die Zustimmung erteilt wurde. Wenn Sie beispielsweise Apps von Drittanbietern organisationsweit deaktivieren oder bestimmte Apps blockieren, um die Zustimmung von Teambesitzern zu verhindern, wird durch diese Änderungen kein bereits gewährter Datenzugriff entfernt.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Einstellung "Apps von Drittanbietern zulassen" in den organisationsweiten App-Einstellungen

Diese organisationsweite Einstellung für Apps steuert, ob Benutzer in Ihrer Organisation Apps von Drittanbietern verwenden können. Diese Einstellung muss aktiviert sein, damit Teambesitzer ihre Zustimmung erteilen können. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps** verwalten", und klicken Sie dann auf  >   **"Organisationsweite App-Einstellungen".**
2. Deaktivieren **oder aktivieren Sie unter "Apps** von Drittanbietern" die "Apps von Drittanbietern **zulassen".**

    ![Screenshot der Einstellung "Apps von Drittanbietern in Teams zulassen"](media/resource-specific-consent-org-wide-setting.png)

Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Zulassen oder Blockieren der App auf Organisationsebene

Wenn Sie eine App auf [](manage-apps.md#allow-and-block-apps) der Seite "Apps verwalten" blockieren oder zulassen, ist diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig. Teambesitzer können einer App nur zustimmen, wenn die App zulässig ist. Gehen Sie wie folgt vor, um eine App auf Organisationsebene zu erlauben oder zu blockieren:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Wählen Sie auf der Seite "Apps verwalten" die App aus, und klicken Sie dann auf "Blockieren", um sie zu blockieren, oder klicken Sie auf **"Zulassen",** um sie zu erlauben. 

    ![Screenshot der blockierten Apps in den organisationsweiten Einstellungen](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Dem Teambesitzer zugewiesene App-Berechtigungsrichtlinie

Teambesitzer können Apps nur zustimmen, dass sie mit ihrer Berechtigungsrichtlinie für Apps ausgeführt werden dürfen. Gehen Sie wie folgt vor, um die einem Teambesitzer zugewiesene Berechtigungsrichtlinie für die App anzeigen und verwalten zu können:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Benutzer".**
2. Doppelklicken Sie auf den Anzeigenamen des Teambesitzers, und klicken Sie dann auf **"Richtlinien".**
3. Die dem Teambesitzer zugewiesene Richtlinie wird unter **"App-Berechtigungsrichtlinie" aufgeführt.**
    - Wenn Sie eine andere Richtlinie zuweisen möchten, klicken Sie auf "Bearbeiten", und wählen Sie dann die Richtlinie aus, die Sie zuweisen möchten.
    - Um die Einstellungen der Richtlinie zu bearbeiten, die dem Teambesitzer zugewiesen ist, klicken Sie auf den Namen der Richtlinie, und nehmen Sie dann die von Ihnen vorgenommenen Änderungen vor.  

## <a name="uploading-custom-apps"></a>Hochladen benutzerdefinierter Apps

Beim Hochladen einer benutzerdefinierten App (auch als Querladen bezeichnet), für die eine ressourcenspezifische Zustimmung verwendet wird, muss die App vom Mandanten stammen, auf dem sie installiert wird. Mit anderen Worten: Die Azure AD-App-Registrierung muss von diesem Mandanten kommen. Globale Administratoren sind von dieser Einschränkung ausgenommen und können benutzerdefinierte Apps von jedem beliebigen Mandanten hochladen, entweder direkt in ein Team (Querladen) oder in den Mandanten-App-Katalog.

## <a name="related-topics"></a>Verwandte Themen

- [Verfügbare RsC-Berechtigungen](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
