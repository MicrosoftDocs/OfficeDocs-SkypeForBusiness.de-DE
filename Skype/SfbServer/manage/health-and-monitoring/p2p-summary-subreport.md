---
title: P2P zusammenfassende Unterbericht in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Zusammenfassung: Informationen Sie zu P2P zusammenfassende Unterbericht in Skype für Business Server.'
ms.openlocfilehash: 019682818d25fcd0088cb47fe51e12a17b9ce1bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915818"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>P2P zusammenfassende Unterbericht in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu P2P zusammenfassende Unterbericht in Skype für Business Server.
  
Der Zusammenfassende Unterbericht über Peer-to-Peer-Sitzungen bietet eine allgemeine Übersicht über fehlerhafte Peer-to-Peer-Kommunikationssitzungen.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Unterbericht über Peer-to-Peer-Sitzungen verwenden können.
  
**Filter im Zusammenfassenden Unterbericht über Peer-to-Peer-Sitzungen**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Unterbericht über Peer-to-Peer-Sitzungen angegeben werden.
  
**Metriken im Zusammenfassenden Unterbericht über Peer-to-Peer-Sitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.  <br/> |
|**Fehlerrate** <br/> |Nein  <br/> |Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist.  <br/> |
|**Sitzungen nach Modalität** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen, gruppiert nach Modalität (z. B. Instant Messaging).  <br/> |
|**Fehlerrate nach Modalität** <br/> |Nein  <br/> |Gesamtzahl der fehlerhaften Sitzungen, gruppiert nach Modalität (z. B. Instant Messaging).  <br/> |
   

