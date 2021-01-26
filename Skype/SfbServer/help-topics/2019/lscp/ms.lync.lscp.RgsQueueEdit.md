---
title: Reaktionsgruppenwarteschlange Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife
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
description: Reaktionsgruppe Warteschleifen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf beantwortet.
ms.openlocfilehash: 097c28db7f2ae52d7ab0b362e828c8f05e132481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808195"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Reaktionsgruppenwarteschleife: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife

Reaktionsgruppe Warteschleifen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf beantwortet.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Jede Warteschlange muss einen Namen haben. Geben Sie einen beschreibenden Namen für die Warteschlange ein.

- **Beschreibung** Dieses Feld ist optional. Verwenden Sie diese, um zusätzliche Details zur Warteschlange zur Verfügung zu stellen.

- **Gruppen** Wählen Sie die Agentgruppen aus, die Sie der Warteschleife zuweisen möchten. Klicken **Sie auf "Auswählen",** um der Liste Agentgruppen hinzuzufügen. Klicken **Sie auf "Entfernen",** um die ausgewählte Agentgruppe aus der Liste zu löschen.

    Mit den Pfeilen nach oben und unten wird eine ausgewählte Agentgruppe in der Liste nach oben und unten bewegt. Die Reihenfolge der Agentgruppen wirkt sich auf die Reihenfolge aus, in der Skype for Business Server nach einem verfügbaren Agent sucht. Das heißt, die erste Gruppe in der Liste wird zuerst nach einem verfügbaren Agent durchsucht, gefolgt von der zweiten Gruppe und so weiter.

- **Aktivieren des Warteschlangen-Zeit-Outs** Aktivieren Sie dieses Kontrollkästchen, um einen maximalen Zeitraum festzulegen, für den ein Anrufer in der Warteschleife wartet, bevor ein Agent den Anruf beantwortet. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Zeitdauer (Sekunden)** Wählen Oder geben Sie die maximale Anzahl von Sekunden ein, die ein Anrufer warten kann, bevor ein Agent den Anruf beantwortet.

  - **Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn bei einem Anruf ein Zeitbedarf auftritt. Ihre Wahl ist:

  - **Disconnect**

  - **An Voicemail weiterleiten** Wenn Sie diese Option auswählen, geben Sie unter **"SIP-Adresse"** eine Voicemailadresse im Format "sip:" ein (z. B. <username> @ <domainname> sip:bob@contoso.com).

  - **Weiterleiten an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie unter **"SIP-Adresse"** die Telefonnummer im Format "sip:" ein (z. B. <number> @ <domainname> sip:+14255550121@contoso.com).

  - **Weiterleiten an die SIP-Adresse** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiter zu weiterleiten. Geben Sie unter "SIP-Adresse" den URI für den Benutzer im Format "sip: "  <username> @ <domainname> ein.

  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschleife, die Anrufe empfangen soll, wenn das Zeit-/Zeit-Zeit für Anrufe ankommt.

- **Aktivieren des Warteschlangenüberlaufs** Aktivieren Sie dieses Kontrollkästchen, um eine maximale Anzahl von Anrufen anzugeben, die die Warteschleife halten kann. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Maximale Anzahl von Anrufen** Wählen Sie die maximale Anzahl von Anrufen aus, die die Warteschleife halten kann, oder geben Sie sie ein.

  - **Weiterleiten des Anrufs** Wählen Sie aus, welcher Anruf aktiv werden soll, wenn der Schwellenwert für den Warteschleifenüberlauf erreicht ist.

  - **Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn der Schwellenwert für den Warteschlangenüberlauf erreicht ist. Folgende Optionen stehen zur Auswahl:

  - **Disconnect**

  - **An Voicemail weiterleiten** Wenn Sie diese Option auswählen, geben Sie unter **"SIP-Adresse"** eine Voicemailadresse im Format "sip:" ein (z. B. <username> @ <domainname> sip:bob@contoso.com).

  - **Weiterleiten an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie unter **"SIP-Adresse"** die Telefonnummer im Format "sip:" ein (z. B. <number> @ <domainname> sip:+14255550121@contoso.com).

  - **Weiterleiten an die SIP-Adresse** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiter zu weiterleiten. Geben Sie unter "SIP-Adresse" den URI für den Benutzer im Format "sip: "  <username> @ <domainname> ein.

  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschleife, die Anrufe empfangen soll, wenn der Schwellenwert für den Warteschleifenüberlauf erreicht ist.

Ausführliche Informationen zu Reaktiongruppenfeatures und -funktionen finden Sie unter ["Plan for the Response Group application in Skype for Business Server" in](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Warteschleifen finden Sie unter [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in der Betriebsdokumentation.


