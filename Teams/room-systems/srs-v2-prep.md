---
title: Vorbereiten der Umgebung
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: In diesem Artikel wird erläutert, die Infrastruktur vorbereitenden Schritte für die Bereitstellung von Microsoft-Teams Chatrooms.
ms.openlocfilehash: b1830ba68b61c322b6eeef95f29b1e72d2b93303
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865014"
---
# <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Dieser Abschnitt enthält eine Übersicht über die erforderlichen Schritte zur Vorbereitung Ihrer Umgebung, damit Sie alle Features von Microsoft-Teams Chatrooms verwenden können.
  
1. Vorbereiten eines Kontos Gerät für jede Microsoft-Teams Räume-Konsole. Einzelheiten finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms](room-systems-v2.md) .
    
2. Stellen Sie sicher, dass eine funktionierende Netzwerk-/Internetverbindung vorhanden ist, die für das Gerät verwendet werden kann. 
    
   - Es muss eine IP-Adresse über DHCP erhalten können. (Microsoft Teams Chatrooms kann nicht mit einer statischen IP-Adresse beim ersten Start Unit konfiguriert werden, aber später statische IP-Adresse für das Gerät konfiguriert werden auf dem Gerät oder auf den Upstream-Switch oder Router.)
    
   - Sie benötigen diese Ports (zusätzlich zum Öffnen der normalen Ports für Medien) zu öffnen:
    
   - HTTPS: 443
    
   - HTTP: 80
    
   - Wenn Sie in Ihrem Netzwerk einen Proxy verwenden, benötigen Sie außerdem die Proxyadresse oder Skriptinformationen.
    
     > [!NOTE]
     > Microsoft Teams Rooms unterstützt keine HDCP-Eingabe. Von dieser ist bekannt, dass sie Probleme mit der HDMI-Erfassungsfunktion (Video, Audio) verursacht. Stellen Sie sicher, dass die HDCP-Optionen der mit Microsoft Teams Rooms verbundenen Switches deaktiviert sind. 
  
3. Microsoft erfasst Daten, um die Benutzerfreundlichkeit zu verbessern. Für die Erfassung der Daten müssen die folgenden Sites in der Whitelist enthalten sein:
    
   - Clientendpunkt Telemetrie:https://vortex.data.microsoft.com/
    
   - Endpunkt für Telemetrie-Einstellungen:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Erstellen und Testen eines Gerätekontos

Ein *Gerät Konto* ist ein Konto, das der Microsoft-Teams Räume-Client-Funktionen von Exchange, wie Kalender zuzugreifen und Skype für Unternehmen aktivieren verwendet. Einzelheiten finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms](room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Überprüfen der Netzwerkverfügbarkeit

Um ordnungsgemäß ausgeführt wird, muss das Gerät Microsoft Teams Räume auf einem verkabelten Netzwerk zugreifen können, die diese Anforderungen erfüllt:
  
- Zugriff auf Ihre Active Directory- oder Azure Active Directory-Instanz (Azure AD) sowie auf Ihre Server mit Microsoft Exchange und Skype for Business Server
- Zugriff auf einen Server, der über DHCP eine IP-Adresse bereitstellen kann. Microsoft-Teams Chatrooms kann nicht mit einer statischen IP-Adresse konfiguriert werden.
- Zugriff auf die HTTP-Ports 80 und 443
- TCP und UDP-Ports konfiguriert als in for beschrieben, [Ports und Protokolle-Anforderungen für Server](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) am Standort Skype für Implementierungen Business Server oder [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) für Microsoft-Teams oder Skype für Business online Implementierungen.

> [!IMPORTANT]
> Verwenden Sie unbedingt eine 1-GBit/s-Kabelnetzwerkverbindung, um sicherzustellen, dass die benötigte Bandbreite verfügbar ist.
  
### <a name="certificates"></a>Zertifikate

Ihr Gerät Microsoft Teams Chatrooms verwendet Zertifikate für Exchange-Webdienste, Microsoft-Teams oder Skype für Unternehmen, Netzwerkauslastung und Authentifizierung. Wenn öffentliche Zertifikate, die die Groß-/Kleinschreibung für die Online- und einige lokale Bereitstellungen ist verwenden Sie die zugehörigen Servern, sollte keine weitere Aktion erforderlich seitens der Admin-Zertifikate installiert sein. Wenn die Zertifizierungsstelle ist eine private Zertifizierungsstelle (Standard für lokale Bereitstellungen) andererseits, muss das Gerät, vertrauen verketten Zertifizierungsstelle die bedeutet, dass die Zertifizierungsstelle + Zertifizierungsstelle Zertifikate auf dem Gerät installiert. Hinzufügen des Geräts auf die Domäne kann diese Aufgabe automatisch ausführen.
  
Sie können Zertifikate genauso installieren wie für jeden anderen Windows-Client. 
  
> [!NOTE]
> Zertifikate Fällen müssen, um Microsoft Teams Räume Skype für Business Server verwendet haben.
  
### <a name="proxy"></a>Proxy

Microsoft-Teams Chatrooms soll das Windows-Betriebssystem Proxyeinstellungen vererben. Greifen Sie wie folgt auf das Windows-Betriebssystem zu:
  
1. Klicken Sie in der Benutzeroberfläche des Microsoft-Teams Chatrooms auf das Symbol Einstellungen Zahnrad, in dem Sie das Kennwort des lokalen Administrators auf dem Gerät aufgefordert werde (das Standard-Kennwort ist **Sfb**).
2. Tippen Sie auf **Einstellungen** , gefolgt von Tippen auf die Schaltfläche **Gehe zu Windows** , und klicken Sie dann auf die Schaltfläche **Wechseln Sie zur Anmeldung Admin** tippen und dann auf die Schaltfläche " **Administrator** " (wenn der Computer der Domäne verbunden ist wählen Sie **Andere Benutzer** verwenden Sie das . \admin als Benutzernamen).
3. In der **Windows Search** Feld unteren linken Geben Sie regedit ein (entweder lange drücken den Bildschirm oder klicken Sie mit der rechten Maustaste auf und wählen Sie **als Administrator ausführen**).
4. Klicken Sie auf den Ordner HKEY_USERS. (Eine Liste der Computerbenutzer-SIDs wird angezeigt.) Stellen Sie sicher, dass der Stammordner HKEY_USERS ausgewählt ist.
       
5. Klicken Sie auf Datei, und wählen Sie dann **Struktur laden.**
6. Durchsuchen der an die **C:\Users\Skype** Ordner und geben Sie den Dateinamen im Feld NTUSER.dat ein, und drücken Sie die Schaltfläche Öffnen

7. Sie werden aufgefordert, einen Schlüsselnamen für die neu geladene Struktur; Geben Sie in Skype (sollte jetzt die registrierungseinstellungen für den Benutzer Skype angezeigt werden).
 
8. Öffnen Sie den Registrierungsschlüssel Skype und gehen Sie auf HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Einstellungen, und stellen Sie sicher, dass diese Einstellungen eingegeben werden: 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"=dword:00000001
    
    "ProxyEnable"=dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    Wenn „ProxyServer“ nicht vorhanden ist, müssen Sie diesen Schlüssel möglicherweise als Zeichenfolge hinzufügen. Ändern Sie „xx.xx.xx.xx:8080“ zu IP/Host und Port Ihres Proxyservers.
    
9. Nachdem Sie die Hervorhebung der Skype-Benutzer (Stammordner für Skype)-Taste, und wählen Sie die Struktur aus der Registrierung im Dateimenü (Sie werden aufgefordert zur Bestätigung - wählen Sie **Ja** ) entfernen Änderungen vorgenommen werden.
    
10. Schließen Sie nun den Registrierungs-Editor, und geben Sie in das Feld der Windows-Suche „Abmelden“ ein.
    
11. Wählen Sie auf der Anmeldeseite den Benutzer **Skype** aus. Wenn die oben beschriebenen Schritte erfolgreich waren, das Microsoft-Teams Chatrooms Gerät wird erfolgreich anmelden.
    
Um diese Anwendung zu verwenden, müssen Sie eine Verbindung mit den unten beschriebenen Endpunkten herstellen können. Die IP-Adressen können Sie anzeigen, indem Sie den Abschnitt mit den IP-Adressen unter der Tabelle erweitern, in der der Datenverkehrsfluss beschrieben wird.
  
**Name des Firewall-Proxyhosts/Portbeispiele**

|Verwendungszweck|Quelle oder Anmeldeinformationen|Quellport|Ziel|CDN|ExpressRoute für Office 365|Ziel-IP|Zielport|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Authentifizierung und Identität  <br/> |Finden Sie unter [Office 365-Authentifizierung und Identität](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal und gemeinsame Dienste  <br/> |Finden Sie unter [Office 365-Portal und freigegebene](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|SIP-Signalisierung  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Webkonferenzen über PSOM-Verbindungen (Persistent Shared Object Model)  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS-Downloads  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |TCP/UDP 50000-50019  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59999  <br/> |
|Video  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |TCP/UDP 50.020-50039  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59999  <br/> |
|Desktopfreigabe  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |TCP/UDP 50.040-50059  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50000-59999  <br/> |
|Lync Mobile-Pushbenachrichtigungen für Lync Mobile 2010 auf iOS-Geräten. Für Android-, Nokia Symbian- oder Windows Phone-Mobilgeräte benötigen Sie dies nicht.  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype-Telemetrie  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |Nein  <br/> |Nein  <br/> |n/v  <br/> |TCP 443  <br/> |
|Skype-Client-Hinweise  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |quicktips.skypeforbusiness.com  <br/> |Nein  <br/> |Nein  <br/> |n/v  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> Der Platzhalter für contoso.com und broadcast.skype.com steht für eine lange Liste von Knoten, die ausschließlich für Office 365 verwendet werden. 
  
### <a name="create-provisioning-packages"></a>Bereitstellung Pakete erstellen

Bereitstellung Pakete verwendet zum Authentifizieren zu Exchange Server oder Office 365.
  
### <a name="admin-group-management"></a>Admin Gruppe-Verwaltung

Nach der Domäne beitreten können Sie Gruppenrichtlinien oder dem lokalen Computer Management verwenden, um eine Sicherheitsgruppe als lokaler Administrator ebenso wie für einen Windows-PC in Ihrer Domäne festzulegen. Jeder Benutzer, der Mitglied der Sicherheitsgruppe ist kann seine Anmeldeinformationen eingeben und entsperren Einstellungen.
  
> [!NOTE]
> Wenn die Vertrauensstellung zwischen Ihrem Microsoft Teams Rooms-Gerät und der Domäne verloren geht (zum Beispiel, wenn Sie Microsoft Teams Rooms nach dem Domänenbeitritt aus der Domäne entfernen), können Sie sich nicht gegenüber dem Gerät authentifizieren und die Einstellungen öffnen. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
  
## <a name="local-accounts"></a>Lokale Konten

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft-Teams, Räume lokales Benutzerkonto

Das Gerät Konto wird nicht in der Regel ein Kennwort verwendet werden. Es ist möglich, ihm ein Kennwort geben, aber es gibt folgen, einschließlich der Möglichkeit, dass Benutzer die Konsolenanwendung möglicherweise beim gesperrt abrufen, Kennwort läuft ab. Daher sollte der Administrator verwenden werden, um sicherzustellen, dass das Kennwort an, die ablaufen nicht zulässig ist.
  
### <a name="admin---local-administrator-account"></a>"Admin" - lokale Administratorkonto

Microsoft-Teams Chatrooms Standard-Kennwort ist auf "Sfb" festgelegt. Das Kennwort kann lokal geändert werden, indem Sie auf Windows-Einstellungen \> Go für Windows oder in der Datei AutoUnattend.xml (verwenden Sie den Windows System Image Manager ADK zum Ändern der Xml-Datei).
  
> [!CAUTION]
> Achten Sie darauf, dass Sie das Microsoft-Teams Chatrooms Kennwort so bald wie möglich zu ändern. 
  
Sie können auch das Kennwort des lokalen Administrators verwalten, indem Sie eine Gruppenrichtlinie zu einrichten, Domänen-Admins werden, auf dem lokale Administratoren vorgenommen..
  
Kennwort für den lokalen Administrator ist nicht während des Setups als Auswahl enthalten.
  
### <a name="machine-account"></a>Computerkonto

Viel wie Windows-Gerät den Namen des Computers können umbenannt werden durch Klicken auf mit der rechten Maustaste in den Einstellungen \> zu \> PC umbenennen.
  
 Wenn Sie den Computer nach verknüpfen es mit einer Domäne umbenennen möchten, verwenden Sie den Rename-Computer-PowerShell-Befehl, gefolgt von der neue Name des Computers.
  
## <a name="see-also"></a>Siehe auch

[Planen der Microsoft-Teams, Räume](skype-room-systems-v2-0.md)

[Microsoft-Teams Chatrooms Anforderungen](requirements.md)
  
[Bereitstellen von Microsoft-Teams, Räume](room-systems-v2.md)
  
[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
