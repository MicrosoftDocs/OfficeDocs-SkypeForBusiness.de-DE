---
title: Anrufrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Informationen Sie zu Richtlinieneinstellungen in der Microsoft-Teams aufrufen.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 007bea10d8e452a2198c869ab545592b29c591c1
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632369"
---
<a name="calling-policies-in-microsoft-teams"></a>Anrufrichtlinien in Microsoft Teams
===================================

In Microsoft-Teams Richtlinien-Steuerelements aufrufen, denen der Aufruf und Features für die anrufweiterleitung für Benutzer verfügbar sind. Aufrufen von Standortrichtlinien wird bestimmt, ob ein Benutzer private aufgerufen werden kann, verwenden Sie die anrufweiterleitung oder Gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern, Weiterleitung von Anrufen an Voicemail, senden Anrufe an Gruppen aufrufen Delegierung für eingehende und ausgehende Anrufe, und so weiter. Eine globale Standardrichtlinie wird automatisch erstellt, aber Administratoren können auch benutzerdefinierte aufrufende Richtlinien zuweisen.

## <a name="create-a-custom-calling-policy"></a>Erstellen Sie eine benutzerdefinierte Richtlinie an aufrufende

Befolgen Sie diese Schritte, um eine benutzerdefinierte aufrufende Richtlinie erstellen.

1. Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.
2. Wählen Sie **neue Richtlinie**aus.
3. Aktivieren Sie die Features, die Sie in der aufrufenden Richtlinie verwenden möchten. Alle ausgewählten Optionen sind standardmäßig **deaktiviert** .
4. Um zu steuern, ob Benutzer eingehende Anrufe an die Voicemail weitergeleitet werden können, wählen Sie **immer aktiviert** , oder **Benutzer gesteuert**. Um zu verhindern, an die Voicemail-routing, wählen Sie **immer deaktiviert**.
5. Wählen Sie **Speichern**aus.

## <a name="modify-an-existing-calling-policy"></a>Ändern einer vorhandenen Richtlinie aufrufen

Befolgen Sie diese Schritte zum Ändern einer vorhandenen Richtlinie aufrufen.

1. Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.
2. Klicken Sie neben der Richtlinie, die Sie ändern, und wählen Sie **Bearbeiten**möchten.
3. Aktivieren Sie die Features, die Sie in der aufrufenden Richtlinie verwenden möchten. Alle ausgewählten Optionen sind standardmäßig **deaktiviert** .
4. Um zu steuern, ob Benutzer eingehende Anrufe an die Voicemail weitergeleitet werden können, wählen Sie **immer aktiviert** , oder **Benutzer gesteuert**. Um zu verhindern, an die Voicemail-routing, wählen Sie **immer deaktiviert**.
5. Wählen Sie **Speichern**aus.

## <a name="assign-a-calling-policy-to-a-user"></a>Zuweisen einer Richtlinie für aufrufenden zu einem Benutzer

Befolgen Sie diese Schritte, um eine benutzerdefinierte Richtlinie an aufrufen, die einem Benutzer zuweisen.

1. Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.
2. Klicken Sie neben den Namen der Richtlinie, wählen Sie sie aus, und wählen Sie dann auf **Benutzer verwalten**.
3. Suchen Sie nach den Namen des Benutzers, klicken Sie im Bereich **Benutzer verwalten** . (Sie müssen mindestens drei Zeichen eingeben.)
4. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann auf **Hinzufügen**.
5. Wählen Sie **Speichern**aus.

## <a name="calling-policy-settings"></a>Aufrufen von Richtlinieneinstellungen

Verwenden Sie die folgenden Einstellungen, um eine benutzerdefinierte aufrufende Richtlinie erstellen.

### <a name="user-can-make-private-calls"></a>Benutzer kann private Anrufe tätigen.

Diese Einstellung steuert alle aufrufende Funktionen in Teams. Deaktivieren Sie diese Option deaktivieren alle Anruffunktionen in Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Die anrufweiterleitung und Gleichzeitiges Klingeln an andere Benutzer

Diese Einstellung steuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können, oder eine andere Person gleichzeitig anrufen können. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Die anrufweiterleitung und Gleichzeitiges Klingeln an externe Telefonnummern

Diese Einstellung steuert, ob eingehende Anrufe an eine externe Nummer weitergeleitet werden können, oder eine externe Nummer gleichzeitig anrufen können.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>Voicemail wird für eingehende Anrufe an die Benutzer verfügbar

Diese Einstellung aktiviert eingehende Anrufe an die Voicemail gesendet werden. Gültige Optionen sind:

   - **Immer aktiviert** Voicemail ist immer für eingehende Anrufe verfügbar. 
   - **Immer deaktiviert**  Voicemail ist nicht verfügbar für eingehende Anrufe. 
   - **Benutzer gesteuert**. Benutzer können bestimmen, ob sie Voicemail verfügbar sein sollen.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Zum Aufrufen von Gruppen können eingehende Anrufe weitergeleitet werden 

Diese Einstellung steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Erlaubt die Delegierung für eingehende und ausgehende Anrufe

Diese Einstellung aktiviert eingehende Anrufe an die Stellvertretungen, Stellvertretungen zu ausgehenden Anrufe im Namen der Benutzer, für den sie Berechtigungen delegiert wurden, zulassen weitergeleitet werden. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung mit einem Delegaten](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Verhindern, dass Gebühren umgehen und senden Sie Anrufe über das Telefonfestnetz 

Durch Festlegen auf **auf** Anrufe über das Telefonfestnetz sendet und Gebühren statt sie über das Netzwerk gesendet werden und umgeht die Gebühren anfallen.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Beschäftigt auf beschäftigt steht während eines Anrufs

Beschäftigt auf beschäftigt (beschäftigt Optionen)) ist, dass eine neue Einstellung in Teams aufrufende Richtlinien, die Sie konfigurieren, wie eingehende Anrufe können behandelt werden, wenn ein Benutzer bereits in einem Anruf oder einer Konferenz oder einen Anruf hat in der Warteschleife platziert. Neue oder eingehende Anrufe können mit einer Besetztzeichen abgelehnt werden. Sie können beschäftigt Optionen auf der Ebene der Mandanten oder auf Benutzerebene aktivieren. Unabhängig davon, wie ihre beschäftigt Optionen konfiguriert werden sind Benutzer in einen Anruf oder Konferenz oder die durch einen Anruf in der Warteschleife nicht verhindert neue anrufen oder Konferenzen initiieren. Diese Einstellung ist standardmäßig deaktiviert.

## <a name="see-also"></a>Siehe auch

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)