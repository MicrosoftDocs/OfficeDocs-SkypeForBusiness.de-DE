---
title: Antwortgruppen-Warteschlange "neue erstellen" oder "vorhandene bearbeiten"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Warteschlangen für Reaktionsgruppen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf annimmt.
ms.openlocfilehash: 3eba4fbba662ecc1497b5c8d0aac14ce5083c1ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286348"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Reaktionsgruppenwarteschleife: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife

Warteschlangen für Reaktionsgruppen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf annimmt.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Jede Warteschlange muss einen Namen haben. Geben Sie einen beschreibenden Namen für die Warteschleife ein.

- **Beschreibung** Dieses Feld ist optional. Geben Sie darin zusätzliche Details zur Warteschleife an.

- **Gruppen** Wählen Sie die Agentengruppen aus, die Sie der Warteschlange zuweisen möchten. Klicken Sie auf **Auswählen**, um der Liste Agentgruppen hinzuzufügen. Klicken Sie auf **Entfernen**, um die ausgewählte Agentgruppe aus der Liste zu löschen.

    Mit den Pfeilschaltflächen können Sie eine ausgewählte Agentgruppe in der Liste nach oben oder unten verschieben. Die Reihenfolge der Agentengruppen wirkt sich auf die Reihenfolge aus, in der der Skype for Business-Server nach einem verfügbaren Agenten sucht. Die erste Gruppe in der Liste wird also zuerst nach einem verfügbaren Agent durchsucht, dann die zweite Gruppe usw.

- **Aktivieren des warteschlangentimeouts** Aktivieren Sie dieses Kontrollkästchen, um eine maximale Zeitdauer anzugeben, die ein Anrufer warten muss, bevor ein Agent den Anruf beantwortet. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Timeoutzeitraum (Sekunden)** Wählen oder geben Sie die maximale Anzahl von Sekunden ein, die ein Anrufer warten kann, bevor ein Agent den Anruf beantwortet.

  - **Anrufaktion** Wählen Sie die Aktion aus, die beim Timeout eines Anrufs eintritt. Ihre Auswahlmöglichkeiten:

  - **Verbindung trennen**

  - **Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse**im Format SIP<username> @ <domainname> : (beispielsweise SIP:Bob@contoso.com) eine Voicemail-Adresse ein.

  - **Weiterleitung an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie in **SIP Address** die Telefonnummer im Format SIP:<number> @ <domainname> ein (beispielsweise SIP:+14255550121@contoso.com).

  - **An SIP-Adresse weiterleiten** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiterzuleiten. Geben Sie in **SIP-Adresse**den URI für den Benutzer im Format SIP:<username>@<domainname>ein.

  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschlange, in der Anrufe empfangen werden, wenn das Zeitlimit für Anrufe abläuft.

- **Aktivieren des Warteschlangen Überlaufs** Aktivieren Sie dieses Kontrollkästchen, um die maximale Anzahl von Anrufen anzugeben, die in der Warteschlange enthalten sein können. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:

  - **Maximale Anzahl von Anrufen** Wählen Sie die maximale Anzahl von Anrufen aus, die die Warteschlange aufnehmen kann, oder geben Sie Sie ein.

  - **Weiterleiten des Anrufs** Wählen Sie aus, welche Aktion durchführen soll, wenn der Schwellenwert für den Warteschlangen Überlauf erfüllt ist.

  - **Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn der Schwellenwert für den Warteschlangen Überlauf erfüllt ist. Sie haben folgende Möglichkeiten:

  - **Verbindung trennen**

  - **Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse**im Format SIP<username> @ <domainname> : (beispielsweise SIP:Bob@contoso.com) eine Voicemail-Adresse ein.

  - **Weiterleitung an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie in **SIP Address** die Telefonnummer im Format SIP:<number> @ <domainname> ein (beispielsweise SIP:+14255550121@contoso.com).

  - **An SIP-Adresse weiterleiten** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiterzuleiten. Geben Sie in **SIP-Adresse**den URI für den Benutzer im Format SIP:<username>@<domainname>ein.

  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschlange, die Anrufe empfangen soll, wenn der Schwellenwert für den Warteschlangen Überlauf erfüllt ist.

Ausführliche Informationen zu den Features und Funktionen der Reaktionsgruppe finden Sie unter [Planen der reaktionsgruppenanwendung in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Warteschleifen finden Sie in der Betriebsdokumentation unter [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx).


