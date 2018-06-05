---
title: Inventurbericht über IP-Telefon in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 'Zusammenfassung: Erfahren Sie mehr über das IP-Telefonbestand in Skype für Business Server 2015.'
ms.openlocfilehash: fd68e94f9d4c30aafb86302d8211b52909f737db
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569554"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server-2015"></a>Inventurbericht über IP-Telefon in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den IP-Telefonbestand in Skype für Business Server 2015.
  
Der Bericht für den IP-Telefonbestand enthält Informationen zu den IP-Telefonen, die derzeit in der Organisation verwendet werden. Er umfasst eine detaillierte Liste der IP-Telefone, die während des angegebenen Berichtszeitraums tatsächlich verwendet wurden. Mithilfe dieses Berichts können Administratoren unter anderem Informationen dazu erhalten, ob alte oder veraltete Telefone vorhanden sind, die ausgetauscht werden sollten. Zudem können Administratoren darauf hingewiesen werden, dass in der Organisation teure Telefone existieren, die kaum verwendet werden. Solche Informationen können außerordentlich wertvoll sein, wenn es darum geht, neue Telefone zu kaufen oder vorhandene Telefone neu zu verteilen. (Ein Benutzer, der sein teures Telefon selten nutzt, kann beispielsweise gebeten werden, sein Telefon mit einem Benutzer zu tauschen, der sein Telefon häufiger verwendet.)
  
Beachten Sie, dass dieser Bericht jedoch einige Einschränkungen vorhanden ist, wenn es darum geht, als true Inventarbericht verwendet wird. Die IP-Telefon Bericht listet einerseits einfach alle Telefone, die sich Skype für Business Server während des angegebenen Zeitraums, sortiert nach der letzten Anmeldung angemeldet. Wenn ein Telefon während des angegebenen Zeitraums nicht anmelden wird dann sie nicht in den Bericht aufgelistet werden. Dazu gehören Telefone, die angemeldet, um den Zeitraum gestartet und noch während des angegebenen Zeitintervalls angemeldet sind. Angenommen Sie, dass Sie alle telefonbestand für Juli 2015 anzeigen möchten. Nehmen wir auch, dass mehrere Telefone an Skype für Business Server auf 30 Juni 2015 angemeldet und noch am 1. Juli angemeldet sind. Diese Telefone werden nicht auf den Bericht für den 1. Juli angezeigt.
  
Weiterhin muss beachtet werden, dass der Bestandsbericht Telefone einschließen kann, die in Ihrer Organisation nicht mehr verwendet werden. Angenommen, eine bestimmte Anzahl Telefone von Fabrikam wurde am Mittwoch, 1. Juli 2015 beim System angemeldet. Fünf Tage später hat sich Ihre Organisation dazu entschlossen, diese Fabrikam-Telefone durch ein neueres Modell von Contoso auszutauschen. Die Fabrikam-Telefone werden jedoch weiterhin im „Bestandsbericht“ aufgeführt, weil sie im Juli beim System angemeldet wurden.
  
Darüber hinaus werden im Bericht für den IP-Telefonbestand keine zusammenfassenden Gesamtzahlen für die verschiedenen Telefontypen angegeben. Nehmen wir beispielsweise an, Sie besitzen 105 Telefone vom Typ Polycom CX600. Aus dem Bericht wird nicht ersichtlich, dass Sie 105 solcher Telefone haben. Stattdessen sehen Sie lediglich 105 separate Einträge für das Modell Polycom Cx600. Die einzige Möglichkeit, um herauszufinden, dass für das Modell Polycom Cx600 105 Einträge vorliegen, besteht darin, diese Einträge manuell zu zählen.
  
> [!TIP]
> Alternativ dazu können Sie die Daten exportieren und die Zählung in Microsoft Excel oder Windows PowerShell vornehmen. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Zugreifen auf den Bericht für den IP-Telefonbestand

Der Zugriff auf den Bericht für den IP-Telefonbestand erfolgt über die Startseite der Überwachungsberichte. Wenn Sie auf die Metrik „Benutzer-URI“ klicken, können Sie auf den Benutzeraktivitätsbericht für den jeweiligen Benutzer zugreifen. Wenn Sie für einen Peer-to-Peer-Anruf auf die Metrik „Letzte Aktivität“ klicken, gelangen Sie zum Detailbericht über Peer-to-Peer-Sitzungen. Wenn Sie für eine Konferenz auf dieselbe Metrik klicken, gelangen Sie zum detaillierten Konferenzbericht.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Optimale Nutzung des Berichts für den IP-Telefonbestand

Wenn Sie nur an Verwendungsinformationen für einen bestimmten Telefontyp interessiert sind (Beispiel: „Wie oft verwenden die Benutzer ein Polycom CX600-Telefon?“), können Sie diese Informationen direkt aus dem Bericht für den IP-Telefonbestand abrufen, indem Sie eine Filterung nach diesem bestimmten Telefontyp ausführen. Wenn Sie jedoch zusammenfassende Informationen für alle Telefone erhalten möchten (wie viele Personen verwenden ein Polycom CX600, wie viele verwenden ein LG-Nortel IP8540 usw.), müssen Sie die Daten exportieren und diese Analyse mithilfe einer anderen Anwendung (z. B. mit Windows PowerShell) ausführen. Nehmen wir beispielsweise an, Sie exportieren die Daten in eine Datei mit durch Komma getrennten Werten (C:\Data\IP_Phone_Inventory_Report.csv). In diesem Fall können Sie die folgenden beiden Befehle verwenden, um für alle Ihre Telefone zusammenfassende Daten bereitzustellen:
  
```
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:
  
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

Gleichermaßen erhalten Sie mithilfe dieser beiden Befehle Informationen dazu, welche Telefone zwar beim System angemeldet, aber tatsächlich nie zum Telefonieren genutzt wurden (der Wert der Metrik „Letzte Aktivität“ ist leer und gibt somit an, dass es keine letzte Aktivität gab):
  
```
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

Eine andere interessante Möglichkeit, verwenden Sie die IP-Telefonbestand ist dies: Wenn Sie die MAC-Adresse eines IP-Telefons verfügen, Sie, die Benutzer, die zuletzt dieses Telefon verwendet einfach herausfinden können, indem Sie diese Adresse in das Textfeld MAC-Adresse eingeben. Der IP-Telefonbestand-Bericht melden zurück (unter anderem) die SIP-Adresse des Benutzers, die zuletzt mit dieses Telefon angemeldet. Alternativ können Sie einen Benutzer-SIP-Adresse (im Feld Benutzer-URI Präfix) eingeben, um herauszufinden, alle Telefone, die von diesem Benutzer verwendet wurden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der IP-Telefonbestand ermöglicht Ihnen beispielsweise das Anzeigen von Telefonen eines bestimmten Herstellers oder sogar einer bestimmten Version dieser Telefone. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht für den IP-Telefonbestand verwenden können.
  
**IP-Telefon Inventar Berichtsfilter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Hersteller** <br/> |Name des Herstellers des IP-Telefons. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.  <br/> |
|**Hardwareversion** <br/> |Versionsnummer des IP-Telefons; mit den Filtern für den Hersteller und die Hardwareversion können Sie einen bestimmten Telefontyp eindeutig identifizieren. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.  <br/> |
|**Benutzer-Agent** <br/> |ID für die vom IP-Telefon verwendete Software. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.  <br/> |
|**MAC-Adresse** <br/> |Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse (Media Access Control) wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.  <br/> Zum Suchen nach Datensätzen mit einer bestimmten MAC-Adresse geben Sie einfach diese Adresse ein, z. B.:  <br/> 00-08-5D-16-16-48  <br/> Die Adresse muss vollständig eingegeben werden. Ein Teil einer Adresse (z. B. 00-08-5D) gibt keine Daten zurück.  <br/> |
|**Letzte Aktivität vor (Tage)** <br/> | Wählen Sie einen der folgenden Werte: <br/>  [Alle] <br/>  10 <br/>  20 <br/>  30 <br/> |
|**Zuletzt abgemeldet vor (Tage):** <br/> | Wählen Sie einen der folgenden Werte: <br/>  [Alle] <br/>  10 <br/>  20 <br/>  30 <br/> |
|**Präfix des Benutzer-URI** <br/> |SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.  <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht für den IP-Telefonbestand angegeben werden.
  
**Metriken im Bericht über IP-Telefon-Inventar**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Hersteller** <br/> |Ja  <br/> |Name des Herstellers des IP-Telefons.  <br/> |
|**Hardwareversion** <br/> |Ja  <br/> |Versionsnummer des IP-Telefons.  <br/> |
|**MAC-Adresse** <br/> |Ja  <br/> |Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.  <br/> |
|**Benutzer-URI** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.  <br/> |
|**Benutzer-Agent** <br/> |Ja  <br/> |ID für die vom IP-Telefon verwendete Software.  <br/> |
|**Zuletzt angemeldet um:** <br/> |Ja  <br/> |Datum und Uhrzeit, zu der IP-Telefon zuletzt an Skype für Business Server angemeldet.  <br/> |
|**Zuletzt abgemeldet um:** <br/> |Ja  <br/> |Datum und Uhrzeit Abmeldung des IP-Telefons zuletzt von Skype für Business Server.  <br/> |
|**Letzte Aktivität** <br/> |Ja  <br/> |Datum und Uhrzeit der letzten Verwendung des IP-Telefons.  <br/> |
   

