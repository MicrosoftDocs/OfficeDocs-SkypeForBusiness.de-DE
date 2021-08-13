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
ms.openlocfilehash: b132982af91f81af1ac1d151853a3f7fdc597ff31476e6a5484fc04b9d9efa4d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301351"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Fehlerlistenbericht in Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie mehr über den Fehlerlistenbericht in Skype for Business Server.
  
Der Fehlerlistenbericht enthält Informationen zu den einzelnen Teilnehmern, die an einer fehlgeschlagenen Peer-to-Peer- oder Konferenzsitzung teilgenommen haben. Diese Informationen enthalten den URI des Benutzers, der das Problem aufgetreten ist, sowie den SIP-Antwortcode und die Diagnose-ID, die mit dem Fehler verknüpft sind.
  
## <a name="accessing-the-failure-list-report"></a>Zugreifen auf den Fehlerlistenbericht

Der Zugriff auf den Fehlerlistenbericht erfolgt durch Klicken auf eine der folgenden Metriken im [Bericht über Fehlerverteilung in Skype for Business Server:](failure-distribution-report.md)
  
- Häufigste Diagnosegründe (Sitzungen)
    
- Häufigste Modalitäten (Sitzungen)
    
- Häufigste Pools (Sitzungen)
    
- Häufigste Quellen (Sitzungen)
    
- Häufigste Komponenten (Sitzungen)
    
- Häufigste Absenderbenutzer (Sitzungen)
    
- Häufigste Empfängerbenutzer (Sitzungen)
    
- Häufigste Absenderbenutzer-Agents (Sitzungen)
    
Über den Fehlerlistenbericht können Sie auf den [Detailbericht über Peer-to-Peer-Sitzungen in Skype for Business Server](peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Metrik "Sitzungsdetail" für eine Peer-to-Peer-Sitzung klicken. Sie können auch auf den Detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Optimale Verwendung des Fehlerlistenberichts

Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode oder jede Diagnose-ID anzeigen, indem Sie einfach den Mauszeiger über diesen Wert halten. Wenn Sie beispielsweise den Mauszeiger über die Diagnose-ID 7025 halten, wird Folgendes in einer QuickInfo angezeigt:
  
Interner Serverfehler beim Erstellen von Medien für den Benutzer.
  
Es ist wichtig zu beachten, dass der Fehlerlistenbericht weder eine einfache Möglichkeit zum direkten Abrufen einer Liste aller Benutzer bietet, die an mindestens einer fehlgeschlagenen Sitzung teilgenommen haben, noch eine Möglichkeit bietet, zu bestimmen, welche Benutzer am häufigsten an einer fehlgeschlagenen Sitzung beteiligt waren. (Der Fehlerlistenbericht verfügt über keine Filterfunktionen.) Wenn Sie die Daten exportieren und dann in eine durch Trennzeichen getrennte Wertedatei konvertieren, können Sie Windows PowerShell verwenden, um Antworten auf Fragen wie diese zu finden. Angenommen, Sie speichern die Daten in einer .CSV Datei mit dem Namen C:\Data\Failure_List.csv. Basierend auf den in dieser Datei gespeicherten Daten listet dieser Befehl alle Benutzer auf, die an mindestens einer fehlgeschlagenen Sitzung beteiligt waren: 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Mit diesem Befehl wird eine Liste zurückgegeben, die der folgenden ähnelt:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Diese beiden Befehle geben die Gesamtzahl der fehlgeschlagenen Sitzungen zurück, an denen jeder Benutzer beteiligt war:
  
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

In der folgenden Tabelle sind die Informationen aufgeführt, die im Fehlerlistenbericht für jeden fehlgeschlagenen Aufruf angegeben sind.
  
**Fehlerlistenberichtsmetriken**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Gemeldete Zeit** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Bericht erfasst wurde.  <br/> |
|**Anforderung** <br/> |Nein  <br/> |Typ der fehlerhaften SIP-Anforderung. Beispiel: INVITE oder BYE.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der gesendet wird, wenn die Konferenz fehlgeschlagen ist.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Beitrittskostenzeit (ms)** <br/> |Nein  <br/> |Zeit (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.  <br/> |
|**Von Benutzer** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.  <br/> |
|**Von Benutzer-Agent** <br/> |Nein  <br/> |Software, die vom Endpunkt des Benutzers verwendet wird, der den Anruf initiiert hat.  <br/> |
|**An Benutzer** <br/> |Nein  <br/> |SIP-Adresse des Benutzers, der angerufen wurde.  <br/> |
   

