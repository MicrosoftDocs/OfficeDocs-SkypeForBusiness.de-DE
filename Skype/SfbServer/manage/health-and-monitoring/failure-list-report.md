---
title: Bericht zur Fehlerliste in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Zusammenfassung: erfahren Sie mehr über den Bericht zur Fehlerliste in Skype for Business Server.'
ms.openlocfilehash: 72637863d7a15d26ea997de8a9c3526279afc57f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305759"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Bericht zur Fehlerliste in Skype for Business Server 
 
**Zusammenfassung:** Informieren Sie sich über den Bericht Fehlerliste in Skype for Business Server.
  
Der Fehlerlistenbericht enthält ausführliche Informationen über die einzelnen Teilnehmer, die an einer fehlerhaften Peer-to-Peer-Sitzung oder Konferenzsitzung beteiligt waren. Diese Informationen umfassen den URI des Benutzers, bei dem das Problem aufgetreten ist, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.
  
## <a name="accessing-the-failure-list-report"></a>Zugriff auf den Fehlerlistenbericht

Der fehlerlistenbericht wird durch Klicken auf eine der folgenden Metriken im Bericht " [Fehlerverteilung" in Skype for Business Server](failure-distribution-report.md)aufgerufen:
  
- Wichtigste Diagnosegründe (Sitzungen)
    
- Wichtigste Modalitäten (Sitzungen)
    
- Wichtigste Pools (Sitzungen)
    
- Wichtigste Quellen (Sitzungen)
    
- Wichtigste Komponenten (Sitzungen)
    
- Wichtigste Absenderbenutzer (Sitzungen)
    
- Wichtigste Empfängerbenutzer (Sitzungen)
    
- Wichtigste Absenderbenutzer-Agenten (Sitzungen)
    
Im Bericht Fehlerliste können Sie auf den [Bericht Peer-to-Peer-Sitzungsdetails in Skype for Business Server](peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Sitzungs Detail Metrik für eine Peer-to-Peer-Sitzung klicken. Sie können ebenfalls auf den detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Bestmögliche Verwendung des Fehlerlistenberichts

Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode bzw. jede Diagnose-ID sehen, indem Sie einfach den Mauszeiger über diesen Wert halten. Wenn Sie zum Beispiel Ihre Maus über die Diagnose-ID 7025 halten, wird in einer QuickInfo folgender Text angezeigt:
  
Interner Serverfehler erstellt Medien für Benutzer.
  
Dabei muss beachtet werden, dass der Fehlerlistenbericht weder eine einfache Methode zum direkten Abrufen einer Liste aller Benutzer, die an mindestens einer fehlerhaften Sitzung beteiligt waren, noch eine Methode zur Ermittlung der Benutzer, die am häufigsten an einer fehlerhaften Sitzung beteiligt waren, darstellt. (Zum einen hat der fehlerlistenbericht keine Filterfunktionen.) Wenn Sie die Daten exportieren und dann in eine Datei mit Komma getrennten Werten konvertieren, können Sie Windows PowerShell verwenden, um Antworten auf Fragen wie diese zu finden. Zum Beispiel können Sie die Daten in einer CSV-Datei mit dem Namen „C:\Data\Failure_List.csv“ speichern. Auf Basis der in dieser Datei gespeicherten Daten können mithilfe dieses Befehls alle Benutzer aufgelistet werden, die an mindestens einer fehlerhaften Sitzung beteiligt waren: 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Die Ausgabe für den Befehl ist eine Liste, die der folgenden Liste ähnelt:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Diese beiden Befehle melden die Gesamtzahl der fehlerhaften Sitzungen zurück, an denen Benutzer beteiligt waren:
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>Filter

Keine. Sie können den Fehlerlistenbericht nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Fehlerlistenbericht enthaltenen Informationen für jeden fehlerhaften Anruf aufgeführt.
  
**Metriken des Fehlerlistenberichts**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Gemeldeter Zeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit der Aufzeichnung des Berichts.  <br/> |
|**Anforderung** <br/> |Nein  <br/> |Typ der fehlerhaften SIP-Anforderung. Beispiel: INVITE oder BYE.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der bei einem Konferenzfehler gesendet wurde.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Beitrittszeitraum (ms)** <br/> |Nein  <br/> |Zeitraum (in Millisekunden), der erforderlich ist, damit der Benutzer der Konferenz beitreten kann.  <br/> |
|**Absenderbenutzer** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.  <br/> |
|**Von Benutzeragent** <br/> |Nein  <br/> |Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.  <br/> |
|**An Benutzer** <br/> |Nein  <br/> |SIP-Adresse des Benutzers, der angerufen wurde.  <br/> |
   

