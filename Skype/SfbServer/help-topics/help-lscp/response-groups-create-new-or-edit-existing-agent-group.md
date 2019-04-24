---
title: Reaktionsgruppen Erstellen einer neuen oder Bearbeiten von vorhandenen Agentgruppe
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe entgegennehmen kann (so genannte Agents). Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.
ms.openlocfilehash: 9dbd8a5d758b9d10ae1d992cd85df91bee19988a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200611"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Reaktionsgruppen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Agentgruppe

Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe entgegennehmen kann (so genannte Agents). Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Jeder Agentengruppe erfordert einen eindeutigen Namen. Verwenden Sie einen beschreibenden Namen, mit dem die Funktion der Gruppe verdeutlicht wird. Beispiel: Helpdesk.

- **Beschreibung** Dieses Feld ist optional. Geben Sie darin zusätzliche Details zur Gruppe an.

- **Beteiligungsrichtlinie für telefonisten** Geben Sie die Möglichkeit, die Agents zum Anmelden bei der reaktionsgruppe sind:

  - Wählen Sie **Informell**, um festzulegen, dass sich die Agents der Gruppe nicht an- und abmelden müssen. Informelle Agents werden bei der Anmeldung automatisch bei der Gruppe angemeldet. Die Standardeinstellung ist **Informell**.

  - Wählen Sie **formelle** um anzugeben, dass die Agents in der Gruppe an-und Abmelden Abmelden müssen. Wenn Sie diese Option auswählen, klicken Sie auf Agents ein Menüelement im-Client auf einen Browser öffnen und Anzeigen von einer Webseite-Konsole für die an-und Abmelden.

- **Agentwarnungszeit (Sekunden)** Geben Sie die Anzahl der Sekunden einen Agent angeboten werden soll, bevor der Anruf dem nächsten verfügbaren Vertreter angeboten. Die Spanne der möglichen Werte reicht von 10 bis weniger als 180 Sekunden. Die Standardeinstellung ist „20 Sekunden“.

- **Routingmethode** Wählen Sie die Methode für die Bestimmung der Reihenfolge, in der Agents Anrufe erhalten:

  - Wählen Sie **Längster Leerlauf**, um den Anruf dem Agent mit der längsten Leerlaufzeit (Anwesenheitsstatus **Verfügbar** oder **Inaktiv**) anzubieten.

  - Wählen Sie **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der ihn annimmt.

  - Wählen Sie **Roundrobin**, um einen neuen Anruf den einzelnen Agents nacheinander anzubieten.

  - Wählen Sie **Seriell**, um einen neuen Anruf den Agents immer in der Reihenfolge anzubieten, in der sie auf der Registerkarte **Agent** aufgeführt sind.

  - Wählen Sie **Attendant** , um einen neuen Anruf den alle Support-Mitarbeiter, die angemeldet sind und die Anwendung "Reaktionsgruppe" unabhängig von der aktuellen Anwesenheit gleichzeitig anzubieten. Um-Telefonzentralen und Clientbenutzer, die konfiguriert werden, wie Agents alle Anrufe sehen können, die darauf warten, und warten Anrufe in beliebiger Reihenfolge beantworten können. Der Anruf wird an den ersten Agent übergeben, der den Anruf annimmt, und den weiteren Attendants und Benutzern nicht mehr angezeigt.

- **Agents** Wählen Sie die Benutzer-Agents für die reaktionsgruppe in eine der folgenden Arten sein:

  - Wählen Sie **eine vorhandene e-Mail-Verteilerliste verwenden** , um eine Exchange-Verteilerliste verwenden. Geben Sie die E-Mail-Adresse der Verteilerliste unter **Verteilerlistenadresse** ein.

    > [!NOTE]
    > Sie können für eine Agentgruppe nur eine Verteilerliste auswählen. Falls die Verteilerliste verschachtelte Verteilerlisten enthält, werden die verschachtelten Verteilerlisten nicht in die Agentgruppe einbezogen.

    > [!NOTE]
    > Die Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind, wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.

    > [!NOTE]
    > Verborgene Mitgliedschaften oder Listen möglicherweise für reaktionsgruppenadministratoren oder Benutzer sichtbar werden. Weitere Informationen hierzu finden Sie unter [Erstellen oder Ändern einer agentgruppe in Skype für Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Wählen Sie **Benutzerdefinierte Gruppe von Agents definieren**, um die Benutzer auszuwählen, die Sie als Agents für die Reaktionsgruppe zuweisen möchten. Klicken Sie auf **Auswählen**, um der Liste einen Agent hinzuzufügen. Klicken Sie auf **Entfernen**, um einen ausgewählten Agent aus der Liste zu löschen.

    Mit dem Pfeil nach oben bzw. nach unten können Sie einen ausgewählten Agent in der Liste mit den Agents nach oben oder unten verschieben. Die Reihenfolge der Agents in der Liste wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.

Ausführliche Informationen zu Response Group Features und Funktionen finden Sie unter [Planen für die Anwendung "Reaktionsgruppe" in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Agentgruppen finden Sie in der Betriebsdokumentation unter [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx).


