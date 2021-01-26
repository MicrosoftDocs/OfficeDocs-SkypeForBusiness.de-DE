---
title: Bericht über die besten Fehler in Skype for Business Server
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
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Zusammenfassung: Erfahren Sie mehr über den Bericht über die wichtigsten Fehler in Skype for Business Server.'
ms.openlocfilehash: bd03dc921e8df122f4e1ac3ca5cf15195a84b13e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816685"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Bericht über die besten Fehler in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bericht über die besten Fehler in Skype for Business Server.
  
Der Bericht über häufigste Fehler bietet einen Überblick über die am häufigsten gemeldeten Fehler mit Trenddarstellung.
  
- **Diagnose-ID**. Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.
    
- **Antwortcode**. Antwortcodes werden in SIP-Kommunikationssitzungen verwendet, um auf SIP-Anforderungen zu reagieren. Angenommen, Ken sendet die INVITE-Anforderung an Pilar Ackerman (das heißt, Ken Myer ruft Pilar Ackerman an). If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered. Der Bericht über die besten Fehler enthält nur Antwortcodes, die als Reaktion auf einen Anruffehler gesendet wurden. Skype for Business Server verfolgt nicht alle Antwortcodes, die während eines Anrufs ausgegeben wurden.
    
Informationen werden nicht nur für die Gesamtzahl an Sitzungen, in denen ein Fehler aufgetreten ist, gemeldet, sondern auch für die Gesamtzahl der Benutzer, die von den Fehlern betroffen waren.
  
## <a name="accessing-the-top-failures-report"></a>Zugriff auf den Bericht über häufigste Fehler

Der Zugriff auf den Bericht über häufigste Fehler erfolgt von der Überwachungsberichte-Startseite aus. Klicken Sie auf die Metrik "Gemeldete Sitzungen", um zum Bericht über Fehlerverteilung [in Skype for Business Server zu gehen.](failure-distribution-report.md)
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Beste Nutzung des Berichts häufigster Fehler

Der Bericht über die top-Fehler ist in einer Hinsicht ungewöhnlich: Er ermöglicht es Ihnen, nach bis zu fünf Diagnose-IDs auf einmal zu filtern. (In der Regel können Sie immer nur nach einem Element filtern , z. B. nach einer Sip-Benutzeradresse.) Um nach mehreren Diagnose-IDs zu filtern, geben Sie einfach jede ID in das Feld "Diagnose-IDs" ein, und trennen Sie die IDs durch Kommas. (Wenn Sie möchten, können Sie nach jedem Komma ein Leerzeichen hinterlassen.) Zum Beispiel:
  
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
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
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
   

