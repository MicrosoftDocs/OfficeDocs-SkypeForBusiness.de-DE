---
title: Aufrufen von Richtlinien in der Microsoft-Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/15/2019
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
ms.openlocfilehash: 20dc75dfeb39fbd7a00e6c389dc923617265cc0b
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869806"
---
<a name="calling-policies-in-microsoft-teams"></a>Aufrufen von Richtlinien in der Microsoft-Teams
==========================================

In Microsoft-Teams Richtlinien-Steuerelements aufrufen, denen der Aufruf und Features für die anrufweiterleitung für Benutzer verfügbar sind. Aufrufen von Standortrichtlinien wird bestimmt, ob ein Benutzer private aufgerufen werden kann, verwenden Sie die anrufweiterleitung oder Gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern, Weiterleitung von Anrufen an Voicemail, senden Anrufe an Gruppen aufrufen Delegierung für eingehende und ausgehende Anrufe, und so weiter. Eine globale Standardrichtlinie wird automatisch erstellt, aber Administratoren können auch benutzerdefinierte aufrufende Richtlinien zuweisen.

## <a name="calling-policy-settings"></a>Aufrufen von Richtlinieneinstellungen

|Aufrufen der richtlinieneinstellung | Beschreibung |
|-----------------------|-------------|
|Benutzer kann private Anrufe tätigen. | Steuert alle aufrufende Funktionen in Teams. Deaktivieren Dies wird alle Anruffunktionen in Teams deaktiviert.|
|Die anrufweiterleitung und Gleichzeitiges Klingeln an andere Benutzer | Steuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden kann oder eine andere Person gleichzeitig Anrufen kann. |
|Die anrufweiterleitung und Gleichzeitiges Klingeln an externe Telefonnummern | Steuert, ob eingehende Anrufe an eine externe Nummer weitergeleitet werden kann, oder eine externe Nummer gleichzeitig Anrufen kann.|
|Voicemail wird für eingehende Anrufe an die Benutzer verfügbar | Ermöglicht die eingehende Anrufe an die Voicemail gesendet werden. Gültige Optionen sind **immer aktiviert**, **immer deaktiviert**oder **Benutzer gesteuert**. |
|Zum Aufrufen von Gruppen können eingehende Anrufe weitergeleitet werden | Steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.  |
|Erlaubt die Delegierung für eingehende und ausgehende Anrufe | Ermöglicht die eingehende Anrufe an die Stellvertretungen weitergeleitet werden sollen; ermöglicht die Stellvertretungen zu ausgehenden Anrufe im Namen der Benutzer, für den sie Berechtigungen delegiert wurden. |
|Verhindern, dass Gebühren umgehen und senden Sie Anrufe über das Telefonfestnetz | Durch Festlegen dieser auf **aktiviert** wird, sendet Anrufe über PSTN und Gebühren für statt über das Netzwerk laufen und umgeht die Gebühren anfallen. |
|Beschäftigt auf beschäftigt ist während eines Anrufs verfügbar.| Konfiguriert, wie eingehende Anrufe verarbeitet werden, wenn ein Benutzer bereits in einem Anruf oder einer Konferenz ist. Neue oder eingehende Anrufe können mit einer Besetztzeichen abgelehnt werden. |

### <a name="busy-options-busy-on-busy-setting"></a>Gebucht-Optionen (beschäftigt auf beschäftigt Einstellung)

Halten Sie eine neue Einstellung in Teams aufrufende Richtlinien, die Sie Konfigurieren eingehender Anrufe können behandelt werden, wenn ein Benutzer bereits eines Anrufs oder einer Konferenz oder auf ein Anruf platziert wird beschäftigt Optionen angezeigt. Neue oder eingehende Anrufe können mit einer Besetztzeichen abgelehnt werden. Sie können auf einer Ebene Mandanten oder auf der Benutzerebene beschäftigt Optionen aktivieren. 

Unabhängig davon, wie ihre beschäftigt Optionen konfiguriert werden sind Benutzer in einen Anruf oder Konferenz oder die durch einen Anruf in der Warteschleife nicht verhindert neue anrufen oder Konferenzen initiieren.

Die beschäftigt können auf beschäftigt Einstellung in den Aufruf von Richtlinieneinstellungen Sie stark ausgelastet Optionen konfigurieren. Diese Einstellung ist standardmäßig deaktiviert.

## <a name="create-a-custom-calling-policy"></a>Erstellen Sie eine benutzerdefinierte Richtlinie an aufrufende

Befolgen Sie diese Schritte, um eine neue benutzerdefinierte aufrufende Richtlinie erstellen.

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
