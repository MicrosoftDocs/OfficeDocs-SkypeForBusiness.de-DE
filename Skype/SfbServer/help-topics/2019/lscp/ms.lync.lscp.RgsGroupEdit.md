---
title: Reaktionsgruppen erstellen eine neue oder bearbeiten eine vorhandene Agentgruppe
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe (so genannte Agents) entgegennehmen kann. Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.
ms.openlocfilehash: 95e2cac8f98dd25811b093aee3dbdd3ce8459b7a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599344"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Reaktionsgruppen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppe

Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe (so genannte Agents) entgegennehmen kann. Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Jede Agentgruppe erfordert einen eindeutigen Namen. Verwenden Sie einen beschreibenden Namen, mit dem die Funktion der Gruppe verdeutlicht wird. Beispiel: Helpdesk.

- **Beschreibung** Dieses Feld ist optional. Geben Sie darin zusätzliche Details zur Gruppe an.

- **Teilnahmerichtlinie** Geben Sie an, wie sich Agents bei der Reaktionsgruppe anmelden sollen:

  - Wählen Sie **"Informell"** aus, um anzugeben, dass sich die Agents in der Gruppe nicht anmelden und abmelden müssen. Informelle Agents werden automatisch angemeldet, wenn sie sich anmelden. Die Standardeinstellung ist **Informell**.

  - Wählen Sie **"Formal"** aus, um anzugeben, dass sich die Agents in der Gruppe anmelden und abmelden müssen. Wenn Sie diese Option auswählen, klicken Agents auf ein Menüelement im Client, um einen Browser zu öffnen und eine Webseitenkonsole zum Anmelden und Abmelden anzuzeigen.

- **Warnungszeit (Sekunden)** Geben Sie die Anzahl der Sekunden an, um die ein Agent klingelt, bevor Sie den Anruf dem nächsten verfügbaren Agent anbieten. Die Spanne der möglichen Werte reicht von 10 bis weniger als 180 Sekunden. Die Standardeinstellung ist "20 Sekunden".

- **Routingmethode** Wählen Sie die Methode aus, um die Reihenfolge zu bestimmen, in der Agents Anrufe empfangen:

  - Wählen Sie **Längster Leerlauf**, um den Anruf dem Agent mit der längsten Leerlaufzeit (Anwesenheitsstatus **Verfügbar** oder **Inaktiv**) anzubieten.

  - Wählen Sie **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.

  - Wählen Sie **Roundrobin**, um einen neuen Anruf den einzelnen Agents nacheinander anzubieten.

  - Wählen Sie **Seriell**, um einen neuen Anruf den Agents immer in der Reihenfolge anzubieten, in der sie auf der Registerkarte **Agent** aufgeführt sind.

  - Wählen Sie **die Telefonzentrale** aus, um allen Agents, die gleichzeitig angemeldet sind, und der Reaktionsgruppenanwendung einen neuen Anruf anzubieten, unabhängig von ihrer aktuellen Anwesenheit. Telefonzentralen und Clientbenutzer, die als Agents konfiguriert sind, können alle wartenden Anrufe sehen und wartende Anrufe in beliebiger Reihenfolge annehmen. Der Anruf wird an den ersten Agent gesendet, der ihn annimmt, und die anderen Telefonzentralen und Benutzer sehen den Anruf nicht mehr.

- **Agents** Wählen Sie auf eine der folgenden Arten die Benutzer aus, die Agents für die Reaktionsgruppe sein sollen:

  - Wählen Sie **"Vorhandene E-Mail-Verteilerliste** verwenden" aus, um eine Exchange Verteilerliste zu verwenden. Geben Sie die E-Mail-Adresse der Verteilerliste unter **Verteilerlistenadresse** ein.

    > [!NOTE]
    > Sie können für eine Agentgruppe nur eine Verteilerliste auswählen. Falls die Verteilerliste verschachtelte Verteilerlisten enthält, werden die verschachtelten Verteilerlisten nicht in die Agentgruppe einbezogen.

    > [!NOTE]
    > Die Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind, wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.

    > [!NOTE]
    > Ausgeblendete Mitgliedschaften oder ausgeblendete Listen werden möglicherweise für Reaktionsgruppenadministratoren oder -benutzer sichtbar. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer Agentgruppe in Skype for Business.](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)

  - Wählen Sie **Benutzerdefinierte Gruppe von Agents definieren**, um die Benutzer auszuwählen, die Sie als Agents für die Reaktionsgruppe zuweisen möchten. Klicken Sie auf **Auswählen**, um einen Agent der Liste hinzuzufügen. Klicken Sie auf **Entfernen**, um einen ausgewählten Agent aus der Liste zu löschen.

    Mit dem Pfeil nach oben bzw. nach unten können Sie einen ausgewählten Agent in der Liste mit den Agents nach oben oder unten verschieben. Die Reihenfolge der Agents in der Liste wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.

Ausführliche Informationen zu den Funktionen und Funktionen von Reaktionsgruppen finden Sie unter [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Agentgruppen finden Sie unter [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in der Betriebsdokumentation.