---
title: Verwalten einer Microsoft-Teams Chatrooms Konsolenstamm Remote mit einer XML-Konfigurationsdatei
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: In diesem Artikel wird remote Management die Standardeinstellungen, die von einem Microsoft-Teams Räume-Gerät, einschließlich eines benutzerdefinierten Designs verwendet.
ms.openlocfilehash: 28a9b64a1385795e9d52f503cba77149eb89679a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915726"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Verwalten einer Microsoft-Teams Chatrooms Konsolenstamm Remote mit einer XML-Konfigurationsdatei
 
In diesem Artikel wird remote Management die Standardeinstellungen, die von einem Microsoft-Teams Räume-Gerät, einschließlich eines benutzerdefinierten Designs verwendet.
  
Eine Master-Shape XML-Datei aktualisiert und Senden von Kopien den Konsolen, die Sie verwalten ermöglicht es zum Ändern der Standardeinstellungen für die Remoteverwaltung Geräte. In diesem Artikel wird erläutert, wie solche einer Datei sowie Links zu Diskussionen zum Platzieren Bedarf auf den Remote verwalteten Geräten zu erstellen. Mit dieser Methode können Sie auch benutzerdefinierte Designs auf Ihre Microsoft-Teams Chatrooms Konsolen implementieren. 
  
## <a name="creating-an-xml-configuration-file"></a>Erstellen einer XML-Konfigurationsdatei

In der folgenden Tabelle wird erläutert, die Elemente in diesem Beispiel SkypeSettings.xml (Dies ist eine erforderliche Dateiname) dargestellt Konfigurationsdatei. 
  
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

Wenn die XML-Datei falsch formatiert wurde (Elemente sind nicht funktionsfähig, Elemente werden nicht geschlossene, d. h., den Wert ein variabler vom falschen Typ ist, usw.), bis zu dem Punkt, auf dem der Fehler gefunden wird, gefunden Einstellungen angewendet werden, wird der Rest der Datei während der Verarbeitung ignoriert. Alle unbekannten Elemente in der XML-Code werden ignoriert. Wenn Parameter ausgelassen wird, wird es auf dem Gerät nicht geändert. Wenn der Wert des Parameters ungültig ist, unverändert der vorherige Wert.
  
**XML-Elemente**
 
|Element|Typ|Ebene|Verwendung|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Container für alle Elemente.   ||Erforderlich.   |
| \<AutoScreenShare\>  |Boolean & #x 2777;  |Erste & #x 2776;  | Falls zutreffend, ist die automatische Bildschirmfreigabe aktiviert.  |
|\<HideMeetingName\>   |Boolean & #x 2777;  |Erste & #x 2776;  |Falls zutreffend, sind die Besprechungsnamen ausgeblendet.   |
|\<"Useraccount" bei\>   |Container   |Erste & #x 2776;  |Container für Anmeldeinformationen-Parameter.   Anmelden bei Adresse, die Exchange-Adresse oder die e-Mail-Adresse in der Regel identisch sind, wie etwa RanierConf<span></span>@contoso.com.   |
|\<SkypeMeetingsEnabled\>  |Boolean & #x 2777;  |Erste & #x 2776;  |Diese Option ist standardmäßig aktiviert.   |
|\<SkypeSignInAddress\>   |Zeichenfolge & #x 2778;  ||Der Anmeldename für das Skype for Business-Gerätekonto der Konsole.   |
|\<ExchangeAddress\>   |Zeichenfolge & #x 2778;  ||Der Anmeldename für das Exchange-Gerätekonto der Konsole.   Wenn die Exchange-Adresse ausgelassen wird, wird die Skype-Anmeldeadresse nicht automatisch wiederverwendet.    |
|\<DomainUsername\>   |Zeichenfolge & #x 2778;  ||Die Domäne und der Benutzername für das Konsolengerät, zum Beispiel Seattle\RanierConf.   |
|\<Passwort\>   |Zeichenfolge 3  || Der Kennwortparameter stimmt mit dem für die Kontoanmeldung für das Skype for Business-Gerät verwendeten Kennwort überein.   |
| \<ConfigureDomain\>  |Zeichenfolge & #x 2778;  ||Sie können mehrere durch Kommata getrennte Domänen auflisten.   |
|\<TeamsMeetingsEnabled\>   |Boolean & #x 2777;  |Erste & #x 2776;  |Diese ist standardmäßig deaktiviert. <br/> <br/> Die XML-Datei wird nicht wohlgeformten betrachtet, wenn beide \<SkypeMeetingsEnabled\> und\<TeamsMeetingsEnabled\> sind deaktiviert, aber es ist akzeptabel, beide Einstellungen zur selben Zeit aktiviert haben.   |
|\<IsTeamsDefaultClient> |Boolean & #x 2777;  |Erste & #x 2776;  |Diese ist standardmäßig deaktiviert. |
|\<BluetoothAdvertisementEnabled> |Boolean & #x 2777;  |Erste & #x 2776;  |Diese Option ist standardmäßig aktiviert. |
|\<DualScreenMode\>  |Boolean & #x 2777;  |Erste & #x 2776;  |Dual-Screen-Modus ist aktiviert, wenn "true". Andernfalls verwendet das Gerät den Einzelbildschirmmodus.   |
|\<SendLogs\>   |Container   |Erste & #x 2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |Zeichenfolge & #x 2778;  ||Damit wird eine optionale E-Mail-Adresse verwendet, an die Protokolle gesendet werden können, wenn das Fenster "Feedback senden" angezeigt wird.    |
|\<SendLogsAndFeedback\>   |Boolean & #x 2777;  || Falls zutreffend werden Protokolle an den Administrator gesendet. Falls zutreffend wird Feedback nur an den Administrator (nicht an die Protokolle) gesendet.  |
| \<Geräte\>  |Container   |Erste & #x 2776;  | Die Namen der verbundenen Audiogeräte in den untergeordneten Elementen stimmen mit den Werten in der Gerätemanager-App überein. Die Konfiguration kann ein Gerät enthalten, das derzeit nicht auf dem System vorhanden ist, wie zum Beispiel ein aktuelle nicht mit der Konsole verbundenes A/V-Gerät. Die Konfiguration würde für das entsprechende Gerät beibehalten.  |
|\<MicrophoneForCommunication\>   |Zeichenfolge & #x 2778;  ||Legt das Mikrofon fest, das als Aufnahmegerät in einer Konferenz verwendet wird.   |
|\<SpeakerForCommunication\>   |Zeichenfolge & #x 2778;  ||Das als Lautsprecher für die Konferenz verwendete Gerät. Diese Einstellung wird verwendet, um das Lautsprechergerät festzulegen, das für die Audiowiedergabe in einem Anruf verwendet wird.   |
|\<DefaultSpeaker\>   |Zeichenfolge & #x 2778;  ||Gerät, das zum Abspielen von Audio aus einer HDMI-Erfassungsquelle verwendet wird.    |
| \<Verwendung von Designs\>  |Container   |Erste & #x 2776;  |Bei einer der Funktionen, die unter Verwendung einer XML-Datei verwendet werden kann, handelt es sich um ein benutzerdefiniertes Design für Ihre Organisation. Sie werden können einen Namen des Standarddesigns, Hintergrundbild und Farbe angeben.   |
|\<ThemeName\>   |Zeichenfolge & #x 2778;  || Wird zum Identifizieren des Designs auf dem Client verwendet. Bei den Optionen für den Designnamen handelt es sich um "Standard" (eines der voreingestellten Designs) oder um "Benutzerdefiniert". <br/>  Benutzerdefiniertes Designnamen sollten stets den Namen *Custom* verwenden. Der Client Benutzeroberfläche kann festgelegt werden in der Konsole auf die Standardvorlage oder eine der Vorgaben, jedoch Anwenden eines benutzerdefinierten Designs muss festgelegt werden Remote von einem Administrator. <br/>  Werkseitig eingestellte Designs enthalten: <br/>  Standard <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Verwenden Sie zum Deaktivieren des aktuellen Designs "Kein Design" für die ThemeName.  |
|\<CustomThemeImageUrl\>   |Zeichenfolge & #x 2778;  ||Bei Verwendung eines benutzerdefinierten Designs erforderlich, andernfalls optional. Finden Sie im Abschnitt [Benutzerdefinierte Designs Bilder](xml-config-file.md#Themes) unter Weitere Details auf das Bild der benutzerdefinierten Designs.  |
|\<CustomThemeColor\>   |Container   ||Container für die \<RedComponent\>, \<GreenComponent\>, und \<BlueComponent\> Werte. diese Werte sind bei Verwendung eines benutzerdefinierten Designs erforderlich.   |
|\<RedComponent\>   |Byte (0-255)   ||Stellt die rote Komponente dar.   |
|\<GreenComponent\>   |Byte (0-255)   ||Stellt die grüne Komponente dar.   |
|\<BlueComponent\>   |Byte (0-255)   ||Stellt die blaue Komponente dar.   |
| | | |
   
& #x 2776; Alle Elemente der ersten Ebene sind optional. Wenn ein Element der ersten Ebene ausgelassen wird, bleiben alle diesem Element untergeordneten Parameter auf dem Gerät unverändert.
  
& #x 2777; Ein boolean-Flag kann eine der folgenden sein: True, False, 0 oder 1. Leere boolesche oder numerische Werte führen möglicherweise zu einer fehlerhaften Darstellung der XML-Datei, und die Einstellungen können nicht angewendet werden.
  
 & #x 2778; Wenn Sie ein Zeichenfolgenparameter vorhanden ist, zu leeren, und leer ist ein gültiger Wert, wird der Parameter auf dem Gerät deaktiviert.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Verwalten von Konsoleneinstellungen unter Verwendung einer XML-Konfigurationsdatei

Beim Start eine Microsoft-Teams Chatrooms Konsole findet eine XML-Datei mit dem Namen SkypeSettings.xml an der Position **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, wird die Konfigurationseinstellungen angewendet durch die XML-Datei und klicken Sie dann Löschen der XML-Datei angegeben wird.
  
Je nach wie vielen Geräten von Microsoft Teams Chatrooms Ihr Unternehmen hat und wie verwalten sie konfiguriert werden soll, es gibt eine Reihe von Methoden, um die XML-Konfigurationsdatei zu platzieren. Sobald die Datei  in die Konsole verschoben wurde, starten Sie das Gerät, um die Konfigurationsänderungen zu verarbeiten. Die XML-Datei wird nach erfolgreicher Verarbeitung entfernt. Die Management-Methoden für Microsoft-Teams Chatrooms Geräte vorgeschlagen werden in erläutert:
  
- [Konfigurieren von Gruppenrichtlinien für Microsoft-Teams, Räume](room-systems-v2-operations.md#GroupPolicy)
    
- [Remoteverwaltung mithilfe von PowerShell](room-systems-v2-operations.md#RemotePS) und [Konfigurieren einer Datei](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Sie können eine beliebige-Methode verwenden, solange Sie es zum Übertragen von Dateien und lösen einen Neustart des Geräts Konsole verwenden können möchten. Die Datei muss lesbar, nicht schreibgeschützt und durch das Gerät lokales Benutzerkonto (vorzugsweise, es sollte Besitz und besitzen vollständige Berechtigungen gewährt, die diesem Benutzer) löschen können. Wenn die Dateiberechtigungen nicht richtig eingestellt sind, wird die Software scheitern mitunter Anwendung die Einstellungen, scheitern mitunter So löschen Sie die Datei beim erfolgreiche Verarbeitung und sogar potenziell abstürzt.
  
## <a name="custom-theme-images"></a>Benutzerdefinierte Designbilder
<a name="Themes"> </a>

Benutzerdefiniertes Design Bilddatei muss platziert werden in **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, geben den Dateinamen und die Erweiterung in der \<CustomThemeImageUrl\> Variable.
  
Die Bilddatei muss genau 3840 x 1080 Pixel groß sein und eines der folgenden Dateiformate aufweisen: JPG, JPEG, PNG oder BMP. Wenn Ihre Organisation ein benutzerdefiniertes Bild möchte, wird ein Graphic Designer unsere [Benutzerdefinierte Designs Photoshop Vorlage](https://go.microsoft.com/fwlink/?linkid=870441) hilfreich. Sie enthält weitere Details zur Platzierung der verschiedenen Elemente in einem Designbild und zu den Bereichen, die auf Konsolen und Displays angezeigt werden.
  
Die XML-Konfigurationsdatei muss beim Starten des Geräts aktualisiert werden, damit das Designbild erkannt wird. Sobald die neue XML-Datei verarbeitet und gelöscht wurde, wird die Designgrafikdatei im Verzeichnis gelöscht.
  
## <a name="see-also"></a>Siehe auch


[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

[Konfigurieren eines Dateielements für](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
