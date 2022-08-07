---
title: Microsoft Teams-Räume vom Kunden gemeldete Vorfälle
author: donnah007
ms.author: v-donnahill
ms.date: 07/08/2022
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Partner/Kunden können Vorfälle manuell schließen und eine genaue Berichterstattung über den Raumzustand in MTRP sicherstellen.
ms.openlocfilehash: 308e2d4578637e4b50a8324a3f98bad82ad5c5d0
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270310"
---
# <a name="customer-reported-incident-tickets"></a>Vom Kunden gemeldete Vorfalltickets

Für jede Art von Vorfall, den Microsoft nicht gekennzeichnet hat, oder für Fragen zu den Diensten/Features können Kunden oder Partner im Namen von Kunden das Feature "Vorfall melden" verwenden, um Microsoft zu benachrichtigen, um das Problem zu untersuchen oder die Frage zu beantworten.

![Screenshot des Vorfalls "Incidents->Report"](../media/customer-reported-incidents-001.png)

Beschreiben Sie im Feld "Beschreibung" das Problem, bei dem Sie Hilfe von Microsoft benötigen, so gut wie möglich. Sie können einen oder mehrere Räume hinzufügen.

Überprüfen Sie  **hohe Auswirkungen** , wenn der Vorfall eine erhebliche Integritätsbeeinträchtigung für den Dienst oder für einen kritischen Raum verursacht. Um Microsoft bei der richtigen Priorisierung Ihrer Anforderung zu unterstützen, beschreiben Sie im Detail, warum dies eine hohe Auswirkung hat.

> [!NOTE]
> Verwenden Sie dieses Feld nicht für allgemeine Fragen, Räume und/oder Probleme, für die keine Entschärfung verfügbar ist.

![Screenshot der betroffenen Vorfallberichtsräume](../media/customer-reported-incidents-002.png)

Vom Kunden gemeldete Vorfälle (CRIs) gelten als kritische Tickets, was bedeutet, dass das Teams-Räume Service Operations Center diese Tickets zuerst selektieren kann. Die SLA zur Dienstbeschreibung für vom Kunden gemeldete Vorfälle finden Sie [hier](microsoft-teams-rooms-premium.md). Wenn ein Raum als Teil des CRI ausgewählt wird (oder Räume ausgewählt werden), wird jeder Raum als **fehlerhaft** gekennzeichnet, bis der CRI geschlossen wird.

## <a name="closing-customer-reported-incident-tickets"></a>Schließen von Vom Kunden gemeldeten Vorfalltickets

Vom Kunden gemeldete Vorfälle können entweder vom Kunden, Partnern, die Räume im Auftrag von Kunden verwalten, oder von Microsoft Service Operations Center-Technikern geschlossen werden.

**So schließen Sie einen Vorfall**

1. Wählen Sie **"Ticket schließen" aus**.

   ![Screenshot der Details zur Vorfallübersicht](../media/customer-reported-incidents-003.png)

1. Wählen Sie einen Grund für das Schließen aus, indem Sie eine Kategorie aus der Liste auswählen.

   Nachdem Sie den Grund für das Schließen bestätigt haben, wird das Ticket geschlossen und nach **Resolved** verschoben.

   ![Screenshot des geschlossenen Tickets](../media/customer-reported-incidents-004.png)

Im Abschnitt "Detailsübersicht" des Tickets wird angezeigt, dass das Ticket vom Dienst für verwaltete Räume (Microsoft) oder dem Namen des Kunden/Partners geschlossen wurde.  

 ![Screenshot der Personen, die das Ticket geschlossen haben ](../media/customer-reported-incidents-005.png)

## <a name="faq"></a>Häufig gestellte Fragen

**Kann jemand Tickets schließen?**

Nur vom Kunden gemeldete Vorfälle können durch einen Benutzer oder das Microsoft Managed Rooms Service Operations Center geschlossen werden. Kunden, die einem Partner zugewiesen haben, ihre Räume mit Ticketverwaltungsberechtigungen zu verwalten, haben die Möglichkeit, vom Kunden gemeldete Vorfälle zu schließen.

**Kann ich einschränken, wer Tickets schließen kann?**

Zurzeit nicht. Alle Benutzer, die über Ticketverwaltungsberechtigungen verfügen, können einen CRI schließen.

**Erhalte ich eine Benachrichtigung, wenn ein vom Kunden gemeldetes Vorfallticket geschlossen wird?**

Zurzeit nicht.