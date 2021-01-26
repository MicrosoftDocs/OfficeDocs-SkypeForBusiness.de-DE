---
title: Fehlerlistenbericht in Skype for Business Server
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
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Zusammenfassung: Erfahren Sie mehr über den Fehlerlistenbericht in Skype for Business Server.'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816845"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Fehlerlistenbericht in Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie mehr über den Fehlerlistenbericht in Skype for Business Server.
  
Der Fehlerlistenbericht enthält Informationen zu den einzelnen Teilnehmern, die an einer fehlgeschlagenen Peer-zu-Peer- oder Konferenzsitzung teilnahmen. Diese Informationen umfassen den URI des Benutzers, der das Problem hatte, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.
  
## <a name="accessing-the-failure-list-report"></a>Zugreifen auf den Fehlerlistenbericht

Auf den Fehlerlistenbericht können Sie zugreifen, indem Sie auf eine der folgenden Metriken im Bericht über Fehlerverteilung [in Skype for Business Server klicken:](failure-distribution-report.md)
  
- Häufigste Diagnosegründe (Sitzungen)
    
- Häufigste Modalitäten (Sitzungen)
    
- Häufigste Pools (Sitzungen)
    
- Häufigste Quellen (Sitzungen)
    
- Häufigste Komponenten (Sitzungen)
    
- Häufigste Absenderbenutzer (Sitzungen)
    
- Häufigste Empfängerbenutzer (Sitzungen)
    
- Häufigste Absenderbenutzer-Agents (Sitzungen)
    
Über den Fehlerlistenbericht können Sie auf den Detailbericht über [Peer-zu-Peer-Sitzungen in Skype for Business Server](peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Metrik "Sitzungsdetail" für eine Peer-zu-Peer-Sitzung klicken. Sie können auch auf den Detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Optimale Nutzung des Fehlerlistenberichts

Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode oder jede Diagnose-ID anzeigen, indem Sie einfach den Mauszeiger über diesen Wert bewegen. Wenn Sie z. B. die Maus über die Diagnose-ID 7025 halten, wird Folgendes in einer QuickInfo angezeigt:
  
Interner Serverfehler beim Erstellen von Medien für Den Benutzer.
  
Es ist wichtig zu beachten, dass der Fehlerlistenbericht weder eine einfache Möglichkeit zum direkten Abrufen einer Liste aller Benutzer bietet, die an mindestens einer fehlgeschlagenen Sitzung teilgenommen haben, noch bietet er eine Möglichkeit, zu ermitteln, welche Benutzer am häufigsten an einer fehlgeschlagenen Sitzung beteiligt waren. (Der Fehlerlistenbericht verfügt über keine Filterfunktionen.) Wenn Sie die Daten jedoch exportieren und dann in eine Datei mit durch Kommas getrennten Werten konvertieren, können Sie Windows PowerShell verwenden, um die Antworten auf solche Fragen zu finden. Angenommen, Sie speichern die Daten in einem . CSV-Datei mit C:\Data\Failure_List.csv. Basierend auf den in dieser Datei gespeicherten Daten listet dieser Befehl alle Benutzer auf, die an mindestens einer fehlgeschlagenen Sitzung beteiligt waren: 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Dieser Befehl gibt eine Liste wie die folgenden zurück:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Diese beiden Befehle geben die Gesamtzahl der fehlgeschlagenen Sitzungen zurück, an der die einzelnen Benutzer beteiligt waren:
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Es werden Daten nach dem folgenden Muster zurückgegeben:
  
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

In der folgenden Tabelle sind die Informationen aufgeführt, die im Fehlerlistenbericht für jeden fehlgeschlagenen Anruf angegeben sind.
  
**Metriken im Bericht über Fehlerlisten**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Gemeldete Zeit** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Bericht erfasst wurde.  <br/> |
|**Anforderung** <br/> |Nein  <br/> |Typ der fehlerhaften SIP-Anforderung. Beispiel: INVITE oder BYE.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der gesendet wurde, als die Konferenz fehlgeschlagen ist.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Beitrittskosten (ms)** <br/> |Nein  <br/> |Zeitdauer (in Millisekunden), die der Benutzer für den Konferenz beitritt.  <br/> |
|**Von Benutzer** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.  <br/> |
|**Von Benutzer-Agent** <br/> |Nein  <br/> |Software, die vom Endpunkt des Benutzers verwendet wird, der den Anruf initiiert hat.  <br/> |
|**An Benutzer** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der angerufen wurde.  <br/> |
   

