---
title: Fehlerlistenbericht in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Zusammenfassung: Informationen Sie zu den Failure List Report in Skype für Business Server 2015.'
ms.openlocfilehash: ef5b11f92997e6919de0fd9056acdeebddc898d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a>Fehlerlistenbericht in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Failure List Report in Skype für Business Server 2015.
  
Der Fehlerlistenbericht enthält ausführliche Informationen über die einzelnen Teilnehmer, die an einer fehlerhaften Peer-to-Peer-Sitzung oder Konferenzsitzung beteiligt waren. Diese Informationen umfassen den URI des Benutzers, bei dem das Problem aufgetreten ist, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.
  
## <a name="accessing-the-failure-list-report"></a>Zugriff auf den Fehlerlistenbericht

Failure List Report erfolgt durch Klicken auf eine der folgenden Metriken im [Bericht über Fehlerverteilung in Skype für Business Server 2015](failure-distribution-report.md):
  
- Wichtigste Diagnosegründe (Sitzungen)
    
- Wichtigste Modalitäten (Sitzungen)
    
- Wichtigste Pools (Sitzungen)
    
- Wichtigste Quellen (Sitzungen)
    
- Wichtigste Komponenten (Sitzungen)
    
- Wichtigste Absenderbenutzer (Sitzungen)
    
- Wichtigste Empfängerbenutzer (Sitzungen)
    
- Wichtigste Absenderbenutzer-Agenten (Sitzungen)
    
Über Failure List Report können Sie der [Peer-zu-Peer-Sitzungsbericht in Skype für Business Server 2015](peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Metrik Session Detail für eine Peer-zu-Peer-Sitzung. Sie können ebenfalls auf den detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Bestmögliche Verwendung des Fehlerlistenberichts

Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode bzw. jede Diagnose-ID sehen, indem Sie einfach den Mauszeiger über diesen Wert halten. Wenn Sie zum Beispiel Ihre Maus über die Diagnose-ID 7025 halten, wird in einer QuickInfo folgender Text angezeigt:
  
Interner Serverfehler erstellt Medien für Benutzer.
  
Dabei muss beachtet werden, dass der Fehlerlistenbericht weder eine einfache Methode zum direkten Abrufen einer Liste aller Benutzer, die an mindestens einer fehlerhaften Sitzung beteiligt waren, noch eine Methode zur Ermittlung der Benutzer, die am häufigsten an einer fehlerhaften Sitzung beteiligt waren, darstellt. (Failure List Report hat einerseits keine Filterfunktionen.) Wenn Sie die Daten exportieren und dann in eine CSV-Datei konvertieren, können Sie Windows PowerShell verwenden, Sie Antworten auf Fragen wie die. Zum Beispiel können Sie die Daten in einer CSV-Datei mit dem Namen „C:\Data\Failure_List.csv“ speichern. Auf Basis der in dieser Datei gespeicherten Daten können mithilfe dieses Befehls alle Benutzer aufgelistet werden, die an mindestens einer fehlerhaften Sitzung beteiligt waren: 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Die Ausgabe für den Befehl ist eine Liste, die der folgenden Liste ähnelt:
  
```
From user
----
Pilar.Ackerman@litwareinc.com
Henrik.Jensen@litwareinc.com
Gilead.Amosnino@litwareinc.com
David.Ahs@litwareinc.com
Ken.Myer@litwareinc.com
```

Diese beiden Befehle melden die Gesamtzahl der fehlerhaften Sitzungen zurück, an denen Benutzer beteiligt waren:
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:
  
```
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
```

## <a name="filters"></a>Filter

Keine. Sie können den Fehlerlistenbericht nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Fehlerlistenbericht enthaltenen Informationen für jeden fehlerhaften Anruf aufgeführt.
  
**Anruflistenbericht-Metriken Failure**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Gemeldeter Zeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit der Aufzeichnung des Berichts.  <br/> |
|**Anforderung** <br/> |Nein  <br/> |Typ der fehlerhaften SIP-Anforderung. Beispiel: INVITE oder BYE.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der bei einem Konferenzfehler gesendet wurde.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Beitrittszeitraum (ms)** <br/> |Nein  <br/> |Zeitraum (in Millisekunden), der erforderlich ist, damit der Benutzer der Konferenz beitreten kann.  <br/> |
|**Absenderbenutzer** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.  <br/> |
|**Von Benutzeragent** <br/> |Nein  <br/> |Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.  <br/> |
|**An Benutzer** <br/> |Nein  <br/> |SIP-Adresse des Benutzers, der angerufen wurde.  <br/> |
   

