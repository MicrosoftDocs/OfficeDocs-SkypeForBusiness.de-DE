---
title: Gerätebericht in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Zusammenfassung: Erfahren Sie mehr über den Gerätebericht in Skype for Business Server.'
---

# <a name="device-report-in-skype-for-business-server"></a>Gerätebericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Gerätebericht in Skype for Business Server.
  
Der Gerätebericht ist möglicherweise besser mit dem Bericht "Mikrofon und Lautsprecher" beschriftet. Dies liegt daran, dass der Gerätebericht anrufbezogene Metriken (z. B. Prozentsatz der Anrufe schlechter Qualität, Echo und Sprachumschaltzeit) abruft, die nach den im Anruf verwendeten Mikrofonen und Lautsprechern gruppiert sind. Wenn Sie sich für IP-Telefone (auch als "Geräte" bezeichnet) interessieren, verwenden Sie stattdessen den [IP-Telefon-Bestandsbericht in Skype for Business Server](ip-phone-inventory-report.md).
  
Der Gerätebericht ist äußerst hilfreich für Administratoren, um festzustellen, ob bei einem bestimmten Gerätetyp eine große Anzahl von Anrufen schlechter Qualität auftritt als bei anderen. Dies kann wiederum alle Entscheidungen beeinflussen, die Sie treffen müssen, wenn es an der Zeit ist, neue Geräte zu kaufen oder vorhandene Geräte zu ersetzen.
  
Standardmäßig basieren die im Gerätebericht angezeigten Informationen auch auf dem Mikrofon (dem Aufnahmegerät) und den Lautsprechern/Headsets (dem Rendergerät), die im Anruf verwendet werden. Angenommen, Sie haben mehrere Benutzer, die das folgende Aufnahmegerät und das folgende Rendergerät verwenden: Die im Gerätebericht angezeigten Informationen basieren standardmäßig auch auf dem Mikrofon (dem Aufnahmegerät) und den Lautsprechern/Headsets (dem Rendergerät), die im Anruf verwendet werden. Angenommen, Sie haben mehrere Benutzer, die das folgende Aufnahmegerät und das folgende Rendergerät verwenden:
  
- Aufnahmegerät – Mikrofon (SoundMAX Integrated Digital HD Audio)
    
- Rendergerät – Headset-Kopfhörer (Microsoft LifeChat LX-3000)
    
Wenn diese Benutzer insgesamt 254 Anrufe getätigt haben, sehen Sie einen Eintrag wie den folgenden im Bericht:
  
|**Aufnahmegerät**|**Darstellungsgerät**|**Anruflautstärke**|
|:-----|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Headset-Kopfhörer (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Angenommen, Sie haben eine Reihe von Benutzern, die dasselbe Aufnahmegerät, aber ein anderes Rendergerät verwenden. In diesem Fall haben Sie einen zweiten Zeileneintrag im Bericht, einen für diese eindeutige Kombination aus Aufnahmegerät und Rendergerät:
  
|**Aufnahmegerät**|**Darstellungsgerät**|**Anruflautstärke**|
|:-----|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Headset-Kopfhörer (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Lautsprecher (SoundMAX Integrated Digital HD Audio)  <br/> |319  <br/> |
   
Wenn Sie lieber kombinierte Gesamtsummen für ein bestimmtes Gerät sehen möchten (z. B. für das SoundMAX-Aufnahmegerät, unabhängig vom verwendeten Rendergerät), wählen Sie die entsprechende Option in der Dropdownliste "Gerätetyp" aus (entweder "Aufnahmegerät" oder "Rendergerät"). Wenn Sie in diesem Beispiel "Aufnahmegerät" auswählen, erhalten Sie eine ähnliche Ausgabe wie die folgende:
  
|**Aufnahmegerät**|**Anruflautstärke**|
|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Zugreifen auf den Gerätebericht

Auf den Gerätebericht wird in der Regel über die Startseite für Überwachungsberichte zugegriffen. Wenn Sie jedoch den [Anrufdetailbericht in Skype for Business Server](call-detail-report.md) können Sie einen Drilldown zum Gerätebericht für ein bestimmtes Gerät ausführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Aufnahmegerät
    
- Rendergerät
    
Aus dem Gerätebericht können Sie einen Drilldown zum [Anruflistenbericht in Skype for Business Server](call-list-report-0.md) ausführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Anrufvolumen
    
- Prozentsatz der Anrufe schlechter Qualität
    
## <a name="making-the-best-use-of-the-device-report"></a>Optimale Nutzung des Geräteberichts

Wenn es um Gerätenamen geht, ist der Gerätebericht äußerst detailliert. Angenommen, Sie verfügen über die folgenden Aufnahmegeräte:
  
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
> Beachten Sie, dass die Namen von Aufnahmegeräten möglicherweise nicht identisch sind, wenn Sie lokalisierte Versionen von Skype for Business Server ausführen. Ein Gerät mit dem Namen Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US-Englisch könnte einen anderen Namen auf Französisch oder Spanisch haben. 
  
Häufig benötigen Sie diese Detailebene. In anderen Fällen sind Sie jedoch möglicherweise nur daran interessiert, wie viele Anrufe ein Aastra-Mikrofon verwenden, unabhängig von der Modellnummer. Eine Möglichkeit zum Abrufen dieser Informationen besteht darin, die Geräteberichtsdaten in Microsoft Excel zu exportieren und diese Daten dann in einer durch Trennzeichen getrennten Wertedatei zu speichern (z. B. C:\Data\Devices_Report.csv). Anschließend können Sie eine Reihe von Ähnlichen Befehlen verwenden, um die .CSV-Datei in Windows PowerShell zu importieren und die Gesamtzahl der Anrufe zu melden, die mit einem Aastra-Aufnahmegerät getätigt wurden:
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Dadurch wird ein einzelner Wert zurückgegeben, der die Gesamtzahl der Anrufe darstellt, die mit einem Aastra-Aufnahmegerät getätigt wurden. Beispiel: 384

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Gerätebericht können Sie beispielsweise nach Denktypen (d. h. war der Anruf ein Clientanruf), einem Telefonkonferenzanruf oder einem PsTN-Anruf (Public Switched Telephone Network) gefiltert werden. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Geräte nach Stunde, Tag, Woche oder Monat gruppiert.
  
In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Gerätebericht verwenden können.
  
**Geräteberichtfilter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ursache des Sprachschalters** <br/> |Grund, warum ein Anruf in den Halbduplex-Modus versetzt werden musste, um Echo zu verhindern. Im Halbduplex-Modus kann die Kommunikation jeweils nur in eine Richtung erfolgen, ähnlich der Art und Weise, in der sich Benutzer bei der Kommunikation mit einem Walkie-Talkie-Gerät abwechseln. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] None Bad timestamp Echo DNLP (dynamic nonlinear processor) Low complexity Bad device state Post-AEC echo (echo cancellation) |
|**Echoursache** <br/> |Grund, warum echo oberhalb der akzeptierten Ebene in einem Anruf erkannt wurde. (In der Telekommunikation ist Echo eine Spiegelung des Sounds, dasselbe Problem, das Sie hören, wenn Sie bis zum Ende eines Welles yelln.) Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] None Bad timestamp post-AEC echo (acoustic echo cancellation) ANLP (adaptiver nichtlinearer Prozessor) DNLP (dynamic nonlinear processor) Microphone clipping |
|**Anruftyp** <br/> |Gibt den Typ des Anrufs an, der ausgeführt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] PsTN-Telefonkonferenzanruf für Clientanrufe |
|**Zugriffstyp** <br/> |Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Intern extern |
|**Netzwerktyp** <br/> |Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Kabelgebundene Drahtlosverbindung |
|**VPN** <br/> |Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] VPN, kein VPN |
|**Gerätetyp** <br/> |Gibt den Typ des Geräts an. Wählen Sie eine der folgenden Optionen aus:  <br/> Geräte-Geräte-Rendergerät erfassen/Gerätepaar rendern |
|**Gerätename** <br/> |Name des Aufnahme- oder Rendergeräts. Sie können den vollständigen Gerätenamen oder einen beliebigen Teil des Gerätenamens eingeben. Um beispielsweise das Gerätemikrofon (Microsoft LifeCam VX-1000) zu finden, können Sie den vollständigen Gerätenamen wie folgt eingeben:  <br/> Mikrofon (Microsoft LifeCam VX-1000.)  <br/> Sie können auch nur einen Teil des Namens eingeben. Beispiel:  <br/> Lifecam  <br/> Beachten Sie, dass der vorherige Filter jedes Gerät zurückgibt, das die Zeichenfolge "LifeCam" an einer beliebigen Stelle im Namen enthält.  <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Im Gerätebericht enthaltenen Informationen aufgeführt.
  
**Metriken des Geräteberichts**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Aufnahmegerät** <br/> |Ja  <br/> |Gerät (z. B. ein Mikrofon oder eine Webcam), das für die Übertragung von Audio verwendet wird.  <br/> |
|**Darstellungsgerät** <br/> |Ja  <br/> |Gerät (z. B. ein Headset oder Lautsprecher), das zum Empfangen von Audio verwendet wird.  <br/> |
|**Anruflautstärke** <br/> |Ja  <br/> |Gesamtzahl der getätigten Anrufe.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Ja  <br/> |Prozentsatz der Anrufe, die als "schlecht" klassifiziert wurden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Eindeutige Benutzer** <br/> |Ja  <br/> |Eindeutige Benutzer, die das Gerät verwendet haben. Wenn ein Benutzer das Gerät 13 Mal verwendet hat, zählt er als ein eindeutiger Benutzer, genauso wie ein Benutzer, der das Gerät nur ein einziges Mal verwendet hat.  <br/> |
|**Verhältnis der Sprachumschaltzeit** <br/> |Ja  <br/> |Prozentsatz des Anrufs, der im Halbduplex-Modus durchgeführt werden musste, um Echo zu verhindern. Im Halbduplex-Modus kann die Kommunikation jeweils nur in eine Richtung erfolgen, ähnlich der Art und Weise, in der sich Benutzer bei der Kommunikation mit einem Walkie-Talkie-Gerät abwechseln.  <br/> |
|**Verhältnis der Nichtfunktion des Mikrofons** <br/> |Ja  <br/> |Prozentsatz des Anrufs, bei dem das Aufnahmegerät nicht auf einem akzeptablen Niveau funktionierte. Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme bei dem Anruf in erster Linie darauf zurückzuführen waren, dass das Aufnahmegerät nicht wie erwartet funktionierte.  <br/> |
|**Verhältnis der nicht funktionierenden Lautsprecher** <br/> |Ja  <br/> |Prozentsatz des Anrufs, bei dem das Rendergerät nicht auf einer akzeptablen Ebene funktionierte. Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme beim Anruf in erster Linie darauf zurückzuführen waren, dass das Rendergerät nicht wie erwartet funktionierte.  <br/> |
|**Anrufe mit Sprachschalter (%)** <br/> |Ja  <br/> |Prozentsatz der Gesamtanrufe, die im Halbduplexmodus getätigt werden mussten. Im Halbduplex-Modus kann die Kommunikation jeweils nur in eine Richtung erfolgen, ähnlich der Art und Weise, in der sich Benutzer bei der Kommunikation mit einem Walkie-Talkie-Gerät abwechseln.  <br/> |
|**Echomikrofon in (%)** <br/> |Ja  <br/> |Prozentsatz der Zeit, in der echo im Mikrofonaufnahmedatenstrom erkannt wurde. In der Regel sind die Werte für Headsets oder Handsets niedrig und für Lautsprechertelefone oder eigenständige Lautsprecher höher. Bei Geräten, die die lokale akustische Echounterdrückung unterstützen, deuten hohe Werte auf einen Echoverlust hin. Bei anderen Geräten sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu bewerten.  <br/> |
|**Echosenden (%)** <br/> |Ja  <br/> |Prozentsatz des Echos, das an andere Benutzer übertragen wurde.  <br/> |
|**Anrufe mit Echo (%)** <br/> |Ja  <br/> |Prozentsatz der Gesamtanrufe, bei denen das Echo den zulässigen Wert überschreitet.  <br/> |
   

