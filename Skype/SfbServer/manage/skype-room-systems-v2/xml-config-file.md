---
title: Verwalten einer Skype Room Systems v2-Konsoleneinstellung auf einem Remote-Gerät mit einer XML-Konfigurationsdatei
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: In diesem Artikel wird remote Management die Standardeinstellungen, die von einem Gerät Skype Raum Systemen v2, einschließlich eines benutzerdefinierten Designs verwendet.
ms.openlocfilehash: 74f098e44e3b25eafd48d1309e0454034f56d1f5
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="manage-a-skype-room-systems-v2-console-settings-remotely-with-an-xml-configuration-file"></a>Verwalten einer Skype Room Systems v2-Konsoleneinstellung auf einem Remote-Gerät mit einer XML-Konfigurationsdatei
 
In diesem Artikel wird remote Management die Standardeinstellungen, die von einem Gerät Skype Raum Systemen v2, einschließlich eines benutzerdefinierten Designs verwendet.
  
Eine Master-Shape XML-Datei aktualisiert und Senden von Kopien den Konsolen, die Sie verwalten ermöglicht es zum Ändern der Standardeinstellungen für die Remoteverwaltung Geräte. In diesem Artikel wird erläutert, wie solche einer Datei sowie Links zu Diskussionen zum Platzieren Bedarf auf den Remote verwalteten Geräten zu erstellen. Mit dieser Methode können Sie auch benutzerdefinierte Designs auf Ihre Skype Raum Systemen v2 Konsolen implementieren. 
  
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
             <AutoRotatePassword>1</AutoRotatePassword>
  </UserAccount>    
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
 
|**Element**|**Typ**|**Ebene**|**Verwendung**|
|:-----|:-----|:-----|:-----|
|\<SkypeSettings\>  <br/> |Container für alle Elemente.  <br/> ||Erforderlich.  <br/> |
| \<AutoScreenShare\> <br/> |Boolescher Wert & #x 2777; <br/> |Erste & #x 2776; <br/> | Falls zutreffend, ist die automatische Bildschirmfreigabe aktiviert. <br/> |
|\<HideMeetingName\>  <br/> |Boolescher Wert & #x 2777; <br/> |Erste & #x 2776; <br/> |Falls zutreffend, sind die Besprechungsnamen ausgeblendet.  <br/> |
|\<"Useraccount" bei\>  <br/> |Container  <br/> |Erste & #x 2776; <br/> |Container für Anmeldeinformationen-Parameter.  <br/> Anmelden bei Adresse, die Exchange-Adresse oder die e-Mail-Adresse in der Regel identisch sind, wie etwa RanierConf<span></span>@contoso.com.  <br/> |
|\<SkypeMeetingsEnabled\>  <br/> |Boolescher Wert & #x 2777; <br/> |Erste & #x 2776; <br/> |Diese Option ist standardmäßig aktiviert.  <br/> |
|\<TeamsMeetingsEnabled\>  <br/> |Boolescher Wert & #x 2777; <br/> |Erste & #x 2776; <br/> |Diese Option ist standardmäßig deaktiviert.  <br/> Die XML-Datei wird nicht wohlgeformten betrachtet, wenn beide \<SkypeMeetingsEnabled\> und\<TeamsMeetingsEnabled\> sind deaktiviert, aber es ist akzeptabel, beide Einstellungen zur selben Zeit aktiviert haben.  <br/> |
|\<SkypeSignInAddress\>  <br/> |Zeichenfolge 3 <br/> ||Der Anmeldename für das Skype for Business-Gerätekonto der Konsole.  <br/> |
|\<ExchangeAddress\>  <br/> |Zeichenfolge 3 <br/> ||Der Anmeldename für das Exchange-Gerätekonto der Konsole.  <br/> Wenn die Exchange-Adresse ausgelassen wird, wird die Skype-Anmeldeadresse nicht automatisch wiederverwendet.   <br/> |
|\<DomainUsername\>  <br/> |Zeichenfolge & #x 2778; <br/> ||Die Domäne und der Benutzername für das Konsolengerät, zum Beispiel Seattle\RanierConf.  <br/> |
|\<Kennwort\>  <br/> |Zeichenfolge 3 <br/> || Der Kennwortparameter stimmt mit dem für die Kontoanmeldung für das Skype for Business-Gerät verwendeten Kennwort überein.  <br/> |
| \<ConfigureDomain\> <br/> |Zeichenfolge & #x 2778; <br/> ||Sie können mehrere durch Kommata getrennte Domänen auflisten.  <br/> |
|\<AutoRotatePassword\>  <br/> |Boolescher Wert & #x 2777; <br/> |||
| \<DualScreenMode\> <br/> |Boolescher Wert & #x 2777; <br/> |Erste & #x 2776; <br/> |Dual-Screen-Modus ist aktiviert, wenn "true". Andernfalls verwendet das Gerät den Einzelbildschirmmodus.  <br/> |
|\<SendLogs\>  <br/> |Container  <br/> |Erste & #x 2776; <br/> ||
|\<EmailAddressForLogsAndFeedback\>  <br/> |Zeichenfolge & #x 2778; <br/> ||Damit wird eine optionale E-Mail-Adresse verwendet, an die Protokolle gesendet werden können, wenn das Fenster "Feedback senden" angezeigt wird.   <br/> |
|\<SendLogsAndFeedback\>  <br/> |Boolescher Wert & #x 2777; <br/> || Falls zutreffend werden Protokolle an den Administrator gesendet. Falls zutreffend wird Feedback nur an den Administrator (nicht an die Protokolle) gesendet. <br/> |
| \<Geräte\> <br/> |Container  <br/> |Erste & #x 2776; <br/> | Die Namen der verbundenen Audiogeräte in den untergeordneten Elementen stimmen mit den Werten in der Gerätemanager-App überein. Die Konfiguration kann ein Gerät enthalten, das derzeit nicht auf dem System vorhanden ist, wie zum Beispiel ein aktuelle nicht mit der Konsole verbundenes A/V-Gerät. Die Konfiguration würde für das entsprechende Gerät beibehalten. <br/> |
|\<MicrophoneForCommunication\>  <br/> |Zeichenfolge 3 <br/> ||Legt das Mikrofon fest, das als Aufnahmegerät in einer Konferenz verwendet wird.  <br/> |
|\<SpeakerForCommunication\>  <br/> |Zeichenfolge 3 <br/> ||Das als Lautsprecher für die Konferenz verwendete Gerät. Diese Einstellung wird verwendet, um das Lautsprechergerät festzulegen, das für die Audiowiedergabe in einem Anruf verwendet wird.  <br/> |
|\<DefaultSpeaker\>  <br/> |Zeichenfolge 3 <br/> ||Gerät, das zum Abspielen von Audio aus einer HDMI-Erfassungsquelle verwendet wird.   <br/> |
| \<Verwendung von Designs\> <br/> |Container  <br/> |Erste & #x 2776; <br/> |Bei einer der Funktionen, die unter Verwendung einer XML-Datei verwendet werden kann, handelt es sich um ein benutzerdefiniertes Design für Ihre Organisation. Sie werden können einen Namen des Standarddesigns, Hintergrundbild und Farbe angeben.  <br/> |
|\<ThemeName\>  <br/> |Zeichenfolge & #x 2778; <br/> || Wird zum Identifizieren des Designs auf dem Client verwendet. Bei den Optionen für den Designnamen handelt es sich um "Standard" (eines der voreingestellten Designs) oder um "Benutzerdefiniert". <br/>  Benutzerdefiniertes Designnamen sollten stets den Namen *Custom* verwenden. Der Client Benutzeroberfläche kann festgelegt werden in der Konsole auf die Standardvorlage oder eine der Vorgaben, jedoch Anwenden eines benutzerdefinierten Designs muss festgelegt werden Remote von einem Administrator. <br/>  Werkseitig eingestellte Designs enthalten: <br/>  Standard <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Verwenden Sie zum Deaktivieren des aktuellen Designs "Kein Design" für die ThemeName. <br/> |
|\<CustomThemeImageUrl\>  <br/> |Zeichenfolge & #x 2778; <br/> ||Erforderlich, wenn ein benutzerdefiniertes Design, andernfalls optional. Finden Sie im Abschnitt [Benutzerdefinierte Designs Bilder](xml-config-file.md#Themes) unter Weitere Details auf das Bild der benutzerdefinierten Designs. <br/> |
|\<CustomThemeColor\>  <br/> |Container  <br/> ||Container für die \<RedComponent\>, \<GreenComponent\>, und \<BlueComponent\> Werte. diese Werte sind bei Verwendung eines benutzerdefinierten Designs erforderlich.  <br/> |
|\<RedComponent\>  <br/> |Byte (0-255)  <br/> ||Stellt die rote Komponente dar.  <br/> |
|\<GreenComponent\>  <br/> |Byte (0-255)  <br/> ||Stellt die grüne Komponente dar.  <br/> |
|\<BlueComponent\>  <br/> |Byte (0-255)  <br/> ||Stellt die blaue Komponente dar.  <br/> |
   
& #x 2776; Alle Elemente der ersten Ebene sind optional. Wenn ein Element der ersten Ebene ausgelassen wird, bleiben alle diesem Element untergeordneten Parameter auf dem Gerät unverändert.
  
& #x 2777; Ein boolean-Flag kann eine der folgenden sein: True, False, 0 oder 1. Leere boolesche oder numerische Werte führen möglicherweise zu einer fehlerhaften Darstellung der XML-Datei, und die Einstellungen können nicht angewendet werden.
  
 & #x 2778; Wenn Sie ein Zeichenfolgenparameter vorhanden ist, zu leeren, und leer ist ein gültiger Wert, wird der Parameter auf dem Gerät deaktiviert.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Verwalten von Konsoleneinstellungen unter Verwendung einer XML-Konfigurationsdatei

Beim Start eine Skype Raum Systemen v2 Konsole findet eine XML-Datei mit dem Namen SkypeSettings.xml an der Position ** C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, anschließend wird der Konfigurationseinstellungen für den angegebenen angewendet Löschen Sie dann die XML-Datei, indem der XML-Datei.
  
Je nach wie vielen Geräten von Skype Raum Systemen v2 Ihr Unternehmen hat und wie verwalten sie konfiguriert werden soll, es gibt eine Reihe von Methoden, um die XML-Konfigurationsdatei zu platzieren. Sobald die Datei  in die Konsole verschoben wurde, starten Sie das Gerät, um die Konfigurationsänderungen zu verarbeiten. Die XML-Datei wird nach erfolgreicher Verarbeitung entfernt. Die Management-Methoden für Skype Raum Systemen v2 Geräte vorgeschlagen werden in erläutert:
  
- [Konfigurieren von Gruppenrichtlinie für Skype Room Systems v2](room-systems-v2-operations.md#GroupPolicy)
    
- [Remoteverwaltung mithilfe von PowerShell](room-systems-v2-operations.md#RemotePS) und [Konfigurieren einer Datei](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Sie können eine beliebige-Methode verwenden, solange Sie es zum Übertragen von Dateien und lösen einen Neustart des Geräts Konsole verwenden können möchten. Die Datei muss lesbar, nicht schreibgeschützt und durch das Gerät lokales Benutzerkonto (vorzugsweise, es sollte Besitz und besitzen vollständige Berechtigungen gewährt, die diesem Benutzer) löschen können. Wenn die Dateiberechtigungen nicht richtig eingestellt sind, wird die Software scheitern mitunter Anwendung die Einstellungen, scheitern mitunter So löschen Sie die Datei beim erfolgreiche Verarbeitung und sogar potenziell abstürzt.
  
## <a name="custom-theme-images"></a>Benutzerdefinierte Designbilder
<a name="Themes"> </a>

Benutzerdefiniertes Design Bilddatei muss platziert werden in **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, geben den Dateinamen und die Erweiterung in der \<CustomThemeImageUrl\> Variable.
  
Die Bilddatei muss genau 3840X1080 Pixel enthalten und eines der folgenden Formate aufweisen: jpg, jpeg, png und bmp. Wenn Ihre Organisation ein benutzerdefiniertes Bild möchte, wird ein Graphic Designer unsere [Benutzerdefinierte Designs Photoshop Vorlage](https://go.microsoft.com/fwlink/?linkid=870441) hilfreich. Sie enthält weitere Details auf verschiedenen Elemente in einem Design-Abbild platzieren und welche Bereiche auf Konsolen und zeigt angezeigt.
  
Die XML-Konfigurationsdatei muss beim Starten des Geräts aktualisiert werden, damit das Designbild erkannt wird. Sobald die neue XML-Datei verarbeitet und gelöscht wurde, wird die Designgrafikdatei im Verzeichnis gelöscht.
  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="Themes"> </a>

#### 

[Verwalten von Skype Raum Systemen v2](skype-room-systems-v2.md)
#### 

[Konfigurieren eines Dateielements für](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

