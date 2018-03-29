---
title: Zusammenfassender Unterbericht über Peer-to-Peer-Sitzungen in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Zusammenfassung: Informationen Sie zu P2P zusammenfassende Unterbericht in Skype für Business Server 2015.'
ms.openlocfilehash: db610f21eda9b4decd01facf55f69699c48aa9f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="p2p-summary-subreport-in-skype-for-business-server-2015"></a>Zusammenfassender Unterbericht über Peer-to-Peer-Sitzungen in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu P2P zusammenfassende Unterbericht in Skype für Business Server 2015.
  
Der Zusammenfassende Unterbericht über Peer-to-Peer-Sitzungen bietet eine allgemeine Übersicht über fehlerhafte Peer-to-Peer-Kommunikationssitzungen.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Unterbericht über Peer-to-Peer-Sitzungen verwenden können.
  
**Filter im zusammenfassenden Unterbericht von P2P**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Unterbericht über Peer-to-Peer-Sitzungen angegeben werden.
  
**Metriken im zusammenfassenden Konferenzunterbericht von P2P**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.  <br/> |
|**Fehlerrate** <br/> |Nein  <br/> |Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist.  <br/> |
|**Sitzungen nach Modalität** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen, gruppiert nach Modalität (z. B. Instant Messaging).  <br/> |
|**Fehlerrate nach Modalität** <br/> |Nein  <br/> |Gesamtzahl der fehlerhaften Sitzungen, gruppiert nach Modalität (z. B. Instant Messaging).  <br/> |
   

