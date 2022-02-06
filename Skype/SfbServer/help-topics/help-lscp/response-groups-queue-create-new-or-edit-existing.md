---
title: Response Groups Queue Create New or Edit Existing
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: 'Reaktionsgruppenwarteschlangen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf entgegennimmt.'
---

# <a name="response-groups-queue-create-new-or-edit-existing"></a>Reaktionsgruppenwarteschleife: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife

Reaktionsgruppenwarteschlangen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf entgegennimmt.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Namen** Jede Warteschlange muss einen Namen haben. Geben Sie einen beschreibenden Namen für die Warteschlange ein.

- **Beschreibung** Dieses Feld ist optional. Verwenden Sie sie, um zusätzliche Details zur Warteschleife bereitzustellen.

- **Gruppen** Wählen Sie die Agentgruppen aus, die Sie der Warteschlange zuweisen möchten. Klicken Sie auf **"Auswählen** ", um der Liste Agentgruppen hinzuzufügen. Klicken Sie auf **"Entfernen** ", um die ausgewählte Agentgruppe aus der Liste zu löschen.

    Mit den Pfeilen nach oben und unten wird eine ausgewählte Agentgruppe in der Liste nach oben und unten verschoben. Die Reihenfolge der Agentgruppen wirkt sich auf die Reihenfolge aus, in der Skype for Business Server nach einem verfügbaren Agent sucht. Das heißt, die erste Gruppe in der Liste wird zuerst nach einem verfügbaren Agent durchsucht, gefolgt von der zweiten Gruppe usw.

- **Aktivieren des Warteschlangentimeouts** Aktivieren Sie dieses Kontrollkästchen, um einen maximalen Zeitraum anzugeben, bis ein Anrufer in der Warteschleife warte, bevor ein Agent den Anruf entgegennimmt. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Timeoutzeitraum (Sekunden)** Wählen Oder geben Sie die maximale Anzahl von Sekunden ein, die ein Anrufer warten kann, bevor ein Agent den Anruf entgegennimmt.

  - **Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn bei einem Anruf ein Zeitüberschreitung auftritt. Sie haben folgende Auswahlmöglichkeiten:

  - **Disconnect**

  - **Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie in **der SIP-Adresse** eine Voicemailadresse im Sip-Format\<username>@\<domainname> ein (z. B. sip:bob@contoso.com).

  - **An Telefonnummer weiterleiten** Wenn Sie diese Option auswählen, geben Sie in der **SIP-Adresse** die Telefonnummer im Sip-Format\<number>@\<domainname> ein (z. B. sip:+14255550121@contoso.com).

  - **An SIP-Adresse weiterleiten** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiterzuleiten. Geben Sie in der **SIP-Adresse** den URI für den Benutzer im Sip-Format ein:\<username>@\<domainname>

  - **An eine andere Warteschlange weiterleiten** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschleife, in der Anrufe empfangen werden sollen, wenn das Zeitlimit für die Anrufe abläuft.

- **Aktivieren des Warteschleifenüberlaufs** Aktivieren Sie dieses Kontrollkästchen, um eine maximale Anzahl von Anrufen anzugeben, die die Warteschleife halten kann. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Maximale Anzahl von Anrufen** Wählen Sie die maximale Anzahl von Anrufen aus, die die Warteschleife halten kann, oder geben Sie sie ein.

  - **Weiterleiten des Anrufs** Wählen Sie aus, welcher Anruf ausgeführt werden soll, wenn der Schwellenwert für den Warteschleifenüberlauf erreicht ist.

  - **Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn der Schwellenwert für den Warteschleifenüberlauf erreicht wird. Folgende Optionen stehen zur Auswahl:

  - **Disconnect**

  - **Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie in **der SIP-Adresse** eine Voicemailadresse im Sip-Format\<username>@\<domainname> ein (z. B. sip:bob@contoso.com).

  - **An Telefonnummer weiterleiten** Wenn Sie diese Option auswählen, geben Sie in der **SIP-Adresse** die Telefonnummer im Sip-Format\<number>@\<domainname> ein (z. B. sip:+14255550121@contoso.com).

  - **An SIP-Adresse weiterleiten** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiterzuleiten. Geben Sie in der **SIP-Adresse** den URI für den Benutzer im Sip-Format ein:\<username>@\<domainname>

  - **An eine andere Warteschlange weiterleiten** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschleife, die Anrufe empfangen soll, wenn der Schwellenwert für den Warteschleifenüberlauf erreicht ist.

Ausführliche Informationen zu den Funktionen und Funktionen von Reaktionsgruppen finden Sie in der Planungsdokumentation unter [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md). Ausführliche Informationen zur Verwendung von Warteschleifen finden Sie unter [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) in der Betriebsdokumentation.