---
title: Bericht über häufigste Fehler in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Zusammenfassung: Erfahren Sie mehr über den Bericht über häufigste Fehler in Skype for Business Server.'
ms.openlocfilehash: 5b932833aa80d11134133b7b3ed13cdfd2a57e29
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606154"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Bericht über häufigste Fehler in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bericht über häufigste Fehler in Skype for Business Server.
  
Der Bericht über häufigste Fehler bietet einen Überblick über die am häufigsten gemeldeten Fehler mit Trenddarstellung.
  
- **Diagnose-ID**. Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.
    
- **Antwortcode**. Antwortcodes werden in SIP-Kommunikationssitzungen verwendet, um auf SIP-Anforderungen zu reagieren. Angenommen, Ken sendet die INVITE-Anforderung an Pilar Ackerman (d. a. Angenommen, Ken Myer ruft Pilar Ackerman auf). Wenn Pilar antwortet, sendet ihr Telefon den Antwortcode 200 (OK), damit Kens Telefon weiß, dass Pilar beantwortet hat. Der Bericht über häufigste Fehler enthält nur Antwortcodes, die als Reaktion auf einen Anruffehler gesendet wurden. Skype for Business Server verfolgt nicht alle Antwortcodes, die während eines Anrufs ausgegeben wurden.
    
Informationen werden nicht nur für die Gesamtzahl an Sitzungen, in denen ein Fehler aufgetreten ist, gemeldet, sondern auch für die Gesamtzahl der Benutzer, die von den Fehlern betroffen waren.
  
## <a name="accessing-the-top-failures-report"></a>Zugriff auf den Bericht über häufigste Fehler

Der Zugriff auf den Bericht über häufigste Fehler erfolgt von der Überwachungsberichte-Startseite aus. Wenn Sie auf die Metrik "Gemeldete Sitzungen" klicken, gelangen Sie zum [Bericht über Fehlerverteilung in Skype for Business Server](failure-distribution-report.md).
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Beste Nutzung des Berichts häufigster Fehler

Der Bericht über häufigste Fehler ist in einer Hinsicht ungewöhnlich: Er ermöglicht es Ihnen, auf bis zu 5 Diagnose-IDs gleichzeitig zu filtern. (In der Regel können Sie jeweils nur nach einem Element filtern , z. B. nach einer SIP-Adresse des Benutzers.) Um nach mehreren Diagnose-IDs zu filtern, geben Sie einfach jede ID in das Feld "Diagnose-IDs" ein, indem Sie die IDs durch Kommas trennen. (Wenn Sie möchten, können Sie nach jedem Komma ein Leerzeichen belassen.) Zum Beispiel:
  
1011, 2412, 1033, 52116, 1008
  
Wenn Sie dies tun, werden nur fehlerhafte Anrufe, die mindestens eine dieser fünf Diagnose-IDs gemeldet haben, angezeigt.
  
Wenn Sie Ihre Maus über einen Antwortcode bewegen, wird eine QuickInfo angezeigt, die Ihnen mitteilt, was der jeweilige Antwortcode bedeutet. Wenn Sie beispielsweise die Maus über den Antwortcode 486 bewegen, wird folgende Meldung angezeigt:
  
Ausgelastet.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die zurückgegebenen Daten im Bericht über häufigste Fehler nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder dem SIP-Antwortcode für die fehlgeschlagene Sitzung filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Ereignisse nach Stunde, Tag, Woche oder Monat zusammengefasst
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über häufigste Fehler verwenden können.
  
**Filter im Bericht über häufigste Fehler**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ziel** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Aktivitätstyp** <br/> | Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Peer-to-Peer <br/>  Konferenz <br/> |
|**Modalität** <br/> |Derzeit ist nur die Option **[Alle]** verfügbar.  <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.<br/> |
|**Kategorie** <br/> | Der Typ des aufgetretenen Fehlers. Wählen Sie eine der folgenden Optionen aus: <br/>  Erwartete und unerwartete Fehler <br/>  Unerwarteter Fehler <br/>  Ein "erwarteter Fehler" ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf Nicht stören festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt. Ein "unerwarteter Fehler" ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden. <br/> |
|**Antwortcode** <br/> |Der SIP-Antwortcode, der gesendet wird, wenn die Konferenz fehlschlägt. Geben Sie den vollständigen Antwortcode ein. Beispiel:  <br/> 400  <br/> |
|**Diagnose-ID** <br/> |Der eindeutige Bezeichner (im Format eines ms-diagnostics-Headers), der an eine SIP-Nachricht angehängt ist und häufig Informationen enthält, die bei der Problembehandlung hilfreich sind. Diagnoseheader sind optional (es gibt auch SIP-Sitzungen, die keinen solchen Header enthalten), und Diagnose-IDs werden nur für Sitzungen zurückgegeben, bei denen ein Problem aufgetreten ist.  <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über häufigste Fehler angegeben werden.
  
**Metriken im Bericht über häufigste Fehler**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Rank** <br/> |Ja  <br/> |Der relative Rang basierend auf der Anzahl der gemeldeten Sitzungen.  <br/> |
|**Gemeldete Sitzungen** <br/> |Ja  <br/> |Die Gesamtzahl der fehlerhaften Sitzungen basierend auf der Diagnose-ID und dem SIP-Antwortcode.  <br/> |
|**Betroffene Benutzer** <br/> |Ja  <br/> |Die Gesamtzahl der Benutzer, die von der fehlerhaften Sitzung betroffen waren.  <br/> |
|**Fehlerinformationen** <br/> |Nein  <br/> |Genaue Angaben zu dem Fehler, u. a. die Diagnose-ID, der SIP-Antwortcode und eine Beschreibung der Ursache des Sitzungsfehlers.  <br/> |
|**Trend in der Vergangenheit** <br/> |Nein  <br/> |Eine grafische Darstellung der fehlerhaften Sitzungen über einen bestimmten Zeitraum.  <br/> |
   

