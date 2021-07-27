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
description: Erfahren Sie, wie Sie benutzerdefinierte Anrufrichtlinien in Microsoft Teams sowie verschiedene Anrufrichtlinieneinstellungen erstellen, ändern und hinzufügen.
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
ms.openlocfilehash: f4502d76bbb2e12f38ba79d0848ecd06739417cc
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2021
ms.locfileid: "53596641"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>Anrufen und Weiterleiten von Anrufen in Teams

In Microsoft Teams steuern Anrufrichtlinien, welche Anruf- und Anruf weiterleitungsfunktionen für Benutzer verfügbar sind. Anrufrichtlinien bestimmen, ob ein Benutzer private Anrufe ausführen, Anrufanrufe oder gleichzeitiges Anrufen an andere Benutzer oder externe Telefonnummern verwenden, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, Delegierung für ein- und ausgehende Anrufe verwenden kann und so weiter.

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

1. Wählen Sie in der linken Navigationsleiste Microsoft Teams Admin Center Die **Richtlinien für Sprachanrufe**  >  **aus.**
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, und wählen Sie dann **Bearbeiten aus.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Einstellungen für Die Anrufrichtlinie

Dies sind die Einstellungen, die Sie für Aufrufrichtlinien konfigurieren können.

### <a name="make-private-calls"></a>Private Anrufe führen

Diese Einstellung steuert alle Aufruffunktionen in Teams. Deaktivieren Sie diese Funktion, um alle Anruffunktionen in ihrer Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Anruf weiterleiten und gleichzeitiges Klingeln an Personen in Ihrer Organisation

Mit dieser Einstellung wird kontrolliert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können oder ob sie eine andere Person gleichzeitig anrufen können. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Anruf weiterleiten und gleichzeitiges Klingeln an externe Telefonnummern

Mit dieser Einstellung wird kontrolliert, ob eingehende Anrufe an eine externe Nummer weitergeleitet werden können oder ob sie gleichzeitig an eine externe Nummer weitergeleitet werden können.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>Voicemail steht für eingehende Anrufe im Routing zur Verfügung.

Mit dieser Einstellung können eingehende Anrufe an die Voicemail gesendet werden. Gültige Optionen sind:

- **Aktiviert** Voicemail ist für eingehende Anrufe immer verfügbar.
- **Deaktiviert**  Voicemail ist für eingehende Anrufe nicht verfügbar.
- **Vom Benutzer gesteuert** Benutzer können bestimmen, ob Voicemail verfügbar sein soll.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Eingehende Anrufe können an Anrufgruppen geroutet werden 

Diese Einstellung steuert, ob eingehende Anrufe an eine Anrufgruppe weitergeleitet werden können.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Delegierung für ein- und ausgehende Anrufe zulassen

Mit dieser Einstellung können eingehende Anrufe an Stellvertretung geroutet werden, sodass Stellvertretung ausgehende Anrufe im Auftrag der Benutzer, für die sie delegierte Berechtigungen haben, abgehen können. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung für eine Stellvertretung.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Verhindern einer gebührenpflichtigen Umgehung und Senden von Anrufen über das PSTN 

Wenn Sie diese Einstellung **auf Ein** festlegen, werden Anrufe über das PSTN gesendet, und es fallen Gebühren an, statt sie über das Netzwerk zu senden und die Gebühren zu umgehen.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>"Beschäftigt" ist während eines Anrufs verfügbar

Beschäftigt bei Beschäftigt (Beschäftigt-Optionen) ist eine neue Einstellung, mit der Sie konfigurieren können, wie eingehende Anrufe verarbeitet werden, wenn ein Benutzer bereits in einem Anruf oder einer Konferenz ist oder ein Anruf in der Warteschleife platziert wird. Neue oder eingehende Anrufe können mit einem Beschäftigt-Signal abgelehnt oder entsprechend den Einstellungen des Benutzers geroutet werden, die nicht beantwortet werden. Sie können Beschäftigt-Optionen auf Mandantenebene oder Benutzerebene aktivieren. Unabhängig davon, wie ihre Beschäftigt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder benutzer mit einem haltenden Anruf nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. Diese Einstellung ist standardmäßig deaktiviert.

### <a name="allow-web-pstn-calling"></a>Zulassen von Anrufen über das Festnetz (Web PSTN)

Mit dieser Einstellung können Benutzer PSTN-Nummern über den Teams anrufen.

### <a name="allow-music-on-hold"></a>Halten von Musik zulassen

Mit dieser Einstellung können Sie die Wartemusik aktivieren oder deaktivieren, wenn ein PSTN-Anrufer in den Halteraum gesetzt wird. Sie ist standardmäßig aktiviert. Diese Einstellung gilt nicht für Anruf parken und Chefstellvertretungsfunktionen und ist derzeit nur über PowerShell verfügbar.

## <a name="related-topics"></a>Verwandte Themen

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
