---
title: Ip Telefon Inventory Report in Skype for Business Server
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
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 'Zusammenfassung: Erfahren Sie mehr über den IP-Telefon-Bestandsbericht in Skype for Business Server.'
ms.openlocfilehash: 00677d5ed31303cd87df6547d2cab99323f6ed53
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630589"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>Ip Telefon Inventory Report in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den IP-Telefon-Bestandsbericht in Skype for Business Server.
  
Der Bericht für den IP-Telefonbestand enthält Informationen zu den IP-Telefonen, die derzeit in der Organisation verwendet werden. Er umfasst eine detaillierte Liste der IP-Telefone, die während des angegebenen Berichtszeitraums tatsächlich verwendet wurden. Mithilfe dieses Berichts können Administratoren unter anderem Informationen dazu erhalten, ob alte oder veraltete Telefone vorhanden sind, die ausgetauscht werden sollten. Zudem können Administratoren darauf hingewiesen werden, dass in der Organisation teure Telefone existieren, die kaum verwendet werden. Solche Informationen können außerordentlich wertvoll sein, wenn es darum geht, neue Telefone zu kaufen oder vorhandene Telefone neu zu verteilen. (Ein Benutzer, der sein teures Telefon selten nutzt, kann beispielsweise gebeten werden, sein Telefon mit einem Benutzer zu tauschen, der sein Telefon häufiger verwendet.)
  
Beachten Sie, dass dieser Bericht einige Einschränkungen aufweist, wenn es darum geht, als wahrer Bestandsbericht verwendet zu werden. Der IP-Telefon Bericht listet lediglich alle Telefone auf, die sich während des angegebenen Zeitraums bei Skype for Business Server angemeldet haben, sortiert nach ihrer letzten Anmeldezeit. Wenn sich ein Telefon während des angegebenen Zeitraums nicht angemeldet hat, wird es nicht im Bestandsbericht aufgeführt. Dazu gehören Telefone, die sich vor Beginn des Zeitraums angemeldet haben und während des angegebenen Zeitintervalls noch angemeldet waren. Angenommen, Sie möchten sich den gesamten Telefonbestand für Juli 2015 ansehen. Nehmen wir auch an, dass sich am 30. Juni 2015 mehrere Telefone bei Skype for Business Server angemeldet haben und seit dem 1. Juli weiterhin angemeldet waren. Diese Telefone werden nicht im Bestandsbericht für den 1. Juli angezeigt.
  
Es ist auch wichtig zu beachten, dass der Bestandsbericht Telefone enthalten kann, die Ihre Organisation nicht mehr verwendet. Angenommen, eine Reihe von Fabrikam-Telefonen ist am 1. Juli 2015 beim System angemeldet; 5 Tage später wurde Ihre Organisation alle diese Fabrikam-Telefone los und ersetzte sie durch ein neueres Contoso-Modell. Die Fabrikam-Telefone werden weiterhin im Bericht "Bestand" angezeigt, einfach weil sie sich im Juli beim System angemeldet haben.
  
Darüber hinaus werden im Bericht für den IP-Telefonbestand keine zusammenfassenden Gesamtzahlen für die verschiedenen Telefontypen angegeben. Nehmen wir beispielsweise an, Sie besitzen 105 Telefone vom Typ Polycom CX600. Aus dem Bericht wird nicht ersichtlich, dass Sie 105 solcher Telefone haben. Stattdessen sehen Sie lediglich 105 separate Einträge für das Modell Polycom Cx600. Die einzige Möglichkeit, um herauszufinden, dass für das Modell Polycom Cx600 105 Einträge vorliegen, besteht darin, diese Einträge manuell zu zählen.
  
> [!TIP]
> Alternativ dazu können Sie die Daten exportieren und die Zählung in Microsoft Excel oder Windows PowerShell vornehmen. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Zugreifen auf den Bericht für den IP-Telefonbestand

Der Zugriff auf den Bericht für den IP-Telefonbestand erfolgt über die Startseite der Überwachungsberichte. Wenn Sie auf die Metrik "Benutzer-URI" klicken, können Sie auf den Benutzeraktivitätsbericht für den jeweiligen Benutzer zugreifen. Wenn Sie für einen Peer-zu-Peer-Anruf auf die Metrik "Letzte Aktivität" klicken, gelangen Sie zum Detailbericht über Peer-zu-Peer-Sitzungen. Wenn Sie für eine Konferenz auf dieselbe Metrik klicken, gelangen Sie zum detaillierten Konferenzbericht.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Optimale Nutzung des Berichts für den IP-Telefonbestand

Wenn Sie nur an Verwendungsinformationen für einen bestimmten Telefontyp interessiert sind (Beispiel: "Wie oft verwenden die Benutzer ein Polycom CX600-Telefon?"), können Sie diese Informationen direkt aus dem Bericht für den IP-Telefonbestand abrufen, indem Sie eine Filterung nach diesem bestimmten Telefontyp ausführen. Wenn Sie jedoch zusammenfassende Informationen für alle Telefone erhalten möchten (wie viele Personen verwenden ein Polycom CX600, wie viele verwenden ein LG-Nortel IP8540 usw.), müssen Sie die Daten exportieren und diese Analyse mithilfe einer anderen Anwendung (z. B. mit Windows PowerShell) ausführen. Nehmen wir beispielsweise an, Sie exportieren die Daten in eine Datei mit durch Komma getrennten Werten (C:\Data\IP_Phone_Inventory_Report.csv). In diesem Fall können Sie die folgenden beiden Befehle verwenden, um für alle Ihre Telefone zusammenfassende Daten bereitzustellen:
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

Dadurch werden Daten zurückgegeben, die den Folgenden ähneln:
  
<pre>
Count    Name
-----    ----
  267    POLYCOM, CX700
  267    POLYCOM, CX600
  166    POLYCOM, C
   68    Microsoft, CPE
   64    LG-Nortel, IP8540
   59    Aastra, 6725ip
   37    LG-Nortel, IP
   22    POLYCOM, CX3000
   11    Microsoft, CPE_A
    9    POLYCOM, CX500
    7    Aastra, 6721ip
</pre>

Gleichermaßen erhalten Sie mithilfe dieser beiden Befehle Informationen dazu, welche Telefone zwar beim System angemeldet, aber tatsächlich nie zum Telefonieren genutzt wurden (der Wert der Metrik "Letzte Aktivität" ist leer und gibt somit an, dass es keine letzte Aktivität gab):
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

Dabei werden für alle nicht verwendeten Telefone Daten zurückgegeben, die den Folgenden ähneln:
  
<pre>
Manufacturer     : POLYCOM
Hardware version : CX600
MAC address      : 00-04-F2-00-01-76
User URI         : 422
User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
Last logon time  : 8/30/2010 4:44:48 PM
Last logoff time : 8/30/2010 5:59:07 PM
Last activity    :
</pre>

Eine weitere interessante Möglichkeit zur Verwendung des IP-Telefon Bestandsberichts ist folgende: Wenn Sie die MAC-Adresse eines IP-Telefon können Sie den Benutzer ermitteln, der das Telefon zuletzt verwendet hat, indem Sie einfach diese Adresse in das TEXTfeld der MAC-Adresse eingeben. Der Bericht "IP Telefon Inventar" meldet dann (unter anderem) die SIP-Adresse des Benutzers zurück, der sich zuletzt mit diesem Telefon angemeldet hat. Alternativ können Sie eine SIP-Adresse des Benutzers (im Präfixfeld "Benutzer-URI") eingeben, um alle Telefone zu ermitteln, die von diesem Benutzer verwendet wurden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der IP-Telefonbestand ermöglicht Ihnen beispielsweise das Anzeigen von Telefonen eines bestimmten Herstellers oder sogar einer bestimmten Version dieser Telefone. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht für den IP-Telefonbestand verwenden können.
  
**Bericht für den IP-Telefonbestand – Filter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ziel** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Hersteller** <br/> |Name des Herstellers des IP-Telefons. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.  <br/> |
|**Hardwareversion** <br/> |Versionsnummer des IP-Telefons; mit den Filtern für den Hersteller und die Hardwareversion können Sie einen bestimmten Telefontyp eindeutig identifizieren. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.  <br/> |
|**Benutzer-Agent** <br/> |ID für die vom IP-Telefon verwendete Software. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.  <br/> |
|**MAC-Adresse** <br/> |Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse (Media Access Control) wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.  <br/> Zum Suchen nach Datensätzen mit einer bestimmten MAC-Adresse geben Sie einfach diese Adresse ein, z. B.:  <br/> 00-08-5D-16-16-48  <br/> Die Adresse muss vollständig eingegeben werden. Ein Teil einer Adresse (z. B. 00-08-5D) gibt keine Daten zurück.  <br/> |
|**Letzte Aktivität vor (Tage)** <br/> | Wählen Sie einen der folgenden Werte: <br/>  [Alle] <br/>  10  <br/>  20 <br/>  30 <br/> |
|**Zuletzt abgemeldet vor (Tage)** <br/> | Wählen Sie einen der folgenden Werte: <br/>  [Alle] <br/>  10  <br/>  20 <br/>  30 <br/> |
|**Präfix des Benutzer-URI** <br/> |SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.  <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht für den IP-Telefonbestand angegeben werden.
  
**Bericht für den IP-Telefonbestand – Metriken**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Hersteller** <br/> |Ja  <br/> |Name des Herstellers des IP-Telefons.  <br/> |
|**Hardwareversion** <br/> |Ja  <br/> |Versionsnummer des IP-Telefons.  <br/> |
|**MAC-Adresse** <br/> |Ja  <br/> |Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.  <br/> |
|**Benutzer-URI** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.  <br/> |
|**Benutzer-Agent** <br/> |Ja  <br/> |ID für die vom IP-Telefon verwendete Software.  <br/> |
|**Zuletzt angemeldet um:** <br/> |Ja  <br/> |Datum und Uhrzeit der letzten Anmeldung des IP-Telefons bei Skype for Business Server.  <br/> |
|**Zuletzt abgemeldet um:** <br/> |Ja  <br/> |Datum und Uhrzeit, zu denen sich das IP-Telefon zuletzt von Skype for Business Server abgemeldet hat.  <br/> |
|**Letzte Aktivität** <br/> |Ja  <br/> |Datum und Uhrzeit der letzten Verwendung des IP-Telefons.  <br/> |
   

