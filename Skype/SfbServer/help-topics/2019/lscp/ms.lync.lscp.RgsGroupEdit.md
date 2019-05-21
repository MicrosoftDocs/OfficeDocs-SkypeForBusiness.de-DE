---
title: Reaktionsgruppen erstellen einer neuen oder Bearbeiten einer vorhandenen Agentengruppe
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe entgegennehmen kann (so genannte Agents). Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.
ms.openlocfilehash: bafa1ae490da49c8a4af096129a122315a2a7809
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292619"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Reaktionsgruppen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Agentgruppe

Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe entgegennehmen kann (so genannte Agents). Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Für jede Agentengruppe ist ein eindeutiger Name erforderlich. Verwenden Sie einen beschreibenden Namen, mit dem die Funktion der Gruppe verdeutlicht wird. Beispiel: Helpdesk.

- **Beschreibung** Dieses Feld ist optional. Geben Sie darin zusätzliche Details zur Gruppe an.

- **Teilnahmerichtlinien** Geben Sie an, wie sich die Agents bei der Reaktionsgruppe anmelden sollen:

  - Wählen Sie **Informell**, um festzulegen, dass sich die Agents der Gruppe nicht an- und abmelden müssen. Informelle Agents werden bei der Anmeldung automatisch bei der Gruppe angemeldet. Die Standardeinstellung ist **Informell**.

  - Wählen Sie **formal** aus, um anzugeben, dass sich die Agents in der Gruppe an-und abmelden müssen. Wenn Sie diese Option auswählen, klicken Sie auf ein Menüelement im Client, um einen Browser zu öffnen und eine Webseite-Konsole zum ein-und Ausloggen anzuzeigen.

- **Warnungszeit (Sekunden)** Geben Sie an, wie viele Sekunden ein Agent anrufen soll, bevor Sie den nächsten verfügbaren Agenten anrufen. Die Spanne der möglichen Werte reicht von 10 bis weniger als 180 Sekunden. Die Standardeinstellung ist „20 Sekunden“.

- **Routing Methode** Wählen Sie die Methode zum Ermitteln der Reihenfolge aus, in der die Agents Anrufe empfangen:

  - Wählen Sie **Längster Leerlauf**, um den Anruf dem Agent mit der längsten Leerlaufzeit (Anwesenheitsstatus **Verfügbar** oder **Inaktiv**) anzubieten.

  - Wählen Sie **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der ihn annimmt.

  - Wählen Sie **Roundrobin**, um einen neuen Anruf den einzelnen Agents nacheinander anzubieten.

  - Wählen Sie **Seriell**, um einen neuen Anruf den Agents immer in der Reihenfolge anzubieten, in der sie auf der Registerkarte **Agent** aufgeführt sind.

  - Wählen Sie **Attendant** aus, um allen Agents, die sich angemeldet haben, und der reaktionsgruppenanwendung gleichzeitig einen neuen Anruf zu bieten, unabhängig von deren derzeitigem Anwesenheitsstatus. Teilnehmer und Clientbenutzer, die als Agents konfiguriert sind, können alle wartenden Anrufe sehen und wartende Anrufe in beliebiger Reihenfolge beantworten. Der Anruf wird an den ersten Agent übergeben, der den Anruf annimmt, und den weiteren Attendants und Benutzern nicht mehr angezeigt.

- **Agents** Wählen Sie auf eine der folgenden Arten die Benutzer aus, die als Agents für die Reaktionsgruppe fungieren sollen:

  - Wählen Sie **vorhandene e-Mail-Verteilerliste verwenden** aus, um eine Exchange-Verteilerliste zu verwenden. Geben Sie die E-Mail-Adresse der Verteilerliste unter **Verteilerlistenadresse** ein.

    > [!NOTE]
    > Sie können für eine Agentgruppe nur eine Verteilerliste auswählen. Falls die Verteilerliste verschachtelte Verteilerlisten enthält, werden die verschachtelten Verteilerlisten nicht in die Agentgruppe einbezogen.

    > [!NOTE]
    > Die Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind, wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.

    > [!NOTE]
    > Ausgeblendete Mitgliedschaften oder ausgeblendete Listen werden möglicherweise für Antwortgruppen Administratoren oder-Benutzer sichtbar. Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer Agentengruppe in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Wählen Sie **Benutzerdefinierte Gruppe von Agents definieren**, um die Benutzer auszuwählen, die Sie als Agents für die Reaktionsgruppe zuweisen möchten. Klicken Sie auf **Auswählen**, um der Liste einen Agent hinzuzufügen. Klicken Sie auf **Entfernen**, um einen ausgewählten Agent aus der Liste zu löschen.

    Mit dem Pfeil nach oben bzw. nach unten können Sie einen ausgewählten Agent in der Liste mit den Agents nach oben oder unten verschieben. Die Reihenfolge der Agents in der Liste wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.

Ausführliche Informationen zu den Features und Funktionen der Reaktionsgruppe finden Sie unter [Planen der reaktionsgruppenanwendung in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Agentgruppen finden Sie in der Betriebsdokumentation unter [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx).


