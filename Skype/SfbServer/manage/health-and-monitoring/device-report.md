---
title: Gerätebericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Zusammenfassung: erfahren Sie mehr über den gerätebericht in Skype for Business Server.'
ms.openlocfilehash: 9b9198d8080c8f1e22e59e2cd496bb7fb318eaae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992412"
---
# <a name="device-report-in-skype-for-business-server"></a>Gerätebericht in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den gerätebericht in Skype for Business Server.
  
Der Gerätebericht wäre mit „Mikrofon- und Lautsprecherbericht“ treffender betitelt, denn er ruft anrufbezogene Metriken ab (z. B. Prozentsatz der Anrufe schlechter Qualität, Echo und Sprachumschaltzeit) und gruppiert sie nach den im Anruf verwendeten Mikrofonen und Lautsprechern. Wenn Sie an IP-Telefonen (auch gemeinhin als "Geräte" bezeichnet) interessiert sind, verwenden Sie stattdessen den [Bericht IP Phone Inventory in Skype for Business Server](ip-phone-inventory-report.md) .
  
Der Gerätebericht ist für Administratoren von großem Nutzen, wenn herausgefunden werden soll, ob bei einem bestimmten Gerätetyp mehr Anrufe schlechter Qualität auftreten als bei anderen Typen. Das kann wiederum Kaufentscheidungen beeinflussen, wenn neue Geräte angeschafft oder vorhandene ausgetauscht werden müssen.
  
Standardmäßig beruhen die Werte im Gerätebericht auch auf dem Mikrofon (dem Aufnahmegerät) und den Lautsprechern bzw. dem Kopfhörer (dem Darstellungsgerät), die bei dem Anruf verwendet werden. Angenommen, Sie haben mehrere Benutzer, die das folgende Aufnahme- bzw. Darstellungsgerät verwenden: Standardmäßig basieren die Informationen im Gerätebericht ebenfalls auf dem Mikrofon (Aufnahmegerät) und den Lautsprechern bzw. dem Kopfhörer (Darstellungsgerät), die für den Anruf verwendet wurden. Nehmen Sie beispielsweise an, dass Sie verschiedene Benutzer haben, die das folgende Aufnahmegerät und das folgende Darstellungsgerät verwenden:
  
- Aufnahmegerät -- Mikrofon (SoundMAX Integrated Digital HD Audio)
    
- Darstellungsgerät -- Headset-Kopfhörer (Microsoft LifeChat LX-3000)
    
Wenn diese Benutzer insgesamt 254 Anrufe getätigt haben, enthält der Bericht den folgenden Eintrag:
  
|**Aufnahmegerät**|**Darstellungsgerät**|**Anruflautstärke**|
|:-----|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Headset-Kopfhörer (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Nehmen wir jetzt an, Sie haben eine Reihe von Benutzern, die das gleiche Aufnahmegerät, aber ein anderes Darstellungsgerät verwenden. In diesem Fall enthält der Bericht eine zweite Zeile, und zwar für diese spezielle Kombination aus Aufnahme- und Darstellungsgerät:
  
|**Aufnahmegerät**|**Darstellungsgerät**|**Anruflautstärke**|
|:-----|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Headset-Kopfhörer (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |Lautsprecher (SoundMAX Integrated Digital HD Audio)  <br/> |319  <br/> |
   
Wenn Sie lieber die Gesamtsumme für ein bestimmtes Gerät angezeigt bekommen möchten (z. B. für das SoundMAX-Aufnahmegerät, unabhängig vom verwendeten Darstellungsgerät), wählen Sie die entsprechende Option in der Dropdownliste „Gerätetyp“ aus (entweder „Aufnahmegerät“ oder „Darstellungsgerät“). Wenn Sie im aktuellen Beispiel „Aufnahmegerät“ wählen, sieht die Ausgabe etwa so aus:
  
|**Aufnahmegerät**|**Anruflautstärke**|
|:-----|:-----|
|Mikrofon (SoundMAX Integrated Digital HD Audio)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Öffnen des Geräteberichts

Auf den Gerätebericht greifen Sie über die Startseite für Überwachungsberichte zu. Wenn Sie jedoch den [Anruf Detail Bericht in Skype for Business Server](call-detail-report.md) anzeigen, können Sie einen Drilldown zum gerätebericht für ein bestimmtes Gerät durchführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Aufnahmegerät
    
- Darstellungsgerät
    
Im gerätebericht können Sie einen Drilldown zum [Anruflistenbericht in Skype for Business Server](call-list-report-0.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Anruflautstärke
    
- Prozentsatz der Anrufe schlechter Qualität
    
## <a name="making-the-best-use-of-the-device-report"></a>Optimales Nutzen des Geräteberichts

Im Hinblick auf Gerätenamen ist der Gerätebericht besonders detailliert. Beispielsweise könnten die folgenden Aufnahmegeräte vorhanden sein:
  
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
> Beachten Sie, dass die Namen von Aufnahmegeräten möglicherweise nicht identisch sind, wenn Sie lokalisierte Versionen von Skype for Business Server ausführen. Ein Gerät namens Aastra 6725ip-Mikrofon (Aastra 6725ip)-V0 hat wahrscheinlich auf Französisch oder Spanisch eine andere Bezeichnung. 
  
Diese Detailgenauigkeit ist häufig sehr nützlich. In manchen Situationen möchten Sie aber vielleicht nur wissen, von wie vielen Anrufen ein beliebiges Aastra-Mikrofon, unabhängig von der Modellnummer, verwendet wird. Dazu können Sie die Geräteberichtsdaten nach Microsoft Excel exportieren und dann in einer CSV-Datei (Comma-Separated Values, Datei mit durch Trennzeichen getrennten Werten) speichern (z. B. C:\Data\Gerätebericht.csv). Anschließend können Sie mithilfe von Befehlen wie den folgenden die CSV-Datei in Windows PowerShell importieren und die Gesamtzahl der Anrufe ausgeben, die mit einem Aastra-Aufnahmegerät getätigt wurden:
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Damit wird ein einzelner Wert zurückgegeben, der die Gesamtzahl der Anrufe angibt, die mit einem Aastra-Aufnahmegerät ausgeführt wurden. Beispiel: 384

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Gerätebericht nach dem Anruftyp filtern (d. h., ob der Anruf ein Clientanruf, eine Telefonkonferenz oder ein PSTN-Anruf ist). Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Geräte nach Stunde, Tag, Woche oder Monat gruppiert.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Gerätebericht verwenden können.
  
**Geräteberichtfilter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ursache für die Sprachumschaltung** <br/> |Der Grund, weshalb der Halbduplex-Modus für einen Anruf verwendet werden musste, um Echo zu verhindern. Im Halbduplex-Modus ist die Kommunikation jeweils nur in eine Richtung möglich, ähnlich wie bei Funksprechgeräten, bei denen auch abwechselnd gesprochen wird. Wählen Sie eine der folgenden Optionen aus:  <br/> Alle Kein fehlerhafter Zeitstempel Echo DNLP (dynamischer nichtlinearer Prozessor) niedrige Komplexität fehlerhafter Gerätezustand nach AEC-Echo (akustische Echounterdrückung) |
|**Ursache für Echo** <br/> |Der Grund, weshalb bei einem Anruf Echo über dem akzeptablen Niveau festgestellt wurde. (In der Telekommunikation handelt es sich bei Echo um eine Schallreflexion; dasselbe Phänomen tritt auf, wenn Sie in einen Brunnen rufen). Wählen Sie eine der folgenden Optionen aus:  <br/> Alle Kein fehlerhafter Timestamp-Post-AEC-Echo (akustische Echounterdrückung) ANLP (adaptiver nichtlinearer Prozessor) DNLP (dynamischer nichtlinearer Prozessor) Mikrofon Ausschnitt |
|**Anruftyp** <br/> |Gibt an, welcher Typ von Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> Alle Client Anruf PSTN-Anruf-Konferenzanruf |
|**Zugriffstyp** <br/> |Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> Alle Intern extern |
|**Netzwerktyp** <br/> |Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:  <br/> Alle Kabelgebundenes WLAN |
|**VPN** <br/> |Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> Alle VPN-nicht-VPN |
|**Gerätetyp** <br/> |Gibt den Typ des Geräts an. Wählen Sie eine der folgenden Optionen aus:  <br/> Capture Device Capture/Render Device Pair |
|**Gerätename** <br/> |Der Name des Aufnahme- oder Darstellungsgeräts. Sie können den vollständigen Gerätenamen oder einen Teil davon eingeben. Geben Sie beispielsweise wie folgt den vollständigen Gerätenamen ein, um nach dem Gerät „Mikrofon (Microsoft LifeCam VX-1000)“ zu suchen:  <br/> Mikrofon (Microsoft LifeCam VX-1000)  <br/> Sie können aber auch nur einen Teil des Namens eingeben. Beispiel:  <br/> LifeCam  <br/> Beachten Sie, dass mit dem vorherigen Filter alle Geräte zurückgegeben werden, welche die Zeichenfolge „LifeCam“ im Namen enthalten.  <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Gerätebericht angegeben werden.
  
**Geräteberichtmetriken**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Aufnahmegerät** <br/> |Ja  <br/> |Ein Gerät (z. B. ein Mikrofon oder eine Webcam), das für die Übertragung von Audio verwendet wird.  <br/> |
|**Darstellungsgerät** <br/> |Ja  <br/> |Ein Gerät (z. B. ein Headset oder Lautsprecher), das für den Empfang von Audio verwendet wird.  <br/> |
|**Anruflautstärke** <br/> |Ja  <br/> |Die Gesamtzahl der getätigten Anrufe.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Ja  <br/> |Der Prozentsatz der Anrufe, die als Anrufe schlechter Qualität klassifiziert wurden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Eindeutige Benutzer** <br/> |Ja  <br/> |Die eindeutigen Benutzer, die das Gerät verwendet haben. Wenn ein Benutzer das Gerät 13 Mal verwendet hat, zählt er als ein eindeutiger Benutzer. Dasselbe gilt für einen Benutzer, der das Gerät nur ein einziges Mal verwendet hat.  <br/> |
|**Anteil Sprachumschaltzeit** <br/> |Ja  <br/> |Der Prozentsatz des Anrufs, der im Halbduplex-Modus getätigt werden musste, um Echo zu verhindern. Im Halbduplex-Modus ist die Kommunikation jeweils nur in eine Richtung möglich, ähnlich wie bei Funksprechgeräten, bei denen auch abwechselnd gesprochen wird.  <br/> |
|**Anteil nicht funktionierendes Mikrofon** <br/> |Ja  <br/> |Der Prozentsatz des Anrufs, bei dem das Aufnahmegerät nicht ordnungsgemäß funktionierte. Ein hoher Wert ist ein Hinweis, dass Qualitätsprobleme beim Anruf in erster Linie darauf zurückzuführen sind, dass das Aufnahmegerät nicht erwartungsgemäß funktionierte.  <br/> |
|**Anteil nicht funktionierender Lautsprecher** <br/> |Ja  <br/> |Der Prozentsatz des Anrufs, bei dem das Darstellungsgerät nicht ordnungsgemäß funktionierte. Ein hoher Wert ist ein Hinweis, dass Qualitätsprobleme beim Anruf in erster Linie darauf zurückzuführen sind, dass das Darstellungsgerät nicht erwartungsgemäß funktionierte.  <br/> |
|**Anrufe mit Sprachumschaltung (%)** <br/> |Ja  <br/> |Der Prozentsatz der Gesamtanrufe, die im Halbduplex-Modus getätigt werden mussten. Im Halbduplex-Modus ist die Kommunikation jeweils nur in eine Richtung möglich, ähnlich wie bei Funksprechgeräten, bei denen auch abwechselnd gesprochen wird.  <br/> |
|**Echo in Mikrofon (%)** <br/> |Ja  <br/> |Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom Echo festgestellt wurde. In der Regel weisen Headsets oder Hörer niedrige Werte und Freisprechvorrichtungen oder eigenständige Lautsprecher höhere Werte auf. Bei Geräten, die eine integrierte akustische Echounterdrückung unterstützen, weisen hohe Werte auf eine Echoausbreitung hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu evaluieren.  <br/> |
|**Echo-Übertragung (%)** <br/> |Ja  <br/> |Der Prozentsatz an Echo, das an andere Benutzer übertragen wird.  <br/> |
|**Anrufe mit Echo (%)** <br/> |Ja  <br/> |Der Prozentsatz der Gesamtanrufe mit Echo über dem akzeptablen Niveau.  <br/> |
   

