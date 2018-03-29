---
title: Bericht über Benutzeraktivität in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
description: 'Zusammenfassung: Erfahren Sie mehr über User Activity Report in Skype für Business Server 2015.'
ms.openlocfilehash: b3a69f067f2acbc27b84b58c7ebc9ba53c979f92
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="user-activity-report-in-skype-for-business-server-2015"></a>Bericht über Benutzeraktivität in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Bericht über Benutzeraktivität in Skype für Business Server 2015.
  
Der Bericht über Benutzeraktivität stellt eine detaillierte Liste der Peer-to-Peer- und Konferenzsitzungen bereit, die von Benutzern in einem bestimmten Zeitraum durchgeführt werden. Anders als bei vielen der Überwachungsberichte ist im Bericht über Benutzeraktivität jeder Anruf mit einzelnen Benutzern verknüpft. Für Peer-to-Peer-Sitzungen ist im Bericht beispielsweise der SIP-URI der Person angegeben, die den Anruf initiiert hat (der Absenderbenutzer), und der Person, die angerufen wurde (der Empfängerbenutzer). Wenn Sie die Informationen zu einer Konferenz erweitern, sehen Sie eine Liste aller Konferenzteilnehmer einschließlich der Rolle, die die bei dieser Konferenz hatten.
  
Der Bericht über Benutzeraktivität wird auch als „Helpdesk“-Bericht bezeichnet. Der Grund ist, dass der Bericht häufig vom Helpdesk-Personal verwendet wird, um Sitzungsinformationen für einen bestimmten Benutzer abzurufen. Sie können den Bericht nach Anrufen filtern, die von einem bestimmten Benutzer entgegengenommen oder initiiert wurden, indem Sie einfach den SIP-URI dieses Benutzers in das Feld „Präfix des Benutzer-URI“ eingeben.
  
Wenn Sie dies tun, gibt User Activity Report Informationen für alle Benutzer zurück, deren SIP-URI mit der angegebenen Zeichenfolge beginnt. Wenn Sie im Feld URI **Ken** eingeben, wird beispielsweise User Activity Report **Ken**suchen. Myer@litwareinc.com. jedoch finden sie auch diese Benutzer:
  
- **Ken** azi@litwareinc.com
    
- **Ken** burg@litwareinc.com
    
- **Ken**. Sanchez@litwareinc.com
    
- **Ken** nedy@litwareinc.com
    
Um diese Informationen nur für Ken Myer zurückgegeben wird, entweder seine vollständige URI (Ken.Myer@litwareinc.com) in das Suchfeld oder zumindest genügend Typ von Ken geben sicherzustellen URI ihm von anderen Benutzern in Ihrer Organisation eindeutig zu unterscheiden. Ein Beispiel:
  
Ken.My
  
## <a name="to-access-the-user-activity-report"></a>So greifen Sie auf den Bericht über Benutzeraktivität zu

Auf den Bericht über Benutzeraktivität können Sie von der Startseite für Überwachungsberichte aus zugreifen. User Activity Report erreichen durch Klicken auf die Metrik-URI des Benutzers im [IP-Telefonbestand in Skype für Business Server 2015](ip-phone-inventory-report.md). Wenn Sie im Bericht über Benutzeraktivität auf den Konferenz-URI (für eine Konferenz) klicken, gelangen Sie zum Konferenzdetailbericht. In ähnlicher Weise gelangen auf die Metrik "Detail" für einen Peer-zu-Peer-Anruf mit dem [Peer-zu-Peer-Sitzungsbericht in Skype für Business Server 2015](peer-to-peer-session-detail-report.md).
  
## <a name="making-the-best-use-of-the-user-activity-report"></a>Optimales Verwenden des Berichts über Benutzeraktivität

Obwohl viele gute Informationen in den Bericht über Benutzeraktivität vorhanden ist, kann diese Informationen manchmal zu schwierig sein. Beispielsweise alle Aktivitäten, die in Ihrer Organisation einen angegebenen Zeitraum stattfindet Benutzer in User Activity Report steht. die bedeutet, dass, verborgen, den Bericht enthält Informationen darüber, welche Benutzer tatsächlich Skype für Business Server 2015 in irgendeiner Weise verwendet.
  
> [!NOTE]
> Technisch gesehen ist es möglich, dass einige Benutzeraktivität nicht aufgezeichneten gehen möglicherweise: while Skype für Business Server ist bestrebt, Synchronisieren von Informationen über alle Anrufe, es ist möglich, dass ein Anruf konnte ohne die Informationen über dieses Aufrufs in geschriebenen vorgenommen wurden die -Datenbank. Skype für Business Server bietet eine sehr genaue jedoch nicht unbedingt perfekt Blick auf wie Skype für Business Server 2015 verwendet wird. (Die Tatsache, dass es nicht gewährleistet ist, dass 100 % aller Anrufe aufgezeichnet wird erläutert, warum Skype für die Überwachung von Business Server nicht als Abrechnung System verwendet werden soll.) Zweite, eine Überwachung kann nur Berichtsanzeige maximal 1.000 Datensätze. Je nach Umfang der Benutzeraktivität und des Zeitraums, den Sie auswählen, werden bei der Abfrage möglicherweise nicht alle Daten zurückgegeben, die tatsächlich in der Datenbank gespeichert sind. 
  
- Welche Benutzter haben das System in diesem Zeitraum tatsächlich verwendet?
    
- Welcher der Benutzer war in diesem Zeitraum am aktivsten?
    
- Sind die Benutzer, die die meisten Telefonate durchführen, auch die Benutzer, die am häufigsten an Chatsitzungen teilnehmen?
    
Wenn Sie Antworten auf Fragen wie diese benötigen, können Sie die von den Überwachungsberichten abgerufenen Daten in ein Excel-Arbeitsblatt exportieren. Sie können dieses Arbeitsblatt und/oder eine CSV-Datei dann verwenden, um die Daten zu analysieren. Angenommen, Sie haben Berichtsdaten nach Excel und dann in eine CSV-Datei exportiert. An dieser Stelle können Sie importieren, die Daten aus der. CSV-Datei zu Windows PowerShell mit einem Befehl wie den folgenden:
  
```
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Nachdem die Daten importiert wurde dann können einfache Windows PowerShell-Befehle Sie Antwort dabei helfen, Ihre Fragen. Mit dem folgenden Befehl wird beispielsweise eine Liste von eindeutigen Benutzern zurückgegeben, die in mindestens einer Sitzung als „Absenderbenutzer“ fungiert haben:
  
```
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

Anders ausgedrückt:
  
```
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
```

Mit diesem Befehl werden eindeutige Benutzer aufgelistet (basierend auf der Gesamtanzahl der Sitzungen, an denen sie teilgenommen haben:
  
```
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Der Befehl gibt ähnliche Daten wie die folgenden zurück:
  
```
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
```

Dieser Befehl beschränkt die gemeldeten Sitzungen auf diejenigen mit Audio als Modalität ein:
  
```
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Wenn Sie mit der Maus auf eine beliebige Diagnose-ID im Bericht zeigen, erscheint eine QuickInfo mit einer Beschreibung der ID.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Benutzeraktivität können Sie beispielsweise die zurückgegebenen Daten nach Kriterien wie dem Aktivitätstyp (Peer-to-Peer-Sitzung oder Konferenzsitzung) oder nach der SIP-Adresse (zum Anzeigen der Aktivitäten eines Benutzers) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzeraktivität verwenden können.
  
**Filter im konferenzaktivitätsbericht Benutzer**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 17.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 13.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 17.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 13.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Aktivitätstyp** <br/> | Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Peer-to-Peer <br/>  Konferenz <br/> |
|**Modalität** <br/> |Die für Sie verfügbare Modalität ist je nach ausgewähltem Aktivitätstyp unterschiedlich. Wenn Aktivitätstyp Peer-zu-Peer ist, können Sie Sofortnachrichten auswählen. Dateiübertragung; Die Anwendungsfreigabe; VoIP; oder Video als die Modalität.  <br/> Wenn der Aktivitätstyp Konferenz ist, können Sie Chat-Telefonkonferenz, Webkonferenz, Anwendungsfreigabe, Sprach-/Videokonferenz oder Telefoniekonferenz auswählen.  <br/> |
|**Sitzungskategorie** <br/> | Gibt an, ob die betreffende Aktivität erfolgreich war oder nicht. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Erfolg <br/>  Erwarteter Fehler <br/>  Unerwarteter Fehler <br/>  Ein „erwarteter Fehler“ ist ein Fehler, der erwartungsgemäß auftritt. Hat beispielsweise ein Benutzer seinen Status auf „Nicht stören“ gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen. Ein „unerwarteter Fehler“ ist ein Fehler, der in einem ansonsten scheinbar fehlerfreien System auftritt. Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet. In diesem Fall würde der Fehler als „unerwartet“ gekennzeichnet. <br/> |
|**Präfix des Benutzer-URI** <br/> |SIP-Adresse für den Benutzer. Um nur die Datensätze des Benutzers Ken Myer anzuzeigen, geben Sie die SIP-Adresse von Ken Myer ein, z. B.:  <br/> SIP:kenmyer@litwareinc.com  <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Peer-to-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.
  
**Metriken für Peer-zu-Peer-Sitzungen**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Detail** <br/> |Nein  <br/> |Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Peer-to-Peer-Sitzungsbericht für die ausgewählte Sitzung an.  <br/> |
|**Absenderbenutzer** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Peer-to-Peer-Sitzung initiiert hat.  <br/> |
|**An Benutzer** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der der Peer-to-Peer-Sitzung beigetreten ist.  <br/> |
|**Modalitäten** <br/> |Ja  <br/> |In der Sitzung verwendete Kommunikationsart, z. B. Instant Messaging, Audio oder Dateiübertragung.  <br/> |
|**Einladungszeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Peer-to-Peer-Sitzungseinladung gesendet wurde.  <br/> |
|**Antwortzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der der eingeladene Benutzer die Sitzungseinladung annahm.  <br/> |
|**Endzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Peer-to-Peer-Sitzung endete.  <br/> |
|**Diagnose-ID** <br/> |Ja  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.
  
**Metriken für konferenzsitzungen**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Konferenz-URI** <br/> |Ja  <br/> |Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Konferenzbericht für die ausgewählte Sitzung an. Erweitern Sie dieses Element, damit der der Bericht Informationen zu den Konferenzteilnehmern anzeigt. Ausführliche Informationen finden Sie im Abschnitt „Metriken für Konferenzteilnehmer“ weiter unten in diesem Thema.  <br/> |
|**Organisator** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Sitzung organisiert hat.  <br/> |
|**Pool** <br/> |Ja  <br/> |Name des in der Konferenz verwendeten Edgeservers (sofern vorhanden).  <br/> |
|**Startzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.  <br/> |
|**Endzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.  <br/> |
   
## <a name="metrics-for-conference-participants"></a>Metriken für Konferenzteilnehmer

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für jeden Teilnehmer einer Konferenz enthaltenen Informationen aufgeführt.
  
**Metriken für Konferenzteilnehmer**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Rolle** <br/> |Nein  <br/> |Konferenzrolle (z. B. Referent) des Benutzers.  <br/> |
|**Teilnehmer** <br/> |Nein  <br/> |SIP-Adresse des Benutzers  <br/> |
|**Verbindung** <br/> |Nein  <br/> |Art der Netzwerkverbindung, z. B. „From Internal“ für interne Verbindungen oder „From PSTN“ für Einwahlbenutzer.  <br/> |
|**Beitrittszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Benutzer der Konferenz beigetreten ist.  <br/> |
|**Beendigungszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Benutzer die Konferenz verlassen hat.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |
   

