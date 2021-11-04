---
title: Bericht über Peer-to-Peer-Chatnachrichten in Skype for Business Server
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
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Zusammenfassung: Erfahren Sie mehr über den Bericht über Peer-to-Peer-Chatnachrichten in Skype for Business Server.'
ms.openlocfilehash: 999750f039b2ca57cc31198bcf1599f042763ed3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767663"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Bericht über Peer-to-Peer-Chatnachrichten in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bericht über Peer-to-Peer-Chatnachrichten in Skype for Business Server.
  
Der Bericht über Peer-zu-Peer-Sofortnachrichten enthält Trendinformationen zu den Peer-zu-Peer-Sofortnachrichtensitzungen, aufgeschlüsselt nach Pool und Authentifizierungstyp. Der Bericht kann entweder die Gesamtanzahl der im angegebenen Zeitraum abgehaltenen Sitzungen (z. B. nach Tag oder nach Stunden) oder die Gesamtanzahl der in diesem Zeitraum gesendeten Sofortnachrichten anzeigen.
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Zugreifen auf den Bericht über Peer-zu-Peer-Sofortnachrichten

Sie können nur auf den Bericht über Peer-to-Peer-Sofortnachrichten zugreifen, indem Sie den [Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server](peer-to-peer-activity-summary-report.md) öffnen und dann auf eine der folgenden Metriken klicken:
  
- Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen
    
- Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Optimales Verwenden des Berichts über Peer-zu-Peer-Sofortnachrichten

Standardmäßig wird im Bericht über Peer-zu-Peer-Sofortnachrichten die Anzahl der Nachrichten pro Stunde (oder, abhängig von Ihren Einstellungen, pro Tag) angezeigt. Sie können jedoch auch den Tag nach Sitzungen pro Stunde anzeigen. Klicken Sie dazu rechts oben im Fenster der Berichte auf die Schaltfläche zum Ein- und Ausblenden der Parameter, und klicken Sie dann in der Liste **Bericht nach** auf **Sitzungsanzahl**.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-zu-Peer-Sofortnachrichten verwenden können.
  
**Filter im Bericht über Peer-zu-Peer-Sofortnachrichten**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die Woche oder den Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie z. B. das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. s. Daten insgesamt 31 Tage). <br/> |
|**Bericht nach:** <br/> | Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus: <br/>  Sitzungsanzahl <br/>  Nachrichtenanzahl <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sofortnachrichten enthalten sind.
  
**Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Pool**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Pool** <br/> |Nein  <br/> |Name des Registrierungsstellenpools oder Edgeservers.  <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.  <br/> |
|**Total** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sofortnachrichten für die einzelnen von den Teilnehmern in einer Peer-zu-Peer-Sitzung verwendeten Authentifizierungstypen angegeben werden.
  
**Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Authentifizierungstyp** <br/> |Nein  <br/> | Der von den Sitzungsteilnehmern verwendete Authentifizierungstyp. Folgende Werte sind möglich: <br/>  Enterprise <br/>  Federated <br/>  PIC <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.  <br/> |
|**Total** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   

