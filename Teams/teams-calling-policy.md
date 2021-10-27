---
title: 'Anrufrichtlinien in Microsoft Teams: Anruf- und Anruf weiterleitungsfeatures'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie benutzerdefinierte Anrufrichtlinien in Microsoft Teams sowie verschiedene Anrufrichtlinieneinstellungen erstellen, ändern und hinzufügen.
ms.localizationpriority: medium
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
ms.openlocfilehash: 16749fa21176622bdd68bcd2034eb94c99773f9e
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596898"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Anrufen und Weiterleiten von Anrufen in Teams

In Microsoft Teams steuern Anrufrichtlinien, welche Anruf- und Anruf weiterleitungsfunktionen benutzern zur Verfügung stehen. Anrufrichtlinien bestimmen, ob ein Benutzer private Anrufe ausführen, Anrufanrufe oder gleichzeitiges Anrufen an andere Benutzer oder externe Telefonnummern verwenden, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, Delegierung für ein- und ausgehende Anrufe verwenden kann und so weiter.

Sie können die globale (organisationsweite Standardrichtlinie) verwenden, die automatisch erstellt wird, oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="create-a-custom-calling-policy"></a>Erstellen einer benutzerdefinierten Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Richtlinien für Sprachanrufe**  >  .
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie die Features, die Sie in Ihrer Anrufrichtlinie verwenden möchten.
4. Um zu steuern, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **Aktiviert** oder **Benutzergesteuert aus.** Um das Routing an Voicemail zu verhindern, wählen Sie **Deaktiviert aus.**
5. Klicken Sie auf **Speichern**.

## <a name="edit-a-calling-policy"></a>Bearbeiten einer Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu bearbeiten.

1. Wählen Sie in der linken Navigationsleiste Microsoft Teams Admin Center Die **Richtlinien für**  >  **Sprachanrufe aus.**
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, und wählen Sie dann **Bearbeiten aus.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Einstellungen für Die Anrufrichtlinie

Dies sind die Einstellungen, die Sie für Anrufrichtlinien konfigurieren können.

### <a name="make-private-calls"></a>Private Anrufe führen

Diese Einstellung steuert alle Aufruffunktionen in Teams. Deaktivieren Sie dies, um alle Anruffunktionen in der Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Anruf weiterleiten und gleichzeitiges Klingeln an Personen in Ihrer Organisation

Mit dieser Einstellung wird kontrolliert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können oder ob sie eine andere Person gleichzeitig anrufen können.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Anruf weiterleitung und gleichzeitiges Anrufen an externe Telefonnummern

Mit dieser Einstellung wird kontrolliert, ob eingehende Anrufe an eine externe Nummer weitergeleitet werden können oder ob sie gleichzeitig an eine externe Nummer weitergeleitet werden können.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>Voicemail ist für eingehende Anrufe im Routing verfügbar.

Mit dieser Einstellung können eingehende Anrufe an die Voicemail gesendet werden. Gültige Optionen sind:

- **Aktiviert** Voicemail ist für eingehende Anrufe immer verfügbar.
- **Deaktiviert**  Voicemail ist für eingehende Anrufe nicht verfügbar.
- **Vom Benutzer gesteuert** Benutzer können bestimmen, ob Voicemail verfügbar sein soll.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Eingehende Anrufe können an Anrufgruppen geroutet werden

Diese Einstellung steuert, ob eingehende Anrufe an eine Anrufgruppe weitergeleitet werden können.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegierung für ein- und ausgehende Anrufe

Mit dieser Einstellung können eingehende Anrufe an Stellvertretung geroutet werden, sodass Stellvertretung ausgehende Anrufe im Auftrag der Benutzer, für die sie delegierte Berechtigungen haben, abgehen können. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung für eine Stellvertretung.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Verhindern einer gebührenpflichtigen Umgehung und Senden von Anrufen über das PSTN 

Wenn Sie diese Einstellung **auf Ein** festlegen, werden Anrufe über das PSTN gesendet, und es fallen Gebühren an, statt sie über das Netzwerk zu senden und die Gebühren zu umgehen.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>"Beschäftigt" ist während eines Anrufs verfügbar

Unter Beschäftigt (Beschäftigt-Optionen) können Sie konfigurieren, wie eingehende Anrufe verarbeitet werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf im Halteraum platziert wird. Neue oder eingehende Anrufe können mit einem Beschäftigt-Signal abgelehnt oder entsprechend den Einstellungen des Benutzers geroutet werden, die nicht beantwortet werden. Sie können Beschäftigt-Optionen auf Mandantenebene oder Benutzerebene aktivieren. Unabhängig davon, wie ihre Beschäftigt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder benutzer mit einem haltenden Anruf nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. Diese Einstellung ist standardmäßig deaktiviert.

### <a name="web-pstn-calling"></a>Anrufe über das Web-PSTN

Mit dieser Einstellung können Benutzer PSTN-Nummern über den Teams Anrufen anrufen.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Eingehende Besprechungs-Einladungen werden automatisch beantwortet.

Diese Einstellung steuert, ob eingehende Besprechungs-Einladungen automatisch beantwortet werden. Diese Option ist standardmäßig deaktiviert. Beachten Sie, dass diese Einstellung nur für eingehende Besprechungs-Einladungen gilt. Sie gelten nicht für andere Arten von Anrufen.

### <a name="allow-music-on-hold"></a>Halten von Musik zulassen

Mit dieser Einstellung können Sie die wartemusik ein- oder ausschalten, wenn ein PSTN-Anrufer in den Halteraum gesetzt wird. Sie ist standardmäßig aktiviert. Diese Einstellung gilt nicht für Anruf parken und Chefstellvertretungsfunktionen und ist derzeit nur über PowerShell verfügbar.

## <a name="related-articles"></a>Verwandte Artikel

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
