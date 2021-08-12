---
title: 'Anrufrichtlinien in Microsoft Teams: Anruf- und Anrufweiterleitungsfunktionen'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Benutzer zu benutzerdefinierten Anrufrichtlinien in Microsoft Teams sowie zu verschiedenen Anrufrichtlinieneinstellungen erstellen, ändern und hinzufügen.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e38a566e025c711a9b17a050137e67af7507e63d5c5e829ba4448ee4a1577790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309244"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>Anrufe und Anrufweiterleitung in Teams

Die Anrufrichtlinien in Microsoft Teams steuern, welche Anruf- und Anrufweiterleitungsfunktionen den Benutzern zur Verfügung stehen. Anrufrichtlinien bestimmen, ob ein Benutzer private Anrufe tätigen, anrufweiterleitung oder gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern verwenden kann, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, Delegierung für eingehende und ausgehende Anrufe verwenden kann usw.

Sie können die globale (organisationsweite Standard)-Richtlinie verwenden, die automatisch erstellt wird, oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="create-a-custom-calling-policy"></a>Erstellen einer benutzerdefinierten Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den   >  **VoIP-Richtlinien.**
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie die Funktionen, die Sie in Ihrer Anrufrichtlinie verwenden möchten.
4. Um zu steuern, ob Benutzer eingehende Anrufe an Voicemail umleiten können, wählen Sie **Aktiviert** oder **Benutzergesteuert** aus. Um das Routing zu Voicemails zu verhindern, wählen Sie **Deaktiviert** aus.
5. Wählen Sie **Speichern** aus.

## <a name="edit-a-calling-policy"></a>Bearbeiten einer Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu bearbeiten.

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers   >  **VoIP-Richtlinien** aus.
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, und wählen Sie dann **Bearbeiten** aus.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **"Speichern".**

## <a name="assign-a-custom-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufrichtlinie einem Benutzer

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Einstellungen für Anrufrichtlinien

Hier sind die Einstellungen, die Sie für Anrufrichtlinien konfigurieren können.

### <a name="make-private-calls"></a>Private Anrufe führen

Diese Einstellung steuert alle Anruffunktionen in Teams. Deaktivieren Sie diese Funktion, um alle Anruffunktionen in Teams zu deaktivieren.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Rufumleitung und gleichzeitiges Anrufen von Personen in Ihrer Organisation

Diese Einstellung steuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können oder gleichzeitig eine andere Person anrufen können. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Rufumleitung und gleichzeitiges Anrufen von externen Telefonnummern

Diese Einstellung steuert, ob eingehende Anrufe an eine externe Nummer weitergeleitet werden können oder gleichzeitig eine externe Nummer klingeln können.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>Voicemail ist für die Weiterleitung eingehender Anrufe verfügbar

Mit dieser Einstellung können eingehende Anrufe an Voicemail gesendet werden. Gültige Optionen sind:

- **Aktiviert** Voicemail ist für eingehende Anrufe immer verfügbar.
- **Deaktiviert**  Voicemail ist für eingehende Anrufe nicht verfügbar.
- **Benutzergesteuert** Benutzer können ermitteln, ob Voicemail verfügbar sein soll.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Eingehende Anrufe können an Rufgruppen weitergeleitet werden

Diese Einstellung steuert, ob eingehende Anrufe an eine Anrufgruppe weitergeleitet werden können.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegierung für eingehende und ausgehende Anrufe

Mit dieser Einstellung können eingehende Anrufe an Stellvertretungen weitergeleitet werden, sodass Stellvertretungen ausgehende Anrufe im Namen der Benutzer tätigen können, für die sie delegierte Berechtigungen haben. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung mit einem Delegaten.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Verhindern der Gebührenumgehung und Senden von Anrufen durch das PSTN 

Wenn Sie diese Einstellung auf **"Ein"** festlegen, werden Anrufe über das Festnetz gesendet, und es fallen Gebühren an, anstatt sie über das Netzwerk zu senden und die Gebühren zu umgehen.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>Beschäftigt bei Gebucht ist verfügbar, wenn in einem Anruf

Mit beschäftigt beschäftigt (Beschäftigt-Optionen) können Sie konfigurieren, wie eingehende Anrufe verarbeitet werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder einen Anruf gehalten hat. Neue oder eingehende Anrufe können mit einem Besetzt-Signal abgelehnt oder entsprechend an die unbeantworteten Einstellungen des Benutzers weitergeleitet werden. Sie können Beschäftigt-Optionen auf Mandantenebene oder auf Benutzerebene aktivieren. Unabhängig davon, wie ihre Beschäftigt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder personen mit einer Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. Diese Einstellung ist standardmäßig deaktiviert.

### <a name="web-pstn-calling"></a>Pstn-Webanrufe

Mit dieser Einstellung können Benutzer PSTN-Nummern über den Teams-Webclient anrufen.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Eingehende Besprechungseinladungen werden automatisch beantwortet.

Diese Einstellung steuert, ob eingehende Besprechungseinladungen automatisch beantwortet werden. Sie ist standardmäßig deaktiviert. Beachten Sie, dass diese Einstellung nur für eingehende Besprechungseinladungen gilt. Sie gilt nicht für andere Arten von Anrufen.

### <a name="allow-music-on-hold"></a>Wartemusik beim Halten zulassen

Mit dieser Einstellung können Sie die Wartemusik aktivieren oder deaktivieren, wenn ein PSTN-Anrufer gehalten wird. Das ist standardmäßig aktiviert. Diese Einstellung gilt nicht für Funktionen zum Parken von Anrufen und zum Stellvertretungsdelegieren und ist derzeit nur über PowerShell verfügbar.

## <a name="related-articles"></a>Verwandte Artikel

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
