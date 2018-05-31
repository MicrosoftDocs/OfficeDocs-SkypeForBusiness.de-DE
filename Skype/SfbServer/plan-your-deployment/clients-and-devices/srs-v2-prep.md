---
title: Vorbereiten der Umgebung
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: In diesem Artikel wird erläutert, die Infrastruktur vorbereitenden Schritte für die Bereitstellung von Skype Raum Systemen v2.
ms.openlocfilehash: b8f1e52686cfab957f2fb81a33deecc778514673
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "19179280"
---
# <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Dieser Abschnitt enthält eine Übersicht über die erforderlichen Schritte zur Ihrer Skype für Business-Umgebung vorbereiten, damit Sie alle Features von Skype Raum Systemen v2 verwenden können.
  
1. Vorbereiten eines Kontos Gerät für jede Skype Raum Systemen v2-Konsole. Einzelheiten finden Sie unter [Bereitstellen von Skype Raum Systemen v2](../../deploy/deploy-clients/room-systems-v2.md) .
    
2. Stellen Sie sicher, dass eine funktionierende Netzwerk-/Internetverbindung vorhanden ist, die für das Gerät verwendet werden kann.  
    
  - Es muss eine IP-Adresse mithilfe von DHCP empfangen (Hinweis: Skype Raum Systemen v2 kann nicht mit einer statischen IP-Adresse beim ersten Start Unit konfiguriert werden)
    
  - Die folgenden Ports müssen geöffnet sein (zusätzlich zu den normalen Ports für Skype for Business-Medien):
    
  - HTTPS: 443
    
  - HTTP: 80
    
  - Wenn Sie in Ihrem Netzwerk einen Proxy verwenden, benötigen Sie außerdem die Proxyadresse oder Skriptinformationen.
    
    > [!NOTE]
    > Skype Raum Systemen v2 HDCP-Eingang festgestellten Probleme mit HDMI verursacht wurde, nicht unterstützt werden Aufnahme Funktionalität (Video, audio). Achten Sie darauf, dass Switches angeschlossen Skype Raum Systemen V2 HDCP-Optionen deaktiviert aufweisen. 
  
3. Microsoft erfasst Daten, um die Benutzerfreundlichkeit zu verbessern. Für die Erfassung der Daten müssen die folgenden Sites in der Whitelist enthalten sein:
    
  - Clientendpunkt Telemetrie:https://vortex.data.microsoft.com/
    
  - Endpunkt für Telemetrie-Einstellungen:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Erstellen und Testen eines Gerätekontos

Ein *Gerät Konto* ist ein Konto, das der Skype Raum Systemen v2-Client-Funktionen von Exchange, wie Kalender zuzugreifen und Skype für Unternehmen aktivieren verwendet. Einzelheiten finden Sie unter [Bereitstellen von Skype Raum Systemen v2](../../deploy/deploy-clients/room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Überprüfen der Netzwerkverfügbarkeit

Um ordnungsgemäß ausgeführt wird, muss das Skype Raum Systemen v2-Gerät auf einem verkabelten Netzwerk zugreifen können, die diese Anforderungen erfüllt:
  
- Zugriff auf Ihre Active Directory- oder Azure Active Directory-Instanz (Azure AD) sowie auf Ihre Server mit Microsoft Exchange und Skype for Business Server
    
- Zugriff auf einen Server, der über DHCP eine IP-Adresse bereitstellen kann. Skype-Chatroom-Systemen v2 kann nicht mit einer statischen IP-Adresse konfiguriert werden.
    
- Zugriff auf die HTTP-Ports 80 und 443
    
- TCP und UDP-Ports, die gemäß der Beschreibung unter [Ports und Protokolle-Anforderungen für Server](../network-requirements/ports-and-protocols.md) für lokal Skype für Business Implementierungen oder [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) für Skype für Business online Implementierungen konfiguriert.
    
> [!IMPORTANT]
> Verwenden Sie unbedingt eine 1-GBit/s-Kabelnetzwerkverbindung, um sicherzustellen, dass die benötigte Bandbreite verfügbar ist.  
  
### <a name="certificates"></a>Zertifikate

Ihr Skype Raum Systemen v2 Gerät verwendet Zertifikate für Exchange-Webdienste, Skype für Unternehmen, Netzwerkauslastung und Authentifizierung. Wenn öffentliche Zertifikate, die die Groß-/Kleinschreibung für die Online- und einige lokale Bereitstellungen ist verwenden Sie die zugehörigen Servern, sollte keine weitere Aktion erforderlich seitens der Admin-Zertifikate installiert sein. Wenn die Zertifizierungsstelle ist eine private Zertifizierungsstelle (Standard für lokale Bereitstellungen) andererseits, muss das Gerät, vertrauen verketten Zertifizierungsstelle die bedeutet, dass die Zertifizierungsstelle + Zertifizierungsstelle Zertifikate auf dem Gerät installiert. Hinzufügen des Geräts auf die Domäne kann diese Aufgabe automatisch ausführen.
  
Sie können Zertifikate genauso installieren wie für jeden anderen Windows-Client. 
  
> [!NOTE]
> Zertifikate Fällen müssen, um die lassen Skype Raum Systemen v2 Skype für Business Server verwenden. 
  
### <a name="proxy"></a>Proxy

Skype Raum Systemen v2 ist darauf ausgelegt, von der Windows-Betriebssystem Proxyeinstellungen erbt. Greifen Sie wie folgt auf das Windows-Betriebssystem zu:
  
1. Klicken Sie auf die Einstellungen Zahnradsymbol, in dem Sie das Kennwort des lokalen Administrators auf dem Gerät aufgefordert werde (das Standard-Kennwort ist **Sfb**), in der Benutzeroberfläche des Skype Raum Systemen v2.
    
2. Tippen Sie auf **Einstellungen** , gefolgt von Tippen auf die Schaltfläche **Gehe zu Windows** , und klicken Sie dann auf die Schaltfläche **Wechseln Sie zur Anmeldung Admin** tippen und dann auf die Schaltfläche " **Administrator** " (wenn der Computer der Domäne verbunden ist wählen Sie **Andere Benutzer** verwenden Sie das . \admin als Benutzernamen).
    
3. In der **Windows Search** Feld unteren linken Geben Sie regedit ein (entweder lange drücken den Bildschirm oder klicken Sie mit der rechten Maustaste auf und wählen Sie **als Administrator ausführen**).
    
4. Klicken Sie auf den Ordner HKEY_USERS. (Eine Liste der Computerbenutzer-SIDs wird angezeigt.) Stellen Sie sicher, dass der Stammordner HKEY_USERS ausgewählt ist.
    
    Sie werden aufgefordert, einen Schlüsselnamen für die neu geladene Struktur; Geben Sie in Skype (sollte jetzt die registrierungseinstellungen für den Benutzer Skype angezeigt werden).
    
5. Klicken Sie auf Datei, und wählen Sie dann **Struktur laden.**
    
6. Durchsuchen der an die **C:\Users\Skype** Ordner und geben Sie den Dateinamen im Feld NTUSER.dat ein, und drücken Sie die Schaltfläche Öffnen
    
7. Öffnen Sie den Registrierungsschlüssel Skype und gehen Sie auf HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Einstellungen, und stellen Sie sicher, dass diese Einstellungen eingegeben werden: 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy" = DWORD: 00000001
    
    "ProxyEnable" = DWORD: 00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    Wenn „ProxyServer“ nicht vorhanden ist, müssen Sie diesen Schlüssel möglicherweise als Zeichenfolge hinzufügen. Ändern Sie „xx.xx.xx.xx:8080“ zu IP/Host und Port Ihres Proxyservers.
    
8. Nachdem Sie die Hervorhebung der Skype-Benutzer (Stammordner für Skype)-Taste, und wählen Sie die Struktur aus der Registrierung im Dateimenü (Sie werden aufgefordert zur Bestätigung - wählen Sie **Ja** ) entfernen Änderungen vorgenommen werden.
    
9. Schließen Sie nun den Registrierungs-Editor, und geben Sie in das Feld der Windows-Suche „Abmelden“ ein.
    
10. Wählen Sie auf der Anmeldeseite den Benutzer **Skype** aus. Wenn die oben beschriebenen Schritte erfolgreich waren, der Skype Raum Systemen v2 Gerät wird erfolgreich anmelden.
    
Um diese Anwendung zu verwenden, müssen Sie eine Verbindung mit den unten beschriebenen Endpunkten herstellen können. Die IP-Adressen können Sie anzeigen, indem Sie den Abschnitt mit den IP-Adressen unter der Tabelle erweitern, in der der Datenverkehrsfluss beschrieben wird.
  
**Beispiele für Firewall-Proxy Host Name/externer Port**

|**Zweck**|**Quell- oder Anmeldeinformationen**|**Quellport**|**Ziel**|**CDN**|**ExpressRoute für Office 365**|**Ziel-IP-**|**Zielport**|
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
|Skype-Telemetrie  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |skypemaprdsitus.trafficmanager.NET  <br/> Pipe.Skype.com  <br/> |Nein  <br/> |Nein  <br/> |n/v  <br/> |TCP 443  <br/> |
|Skype-Client-Hinweise  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |quicktips.skypeforbusiness.com  <br/> |Nein  <br/> |Nein  <br/> |n/v  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> Der Platzhalter für contoso.com und broadcast.skype.com steht für eine lange Liste von Knoten, die ausschließlich für Office 365 verwendet werden. 
  
### <a name="create-provisioning-packages"></a>Erstellen von Bereitstellungspaketen

Provisioning Pakete verwendet zum Authentifizieren zu Exchange Server oder Skype für Business Server.
  
### <a name="admin-group-management"></a>Verwaltung von Administratorgruppen

Nach dem Beitritt zur Domäne können Sie Gruppenrichtlinie oder die lokale Computerverwaltung nutzen, um eine Sicherheitsgruppe als lokalen Administrator festzulegen, so wie Sie es auch auf einem Windows-PC in Ihrer Domäne tun. Alle Mitglieder dieser Sicherheitsgruppe können ihre Anmeldeinformationen eingeben und die Einstellungen entsperren.
  
> [!NOTE]
> Wenn Ihre Skype Raum Systemen v2-Gerät verliert Vertrauensstellung mit der Domäne (beispielsweise, wenn Sie die Skype Raum Systemen v2 aus der Domäne entfernen, nach der Domäne beigetreten ist), werden nicht Sie an das Gerät authentifizieren und Einstellungen zu öffnen. Zur Problemumgehung können Sie sich mit dem lokalen Administratorkonto anmelden. 
  
## <a name="local-accounts"></a>Lokale Konten

### <a name="skype-room-systems-local-user-account"></a>Lokales Benutzerkonto für Skype Room System

Das Gerät Konto wird nicht in der Regel ein Kennwort verwendet werden. Es ist möglich, ihm ein Kennwort geben, aber es gibt folgen, einschließlich der Möglichkeit, dass Benutzer die Konsolenanwendung möglicherweise beim gesperrt abrufen, Kennwort läuft ab. Daher sollte der Administrator verwenden werden, um sicherzustellen, dass das Kennwort an, die ablaufen nicht zulässig ist.
  
### <a name="admin---local-administrator-account"></a>„Admin“ – lokales Administratorkonto

Skype-Chatroom-Systemen v2 Standard-Kennwort ist auf "Sfb" festgelegt. Das Kennwort kann lokal geändert werden, indem Sie auf Windows-Einstellungen \> Go für Windows oder in der Datei AutoUnattend.xml (verwenden Sie den Windows System Image Manager ADK zum Ändern der Xml-Datei).
  
> [!CAUTION]
> Achten Sie darauf, dass das Skype Raum Systemen v2 Kennwort so bald wie möglich zu ändern. 
  
Das Kennwort des lokalen Administrators können Sie auch verwalten, indem Sie eine Gruppenrichtlinie einrichten, in der Domänenadministratoren als lokale Administratoren festgelegt werden.
  
Das Kennwort des lokalen Administrators wird beim Setup nicht als Auswahl angeboten.
  
### <a name="machine-account"></a>Computerkonto

Viel wie Windows-Gerät den Namen des Computers können umbenannt werden durch Klicken auf mit der rechten Maustaste in den Einstellungen \> zu \> PC umbenennen.
  
 Wenn Sie den Computer nach verknüpfen es mit einer Domäne umbenennen möchten, verwenden Sie den Rename-Computer-PowerShell-Befehl, gefolgt von der neue Name des Computers.
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen von Skype Raum Systemen v2](skype-room-systems-v2-0.md)

[Skype-Chatroom-Systemen v2 Anforderungen](requirements.md)
  
[Bereitstellen von Skype Raum Systemen v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Konfigurieren einer Skype Raum Systemen v2-Konsole](../../deploy/deploy-clients/console.md)
  
[Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

