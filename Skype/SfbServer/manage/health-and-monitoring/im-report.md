---
title: Peer-zu-Peer-Sofortnachrichten-Bericht in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Zusammenfassung: Informationen Sie zu den Bericht über Peer-zu-Peer-Sofortnachrichten in Skype für Business Server.'
ms.openlocfilehash: 89b5d7e76b476c112b1938d5fe9692625641214d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873429"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Peer-zu-Peer-Sofortnachrichten-Bericht in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Bericht über Peer-zu-Peer-Sofortnachrichten in Skype für Business Server.
  
Der Bericht über Peer-to-Peer-Sofortnachrichten enthält Trendinformationen zu den Peer-to-Peer-Sofortnachrichtensitzungen, aufgeschlüsselt nach Pool und Authentifizierungstyp. Der Bericht kann entweder die Gesamtanzahl der im angegebenen Zeitraum abgehaltenen Sitzungen (z. B. nach Tag oder nach Stunden) oder die Gesamtanzahl der in diesem Zeitraum gesendeten Sofortnachrichten anzeigen.
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Zugreifen auf den Bericht über Peer-to-Peer-Sofortnachrichten

Sie können den Bericht über Peer-zu-Peer-Sofortnachrichten nur zugreifen, indem die [Zusammenfassung für Peer-zu-Peer-Aktivität in Skype für Business Server Report](peer-to-peer-activity-summary-report.md) öffnen und dann auf eine der folgenden Metriken:
  
- Peer-to-Peer-Chatsitzungen insgesamt
    
- Peer-to-Peer-Chatnachrichten insgesamt
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Optimales Verwenden des Berichts über Peer-to-Peer-Sofortnachrichten

Standardmäßig wird im Bericht über Peer-to-Peer-Sofortnachrichten die Anzahl der Nachrichten pro Stunde (oder, abhängig von Ihren Einstellungen, pro Tag) angezeigt. Sie können jedoch auch den Tag nach Sitzungen pro Stunde anzeigen. Klicken Sie dazu rechts oben im Berichtfenster auf die Schaltfläche zum **Ein- und Ausblenden der Parameter** und klicken Sie dann in der Liste **Bericht nach** auf **Sitzungsanzahl**.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-to-Peer-Sofortnachrichten verwenden können.
  
**Filter im Bericht über Peer-to-Peer-Sofortnachrichten**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die Woche oder den Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Bericht nach** <br/> | Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus: <br/>  Sitzungsanzahl <br/>  Nachrichtenanzahl <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sofortnachrichten enthalten sind.
  
**Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Pool**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Pool** <br/> |Nein  <br/> |Name des Registrar-Pools oder Edgeservers.  <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.  <br/> |
|**Gesamt** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sofortnachrichten für die einzelnen von den Teilnehmern in einer Peer-to-Peer-Sitzung verwendeten Authentifizierungstypen angegeben werden.
  
**Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Authentifizierungstyp** <br/> |Nein  <br/> | Der von den Sitzungsteilnehmern verwendete Authentifizierungstyp. Folgende Werte sind möglich: <br/>  Enterprise <br/>  Federated <br/>  PIC <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.  <br/> |
|**Gesamt** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   

