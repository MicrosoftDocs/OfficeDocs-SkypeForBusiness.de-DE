---
title: 'Anrufrichtlinien in Microsoft Teams: Anruf- und Anrufweiterleitungsfeatures'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie benutzerdefinierte Anrufrichtlinien in Microsoft Teams sowie verschiedene Anrufrichtlinieneinstellungen erstellen, ändern und hinzufügen.
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
ms.openlocfilehash: 5097586825b231decd220a30bdde85bf258e27fc
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2022
ms.locfileid: "65313107"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Anruf- und Anrufweiterleitung in Teams

In Microsoft Teams steuern Anrufrichtlinien, welche Anruf- und Anrufweiterleitungsfeatures benutzern zur Verfügung stehen. Anrufrichtlinien bestimmen, ob ein Benutzer private Anrufe tätigen, Anrufweiterleitung oder gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern verwenden, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, Delegierung für eingehende und ausgehende Anrufe verwenden kann usw.

Sie können die globale Richtlinie (organisationsweite Standardrichtlinie), die automatisch erstellt wird, verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="create-a-custom-calling-policy"></a>Erstellen einer benutzerdefinierten Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **VoiceCalling-Richtlinien** > .
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie die Features, die Sie in Ihrer Anrufrichtlinie verwenden möchten.
4. Um zu steuern, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **"Aktiviert"** oder " **Benutzergesteuert" aus**. Um das Routing an Voicemail zu verhindern, wählen Sie **"Deaktiviert"** aus.
5. Klicken Sie auf **Speichern**.

## <a name="edit-a-calling-policy"></a>Bearbeiten einer Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu bearbeiten.

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center **VoiceCalling-Richtlinien** >  aus.
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, und wählen Sie dann **"Bearbeiten"** aus.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **"Speichern"**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Anrufrichtlinieneinstellungen

Hier sind die Einstellungen, die Sie für Anrufrichtlinien konfigurieren können.

### <a name="make-private-calls"></a>Private Anrufe führen

Diese Einstellung steuert alle Anruffunktionen in Teams. Deaktivieren Sie diese Option, um alle Anruffunktionen in Teams zu deaktivieren.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Anrufweiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation

Diese Einstellung steuert, ob eingehende Anrufe an andere Benutzer weitergeleitet oder gleichzeitig an eine andere Person weitergeleitet werden können.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Anrufweiterleitung und gleichzeitiges Klingeln an externen Telefonnummern

Mit dieser Einstellung wird gesteuert, ob eingehende Anrufe gleichzeitig an eine externe Nummer weitergeleitet oder an eine externe Rufnummer weitergeleitet werden können.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>Voicemail ist für das Routing eingehender Anrufe verfügbar.

Diese Einstellung ermöglicht das Senden eingehender Anrufe an Voicemail. Gültige Optionen sind:

- **Aktiviert** Voicemail ist immer für eingehende Anrufe verfügbar.
- **Deaktiviert**  Voicemail ist für eingehende Anrufe nicht verfügbar.
- **Benutzergesteuert** Benutzer können bestimmen, ob Voicemail verfügbar sein soll.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Eingehende Anrufe können an Anrufgruppen weitergeleitet werden.

Diese Einstellung steuert, ob eingehende Anrufe an eine Anrufgruppe weitergeleitet werden können.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegierung für eingehende und ausgehende Anrufe

Diese Einstellung ermöglicht das Weiterleiten eingehender Anrufe an Stellvertretungen, sodass Stellvertretungen ausgehende Anrufe im Namen der Benutzer tätigen können, für die sie über delegierte Berechtigungen verfügen. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung für einen Stellvertreter](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Verhindern der gebührenpflichtigen Umgehung und Senden von Anrufen über das PSTN

Wenn Sie diese Einstellung auf **"Ein** " festlegen, werden Anrufe über das PSTN gesendet, und es fallen Gebühren an, anstatt sie über das Netzwerk zu senden und die Gebühren zu umgehen.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>"Beschäftigt bei Beschäftigt" ist verfügbar, wenn ein Anruf ausgeführt wird.

Mit "Beschäftigt bei Beschäftigt" (Beschäftigt-Optionen) können Sie konfigurieren, wie eingehende Anrufe behandelt werden, wenn sich ein Benutzer bereits an einem Anruf oder einer Konferenz befindet oder ein Anruf gehalten wird. Neue oder eingehende Anrufe können mit einem besetzten Signal abgelehnt oder entsprechend an die unbeantworteten Einstellungen des Benutzers weitergeleitet werden. Sie können Beschäftigt-Optionen auf Mandantenebene oder auf Benutzerebene aktivieren. Unabhängig davon, wie ihre Beschäftigt-Optionen konfiguriert sind, sind Benutzer in einer Telefonkonferenz oder in der Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. Diese Einstellung ist standardmäßig deaktiviert.

### <a name="web-pstn-calling"></a>Web-PSTN-Anrufe

Mit dieser Einstellung können Benutzer PSTN-Nummern mithilfe des Teams-Webclients aufrufen.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Eingehende Besprechungseinladungen werden automatisch beantwortet.

Diese Einstellung steuert, ob eingehende Besprechungseinladungen automatisch beantwortet werden. Diese Option ist standardmäßig deaktiviert. Beachten Sie, dass diese Einstellung nur für eingehende Besprechungseinladungen gilt. Sie gilt nicht für andere Arten von Anrufen.

### <a name="allow-music-on-hold"></a>Wartemusik zulassen

Mit dieser Einstellung können Sie die Wartemusik aktivieren oder deaktivieren, wenn ein PSTN-Anrufer in den Haltebereich gesetzt wird. Sie ist standardmäßig aktiviert. Diese Einstellung gilt nicht für Funktionen zum Parken von Anrufen und Chefstellvertretungen.

### <a name="allow-sip-devices-calling"></a>Sip-Geräteanrufe zulassen

Mit dieser Einstellung können Benutzer ein SIP-Gerät verwenden, um Anrufe zu tätigen und zu empfangen.

### <a name="spam-filtering"></a>Spamfilterung

Mit dieser Einstellung können Sie die Art der Spamfilterung steuern, die bei eingehenden Anrufen verfügbar ist.

### <a name="call-recording-live-captions-and-transcription"></a>Anrufaufzeichnung, Liveuntertitel und Transkription

Mit diesen Einstellungen können Sie steuern, ob Anrufaufzeichnung, Liveuntertitel und Transkription für die Benutzer verfügbar sind.

## <a name="related-articles"></a>Verwandte Artikel

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
