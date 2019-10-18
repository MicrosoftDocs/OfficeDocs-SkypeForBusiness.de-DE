---
title: Anrufrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Erfahren Sie mehr über die Anruf Richtlinieneinstellungen in Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-voice
f1keywords:
- ms.teamsadmincenter.callingpolicies.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 788cc0e93b16585f1d3424d3bfa0a62693528740
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570270"
---
<a name="calling-policies-in-microsoft-teams"></a>Anrufrichtlinien in Microsoft Teams
===================================

In Microsoft Teams Steuern Anruf Richtlinien, welche Anruf-und Anrufweiterleitungsfunktionen Benutzern zur Verfügung stehen. Anruf Richtlinien legen fest, ob ein Benutzer private Anrufe tätigen, Anrufweiterleitung oder gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern durchführen, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, die Delegation für ein-und ausgehende Anrufe verwenden usw. Eine globale Standardrichtlinie wird automatisch erstellt, aber Administratoren können auch benutzerdefinierte Anruf Richtlinien erstellen und zuweisen.

## <a name="create-a-custom-calling-policy"></a>Erstellen einer benutzerdefinierten Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.

1. Wählen Sie im Microsoft Teams Admin Center die Option **VoIP** > -**Anrufrichtlinie**aus.
2. Wählen Sie **neue Richtlinie**aus.
3. Aktivieren Sie die Features, die Sie in ihrer Anrufrichtlinie verwenden möchten. Standardmäßig sind alle Auswahlen **deaktiviert** .
4. Wenn Sie steuern möchten, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **immer aktiviert** oder **Benutzer gesteuert**aus. Wenn Sie die Weiterleitung an Voicemail verhindern möchten, wählen Sie **immer deaktiviert**aus.
5. Wählen Sie **Speichern**aus.

## <a name="modify-an-existing-calling-policy"></a>Ändern einer vorhandenen Anrufrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu ändern.

1. Wählen Sie im Microsoft Teams Admin Center die Option **VoIP** > -**Anrufrichtlinie**aus.
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, auf, und wählen Sie dann **Bearbeiten**aus.
3. Aktivieren Sie die Features, die Sie in ihrer Anrufrichtlinie verwenden möchten. Standardmäßig sind alle Auswahlen **deaktiviert** .
4. Wenn Sie steuern möchten, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **immer aktiviert** oder **Benutzer gesteuert**aus. Wenn Sie die Weiterleitung an Voicemail verhindern möchten, wählen Sie **immer deaktiviert**aus.
5. Wählen Sie **Speichern**aus.

## <a name="assign-a-calling-policy-to-a-user"></a>Zuweisen einer Anrufrichtlinie zu einem Benutzer

Führen Sie die folgenden Schritte aus, um einem Benutzer eine benutzerdefinierte Anrufrichtlinie zuzuweisen.

1. Wählen Sie im Microsoft Teams Admin Center die Option **VoIP** > -**Anrufrichtlinie**aus.
2. Klicken Sie neben dem Richtliniennamen auf, um ihn auszuwählen, und wählen Sie dann **Benutzer verwalten**aus.
3. Suchen Sie im Bereich **Benutzer verwalten** nach dem Namen des Benutzers. (Sie müssen mindestens drei Zeichen eingeben.)
4. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann **Hinzufügen**aus.
5. Wählen Sie **Speichern**aus.

## <a name="calling-policy-settings"></a>Einstellungen für Anruf Richtlinien

Verwenden Sie die folgenden Einstellungen, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.

### <a name="user-can-make-private-calls"></a>Der Benutzer kann private Anrufe tätigen

Mit dieser Einstellung werden alle Anruffunktionen in Teams gesteuert. Deaktivieren Sie diese Option, um alle Anruffunktionen in Teams zu deaktivieren.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Anrufweiterleitung und gleichzeitiges Klingeln an andere Benutzer

Mit dieser Einstellung wird gesteuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können oder dass Sie eine andere Person gleichzeitig anrufen können. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Anrufweiterleitung und gleichzeitiges Klingeln an externe Telefonnummern

Diese Einstellung steuert, ob eingehende Anrufe an eine externe Rufnummer weitergeleitet werden können oder gleichzeitig eine externe Rufnummer anrufen können.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>Voicemail steht zum Weiterleiten von eingehenden Anrufen an Benutzer zur Verfügung.

Mit dieser Einstellung können eingehende Anrufe an Voicemail gesendet werden. Gültige Optionen sind:

   - **Immer aktiviert** Voicemail steht für eingehende Anrufe immer zur Verfügung. 
   - **Immer deaktiviert**  Voicemail steht für eingehende Anrufe nicht zur Verfügung. 
   - **Benutzer gesteuert**. Benutzer können feststellen, ob Voicemail verfügbar sein soll.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Eingehende Anrufe können an Anrufgruppen weitergeleitet werden 

> [!Include [feature preview](includes/preview-feature.md)]

Diese Einstellung steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Zulassen der Delegierung für eingehende und ausgehende Anrufe

> [!Include [feature preview](includes/preview-feature.md)]

Mit dieser Einstellung können eingehende Anrufe an Stellvertretungen weitergeleitet werden, sodass Stellvertretungen im Namen der Benutzer, für die Sie Berechtigungen delegiert haben, ausgehende Anrufe tätigen können. Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Vermeidung von Maut Umgehung und Senden von Anrufen über das PSTN 

Wenn Sie diese Einstellung **aktivieren** , werden Anrufe über das PSTN durchgeführt, und es fallen Gebühren an, anstatt Sie über das Netzwerk zu senden und die Mautgebühren zu umgehen.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Busy on Busy steht während eines Anrufs zur Verfügung

Busy on Busy (busy-Optionen)) ist eine neue Einstellung in Teams, die Richtlinien aufrufen, mit denen Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in Wartestellung gesetzt wurde. Neue oder eingehende Anrufe können mit einem Besetztzeichen zurückgewiesen werden. Sie können die Auslastungs Optionen auf Mandantenebene oder auf Benutzerebene aktivieren. Unabhängig davon, wie Ihre besetzt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder Personen mit einem Anruf in Wartestellung nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. Diese Einstellung ist standardmäßig deaktiviert.

## <a name="see-also"></a>Siehe auch

[Satz-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)