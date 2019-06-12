---
title: Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: In diesem Artikel wird die Remoteverwaltung der Standardeinstellungen beschrieben, die von einem Microsoft Teams rooms-Gerät verwendet werden, einschließlich der Anwendung eines benutzerdefinierten Designs.
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305333"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei
 
In diesem Artikel wird die Remoteverwaltung der Standardeinstellungen beschrieben, die von einem Microsoft Teams rooms-Gerät verwendet werden, einschließlich der Anwendung eines benutzerdefinierten Designs.
  
Wenn Sie eine Master-XML-Datei aktualisieren und Kopien an die von Ihnen verwalteten Konsolen senden, können Sie die Standardeinstellungen für Remote verwaltete Geräte ändern. In diesem Artikel wird beschrieben, wie Sie eine solche Datei erstellen, und Links zu Diskussionen darüber, wie Sie auf den Remote verwalteten Geräten nach Bedarf platziert werden. Mit dieser Methode können Sie auch benutzerdefinierte Designs auf Ihren Microsoft Teams rooms-Konsolen implementieren. 
  
## <a name="creating-an-xml-configuration-file"></a>Erstellen einer XML-Konfigurationsdatei

In der folgenden Tabelle werden die in diesem Beispiel SkypeSettings. XML (Dies ist eine erforderliche Dateinamen)-Konfigurationsdatei dargestellten Elemente erläutert. 
  
```
<SkypeSettings>
  <AutoScreenShare>true</AutoScreenShare>
  <HideMeetingName>true</HideMeetingName>
  <UserAccount>
             <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
             <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
             <DomainUsername>Seattle\RanierConf</DomainUsername>
             <Password>password</Password>
             <ConfigureDomain>domain1, domain2</ConfigureDomain>
  </UserAccount>    
  <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
  <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
  <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled> 
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled> 
  <DualScreenMode>true</DualScreenMode>
  <SendLogs>                           
             <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
                <SendLogsAndFeedback>true</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
              <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
              <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
              <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
  </Devices>
  <Theming> 
    <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
      <CustomThemeColor>
           <RedComponent>100</RedComponent>
           <GreenComponent>100</GreenComponent>
           <BlueComponent>100</BlueComponent>
         </CustomThemeColor>
  </Theming>
</SkypeSettings>
```

Wenn die XML-Datei schlecht geformt ist (was bedeutet, dass ein Variablenwert vom falschen Typ ist, die Elemente nicht in der richtigen Reihenfolge sind, Elemente nicht geschlossen sind usw.), werden die Einstellungen, die bis zu dem Punkt gefunden wurden, an dem der Fehler gefunden wird, angewendet, und die restliche Datei wird während der Verarbeitung ignoriert. Unbekannte Elemente im XML-Code werden ignoriert. Wenn ein Parameter ausgelassen wird, bleibt er auf dem Gerät unverändert. Wenn der Wert eines Parameters ungültig ist, bleibt sein vorheriger Wert unverändert.
  
**XML-Elemente**
 
|Element|Typ|Ebene|Verwendung|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Container für alle Elemente.   ||Erforderlich.   |
| \<AutoScreenShare\>  |Boolescher #a0  |Erste #a0  | Falls zutreffend, ist die automatische Bildschirmfreigabe aktiviert.  |
|\<HideMeetingName\>   |Boolescher #a0  |Erste #a0  |Falls zutreffend, sind die Besprechungsnamen ausgeblendet.   |
|\<Benutzerkonto\>   |Container   |Erste #a0  |Container für Anmeldeinformationen-Parameter.   Die Anmeldeadresse, die Exchange-Adresse oder die e-Mail-Adresse sind in der Regel<span></span>identisch, beispielsweise RanierConf @contoso. com.   |
|\<SkypeMeetingsEnabled\>  |Boolescher #a0  |Erste #a0  |Diese Option ist standardmäßig aktiviert.   |
|\<SkypeSignInAddress\>   |Zeichenfolge #a0  ||Der Anmeldename für das Skype for Business-Gerätekonto der Konsole.   |
|\<ExchangeAddress\>   |Zeichenfolge #a0  ||Der Anmeldename für das Exchange-Gerätekonto der Konsole.   Wenn die Exchange-Adresse ausgelassen wird, wird die Skype-Anmeldeadresse nicht automatisch wiederverwendet.    |
|\<Domain User Name\>   |Zeichenfolge #a0  ||Die Domäne und der Benutzername für das Konsolengerät, zum Beispiel Seattle\RanierConf.   |
|\<Kennwort\>   |Zeichenfolge 3  || Der Kennwortparameter stimmt mit dem für die Kontoanmeldung für das Skype for Business-Gerät verwendeten Kennwort überein.   |
| \<ConfigureDomain\>  |Zeichenfolge #a0  ||Sie können mehrere durch Kommata getrennte Domänen auflisten.   |
|\<TeamsMeetingsEnabled\>   |Boolescher #a0  |Erste #a0  |Diese ist standardmäßig deaktiviert. <br/> <br/> Die XML-Datei wird als schlecht geformt betrachtet \<,\> Wenn\<sowohl\> SkypeMeetingsEnabled als auch TeamsMeetingsEnabled deaktiviert sind, es aber akzeptabel ist, dass beide Einstellungen gleichzeitig aktiviert sind.   |
|\<IsTeamsDefaultClient> |Boolescher #a0  |Erste #a0  |Diese ist standardmäßig deaktiviert. |
|\<BluetoothAdvertisementEnabled> |Boolescher #a0  |Erste #a0  |Diese Option ist standardmäßig aktiviert. |
|\<DualScreenMode\>  |Boolescher #a0  |Erste #a0  |Ist der Wert "true", ist der duale Bildschirm aktiviert. Andernfalls verwendet das Gerät den Einzelbildschirmmodus.   |
|\<SendLogs\>   |Container   |Erste #a0  ||
|\<EmailAddressForLogsAndFeedback\>   |Zeichenfolge #a0  ||Damit wird eine optionale E-Mail-Adresse verwendet, an die Protokolle gesendet werden können, wenn das Fenster "Feedback senden" angezeigt wird.    |
|\<SendLogsAndFeedback\>   |Boolescher #a0  || Falls zutreffend werden Protokolle an den Administrator gesendet. Falls zutreffend wird Feedback nur an den Administrator (nicht an die Protokolle) gesendet.  |
| \<Geräte\>  |Container   |Erste #a0  | Die Namen der verbundenen Audiogeräte in den untergeordneten Elementen stimmen mit den Werten in der Gerätemanager-App überein. Die Konfiguration kann ein Gerät enthalten, das derzeit nicht auf dem System vorhanden ist, wie zum Beispiel ein aktuelle nicht mit der Konsole verbundenes A/V-Gerät. Die Konfiguration würde für das entsprechende Gerät beibehalten.  |
|\<MicrophoneForCommunication\>   |Zeichenfolge #a0  ||Legt das Mikrofon fest, das als Aufnahmegerät in einer Konferenz verwendet wird.   |
|\<SpeakerForCommunication\>   |Zeichenfolge #a0  ||Das als Lautsprecher für die Konferenz verwendete Gerät. Diese Einstellung wird verwendet, um das Lautsprechergerät festzulegen, das für die Audiowiedergabe in einem Anruf verwendet wird.   |
|\<DefaultSpeaker\>   |Zeichenfolge #a0  ||Gerät, das zum Abspielen von Audio aus einer HDMI-Erfassungsquelle verwendet wird.    |
| \<Design\>  |Container   |Erste #a0  |Bei einer der Funktionen, die unter Verwendung einer XML-Datei verwendet werden kann, handelt es sich um ein benutzerdefiniertes Design für Ihre Organisation. Sie können einen Designnamen, ein Hintergrundbild und eine Farbe angeben.   |
|\<ThemeName\>   |Zeichenfolge #a0  || Wird zum Identifizieren des Designs auf dem Client verwendet. Bei den Optionen für den Designnamen handelt es sich um "Standard" (eines der voreingestellten Designs) oder um "Benutzerdefiniert". <br/>  Benutzerdefinierte Designnamen sollten immer den Namen *Custom* verwenden. Die Client-Benutzeroberfläche kann in der Konsole auf den Standardwert oder eine der Voreinstellungen eingestellt werden, doch die Anwendung eines benutzerdefinierten Designs muss von einem Administrator Remote eingerichtet werden. <br/>  Werkseitig eingestellte Designs enthalten: <br/>  Standard <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Wenn Sie das aktuelle Design deaktivieren möchten, verwenden Sie für den Designname "kein Design".  |
|\<CustomThemeImageUrl\>   |Zeichenfolge #a0  ||Bei Verwendung eines benutzerdefinierten Designs erforderlich, andernfalls optional. Weitere Informationen zum benutzerdefinierten Design Bild finden Sie unten im Abschnitt [benutzerdefinierte Design Bilder](xml-config-file.md#Themes) .  |
|\<CustomThemeColor\>   |Container   ||Container für die \<Werte für\>" \<iscomponent" \<,\> "GreenComponent\>" und "BlueComponent". diese Werte sind bei Verwendung eines benutzerdefinierten Designs erforderlich.   |
|\<Komponente\>   |Byte (0-255)   ||Stellt die rote Komponente dar.   |
|\<GreenComponent\>   |Byte (0-255)   ||Stellt die grüne Komponente dar.   |
|\<BlueComponent\>   |Byte (0-255)   ||Stellt die blaue Komponente dar.   |
| | | |
   
&#x2776; alle Elemente der ersten Ebene sind optional. Wenn ein Element der ersten Ebene ausgelassen wird, bleiben alle diesem Element untergeordneten Parameter auf dem Gerät unverändert.
  
&#x2777; ein boolesches Flag kann einen der folgenden Werte aufweisen: true, false, 0 oder 1. Leere boolesche oder numerische Werte führen möglicherweise zu einer fehlerhaften Darstellung der XML-Datei, und die Einstellungen können nicht angewendet werden.
  
 &#x2778; Wenn ein Zeichenfolgenparameter vorhanden, leer und leer ein gültiger Wert ist, wird der Parameter auf dem Gerät gelöscht.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Verwalten von Konsoleneinstellungen unter Verwendung einer XML-Konfigurationsdatei

Wenn eine Microsoft Teams rooms-Konsole beim Start eine XML-Datei mit dem Namen "SkypeSettings. xml" am Standort **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**findet, werden die Konfigurationseinstellungen übernommen. durch die XML-Datei gekennzeichnet, und löschen Sie dann die XML-Datei.
  
Je nachdem, wie viele Microsoft Teams rooms-Geräte in Ihrem Unternehmen vorhanden sind und wie Sie diese Konfiguration verwalten, gibt es eine Reihe von Möglichkeiten, die XML-Konfigurationsdatei zu platzieren. Sobald die Datei  in die Konsole verschoben wurde, starten Sie das Gerät, um die Konfigurationsänderungen zu verarbeiten. Die XML-Datei wird nach erfolgreicher Verarbeitung entfernt. Die für Microsoft Teams Room-Geräte vorgeschlagenen Verwaltungsmethoden werden in folgenden Themen erörtert:
  
- [Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Chatrooms](room-systems-v2-operations.md#GroupPolicy)
    
- [Remote Verwaltung mithilfe von PowerShell](room-systems-v2-operations.md#RemotePS) und [Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Sie können jede beliebige Methode so lange verwenden, wie Sie Sie verwenden können, um Dateien zu übertragen und einen Neustart auf dem Konsolengerät auszulösen. Die Datei muss für das lokale Benutzerkonto des Geräts lesbar, beschreibbar und löschbar sein (vorzugsweise sollte Sie im Besitz des Besitzers sein und die vollständigen Berechtigungen besitzen, die diesem Benutzer gewährt wurden). Wenn die Dateiberechtigungen nicht richtig gesetzt sind, kann es vorkommen, dass die Software die Einstellungen nicht anwendet, die Datei bei erfolgreicher Verarbeitung möglicherweise nicht löscht und sogar potenziell abstürzt.
  
## <a name="custom-theme-images"></a>Benutzerdefinierte Designbilder
<a name="Themes"> </a>

Die Image-Datei für ein benutzerdefiniertes Design muss in **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**abgelegt werden, geben Sie einfach den \<Datei\> Namen und die Erweiterung in die CustomThemeImageUrl-Variable ein.
  
Die Bilddatei muss genau 3840 x 1080 Pixel groß sein und eines der folgenden Dateiformate aufweisen: JPG, JPEG, PNG oder BMP. Wenn Ihre Organisation ein benutzerdefiniertes Bild wünscht, findet ein Grafikdesigner unsere [benutzerdefinierte Design-Photoshop-Vorlage](https://go.microsoft.com/fwlink/?linkid=870441) hilfreich. Sie enthält weitere Details zur Platzierung der verschiedenen Elemente in einem Designbild und zu den Bereichen, die auf Konsolen und Displays angezeigt werden.
  
Die XML-Konfigurationsdatei muss beim Starten des Geräts aktualisiert werden, damit das Designbild erkannt wird. Sobald die neue XML-Datei verarbeitet und gelöscht wurde, wird die Designgrafikdatei im Verzeichnis gelöscht.
  
## <a name="see-also"></a>Siehe auch


[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

[Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
