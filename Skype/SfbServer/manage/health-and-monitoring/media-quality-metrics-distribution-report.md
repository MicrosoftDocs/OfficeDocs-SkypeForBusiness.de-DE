---
title: Der Bericht über die Metrikverteilung der Medienqualität in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Zusammenfassung: Erfahren Sie mehr über den Bericht über die Metrikverteilung der Medienqualität in Skype for Business Server.'
ms.openlocfilehash: b90b54ede899d8eb085ad65392280e3910498128e5a43c927260b20e501e2292
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290313"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Der Bericht über die Metrikverteilung der Medienqualität in Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie mehr über den Bericht über die Metrikverteilung der Medienqualität in Skype for Business Server.
  
Mit dem Bericht über die Metrikverteilung der Medienqualität können Sie ein Diagramm anzeigen, das die Verteilungswerte für eine QoE-Metrik wie Jitter oder Paketverlust anzeigt. Nehmen wir beispielsweise an, dass Ihre Benutzer insgesamt 10 Telefonanrufe tätigen; Diese 10 Anrufe melden die folgenden Roundtripzeiten:
  
|**Anrufnummer**|**Roundtripzeit (Millisekunden)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4   <br/> |50  <br/> |
|5   <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10   <br/> |50  <br/> |
   
Der Durchschnitt für diese Roundtripzeiten beträgt 500 Millisekunden (5000 dividiert durch 10). 500 Millisekunden sind eine extrem große Roundtripzeit. Daher könnten Sie annehmen, dass Sie ein schwerwiegendes Problem mit der Netzwerküberlastung haben. (Lange Roundtripzeiten sind in der Regel das Ergebnis überlasteter Netzwerke.)
  
Tatsächlich hatten 90 % Ihrer Anrufe hervorragende Roundtripzeiten. Sie hatten lediglich einen schlechten Aufruf, der die Gesamtergebnisse verzerrte. Wenn Sie sich nur die durchschnittliche Roundtripzeit ansehen, können Sie zu einem sehr falschen Ergebnis springen.
  
Der Bericht über die Metrikverteilung der Medienqualität hilft Ihnen dabei, zu falschen Schlussfolgerungen zu springen, indem Ihnen eine grafische Verteilung einer angegebenen Metrik (z. B. Roundtripzeit) angezeigt wird. Diese Diagramme können ihnen helfen, deutlich zu machen, dass Sie neun sehr gute und einen sehr schlechten Anruf hatten. Zugegeben, Sie möchten diesen einen Anruf möglicherweise noch genauer untersuchen. Die Tatsache, dass 9 von 10 Anrufen sehr gut waren, deutet jedoch darauf hin, dass es keinen Grund gibt, erhebliche Änderungen an Ihrem Netzwerk vorzunehmen, zumindest nicht zu diesem Zeitpunkt.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Bericht über die Metrikverteilung der Medienqualität verwenden können.
  
**Filter im Bericht über Metrikverteilung der Medienqualität**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ziel** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Minimum in x-Achse** <br/> |Niedrigster Wert, der auf der X-Achse des Diagramms angezeigt werden soll.  <br/> |
|**Maximum in x-Achse** <br/> |Der höchste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.  <br/> |
|**Zugriffstyp** <br/> | Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Intern <br/>  Extern <br/> |
|**VPN** <br/> | Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  VPN <br/>  Nicht-VPN <br/> |
|**Netzwerktyp** <br/> | Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Wired <br/>  Wireless <br/> |
   

