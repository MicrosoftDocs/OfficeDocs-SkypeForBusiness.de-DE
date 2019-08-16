---
title: Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: In diesem Artikel wird die Remoteverwaltung der Standardeinstellungen beschrieben, die von einem Microsoft Teams rooms-Gerät verwendet werden, einschließlich der Anwendung eines benutzerdefinierten Designs.
ms.openlocfilehash: c66aaba35fc678400118e67d7c66f362842c869f
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427621"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei

In diesem Artikel wird die Remoteverwaltung der Standardeinstellungen beschrieben, die von einem Microsoft Teams rooms-Gerät verwendet werden, einschließlich der Anwendung eines benutzerdefinierten Designs.
  
Wenn Sie eine Master-XML-Datei aktualisieren und Kopien an die von Ihnen verwalteten Konsolen senden, können Sie die Standardeinstellungen für Remote verwaltete Geräte ändern. In diesem Artikel wird beschrieben, wie Sie eine solche Datei erstellen, und Links zu Diskussionen darüber, wie Sie auf den Remote verwalteten Geräten nach Bedarf platziert werden. Mit dieser Methode können Sie auch benutzerdefinierte Designs auf Ihren Microsoft Teams rooms-Konsolen implementieren.
  
## <a name="create-an-xml-configuration-file"></a>Erstellen einer XML-Konfigurationsdatei

In der folgenden Tabelle werden die in dieser Beispielkonfigurationsdatei SkypeSettings. XML (Dateinamen erforderlich) angezeigten Elemente erläutert.
  
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
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
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

Wenn die XML-Datei schlecht geformt ist (ein Variablenwert ist vom falschen Typ, Elemente sind nicht in der richtigen Reihenfolge, Elemente werden nicht geschlossen usw.), Einstellungen, die bis zu dem Punkt gefunden wurden, an dem der Fehler gefunden wurde, werden angewendet, und die restliche Datei wird während der Verarbeitung ignoriert. Unbekannte Elemente im XML-Code werden ignoriert. Wenn ein Parameter ausgelassen wird, bleibt er auf dem Gerät unverändert. Wenn ein Parameterwert ungültig ist, bleibt sein vorheriger Wert unverändert.
  
**XML-Elemente**

|Element|Typ|Ebene|Verwendung|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |Container für alle Elemente. ||Erforderlich. |
| \<AutoScreenShare\>  |Boolescher #a0  |Erste #a0  | Falls zutreffend, ist die automatische Bildschirmfreigabe aktiviert.  |
|\<HideMeetingName\> |Boolescher #a0  |Erste #a0  |Falls zutreffend, sind die Besprechungsnamen ausgeblendet. |
|\<Benutzerkonto\> |Container |Erste #a0  |Container für Anmeldeinformationen-Parameter. Die Anmeldeadresse, die Exchange-Adresse oder die e-Mail-Adresse sind in der Regel<span></span>identisch, beispielsweise RanierConf @contoso. com. |
|\<SkypeMeetingsEnabled\>  |Boolescher #a0  |Erste #a0  |Diese Option ist standardmäßig aktiviert. |
|\<SkypeSignInAddress\> |Zeichenfolge #a0  ||Der Anmeldename für das SFB-oder Teams-Geräte Konto der Konsole. |
|\<ExchangeAddress\> |Zeichenfolge #a0  ||Der Anmeldename für das Exchange-Gerätekonto der Konsole. Wenn der ExchangeAddress ausgelassen wird, wird der SkypeSignInAddress nicht automatisch wieder verwendet. |
|\<Domain User Name\> |Zeichenfolge #a0  ||Die Domäne und der Benutzername für das Konsolengerät, zum Beispiel Seattle\RanierConf. |
|\<Kennwort\> |Zeichenfolge 3  || Der Kennwortparameter stimmt mit dem für die Kontoanmeldung für das Skype for Business-Gerät verwendeten Kennwort überein.   |
| \<ConfigureDomain\>  |Zeichenfolge #a0  ||Sie können mehrere durch Kommata getrennte Domänen auflisten. |
|\<TeamsMeetingsEnabled\> |Boolescher #a0  |Erste #a0  |Diese ist standardmäßig deaktiviert. <br/> <br/> Die XML-Datei wird als schlecht geformt betrachtet \<,\> Wenn\<sowohl\> SkypeMeetingsEnabled als auch TeamsMeetingsEnabled deaktiviert sind, es aber akzeptabel ist, dass beide Einstellungen gleichzeitig aktiviert sind. |
|\<IsTeamsDefaultClient> |Boolescher #a0  |Erste #a0  |Diese ist standardmäßig deaktiviert. |
|\<BluetoothAdvertisementEnabled> |Boolescher #a0  |Erste #a0  |Diese Option ist standardmäßig aktiviert. |
|\<DualScreenMode\>  |Boolescher #a0  |Erste #a0  |Ist der Wert "true", ist der duale Bildschirm aktiviert. Andernfalls verwendet das Gerät den Single-Screen-Modus. |
|\<SendLogs\> |Container |Erste #a0  ||
|\<EmailAddressForLogsAndFeedback\> |Zeichenfolge #a0  || Legt eine optionale e-Mail-Adresse fest, an die Protokolle gesendet werden können, wenn das Fenster "Feedback senden" angezeigt wird. |
|\<SendLogsAndFeedback\> |Boolescher #a0  || Falls zutreffend werden Protokolle an den Administrator gesendet. Falls zutreffend wird Feedback nur an den Administrator (nicht an die Protokolle) gesendet.  |
| \<Geräte\>  |Container |Erste #a0  | Die Namen der verbundenen Audiogeräte in den untergeordneten Elementen stimmen mit den Werten in der Gerätemanager-App überein. Die Konfiguration kann ein Gerät enthalten, das derzeit nicht auf dem System vorhanden ist, wie zum Beispiel ein aktuelle nicht mit der Konsole verbundenes A/V-Gerät. Die Konfiguration würde für das entsprechende Gerät beibehalten.  |
|\<MicrophoneForCommunication\> |Zeichenfolge #a0  ||Legt das Mikrofon fest, das in einer Konferenz als Aufnahmegerät verwendet wird. |
|\<SpeakerForCommunication\> |Zeichenfolge #a0  ||Das als Lautsprecher für die Konferenz verwendete Gerät. Diese Einstellung wird verwendet, um das Lautsprechergerät festzulegen, das für die Audiowiedergabe in einem Anruf verwendet wird. |
|\<DefaultSpeaker\> |Zeichenfolge #a0  ||Gerät, das zum Abspielen von Audio aus einer HDMI-Erfassungsquelle verwendet wird.  |
|\<ContentCameraId>  | Zeichenfolge #a0  | | Definieren Sie den instanzweg für die Kamera, die in Room so konfiguriert ist, dass analoge Whiteboard-Inhalte in einer Besprechung freigegeben werden. Weitere Informationen finden Sie unter [Suchen des USB-Instanzen Pfads der Inhalts Kamera](#locate-the-content-camera-usb-instance-path).|
|\<ContentCameraInverted>  | Boolescher #a0 | | Geben Sie an, ob die Inhalts Kamera physisch auf den Kopf gestellt wird. Für Inhalts Kameras, die die automatische Drehung unterstützen, geben Sie false an. |
|\<ContentCameraEnhancement>  | Boolescher #a0 | |Wenn Sie auf "true" (Standardeinstellung) festgelegt ist, wird das Bild der Inhalts Kamera Digital verbessert: der Whiteboard-Rand wird erkannt und ein geeigneter Zoom ausgewählt, frei Handlinien werden verbessert, und die Person, die auf dem Whiteboard schreibt, wird transparent gemacht.  <br><br> Legen Sie diesen Wert auf "false" fest, wenn Sie einen unformatierten Videofeed an Besprechungsteilnehmer für Räume senden möchten, in denen ein Whiteboard nicht mit einem Stift gezeichnet wird, und stattdessen die Kamera verwendet wird, um Haftnotizen, Poster oder andere Medien anzuzeigen.  |
| \<Design\>  |Container |Erste #a0  |Bei einer der Funktionen, die unter Verwendung einer XML-Datei verwendet werden kann, handelt es sich um ein benutzerdefiniertes Design für Ihre Organisation. Sie können einen Designnamen, ein Hintergrundbild und eine Farbe angeben. |
|\<ThemeName\> |Zeichenfolge #a0  || Wird zum Identifizieren des Designs auf dem Client verwendet. Bei den Optionen für den Designnamen handelt es sich um "Standard" (eines der voreingestellten Designs) oder um "Benutzerdefiniert". <br/>  Für benutzerdefinierte Namen sollte immer der Name *Benutzerdefiniert* verwendet werden. Die Client-UI kann an der Konsole auf "Standard" oder eine der Werkseinstellungen festgelegt werden. Die Anwendung eines benutzerdefinierten Designs muss jedoch remote von einem Administrator festgelegt werden. <br/>  Werkseitig eingestellte Designs enthalten:  <br/>  Standard <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Wenn Sie das aktuelle Design deaktivieren möchten, verwenden Sie für den Designname "kein Design".  |
|\<CustomThemeImageUrl\> |Zeichenfolge #a0  ||Bei Verwendung eines benutzerdefinierten Designs erforderlich, andernfalls optional. Weitere Informationen zum benutzerdefinierten Design Bild finden Sie unten im Abschnitt [benutzerdefinierte Design Bilder](xml-config-file.md#Themes) .  |
|\<CustomThemeColor\> |Container ||Container für die \<Werte für\>" \<iscomponent" \<,\> "GreenComponent\>" und "BlueComponent". diese Werte sind bei Verwendung eines benutzerdefinierten Designs erforderlich. |
|\<Komponente\> |Byte (0-255) ||Stellt die rote Komponente dar. |
|\<GreenComponent\> |Byte (0-255) ||Stellt die grüne Komponente dar. |
|\<BlueComponent\> |Byte (0-255) ||Stellt die blaue Komponente dar. |
| | | |
 
&#x2776; alle Elemente der ersten Ebene sind optional. Wenn ein Element der ersten Ebene ausgelassen wird, bleiben alle diesem Element untergeordneten Parameter auf dem Gerät unverändert.
  
&#x2777; ein boolesches Flag kann einen der folgenden Werte aufweisen: true, false, 0 oder 1. Wenn Sie boolesche oder numerische Werte leer lassen, wird die XML-Datei möglicherweise fehlerhaft gerendert, und Änderungen an den Einstellungen werden verhindert.
  
 &#x2778; Wenn ein Zeichenfolgenparameter vorhanden, leer und leer ein gültiger Wert ist, wird der Parameter auf dem Gerät gelöscht.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Verwalten von Konsoleneinstellungen unter Verwendung einer XML-Konfigurationsdatei

Wenn eine Microsoft Teams rooms-Konsole beim Start eine XML-Datei mit dem Namen "SkypeSettings. xml" am Standort **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**findet, wendet Sie die Konfigurationseinstellungen an. durch die XML-Datei gekennzeichnet, und löschen Sie dann die XML-Datei.
  
Je nachdem, wie viele Microsoft Teams rooms-Geräte in Ihrem Unternehmen vorhanden sind und wie Sie diese Konfiguration verwalten, gibt es verschiedene Möglichkeiten, die XML-Konfigurationsdatei zu platzieren. Sobald die Datei  in die Konsole verschoben wurde, starten Sie das Gerät, um die Konfigurationsänderungen zu verarbeiten. Die XML-Datei wird nach erfolgreicher Verarbeitung entfernt. Die für Microsoft Teams Room-Geräte vorgeschlagenen Verwaltungsmethoden werden in folgenden Themen erörtert:
  
- [Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Chatrooms](room-systems-v2-operations.md#GroupPolicy)

- [Remote Verwaltung mithilfe von PowerShell](room-systems-v2-operations.md#RemotePS) und [Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

Sie können jede beliebige Methode so lange verwenden, wie Sie Sie verwenden können, um Dateien zu übertragen und einen Neustart auf dem Konsolengerät auszulösen. Die Datei muss für das lokale Benutzerkonto des Geräts lesbar, beschreibbar und löschbar sein (vorzugsweise sollte Sie im Besitz des Besitzers sein und die vollständigen Berechtigungen besitzen, die diesem Benutzer gewährt wurden). Wenn die Dateiberechtigungen nicht richtig gesetzt sind, kann es vorkommen, dass die Software die Einstellungen nicht anwendet, die Datei bei erfolgreicher Verarbeitung möglicherweise nicht löscht und sogar potenziell abstürzt.
  
## <a name="custom-theme-images"></a>Benutzerdefinierte Designbilder

<a name="Themes"> </a>

Die benutzerdefinierte Design-Bilddatei muss in **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**abgelegt werden, geben Sie den Dateinamen und \<die\> Erweiterung in die CustomThemeImageUrl-Variable ein.
  
Die Bilddatei sollte genau 3840X1080 Pixel sein und eines der folgenden Dateiformate aufweisen: JPG, JPEG, PNG und BMP. Wenn Ihre Organisation ein benutzerdefiniertes Bild wünscht, kann ein Grafikdesigner die [Photoshop-Vorlage "benutzerdefiniertes Design](https://go.microsoft.com/fwlink/?linkid=870441)" verwenden. Sie enthält weitere Details zur Platzierung der verschiedenen Elemente in einem Designbild und zu den Bereichen, die auf Konsolen und Displays angezeigt werden.
  
Die XML-Konfigurationsdatei muss beim Starten des Geräts aktualisiert werden, damit das Designbild erkannt wird. Nachdem die neue XML-Datei verarbeitet und gelöscht wurde, wird die Design Grafikdatei aus dem Verzeichnis gelöscht.
  
## <a name="locate-the-content-camera-usb-instance-path"></a>Suchen des USB-Instanzen Pfads der Inhalts Kamera

So suchen Sie den Instanzen Pfad:

1. Wechseln Sie in der Microsoft Teams rooms-Konsole zu Windows-Einstellungen.
2. Geben Sie das Administratorkennwort ein.
3. Geben `devmgmt.msc` Sie an der Eingabeaufforderung ein, um den Geräte-Manager aufzurufen.
4. Suchen Sie im **Geräte-Manager**den Knoten **Imaging Devices** , und suchen Sie die Inhalts Kamera.
5. Klicken Sie mit der rechten Maustaste auf die Kamera, und öffnen Sie **Eigenschaften**.
6. Wählen Sie die Registerkarte **Details** aus, und suchen Sie in der Dropdownliste die Eigenschaft **Geräteinstanzen Pfad** .
7. Der angezeigte Wert ist der in der XML-Konfigurationsdatei zu definierende Device-Instanzen Pfad. Wenn Sie den Pfad in XML angeben, ersetzen Sie das kaufmännische und `&amp;`-Zeichen (#a0) durch.

## <a name="see-also"></a>Siehe auch

[Content-Kameras](content-camera.md)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

[Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
