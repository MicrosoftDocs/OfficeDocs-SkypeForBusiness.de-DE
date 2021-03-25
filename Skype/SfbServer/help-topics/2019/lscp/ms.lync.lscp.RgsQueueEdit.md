---
title: ReaktionsgruppenWarteschlange Erstellen neuer oder Bearbeiten vorhandener Warteschlangen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Reaktionsgruppe Warteschlangen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf beantwortet.
ms.openlocfilehash: ee99ac8cb4f3ea9c2f0e1804914eaf30c909a2b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118804"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Reaktionsgruppenwarteschleife: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife

Reaktionsgruppe Warteschlangen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf beantwortet.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Jede Warteschlange muss einen Namen haben. Geben Sie einen beschreibenden Namen für die Warteschlange ein.

- **Beschreibung** Dieses Feld ist optional. Verwenden Sie sie, um zusätzliche Details zur Warteschlange zur Verfügung zu stellen.

- **Gruppen** Wählen Sie die Agentgruppen aus, die Sie der Warteschlange zuweisen möchten. Klicken **Sie auf Auswählen,** um der Liste Agentgruppen hinzuzufügen. Klicken **Sie auf Entfernen,** um die ausgewählte Agentgruppe aus der Liste zu löschen.

    Mit den Pfeilen nach oben und unten wird eine ausgewählte Agentgruppe in der Liste nach oben und unten bewegt. Die Reihenfolge der Agentgruppen wirkt sich auf die Reihenfolge aus, in der Skype for Business Server nach einem verfügbaren Agent sucht. Das heißt, die erste Gruppe in der Liste wird zuerst nach einem verfügbaren Agent durchsucht, gefolgt von der zweiten Gruppe und so weiter.

- **Aktivieren des Warteschlangen-Zeit-Outs** Aktivieren Sie dieses Kontrollkästchen, um einen maximalen Zeitraum für die Wartezeit eines Anrufers anzugeben, bevor ein Agent den Anruf beantwortet. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Time-out-Zeitraum (Sekunden)** Wählen oder geben Sie die maximale Anzahl von Sekunden ein Anrufer warten kann, bevor ein Agent den Anruf beantwortet.

  - **Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn bei einem Anruf ein Zeit-Out auftritt. Ihre Auswahl ist:

  - **Disconnect**

  - **Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse** eine Voicemailadresse im Format sip: ein (z. B. <username> @ <domainname> sip:bob@contoso.com).

  - **Weiterleiten an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie in **SIP-Adresse** die Telefonnummer im Format sip: ein (z. B. <number> @ <domainname> sip:+14255550121@contoso.com).

  - **Weiterleiten an die SIP-Adresse** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiter zu weiterleiten. Geben **Sie unter** SIP-Adresse den URI für den Benutzer im Format sip: <username> @ <domainname> ein.

  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschlange, in der Anrufe empfangen werden sollen, wenn das Zeit-Out für Anrufe liegt.

- **Aktivieren des Warteschlangenüberlaufs** Aktivieren Sie dieses Kontrollkästchen, um eine maximale Anzahl von Anrufen anzugeben, die in der Warteschlange gespeichert werden können. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Maximale Anzahl von Anrufen** Wählen Oder geben Sie die maximale Anzahl von Anrufen ein, die die Warteschlange halten kann.

  - **Weiterleiten des Anrufs** Wählen Sie aus, welcher Aufruf aktiv werden soll, wenn der Schwellenwert für den Warteschlangenüberlauf erreicht ist.

  - **Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn der Schwellenwert für den Warteschlangenüberlauf erreicht ist. Folgende Optionen stehen zur Auswahl:

  - **Disconnect**

  - **Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse** eine Voicemailadresse im Format sip: ein (z. B. <username> @ <domainname> sip:bob@contoso.com).

  - **Weiterleiten an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie in **SIP-Adresse** die Telefonnummer im Format sip: ein (z. B. <number> @ <domainname> sip:+14255550121@contoso.com).

  - **Weiterleiten an die SIP-Adresse** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiter zu weiterleiten. Geben **Sie unter** SIP-Adresse den URI für den Benutzer im Format sip: <username> @ <domainname> ein.

  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschlange, die Anrufe empfangen soll, wenn der Schwellenwert für den Warteschlangenüberlauf erreicht ist.

Ausführliche Informationen zu den Funktionen und Funktionen von Reaktionsgruppe finden Sie unter [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Warteschleifen finden Sie unter [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) in der Betriebsdokumentation.