---
title: Bericht über häufigste Fehler in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Zusammenfassung: Informationen Sie zu Skype für Business Server Bericht über häufigste Fehler.'
ms.openlocfilehash: a2e8b0592e7525b1102d198de32643109304ed82
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897636"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Bericht über häufigste Fehler in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu Skype für Business Server Bericht über häufigste Fehler.
  
Der Bericht über häufigste Fehler bietet einen Überblick über die am häufigsten gemeldeten Fehler mit Trenddarstellung. Die Fehler basieren auf einer Kombination der folgenden zwei Metriken:
  
- **Diagnose-ID**. Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.
    
- **Antwortcode**. Antwortcodes werden in SIP-kommunikationssitzungen verwendet, um auf SIP-Anforderungen zu reagieren. Angenommen Sie, dass Ken INVITE-Anforderung an den Pilar Ackerman sendet (d. h., angenommen, Ken Myer "Pilar Ackerman" aufruft). Wenn Pilar annimmt, wird ihr Telefon Navigate wissen, dass Pilar beantwortet hat Ken Telefon Antwortcode 200 (OK), senden. Der Bericht über häufigste Fehler enthält nur Antwortcodes, die als Reaktion auf einen Aufruf des gesendet wurden. Skype für Business Server werden nicht alle im Verlauf eines Aufrufs ausgestellt Antwortcodes mitverfolgen.
    
Informationen werden nicht nur für die Gesamtzahl an Sitzungen, in denen ein Fehler aufgetreten ist, gemeldet, sondern auch für die Gesamtzahl der Benutzer, die von den Fehlern betroffen waren.
  
## <a name="accessing-the-top-failures-report"></a>Zugriff auf den Bericht über häufigste Fehler

Der Zugriff auf den Bericht über häufigste Fehler erfolgt von der Startseite für Überwachungsberichte aus. Durch Klicken auf die Metrik "gemeldet Sitzungen" gelangen Sie zu dem [Bericht über Fehlerverteilung in Skype für Business Server](failure-distribution-report.md).
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Beste Nutzung des Berichts häufigster Fehler

Der Bericht über häufigste Fehler ist in einer Hinsicht ungewöhnlich: sie können bis zu 5 Diagnose-IDs gleichzeitig filtern. (In der Regel können Sie nur ein einzelnes Element - wie SIP-Adresse für einen Benutzer - jeweils filtern.) Um mehrere Diagnose-IDs zu filtern, geben Sie einfach jede-ID im Feld Diagnose-IDs, die IDs durch Kommas voneinander getrennt ein. (Wenn Sie möchten, können Sie ein Leerzeichen nach jedem Komma beibehalten.) Zum Beispiel:
  
1011, 2412, 1033, 52116, 1008
  
Wenn Sie dies tun, werden nur fehlerhafte Anrufe, die mindestens eine dieser fünf Diagnose-IDs gemeldet haben, angezeigt.
  
Wenn Sie Ihre Maus über einen Antwortcode bewegen, wird eine QuickInfo angezeigt, die Ihnen mitteilt, was der jeweilige Antwortcode bedeutet. Wenn Sie beispielsweise die Maus über den Antwortcode 486 bewegen, wird folgende Meldung angezeigt:
  
Ausgelastet.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die zurückgegebenen Daten im Bericht über häufigste Fehler nach Kriterien wie dem Aktivitätstyp (Peer-to-Peer-Sitzung oder Konferenzsitzung) oder dem SIP-Antwortcode für die fehlgeschlagene Sitzung filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Ereignisse nach Stunde, Tag, Woche oder Monat zusammengefasst
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über häufigste Fehler verwenden können.
  
**Filter im Bericht über häufigste Fehler**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Aktivitätstyp** <br/> | Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Peer-to-Peer <br/>  Konferenz <br/> |
|**Modalität** <br/> |Derzeit ist nur die Option **[Alle]** verfügbar.  <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
|**Kategorie** <br/> | Der Typ des aufgetretenen Fehlers. Wählen Sie eine der folgenden Optionen aus: <br/>  Erwartete und unerwartete Fehler <br/>  Unerwarteter Fehler <br/>  Ein „erwarteter Fehler“ ist ein Fehler, der zu erwarten ist. Hat beispielsweise ein Benutzer seinen Status auf „Nicht stören“ gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen. Ein „unerwarteter Fehler“ ist ein Fehler, der in einem ansonsten scheinbar fehlerfreien System auftritt. Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet. In diesem Fall würde der Fehler als „unerwartet“ gekennzeichnet. <br/> |
|**Antwortcode** <br/> |Der SIP-Antwortcode, der gesendet wird, wenn die Konferenz fehlschlägt. Geben Sie den vollständigen Antwortcode ein. Beispiel:  <br/> 400  <br/> |
|**Diagnose-ID** <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über häufigste Fehler angegeben werden.
  
**Metriken im Bericht über häufigste Fehler**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Rang** <br/> |Ja  <br/> |Der relative Rang basierend auf der Anzahl der gemeldeten Sitzungen.  <br/> |
|**Gemeldete Sitzungen** <br/> |Ja  <br/> |Die Gesamtzahl der fehlerhaften Sitzungen basierend auf der Diagnose-ID und dem SIP-Antwortcode.  <br/> |
|**Betroffene Benutzer** <br/> |Ja  <br/> |Die Gesamtzahl der Benutzer, die von der fehlerhaften Sitzung betroffen waren.  <br/> |
|**Fehlerinformationen** <br/> |Nein  <br/> |Genaue Angaben zu dem Fehler, u. a. die Diagnose-ID, der SIP-Antwortcode und eine Beschreibung der Ursache des Sitzungsfehlers.  <br/> |
|**Trend in der Vergangenheit** <br/> |Nein  <br/> |Eine grafische Darstellung der fehlerhaften Sitzungen über einen bestimmten Zeitraum.  <br/> |
   

