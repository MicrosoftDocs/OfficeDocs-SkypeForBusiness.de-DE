---
title: Zusammenfassender Unterbericht zu P2P in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Zusammenfassung: Erfahren Sie mehr über den zusammenfassenden Unterbericht über P2P in Skype for Business Server.'
ms.openlocfilehash: 14472ee8ede0e05d56f026561dfd8884c3d6c152
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774855"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Zusammenfassender Unterbericht zu P2P in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den zusammenfassenden Unterbericht über P2P in Skype for Business Server.
  
Der zusammenfassende Unterbericht über P2P bietet eine Gesamtansicht ihrer fehlgeschlagenen Peer-to-Peer-Kommunikationssitzungen.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Zusammenfassenden Unterbericht über P2P verwenden können.
  
**Filter für zusammenfassende P2P-Unterberichte**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im zusammenfassenden Unterbericht über P2P bereitgestellt werden.
  
**Zusammenfassende Unterberichtsmetriken für P2P**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.  <br/> |
|**Fehlerrate** <br/> |Nein  <br/> |Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist.  <br/> |
|**Sitzungen nach Modalität** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen gruppiert nach Modalität (z. B. Chat).  <br/> |
|**Fehlerrate nach Modalität** <br/> |Nein  <br/> |Gesamtzahl der fehlgeschlagenen Sitzungen gruppiert nach Modalität (z. B. Chat).  <br/> |
   

