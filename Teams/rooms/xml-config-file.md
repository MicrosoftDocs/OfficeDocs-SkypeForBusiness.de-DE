---
title: Remoteverwaltung von Microsoft Teams rooms-Geräteeinstellungen
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
description: Remote Verwaltung der Standardeinstellungen, die von einem Microsoft Teams rooms-Gerät verwendet werden, einschließlich Anwenden eines benutzerdefinierten Designs und Erstellen einer Master Einstellungsdatei
ms.openlocfilehash: 0334b9de7759885b6bf00dae7a6418b3c381c68f
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160069"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei

In diesem Artikel wird die Remoteverwaltung der Standardeinstellungen beschrieben, die von einem Microsoft Teams rooms-Gerät verwendet werden, einschließlich der Anwendung eines benutzerdefinierten Designs. In diesem Artikel wird erläutert, wie Sie eine Master Einstellungsdatei erstellen, und Links zu Diskussionen darüber, wie Sie auf den Remote verwalteten Geräten nach Bedarf platziert werden.
  
Sie können die Standardeinstellungen von Remote verwalteten Geräten ändern, indem Sie eine Master-XML-Datei aktualisieren und Kopien an die verwalteten Konsolen senden. Sie können auch benutzerdefinierte Designs auf Ihren Microsoft Teams rooms-Konsolen mit XML-Konfigurationsdateien implementieren.
  
## <a name="create-an-xml-configuration-file"></a>Erstellen einer XML-Konfigurationsdatei

Sie können einen beliebigen Text-Editor verwenden, um eine Einstellungsdatei zu erstellen. In der Tabelle **XML-Elemente** werden die Elemente erläutert, die in dieser Beispielkonfigurationsdatei SkypeSettings. XML (required File Name) angezeigt werden.
  
```XML
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
    <ModernAuthEnabled>false</ModernAuthEnabled>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <DuplicateIngestDefault>false</DuplicateIngestDefault>
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
        <CustomThemeImageUrl>file name</CustomThemeImageUrl>
        <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
        </CustomThemeColor>
    </Theming>
</SkypeSettings>
```

Wenn ein Variablenwert vom falschen Typ ist, Elemente nicht in der richtigen Reihenfolge sind, Elemente nicht geschlossen sind oder ein anderer Fehler gefunden wird, ist die XML-Datei *schlecht geformt*. Beim Verarbeiten einer schlecht ausgebildeten XML-Datei werden die Einstellungen, die bis zu dem Punkt gefunden wurden, an dem der Fehler auftritt, übernommen, und der restliche Teil der Datei wird ignoriert. Unbekannte Elemente im XML-Code werden ignoriert. Wenn ein Parameter ausgelassen wird, bleibt er auf dem Gerät unverändert. Wenn ein Parameterwert ungültig ist, bleibt sein vorheriger Wert unverändert.
  
**XML-Elemente**

|Element|Typ|Ebene|Verwendung|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |Container für alle Elemente. ||Erforderlich. |
| \<AutoScreenShare\>  |Boolescher &#x2777;  |Erste &#x2776;  | Falls zutreffend, ist die automatische Bildschirmfreigabe aktiviert.  |
|\<HideMeetingName\> |Boolescher &#x2777;  |Erste &#x2776;  |Falls zutreffend, sind die Besprechungsnamen ausgeblendet. |
|\<Benutzerkonto\> |Container |Erste &#x2776;  |Container für Anmeldeinformationen-Parameter. Die Anmeldeadresse, die Exchange-Adresse oder die e-Mail-Adresse sind in der Regel<span></span>identisch, beispielsweise RanierConf @contoso. com. |
|\<SkypeMeetingsEnabled\>  |Boolescher &#x2777;  |Erste &#x2776;  |Diese Option ist standardmäßig aktiviert. |
|\<SkypeSignInAddress\> |Zeichenfolge &#x2778;  ||Der Anmeldename für das SFB-oder Teams-Geräte Konto der Konsole. |
|\<ExchangeAddress\> |Zeichenfolge &#x2778;  ||Der Anmeldename für das Exchange-Gerätekonto der Konsole. Wenn der ExchangeAddress ausgelassen wird, wird der SkypeSignInAddress nicht automatisch wieder verwendet. |
|\<Domain User Name\> |Zeichenfolge &#x2778;  ||Die Domäne und der Benutzername für das Konsolengerät, zum Beispiel Seattle\RanierConf. |
|\<Kennwort\> |Zeichenfolge 3  || Der Kennwortparameter stimmt mit dem für die Kontoanmeldung für das Skype for Business-Gerät verwendeten Kennwort überein.   |
| \<ConfigureDomain\>  |Zeichenfolge &#x2778;  ||Sie können mehrere durch Kommata getrennte Domänen auflisten. |
|\<TeamsMeetingsEnabled\> |Boolescher &#x2777;  |Erste &#x2776;  |Diese ist standardmäßig deaktiviert. <br/> <br/> Die XML-Datei wird als schlecht geformt betrachtet \<,\> Wenn\<sowohl\> SkypeMeetingsEnabled als auch TeamsMeetingsEnabled deaktiviert sind, es aber akzeptabel ist, dass beide Einstellungen gleichzeitig aktiviert sind. |
|\<IsTeamsDefaultClient> |Boolescher &#x2777;  |Erste &#x2776;  |Diese ist standardmäßig deaktiviert. |
|\<ModernAuthEnabled> |Boolescher &#x2777;  |Erste &#x2776;  |Diese ist standardmäßig deaktiviert. <br/> <br/>Wenn Sie auf "true" festgelegt ist, verwendet die Microsoft Teams rooms-Anwendung nur die moderne Authentifizierung, um eine Verbindung mit Ressourcen herzustellen, die nicht auf die Standardauthentifizierung zurückgreifen.|
|\<BluetoothAdvertisementEnabled> |Boolescher &#x2777;  |Erste &#x2776;  |Diese Option ist standardmäßig aktiviert. |
|\<DualScreenMode\>  |Boolescher &#x2777;  |Erste &#x2776;  |Ist der Wert "true", ist der duale Bildschirm aktiviert. Andernfalls verwendet das Gerät den Single-Screen-Modus. |
| \<DuplicateIngestDefault\> |Boolescher &#x2777;  |Erste &#x2776; |Wenn "true" festgelegt ist, wird der Inhalt auf beiden Bildschirmen im dualen Bildschirm angezeigt, wenn die Besprechung nicht stattfindet. | 
|\<SendLogs\> |Container |Erste &#x2776;  |  |
|\<EmailAddressForLogsAndFeedback\> |Zeichenfolge &#x2778;  | | Legt eine optionale e-Mail-Adresse fest, an die Protokolle gesendet werden können, wenn das Fenster "Feedback senden" angezeigt wird. |
|\<SendLogsAndFeedback\> |Boolescher &#x2777;  | | Falls zutreffend werden Protokolle an den Administrator gesendet. Falls zutreffend wird Feedback nur an den Administrator (nicht an die Protokolle) gesendet.  |
| \<Geräte\>  |Container |Erste &#x2776;  | Die Namen der verbundenen Audiogeräte in den untergeordneten Elementen stimmen mit den Werten in der Gerätemanager-App überein. Die Konfiguration kann ein Gerät enthalten, das derzeit nicht auf dem System vorhanden ist, wie zum Beispiel ein aktuelle nicht mit der Konsole verbundenes A/V-Gerät. Die Konfiguration würde für das entsprechende Gerät beibehalten.  |
|\<MicrophoneForCommunication\> |Zeichenfolge &#x2778;  ||Legt das Mikrofon fest, das in einer Konferenz als Aufnahmegerät verwendet wird. |
|\<SpeakerForCommunication\> |Zeichenfolge &#x2778;  ||Das als Lautsprecher für die Konferenz verwendete Gerät. Diese Einstellung wird verwendet, um das für einen Anruf verwendete Lautsprecher Gerät festzulegen. |
|\<DefaultSpeaker\> |Zeichenfolge &#x2778;  ||Gerät, das zum Abspielen von Audio aus einer HDMI-Erfassungsquelle verwendet wird.  |
|\<ContentCameraId>  | Zeichenfolge &#x2778;  | | Definieren Sie den instanzweg für die Kamera, die in Room so konfiguriert ist, dass analoge Whiteboard-Inhalte in einer Besprechung freigegeben werden. Weitere Informationen finden Sie unter [Suchen des USB-Instanzen Pfads der Inhalts Kamera](#locate-the-content-camera-usb-instance-path).|
|\<ContentCameraInverted>  | Boolescher &#x2777; | | Geben Sie an, ob die Inhalts Kamera physisch auf den Kopf gestellt wird. Für Inhalts Kameras, die die automatische Drehung unterstützen, geben Sie false an. |
|\<ContentCameraEnhancement>  | Boolescher &#x2777; | |Wenn Sie auf "true" (Standardeinstellung) festgelegt ist, wird das Bild der Inhalts Kamera Digital verbessert: der Whiteboard-Rand wird erkannt und ein geeigneter Zoom ausgewählt, frei Handlinien werden verbessert, und die Person, die auf dem Whiteboard schreibt, wird transparent gemacht.  <br><br> Auf "false" festlegen, wenn Sie einen unformatierten Videofeed an Besprechungsteilnehmer für Räume senden möchten, in denen ein Whiteboard nicht mit einem Stift gezeichnet wird, und stattdessen die Kamera verwendet wird, um Haftnotizen, Poster oder andere Medien anzuzeigen.  |
| \<Design\>  |Container |Erste &#x2776;  |Eines der Features, die mit einer XML-Datei angewendet werden können, ist ein benutzerdefiniertes Design für Ihre Organisation. Sie können einen Designnamen, ein Hintergrundbild und eine Farbe angeben. |
|\<ThemeName\> |Zeichenfolge &#x2778;  || Wird zum Identifizieren des Designs auf dem Client verwendet. Bei den Optionen für den Designnamen handelt es sich um "Standard" (eines der voreingestellten Designs) oder um "Benutzerdefiniert". <br/>  Benutzerdefinierte Designnamen verwenden immer den Namen *Custom*. Die Client-Benutzeroberfläche kann in der Konsole auf den Standardwert oder eine der Voreinstellungen eingestellt werden, doch die Verwendung eines benutzerdefinierten Designs muss von einem Administrator Remote eingerichtet werden. <br/>  Werkseitig eingestellte Designs enthalten:  <br/>  Standard <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Wenn Sie das aktuelle Design deaktivieren möchten, verwenden Sie für den Designname "kein Design".  |
|\<CustomThemeImageUrl\> |Zeichenfolge &#x2778;  ||Erforderlich für ein benutzerdefiniertes Design, andernfalls optional. Geben Sie nur den Dateinamen ein.   |Weitere Informationen zum benutzerdefinierten Design Bild finden Sie im Abschnitt [benutzerdefinierte Design Bilder](xml-config-file.md#Themes) .
|\<CustomThemeColor\> |Container ||Container für die \<Werte für\>" \<iscomponent" \<,\> "GreenComponent\>" und "BlueComponent". Diese Werte sind für ein benutzerdefiniertes Design erforderlich. |
|\<Komponente\> |Byte (0-255) ||Stellt die rote Komponente dar. |
|\<GreenComponent\> |Byte (0-255) ||Stellt die grüne Komponente dar. |
|\<BlueComponent\> |Byte (0-255) ||Stellt die blaue Komponente dar. | 
| | | |

&#x2776; alle Elemente der ersten Ebene sind optional. Wenn ein Element der ersten Ebene ausgelassen wird, bleiben alle diesem Element untergeordneten Parameter auf dem Gerät unverändert.
  
&#x2777; ein boolesches Flag kann: wahr, falsch, 0 oder 1 sein. Wenn Sie boolesche oder numerische Werte leer lassen, kann die XML-Datei fehlerhaft gerendert werden, sodass Änderungen an den Einstellungen verhindert werden.
  
&#x2778; Wenn ein Zeichenfolgenparameter vorhanden und leer ist und Empty ein gültiger Wert ist, wird der Parameter auf dem Gerät gelöscht.
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>Verwalten von Konsoleneinstellungen unter Verwendung einer XML-Konfigurationsdatei

Wenn eine Microsoft Teams rooms-Konsole beim Start eine XML-Datei mit dem Namen "SkypeSettings. `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`XML" gefunden hat, wendet Sie die von der XML-Datei angegebenen Konfigurationseinstellungen an und löscht dann die XML-Datei.
  
Je nachdem, wie viele Microsoft Teams rooms-Geräte in Ihrem Unternehmen vorhanden sind und wie Sie diese Konfiguration verwalten, gibt es verschiedene Möglichkeiten, die XML-Konfigurationsdatei zu platzieren. Sobald die Datei  in die Konsole verschoben wurde, starten Sie das Gerät, um die Konfigurationsänderungen zu verarbeiten. Die XML-Datei wird nach erfolgreicher Verarbeitung entfernt. Die für Microsoft Teams Room-Geräte vorgeschlagenen Verwaltungsmethoden werden in folgenden Themen erörtert:
  
- [Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Chatrooms](rooms-operations.md#GroupPolicy)
- [Remote Verwaltung mithilfe von PowerShell](rooms-operations.md#RemotePS) und [Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

Sie können jede beliebige Methode so lange verwenden, wie Sie Sie verwenden können, um Dateien zu übertragen und einen Neustart auf dem Konsolengerät auszulösen. Die Datei muss für das lokale Benutzerkonto des Geräts lesbar, schreibbar und Lösch fähig sein. Vorzugsweise ist es im Besitz von und hat alle Rechte, die diesem Nutzer gewährt werden. Wenn die Dateiberechtigungen nicht richtig gesetzt sind, kann die Software die Einstellungen nicht anwenden, kann die Datei bei erfolgreicher Verarbeitung nicht löschen und kann sogar abstürzen.
  
## <a name="custom-theme-images"></a>Benutzerdefinierte Designbilder

<a name="Themes"> </a>

Die Image-Datei für ein benutzerdefiniertes Design`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` muss im Ordner abgelegt werden. Geben Sie den Dateinamen und die Erweiterung \<in\> die CustomThemeImageUrl-Variable ein.
  
Die Bilddatei sollte genau 3840X1080 Pixel sein und eines der folgenden Dateiformate aufweisen: JPG, JPEG, PNG und BMP. Wenn Ihre Organisation ein benutzerdefiniertes Bild wünscht, kann ein Grafikdesigner die [Photoshop-Vorlage "benutzerdefiniertes Design](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)" verwenden. Sie enthält weitere Informationen darüber, wo sich verschiedene Benutzeroberflächenelemente relativ zum restlichen Design Bild befinden und welche Bereiche auf Konsolen und Displays angezeigt werden.
  
Die XML-Konfigurationsdatei muss beim Starten des Geräts aktualisiert werden, damit das Designbild erkannt wird. Nachdem die neue XML-Datei verarbeitet und gelöscht wurde, wird die Design Grafikdatei aus dem Verzeichnis gelöscht.
  
## <a name="locate-the-content-camera-usb-instance-path"></a>Suchen des USB-Instanzen Pfads der Inhalts Kamera

So suchen Sie den Instanzen Pfad:

1. Wechseln Sie in der Microsoft Teams rooms-Konsole zu Windows-Einstellungen.
2. Geben Sie das Administratorkennwort ein.
3. Geben `devmgmt.msc` Sie an der Eingabeaufforderung ein, um den Geräte-Manager aufzurufen.
4. Suchen Sie im **Geräte-Manager**den Knoten **Imaging Devices** , und suchen Sie die Inhalts Kamera.
5. Klicken Sie mit der rechten Maustaste auf die Kamera, und öffnen Sie **Eigenschaften**.
6. Wählen Sie die Registerkarte **Details** aus, und suchen Sie in der Dropdownliste die Eigenschaft **Geräteinstanzen Pfad** .
7. Der angezeigte Wert ist der in der XML-Konfigurationsdatei zu definierende Device-Instanzen Pfad. Wenn Sie den Pfad in XML angeben, ersetzen Sie das kaufmännische und `&amp;`-Zeichen (&) durch.

## <a name="see-also"></a>Siehe auch

[Inhalts-Kameras](content-camera.md)

[Microsoft Teams Rooms verwalten](rooms-manage.md)

[Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
