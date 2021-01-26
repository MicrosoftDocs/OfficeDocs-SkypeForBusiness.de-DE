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
ms.openlocfilehash: c39282ab2d5d6ce903affd807d22116a98de3620
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827805"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Der Bericht über die Metrikverteilung der Medienqualität in Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie mehr über den Bericht über die Metrikverteilung der Medienqualität in Skype for Business Server.
  
Im Bericht über die Metrikverteilung der Medienqualität können Sie ein Diagramm mit den Verteilungswerten für eine Quality of Experience-Metrik wie Jitter oder Paketverlust anzeigen. Angenommen, Ihre Benutzer machen insgesamt 10 Telefonanrufe. Diese 10 Anrufe melden die folgenden Roundtripzeiten:
  
|**Call Number**|**Roundtripzeit (Millisekunden)**|
|:-----|:-----|
|1   <br/> |50  <br/> |
|2   <br/> |50  <br/> |
|3   <br/> |50  <br/> |
|4   <br/> |50  <br/> |
|5   <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10   <br/> |50  <br/> |
   
Der Durchschnitt für diese Roundtripzeiten beträgt 500 Millisekunden (5000 dividiert durch 10). 500 Millisekunden sind eine extrem große Roundtripzeit. Daher könnten Sie glauben, dass sie ein schwerwiegendes Problem mit der Netzwerküberlastung haben. (Lange Roundtripzeiten sind in der Regel das Ergebnis überlastete Netzwerke.)
  
In Der Praxis hatten 90 % Ihrer Anrufe hervorragende Roundtripzeiten. Sie hatten lediglich einen ungültigen Aufruf, der die Gesamtergebnisse verfing. Wenn Sie sich nur die durchschnittliche Roundtripzeit anschauen, können Sie zu einer völlig falschen Schlussfolgerung springen.
  
Mit dem Bericht über die Metrikverteilung der Medienqualität können Sie vermeiden, zu falschen Schlussfolgerungen zu springen, indem Sie eine grafische Verteilung einer bestimmten Metrik (z. B. Roundtripzeit) anzeigen. Mit diesen Diagrammen können Sie deutlich machen, dass Sie neun sehr gute Anrufe und einen sehr schlechten Anruf hatten. Zugegebene denn, Sie möchten den einen Anruf weiter untersuchen. Die Tatsache, dass 9 der 10 Anrufe sehr gut waren, deutet jedoch darauf hin, dass es keinen Grund gibt, änderungen an Ihrem Netzwerk vorzunehmen, zumindest zu diesem Zeitpunkt nicht.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Bericht über die Metrikverteilung der Medienqualität verwenden können.
  
**Filter im Bericht über die Metrikverteilung der Medienqualität**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Minimum in x-Achse** <br/> |Niedrigster Wert, der auf der X-Achse des Diagramms angezeigt werden soll.  <br/> |
|**Maximum in x-Achse** <br/> |Der höchste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.  <br/> |
|**Zugriffstyp** <br/> | Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Intern <br/>  Extern <br/> |
|**VPN** <br/> | Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  VPN <br/>  Nicht-VPN <br/> |
|**Netzwerktyp** <br/> | Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Verkabelt <br/>  Drahtlos <br/> |
   

