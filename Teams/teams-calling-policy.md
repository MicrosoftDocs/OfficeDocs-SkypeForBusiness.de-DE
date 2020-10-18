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
description: Informationen zum Erstellen, ändern und Hinzufügen von Benutzern zu benutzerdefinierten Anruf Richtlinien in Microsoft Teams sowie zu verschiedenen Anruf Richtlinieneinstellungen.
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
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581096"
---
<a name="calling-policies-in-microsoft-teams"></a>Anrufrichtlinien in Microsoft Teams
===================================

In Microsoft Teams Steuern Anruf Richtlinien, welche Anruf-und Anrufweiterleitungsfunktionen Benutzern zur Verfügung stehen. Anruf Richtlinien legen fest, ob ein Benutzer private Anrufe tätigen, Anrufweiterleitung oder gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern durchführen, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, die Delegation für ein-und ausgehende Anrufe verwenden usw.

Sie können die Global (org-Wide Standard)-Richtlinie verwenden, die automatisch erstellt wird, oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="create-a-custom-calling-policy"></a>Erstellen einer benutzerdefinierten Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Anruf Richtlinien**.
2. Wählen Sie **Hinzufügen**aus.
3. Aktivieren oder deaktivieren Sie die Features, die Sie in ihrer Anrufrichtlinie verwenden möchten.
4. Wenn Sie steuern möchten, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **aktiviert** oder **Benutzer gesteuert**aus. Wenn Sie die Weiterleitung an Voicemail verhindern möchten, wählen Sie **deaktiviert**aus.
5. Wählen Sie **Speichern**aus.

## <a name="edit-a-calling-policy"></a>Bearbeiten einer Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu bearbeiten.

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers die Option **VoIP**-  >  **Anruf Richtlinien**aus.
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, auf, und wählen Sie dann **Bearbeiten**aus.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Einstellungen für Anruf Richtlinien

Hier sind die Einstellungen, die Sie für Anruf Richtlinien konfigurieren können.

### <a name="make-private-calls"></a>Private Anrufe führen

Mit dieser Einstellung werden alle Anruffunktionen in Teams gesteuert. Deaktivieren Sie diese Option, um alle Anruffunktionen in Teams zu deaktivieren.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Anrufweiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation

Mit dieser Einstellung wird gesteuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können oder dass Sie eine andere Person gleichzeitig anrufen können. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Anrufweiterleitung und gleichzeitiges Klingeln an externe Telefonnummern

Diese Einstellung steuert, ob eingehende Anrufe an eine externe Rufnummer weitergeleitet werden können oder gleichzeitig eine externe Rufnummer anrufen können.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>Voicemail steht zum Weiterleiten von eingehenden Anrufen zur Verfügung

Mit dieser Einstellung können eingehende Anrufe an Voicemail gesendet werden. Gültige Optionen sind:

- **Aktiviert** Voicemail steht für eingehende Anrufe immer zur Verfügung.
- **Deaktiviert**  Voicemail steht für eingehende Anrufe nicht zur Verfügung.
- **Benutzer gesteuert** Benutzer können feststellen, ob Voicemail verfügbar sein soll.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Eingehende Anrufe können an Anrufgruppen weitergeleitet werden 

> [!Include [feature preview](includes/preview-feature.md)]

Diese Einstellung steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Zulassen der Delegierung für eingehende und ausgehende Anrufe

> [!Include [feature preview](includes/preview-feature.md)]

Mit dieser Einstellung können eingehende Anrufe an Stellvertretungen weitergeleitet werden, sodass Stellvertretungen im Namen der Benutzer, für die Sie Berechtigungen delegiert haben, ausgehende Anrufe tätigen können. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Vermeidung von Maut Umgehung und Senden von Anrufen über das PSTN 

Wenn Sie diese Einstellung **aktivieren** , werden Anrufe über das PSTN durchgeführt, und es fallen Gebühren an, anstatt Sie über das Netzwerk zu senden und die Mautgebühren zu umgehen.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Busy on Busy steht während eines Anrufs zur Verfügung

Busy on Busy (busy-Optionen) ist eine neue Einstellung, mit der Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in Wartestellung gesetzt wurde. Neue oder eingehende Anrufe können mit einem Besetztzeichen zurückgewiesen werden. Sie können die Auslastungs Optionen auf Mandantenebene oder auf Benutzerebene aktivieren. Unabhängig davon, wie Ihre besetzt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder Personen mit einem Anruf in Wartestellung nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. Diese Einstellung ist standardmäßig deaktiviert.

### <a name="allow-web-pstn-calling"></a>Zulassen von webpstn-anrufen

Mit dieser Einstellung können Benutzer PSTN-Nummern über den Microsoft Teams-WebClient anrufen.

### <a name="allow-music-on-hold"></a>Musik in Wartestellung zulassen

Mit dieser Einstellung können Sie die Musik im Wartebereich aktivieren oder deaktivieren, wenn ein PSTN-Anrufer in Wartestellung gesetzt wird. Sie ist standardmäßig aktiviert. Diese Einstellung gilt nicht für die Features von Park-und Boss-Stellvertretungen und steht derzeit nur über PowerShell zur Verfügung.

## <a name="related-topics"></a>Verwandte Themen

[Satz-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
