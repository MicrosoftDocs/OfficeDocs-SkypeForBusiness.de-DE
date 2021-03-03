---
title: Gerätebericht in Skype for Business Server
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
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Zusammenfassung: Erfahren Sie mehr über den Gerätebericht in Skype for Business Server.'
ms.openlocfilehash: 2471f232256e4715f271cd310f0b1415555ca4c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826415"
---
# <a name="device-report-in-skype-for-business-server"></a>Gerätebericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Gerätebericht in Skype for Business Server.
  
Der Gerätebericht kann besser als "Mikrofon- und Lautsprecherbericht" betitelt werden. Der Grund dafür ist, dass der Gerätebericht anrufbezogene Metriken (z. B. Prozentsatz schlechter Anrufe, Echo und Sprachumschaltzeit) abruft, die nach den im Anruf verwendeten Mikrofonen und Lautsprechern gruppieren. Wenn Sie an #A0 interessiert sind (auch als "Geräte" bezeichnet), verwenden Sie stattdessen den [#A1 in Skype for Business Server.](ip-phone-inventory-report.md)
  
Der Gerätebericht ist für Administratoren äußerst nützlich, um festzustellen, ob ein bestimmter Gerätetyp ein hohes Volumen an Anrufen schlechter Qualität als andere hat. Dies könnte wiederum alle Entscheidungen beeinflussen, die Sie treffen müssen, wenn es an der Zeit ist, neue Geräte zu kaufen oder vorhandene Geräte zu ersetzen.
  
Standardmäßig basieren die im Gerätebericht angezeigten Informationen auch auf dem Mikrofon (dem Aufnahmegerät) und den Lautsprechern/Headsets (dem Rendergerät), die im Anruf verwendet werden. Angenommen, Sie haben mehrere Benutzer, die das folgende Aufnahmegerät und das folgende Rendergerät verwenden: Standardmäßig basieren die im Gerätebericht angezeigten Informationen auch auf dem Mikrofon (dem Aufnahmegerät) und den Lautsprechern/Headsets (dem Rendergerät), die im Anruf verwendet werden. Angenommen, Sie haben mehrere Benutzer, die das folgende Aufnahmegerät und das folgende Rendergerät verwenden:
  
- Aufnahmegerät – Mikrofon (SoundMAX Integrated Digital HD Audio)
    
- Rendergerät – Headset-Kopfhörer (Microsoft LifeChat LX-3000)
    
Wenn diese Benutzer insgesamt 254 Anrufe vorgenommen haben, wird im Bericht ein Eintrag wie dieser zu sehen sein:
  
|**Aufnahmegerät**|**Darstellungsgerät**|**Anruflautstärke**|
|:-----|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Headset Earphone (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Angenommen, Sie haben eine Reihe von Benutzern, die dasselbe Aufnahmegerät, aber ein anderes Rendergerät verwenden. In diesem Fall haben Sie einen zweiten Zeileneintrag im Bericht, einen eintrag für diese eindeutige Kombination aus Aufnahmegerät und Rendergerät:
  
|**Aufnahmegerät**|**Darstellungsgerät**|**Anruflautstärke**|
|:-----|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Headset Earphone (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Lautsprecher (SoundMAX Integrated Digital HD Audio)  <br/> |319  <br/> |
   
Wenn Sie lieber kombinierte Gesamtwerte für ein bestimmtes Gerät anzeigen möchten (z. B. für das SoundMAX-Aufnahmegerät, unabhängig vom verwendeten Rendergerät), wählen Sie die entsprechende Option aus der Dropdownliste "Gerätetyp" (Aufnahmegerät oder Rendergerät) aus. Wenn Sie in diesem Beispiel "Aufnahmegerät" auswählen, erhalten Sie eine Ausgabe wie die folgende:
  
|**Aufnahmegerät**|**Anruflautstärke**|
|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Zugreifen auf den Gerätebericht

Der Zugriff auf den Gerätebericht erfolgt in der Regel über die Startseite für Überwachungsberichte. Wenn Sie jedoch den Anrufdetailbericht [in Skype for Business Server](call-detail-report.md) anzeigen, können Sie einen Drilldown zum Gerätebericht für ein bestimmtes Gerät anzeigen, indem Sie auf eine der folgenden Metriken klicken:
  
- Aufnahmegerät
    
- Rendergerät
    
Im Gerätebericht können Sie einen Drilldown zum Anruflistenbericht [in Skype for Business Server](call-list-report-0.md) erstellen, indem Sie auf eine der folgenden Metriken klicken:
  
- Anrufvolumen
    
- Prozentsatz der Anrufe schlechter Qualität
    
## <a name="making-the-best-use-of-the-device-report"></a>Optimale Nutzung des Geräteberichts

Wenn es um Gerätenamen geht, ist der Gerätebericht sehr detailliert. Angenommen, Sie verfügen über die folgenden Aufnahmegeräte:
  
- Aastra 3002-Mikrofon (2- Aastra 3002)
    
- Aastra 3002-Mikrofon (3- Aastra 3002)
    
- Aastra 3002-Mikrofon (Aastra 3002)
    
- Aastra 6725ip
    
- Aastra 6725ip-Mikrofon (10- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (10- Aastra 6725ip)-V0
    
- Aastra 6725ip-Mikrofon (2- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (3- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (4- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (5- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (6- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (7- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (9- Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (9- Aastra 6725ip)-V0
    
- Aastra 6725ip-Mikrofon (Aastra 6725ip)
    
- Aastra 6725ip-Mikrofon (Aastra 6725ip)-V0
    
- Aastra 6725ip-Mikrofon (USB-Audiogerät)
    
- Aastra 6725ip-Mikrofon (USB-Audiogerät)-V0
    
> [!NOTE]
> Beachten Sie, dass die Namen der Aufnahmegeräte möglicherweise nicht identisch sind, wenn Sie lokalisierte Versionen von Skype for Business Server ausführen. Ein Gerät mit dem Namen "Aastra 6725ip Microphone (Aastra 6725ip)-V0" in Englisch (USA) könnte in Französisch oder Spanisch einen anderen Namen haben. 
  
Häufig möchten Sie diese Detailebene haben. In anderen Zeiten interessiert Sie jedoch möglicherweise nur, wie viele Anrufe ein beliebiges Aastra-Mikrofon verwenden, unabhängig von der Modellnummer. Eine Möglichkeit, informationen wie diese zu erhalten, ist das Exportieren der Geräteberichtsdaten nach Microsoft Excel und das anschließende Speichern dieser Daten in einer Datei mit durch Kommas getrennten Werten (z. B. C:\Data\Devices_Report.csv). Sie können dann eine Reihe von Befehlen verwenden, die diesen ähneln, um die zu importieren. csv file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Dies gibt einen einzelnen Wert zurück, der die Gesamtzahl der Anrufe darstellt, die mit einem Aastra-Aufnahmegerät erfolgt sind. Beispiel: 384

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Gerätebericht können Sie z. B. nach Dem Anruftyp (d. h. einem Clientanruf), einem Konferenzanruf oder einem Festnetzanruf (Public Switched Telephone Network, PSTN) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Geräte nach Stunde, Tag, Woche oder Monat gruppieren.
  
In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Gerätebericht verwenden können.
  
**Geräteberichtsfilter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ursache des Sprachwechsels** <br/> |Grund, warum ein Anruf in den Halbduplexmodus versetzt werden musste, um Echo zu verhindern. Im Halbduplexmodus kann die Kommunikation in einer Richtung gleichzeitig ausgeführt werden, ähnlich wie bei der Kommunikation mit einem Walkie-Talkie-Benutzer. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] None Bad timestamp Echo DNLP (dynamic nonlinear processor) Low complexity Bad device state Post-AEC echo (echo cancellation) |
|**Echoursache** <br/> |Grund, warum echo über der akzeptierten Ebene in einem Anruf erkannt wurde. (In der Telekommunikation ist Echo eine Spiegelung von Sound, die gleiche Musik, die Sie hören, wenn Sie nach unten in einem Welle klingen.) Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] None Bad timestamp Post-AEC echo (echounterdrückung) ANLP (adaptiver nichtlinearer Prozessor) DNLP (dynamic nonlinear processor) Microphone Clipping |
|**Anruftyp** <br/> |Gibt den Typ des Anrufs an, der ausgeführt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Telefonkonferenzanruf für Clientanrufe |
|**Zugriffstyp** <br/> |Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Intern extern |
|**Netzwerktyp** <br/> |Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Kabelgebundenes Drahtlos |
|**VPN** <br/> |Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] VPN-Nicht-VPN |
|**Gerätetyp** <br/> |Gibt den Gerätetyp an. Wählen Sie eine der folgenden Optionen aus:  <br/> Aufnahmegerät Rendergerät Aufnahme-/Rendergerätpaar |
|**Gerätename** <br/> |Name des Aufnahme- oder Rendergeräts. Sie können den vollständigen Gerätenamen oder einen beliebigen Teil des Gerätenamens eingeben. Um beispielsweise das Gerätemikrofon (Microsoft LifeCam VX-1000) zu finden, können Sie den vollständigen Gerätenamen wie folgt eingeben:  <br/> Mikrofon (Microsoft LifeCam VX-1000))  <br/> Sie können auch nur einen Teil des Namens eingeben. Beispiel:  <br/> LifeCam  <br/> Beachten Sie, dass der vorstehende Filter alle Geräte zurückgibt, die die Zeichenfolge "LifeCam" an einer beliebigen Stelle im Namen enthalten.  <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Gerätebericht angegebenen Informationen aufgeführt.
  
**Metriken im Gerätebericht**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Aufnahmegerät** <br/> |Ja  <br/> |Gerät (z. B. ein Mikrofon oder eine Webcam), das für die Übertragung von Audiodaten verwendet wird.  <br/> |
|**Darstellungsgerät** <br/> |Ja  <br/> |Gerät (z. B. ein Headset oder Lautsprecher), das zum Empfangen von Audiodaten verwendet wird.  <br/> |
|**Anruflautstärke** <br/> |Ja  <br/> |Gesamtanzahl der anrufe.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Ja  <br/> |Prozentsatz der Anrufe, die als "schlecht" klassifiziert wurden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Eindeutige Benutzer** <br/> |Ja  <br/> |Eindeutige Benutzer, die das Gerät verwendet haben. Wenn ein Benutzer das Gerät 13-mal verwendet, zählt er als ein eindeutiger Benutzer, genauso wie ein Benutzer, der das Gerät nur einmal verwendet hat.  <br/> |
|**Verhältnis der Sprachumschaltzeit** <br/> |Ja  <br/> |Prozentsatz des Anrufs, der im Halbduplexmodus durchgeführt werden musste, um Echo zu verhindern. Im Halbduplexmodus kann die Kommunikation in einer Richtung gleichzeitig ausgeführt werden, ähnlich wie bei der Kommunikation mit einem Walkie-Talkie-Benutzer.  <br/> |
|**Verhältnis des Mikrofons, das nicht funktioniert** <br/> |Ja  <br/> |Prozentsatz des Anrufs, bei dem das Aufnahmegerät auf einer akzeptablen Ebene nicht funktioniert hat. Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme mit dem Anruf in erster Linie darauf hindeuteten, dass das Aufnahmegerät nicht wie erwartet funktionierte.  <br/> |
|**Verhältnis der nicht funktionierenden Lautsprecher** <br/> |Ja  <br/> |Prozentsatz des Anrufs, bei dem das Rendergerät nicht auf einer akzeptablen Ebene funktioniert hat. Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme mit dem Anruf in erster Linie darauf hindeuteten, dass das Rendergerät nicht wie erwartet funktionierte.  <br/> |
|**Anrufe mit Sprachumschaltung (%)** <br/> |Ja  <br/> |Prozentsatz der Gesamtanrufe, die in den Halbduplexmodus versetzt werden mussten. Im Halbduplexmodus kann die Kommunikation in einer Richtung gleichzeitig ausgeführt werden, ähnlich wie bei der Kommunikation mit einem Walkie-Talkie-Benutzer.  <br/> |
|**Echomikrofon in (%)** <br/> |Ja  <br/> |Prozentsatz der Zeit, in der echo im Mikrofonaufnahmedatenstrom erkannt wurde. In der Regel sind die Werte für Headsets oder Handsets niedrig und für Freisprechtelefone oder eigenständige Lautsprecher höher. Bei Geräten, die die Echounterdrückung an Bord unterstützen, weisen hohe Werte auf ein Echoleck hin. Bei anderen Geräten sollte diese Metrik nicht zum Bewerten der Gerätequalität verwendet werden.  <br/> |
|**Echo senden (%)** <br/> |Ja  <br/> |Prozentsatz des Echos, das an andere Benutzer übertragen wird.  <br/> |
|**Anrufe mit Echo (%)** <br/> |Ja  <br/> |Prozentsatz der Gesamtanrufe, bei deren Echo die akzeptable Ebene überschritten wurde.  <br/> |
   

