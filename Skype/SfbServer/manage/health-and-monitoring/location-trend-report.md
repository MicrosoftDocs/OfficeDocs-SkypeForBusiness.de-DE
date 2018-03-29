---
title: Standort-Trendbericht in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
description: 'Zusammenfassung: Erfahren Sie mehr über die Standort-Trendbericht in Skype für Business Server 2015.'
ms.openlocfilehash: c28a22fdf4122dde45b506e90cf752794deaf781
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="location-trend-report-in-skype-for-business-server-2015"></a>Standort-Trendbericht in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu Standort-Trendbericht in Skype für Business Server 2015.
  
Der Standort-Trendbericht enthält Angaben über den Verlauf der Anrufqualität für Netzwerkstandorte.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine bestimmte Untermenge von Daten zurückgeben oder zurückgegebene Daten anders anzeigen lassen. So können Sie zum Beispiel im Standort-Trendbericht die zurückgegebenen Daten nach Aspekten wie dem Zugriffstyp (d. h. interner oder externer Zugriff) oder dem Netzwerktyp (verkabelt oder Funk) filtern. Sie können auch festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag oder Woche gruppiert.
  
In der folgenden Tabelle sind die Filter aufgeführt, die Sie beim Standort-Trendbericht verwenden können. 
  
**Trend im Standortbericht**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 01.01.2011 und dem Enddatum 28.02.2011 ausgewählt haben, werden Daten für die Tage 01.08.2011 12:00 Uhr bis 01.09.2011 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Zugriffstyp** <br/> | Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Intern <br/>  Extern <br/> |
|**Netzwerktyp** <br/> | Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Verkabelt <br/>  Funk <br/> |
|**VPN** <br/> | Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  VPN <br/>  Nicht-VPN <br/> |
   

