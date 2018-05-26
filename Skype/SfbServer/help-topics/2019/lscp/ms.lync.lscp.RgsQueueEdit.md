---
title: Reaktionsgruppenwarteschleife Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Reaktionsgruppenwarteschleifen halten Anrufe an eine reaktionsgruppe, bis ein Agent den Anruf annimmt.
ms.openlocfilehash: 7927efe94ee913921c2ddf139d2643084127bfc0
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Reaktionsgruppenwarteschleife: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife
 
Reaktionsgruppenwarteschleifen halten Anrufe an eine reaktionsgruppe, bis ein Agent den Anruf annimmt.
  
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.
  
- **Name** Jede Warteschleife muss einen Namen aufweisen. Geben Sie einen beschreibenden Namen für die Warteschleife ein.
    
- **Beschreibung** Dieses Feld ist optional. Geben Sie darin zusätzliche Details zur Warteschleife an.
    
- **Gruppen** Wählen Sie die agentgruppen, die Sie an die Warteschlange zuweisen möchten. Klicken Sie auf **Auswählen**, um der Liste Agentgruppen hinzuzufügen. Klicken Sie auf **Entfernen**, um die ausgewählte Agentgruppe aus der Liste zu löschen.
    
    Mit den Pfeilschaltflächen können Sie eine ausgewählte Agentgruppe in der Liste nach oben oder unten verschieben. Die Reihenfolge der Agentengruppen wirkt sich auf die Reihenfolge, in der Skype für Business Server nach einem verfügbaren Agent sucht. Die erste Gruppe in der Liste wird also zuerst nach einem verfügbaren Agent durchsucht, dann die zweite Gruppe usw.
    
- **Timeout der Nachrichtenwarteschlange aktivieren** Aktivieren Sie dieses Kontrollkästchen an eine maximale Zeitspanne für ein Anrufer in der Warteschleife warten, bevor ein Agent den Anruf annimmt. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:
    
  - **Timeout (Sekunden)** Wählen Sie aus, oder geben Sie die maximale Anzahl von Sekunden ein, die ein Anrufer warten kann, bevor ein Agent den Anruf annimmt.
    
  - **Aktion zum Aufrufen eines** Wählen Sie die Aktion, die bei Zeitüberschreitung eines Anrufs. Die folgenden Optionen sind:
    
  - **Verbindung trennen**
    
  - **An Voicemail weiterleiten** Wenn Sie diese Option in **SIP-Adresse**auswählen, geben Sie eine Voicemail-Adresse im Format Sip:<username> @ <domainname> (beispielsweise sip:bob@contoso.com).
    
  - **An Telefonnummer weiterleiten** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse** die Telefonnummer im Format Sip:<number> @ <domainname> (beispielsweise sip:+14255550121@contoso.com).
    
  - **Weiterleiten an SIP-Adresse** Wählen Sie diese Option, um den Anruf an einen anderen Benutzer weiterzuleiten. Geben Sie in der **SIP-Adresse**, den URI für den Benutzer im Format Sip:<username>@<domainname>.
    
  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, wechseln Sie zu der Warteschleife, empfangen anruft, während das Timeout für Anrufe.
    
- **Aktivieren der Warteschlange Overflow (engl.)** Aktivieren Sie dieses Kontrollkästchen, um eine maximale Anzahl der Anrufe anzugeben, die die Warteschleife aufnehmen kann. Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:
    
  - **Maximale Anzahl von Anrufen** Wählen Sie aus, oder geben Sie die maximale Anzahl von Anrufen, die die Warteschleife aufnehmen kann.
    
  - **Den Anruf weiterleiten** Wählen Sie aus, welchen Anruf reagiert werden soll, wenn die für die Warteschlange Überlauf durchgeführt wird.
    
  - **Aktion zum Aufrufen eines** Wählen Sie die Aktion, die bei der für die Warteschlange Überlauf durchgeführt wird. Sie haben folgende Möglichkeiten:
    
  - **Verbindung trennen**
    
  - **An Voicemail weiterleiten** Wenn Sie diese Option in **SIP-Adresse**auswählen, geben Sie eine Voicemail-Adresse im Format Sip:<username> @ <domainname> (beispielsweise sip:bob@contoso.com).
    
  - **An Telefonnummer weiterleiten** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse** die Telefonnummer im Format Sip:<number> @ <domainname> (beispielsweise sip:+14255550121@contoso.com).
    
  - **Weiterleiten an SIP-Adresse** Wählen Sie diese Option, um den Anruf an einen anderen Benutzer weiterzuleiten. Geben Sie in der **SIP-Adresse**, den URI für den Benutzer im Format Sip:<username>@<domainname>.
    
  - **Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, wechseln Sie zu der Warteschleife, Anrufe, die für die Warteschlange Überlauf durchgeführt wird.
    
Ausführliche Informationen zu Response Group Features und Funktionen finden Sie unter [Planen für die Anwendung "Reaktionsgruppe" in Skype für Business Server 2015](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Warteschlangen finden Sie unter [Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in der Betriebsdokumentation.
  

