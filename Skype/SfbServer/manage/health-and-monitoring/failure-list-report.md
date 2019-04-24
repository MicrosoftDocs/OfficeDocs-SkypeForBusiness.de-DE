---
title: Failure List Report in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Zusammenfassung: Informationen Sie zu den Failure List Report in Skype für Business Server.'
ms.openlocfilehash: f286dfe288b82b1e8ab0f5b4956c4f75c5bd72a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199707"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Failure List Report in Skype für Business Server 
 
**Zusammenfassung:** Informationen Sie zu den Failure List Report in Skype für Business Server.
  
Der Fehlerlistenbericht enthält ausführliche Informationen über die einzelnen Teilnehmer, die an einer fehlerhaften Peer-to-Peer-Sitzung oder Konferenzsitzung beteiligt waren. Diese Informationen umfassen den URI des Benutzers, bei dem das Problem aufgetreten ist, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.
  
## <a name="accessing-the-failure-list-report"></a>Zugriff auf den Fehlerlistenbericht

Failure List Report erfolgt durch Klicken auf eine der folgenden Metriken im [Bericht über Fehlerverteilung in Skype für Business Server](failure-distribution-report.md):
  
- Wichtigste Diagnosegründe (Sitzungen)
    
- Wichtigste Modalitäten (Sitzungen)
    
- Wichtigste Pools (Sitzungen)
    
- Wichtigste Quellen (Sitzungen)
    
- Wichtigste Komponenten (Sitzungen)
    
- Wichtigste Absenderbenutzer (Sitzungen)
    
- Wichtigste Empfängerbenutzer (Sitzungen)
    
- Wichtigste Absenderbenutzer-Agenten (Sitzungen)
    
Über Failure List Report können Sie der [Peer-zu-Peer-Sitzungsbericht in Skype für Business Server](peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Metrik Session Detail für eine Peer-zu-Peer-Sitzung. Sie können ebenfalls auf den detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Bestmögliche Verwendung des Fehlerlistenberichts

Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode bzw. jede Diagnose-ID sehen, indem Sie einfach den Mauszeiger über diesen Wert halten. Wenn Sie zum Beispiel Ihre Maus über die Diagnose-ID 7025 halten, wird in einer QuickInfo folgender Text angezeigt:
  
Interner Serverfehler erstellt Medien für Benutzer.
  
Dabei muss beachtet werden, dass der Fehlerlistenbericht weder eine einfache Methode zum direkten Abrufen einer Liste aller Benutzer, die an mindestens einer fehlerhaften Sitzung beteiligt waren, noch eine Methode zur Ermittlung der Benutzer, die am häufigsten an einer fehlerhaften Sitzung beteiligt waren, darstellt. (Failure List Report hat einerseits keine Filterfunktionen.) Wenn Sie die Daten exportieren und dann in eine CSV-Datei konvertieren, können Sie Windows PowerShell verwenden, Sie Antworten auf Fragen wie die. Zum Beispiel können Sie die Daten in einer CSV-Datei mit dem Namen „C:\Data\Failure_List.csv“ speichern. Auf Basis der in dieser Datei gespeicherten Daten können mithilfe dieses Befehls alle Benutzer aufgelistet werden, die an mindestens einer fehlerhaften Sitzung beteiligt waren: 
  
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
   

