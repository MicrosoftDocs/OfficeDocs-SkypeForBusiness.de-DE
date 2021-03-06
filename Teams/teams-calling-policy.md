---
title: Anrufrichtlinien in Microsoft Teams
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
ms.openlocfilehash: 6cfa0043b4da6c3087c0e144bb0759ed5b87f01c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50465298"
---
<a name="calling-policies-in-microsoft-teams"></a>Anrufrichtlinien in Microsoft Teams
===================================

In Microsoft Teams steuern Anrufrichtlinien, welche Anruf- und Anruf weiterleitungsfeatures für Benutzer verfügbar sind. Anrufrichtlinien legen fest, ob ein Benutzer private Anrufe, Anrufanrufe oder gleichzeitiges Anrufen an andere Benutzer oder externe Telefonnummern, Weiterleiten von Anrufen an Voicemail, Senden von Anrufen an Anrufgruppen, Verwenden der Delegierung für eingehende und ausgehende Anrufe und so weiter ausführen kann.

Sie können die globale (organisationsweite Standardrichtlinie) verwenden, die automatisch erstellt wird, oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="create-a-custom-calling-policy"></a>Erstellen einer benutzerdefinierten Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu  >  **Sprachanrufrichtlinien.**
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie die Features, die Sie in Ihrer Anrufrichtlinie verwenden möchten.
4. Um zu steuern, ob Benutzer eingehende Anrufe an voicemail weiterleiten können, wählen Sie **Aktiviert** oder **Benutzergesteuert aus.** Um das Routing zu Voicemail zu verhindern, wählen Sie **Deaktiviert aus.**
5. Klicken Sie auf **Speichern**.

## <a name="edit-a-calling-policy"></a>Bearbeiten einer Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu bearbeiten.

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers die Option **Voice calling**  >  **policies aus.**
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, und wählen Sie dann **Bearbeiten aus.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Anrufrichtlinieneinstellungen

Hier sind die Einstellungen, die Sie für das Aufrufen von Richtlinien konfigurieren können.

### <a name="make-private-calls"></a>Private Anrufe führen

Diese Einstellung steuert alle Anruffunktionen in Teams. Deaktivieren Sie diese Funktion, um alle Anruffunktionen in Teams zu deaktivieren.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Anruf weiterleitung und gleichzeitiges Anrufen an Personen in Ihrer Organisation

Mit dieser Einstellung wird bestimmt, ob eingehende Anrufe an andere Benutzer weitergeleitet oder gleichzeitig an eine andere Person weitergeleitet werden können. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Anruf weiterleitung und gleichzeitiges Klingeln an externe Telefonnummern

Mit dieser Einstellung wird bestimmt, ob eingehende Anrufe an eine externe Rufnummer weitergeleitet werden oder gleichzeitig an eine externe Nummer weitergeleitet werden können.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>Voicemail ist für die Weiterleitung eingehender Anrufe verfügbar.

Mit dieser Einstellung können eingehende Anrufe an die Voicemail gesendet werden. Gültige Optionen sind:

- **Aktiviert** Voicemail ist immer für eingehende Anrufe verfügbar.
- **Deaktiviert**  Voicemail ist für eingehende Anrufe nicht verfügbar.
- **Vom Benutzer gesteuert** Benutzer können bestimmen, ob Voicemail verfügbar sein soll.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Eingehende Anrufe können an Anrufgruppen geroutet werden 

Diese Einstellung steuert, ob eingehende Anrufe an eine Anrufgruppe weitergeleitet werden können.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Zulassen der Delegierung für eingehende und ausgehende Anrufe

Mit dieser Einstellung können eingehende Anrufe an Stellvertretungsteilnehmer weiter geroutet werden, sodass Stellvertretung ausgehende Anrufe im Auftrag der Benutzer, für die sie delegierte Berechtigungen besitzen, erstellen können. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung für eine Stellvertretung.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Verhindern der Umgehung der Gebühren und Senden von Anrufen über das PSTN 

Wenn Sie dies **auf Ein** festlegen, werden Anrufe über das PSTN gesendet, und es fallen Gebühren an, anstatt sie über das Netzwerk zu senden und die Gebühren zu umgehen.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Beschäftigt ist während eines Anrufs verfügbar

Beschäftigt bei Beschäftigt (Beschäftigt-Optionen) ist eine neue Einstellung, mit der Sie konfigurieren können, wie eingehende Anrufe behandelt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf im Halteraum platziert wird. Neue oder eingehende Anrufe können mit einem gebuchten Signal abgelehnt werden. Sie können Beschäftigt-Optionen auf Mandantenebene oder auf Benutzerebene aktivieren. Unabhängig davon, wie ihre Gebucht-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder personen, die einen Anruf im Halteraum haben, nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. Diese Einstellung ist standardmäßig deaktiviert.

### <a name="allow-web-pstn-calling"></a>Zulassen von Web-PSTN-Anrufen

Diese Einstellung ermöglicht benutzern das Aufrufen von PSTN-Nummern über den Teams-Webclient.

### <a name="allow-music-on-hold"></a>Musik im Halteraum zulassen

Mit dieser Einstellung können Sie Musik im Halteraum aktivieren oder deaktivieren, wenn ein PSTN-Anrufer in den Halteraum gesetzt wird. Sie ist standardmäßig aktiviert. Diese Einstellung gilt nicht für Funktionen für Anrufpark- und Bossstellvertretung und steht derzeit nur über PowerShell zur Verfügung.

## <a name="related-topics"></a>Verwandte Themen

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
