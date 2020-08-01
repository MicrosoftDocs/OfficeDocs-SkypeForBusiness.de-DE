---
title: Vorbereiten Ihrer Umgebung
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie Ihre Infrastruktur für die Bereitstellung von Microsoft Teams-Räumen vorbereiten, damit Sie alle Features nutzen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e520643d40e78065d4b6a0359a8ca567ba2284c
ms.sourcegitcommit: bf6521f0bc91a55dcf849506bb757ebfae54fcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529178"
---
# <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Dieser Abschnitt enthält eine Übersicht über die Schritte, die erforderlich sind, um Ihre Umgebung vorzubereiten, damit Sie alle Features von Microsoft Teams-Räumen verwenden können.
  
1. Bereiten Sie ein Geräte Konto für jede Microsoft Teams rooms-Konsole vor. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen](rooms-deploy.md) .
    
2. Stellen Sie sicher, dass eine funktionierende Netzwerk-/Internetverbindung vorhanden ist, die für das Gerät verwendet werden kann. 
    
   - Sie muss eine IP-Adresse über DHCP empfangen können. (Microsoft Teams-Räume können beim ersten Start der Einheit nicht mit einer statischen IP-Adresse konfiguriert werden, aber anschließend kann die statische IP für das Gerät auf dem Gerät oder auf dem Upstream-Switch oder-Router konfiguriert werden.)
   - Diese Ports müssen geöffnet sein (zusätzlich zum Öffnen der normalen Ports für Medien):
   - HTTPS: 443
   - HTTP: 80
   - Wenn Sie in Ihrem Netzwerk einen Proxy verwenden, benötigen Sie außerdem die Proxyadresse oder Skriptinformationen.
    
     > [!IMPORTANT]
     > Microsoft Teams rooms unterstützt keine Proxyauthentifizierung, da dies den normalen Betrieb des Raums stören kann. Stellen Sie sicher, dass Microsoft Teams-Chatrooms von der Proxyauthentifizierung ausgenommen wurden, bevor Sie die Produktion durchlaufen.
  
3. Microsoft erfasst Daten, um die Benutzerfreundlichkeit zu verbessern. Damit Microsoft Daten sammeln kann, können Sie diese Websites zulassen:

   - Telemetrie-Clientendpunkt:https://vortex.data.microsoft.com/
   - Endpunkt der Telemetrie-Einstellungen:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Erstellen und Testen eines Gerätekontos

Bei einem *Geräte Konto* handelt es sich um ein Konto, das der Microsoft Teams rooms-Client verwendet, um auf Features aus Exchange zuzugreifen, wie Kalender, und um Skype for Business zu aktivieren. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen](rooms-deploy.md) .
  
### <a name="check-network-availability"></a>Überprüfen der Netzwerkverfügbarkeit

Um ordnungsgemäß zu funktionieren, muss das Microsoft Teams rooms-Gerät Zugriff auf ein kabelgebundenes Netzwerk haben, das diese Anforderungen erfüllt:
  
- Zugriff auf Ihre Active Directory- oder Azure Active Directory-Instanz (Azure AD) sowie auf Ihre Server mit Microsoft Exchange und Skype for Business Server
- Zugriff auf einen Server, der über DHCP eine IP-Adresse bereitstellen kann. Microsoft Teams-Räume können beim ersten Start der Einheit nicht mit einer statischen IP-Adresse konfiguriert werden.
- Zugriff auf die HTTP-Ports 80 und 443
- TCP-und UDP-Ports, wie unter [Port-und Protokollanforderungen für Server](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) für lokale Skype for Business Server-Implementierungen oder [Microsoft 365-und Office 365-URLs und IP-Adressbereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) für Microsoft Teams oder Skype for Business Online-Implementierungen beschrieben.

> [!IMPORTANT]
> Verwenden Sie unbedingt eine 1-GBit/s-Kabelnetzwerkverbindung, um sicherzustellen, dass die benötigte Bandbreite verfügbar ist.

> [!NOTE]
> Software Updates für Microsoft Teams-Chatrooms werden automatisch aus dem Microsoft Store für Unternehmen heruntergeladen. Weitere Informationen finden Sie unter [Voraussetzungen für Microsoft Store für Unternehmen und Bildungseinrichtungen](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) , um zu überprüfen, ob die Raum Konsole auf den Store zugreifen und sich selbst aktualisieren kann.
  
### <a name="certificates"></a>Zertifikate

Ihr Microsoft Teams rooms-Gerät verwendet Zertifikate für Exchange-Webdienste, Microsoft Teams oder Skype for Business, Netzwerkverwendung und Authentifizierung. Wenn die verwandten Server öffentliche Zertifikate verwenden, was bei Online-und einigen lokalen Bereitstellungen der Fall ist, ist es nicht erforderlich, dass der Administrator weitere Aktionen zum Installieren von Zertifikaten benötigt. Handelt es sich bei der Zertifizierungsstelle andererseits um eine private Zertifizierungsstelle (die für lokale Bereitstellungen typisch ist), muss das Gerät dieser Zertifizierungsstelle vertrauen, was bedeutet, dass die Zertifizierungsstellenzertifikate auf dem Gerät installiert sind. Durch Hinzufügen des Geräts zur Domäne kann diese Aufgabe automatisch ausgeführt werden.
  
Sie können Zertifikate genauso installieren wie für jeden anderen Windows-Client. 
  
> [!NOTE]
> Möglicherweise sind Zertifikate erforderlich, damit Microsoft Teams-Chatrooms Skype for Business Server verwenden können.
  
### <a name="proxy"></a>Proxy

Microsoft Teams rooms wurde entwickelt, um Proxy Einstellungen vom Windows-Betriebssystem zu erben. Greifen Sie wie folgt auf das Windows-Betriebssystem zu:
  
1. Klicken Sie in der Microsoft Teams-Benutzeroberfläche auf das Zahnradsymbol für Einstellungen, in dem Sie aufgefordert werden, das lokale Administrator Kennwort auf dem Gerät einzugeben (das Standardkennwort ist **SFB**).
2. Tippen Sie auf **Einstellungen** , und klicken Sie dann auf die Schaltfläche **zu Windows wechseln** , und tippen Sie dann auf die Schaltfläche **zur Administratoranmeldung** und dann auf die Schaltfläche **Administrator** (wenn der Computer der Domäne beigetreten ist, wählen Sie **anderer Benutzer aus,** und verwenden Sie dann .\admin als Benutzernamen).
3. Geben Sie im Feld **Suchfenster** unten links in regedit ein (entweder lang drücken Sie den Bildschirm, oder klicken Sie mit der rechten Maustaste, und wählen Sie **als Administrator ausführen**) aus.
4. Klicken Sie auf den Ordner HKEY_USERS. (Eine Liste der Computerbenutzer-SIDs wird angezeigt.) Stellen Sie sicher, dass der Stammordner HKEY_USERS ausgewählt ist.
       
5. Klicken Sie auf Datei, und wählen Sie dann **Hive laden aus.**
6. Navigieren Sie zum Ordner **C:\Users\Skype** , geben Sie im Feld Dateiname den Namen Ntuser. dat ein, und drücken Sie die Schaltfläche öffnen.

7. Sie werden aufgefordert, einen Schlüsselnamen für die neu geladene Struktur zu erhalten. Geben Sie Skype ein (die Registrierungseinstellungen für den Skype-Nutzer sollten nun angezeigt werden).
 
8. Öffnen Sie den Skype-Schlüssel und navigieren Sie zu HKEY_USERS \skype\software\microsoft\windows\currentversion\internet-Einstellungen, und stellen Sie sicher, dass diese Einstellungen eingegeben werden: 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    Wenn „ProxyServer“ nicht vorhanden ist, müssen Sie diesen Schlüssel möglicherweise als Zeichenfolge hinzufügen. Ändern Sie „xx.xx.xx.xx:8080“ zu IP/Host und Port Ihres Proxyservers.
    
9. Nachdem Sie Ihre Änderungen vorgenommen haben, markieren Sie den Skype-Nutzer Schlüssel (Root-Ordner für Skype), und wählen Sie im Menü der Registrierungsdatei die Option "Hive entladen" aus (Sie werden zur Bestätigung aufgefordert – wählen Sie **Ja** ).
    
10. Schließen Sie nun den Registrierungs-Editor, und geben Sie in das Feld der Windows-Suche „Abmelden“ ein.
    
11. Wählen Sie auf der Anmeldeseite den Benutzer **Skype** aus. Wenn alle vorherigen Schritte erfolgreich waren, meldet sich das Microsoft Teams rooms-Gerät erfolgreich an.
    
Um diese Anwendung zu verwenden, müssen Sie eine Verbindung mit den unten beschriebenen Endpunkten herstellen können. Die IP-Adressen können Sie anzeigen, indem Sie den Abschnitt mit den IP-Adressen unter der Tabelle erweitern, in der der Datenverkehrsfluss beschrieben wird.
  
**Name des Firewall-Proxyhosts/Portbeispiele**

|Verwendungszweck|Quelle oder Anmeldeinformationen|Quellport|Ziel|CDN|ExpressRoute für Office 365|Ziel-IP|Zielport|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Authentifizierung und Identität  <br/> |Informationen zu [Microsoft 365 und Office 365-Authentifizierung und-Identität](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal und gemeinsame Dienste  <br/> |Siehe [Microsoft 365 Admin Center und freigegeben](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|SIP-Signalisierung  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[IP-Bereiche für Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Webkonferenzen über PSOM-Verbindungen (Persistent Shared Object Model)  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[IP-Bereiche für Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS-Downloads  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[IP-Bereiche für Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |TCP/UDP 50000-50019  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[IP-Bereiche für Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59999  <br/> |
|Video  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |TCP/UDP 50.020-50039  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[IP-Bereiche für Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59999  <br/> |
|Desktopfreigabe  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |TCP/UDP 50.040-50059  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[IP-Bereiche für Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50000-59999  <br/> |
|Lync Mobile-Pushbenachrichtigungen für Lync Mobile 2010 auf iOS-Geräten. Für Android-, Nokia Symbian- oder Windows Phone-Mobilgeräte benötigen Sie dies nicht.  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |\*. contoso.com  <br/> |Nein  <br/> |Ja  <br/> |[IP-Bereiche für Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype-Telemetrie  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |Nein  <br/> |Nein  <br/> |n/v  <br/> |TCP 443  <br/> |
|Skype-Client – schnelle Tipps  <br/> |Clientcomputer oder angemeldeter Benutzer  <br/> |Kurzlebige Ports  <br/> |quicktips.skypeforbusiness.com  <br/> |Nein  <br/> |Nein  <br/> |n/v  <br/> |TCP 443  <br/> |

> [!NOTE]
> Der Platzhalter für contoso.com und Broadcast.Skype.com stellt eine lange Liste von Knoten dar, die ausschließlich für Microsoft 365 oder Office 365 verwendet werden. 
  
### <a name="create-provisioning-packages"></a>Erstellen von Bereitstellungspaketen

Sie verwenden Bereitstellungspakete zur Authentifizierung bei Exchange Server, Microsoft 365 oder Office 365.
  
### <a name="admin-group-management"></a>Verwaltung von Administratoren Gruppen

Nach dem Beitritt zur Domäne können Sie mithilfe von Gruppenrichtlinien oder der lokalen Computer Verwaltung eine Sicherheitsgruppe wie bei einem Windows-PC in Ihrer Domäne als lokaler Administrator festlegen. Jeder, der Mitglied dieser Sicherheitsgruppe ist, kann seine Anmeldeinformationen eingeben und Einstellungen entsperren.
  
> [!NOTE]
> Wenn die Vertrauensstellung zwischen Ihrem Microsoft Teams Rooms-Gerät und der Domäne verloren geht (zum Beispiel, wenn Sie Microsoft Teams Rooms nach dem Domänenbeitritt aus der Domäne entfernen), können Sie sich nicht gegenüber dem Gerät authentifizieren und die Einstellungen öffnen. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
  
## <a name="local-accounts"></a>Lokale Konten

### <a name="microsoft-teams-rooms-local-user-account"></a>Lokales Benutzerkonto für Microsoft Teams rooms

Das Geräte Konto verwendet in der Regel kein Kennwort. Es ist möglich, ihm ein Kennwort zu geben, doch es gibt Konsequenzen, einschließlich der Möglichkeit, dass Benutzer möglicherweise aus der Konsolenanwendung ausgeschlossen werden, wenn das Kennwort abläuft. Daher sollte der Administrator sicherstellen, dass das Kennwort nicht abläuft.
  
### <a name="admin---local-administrator-account"></a>"Administrator" – Lokales Administrator Konto

Microsoft Teams rooms Standardkennwort ist auf "SFB" eingestellt. Das Kennwort kann lokal geändert werden, indem Sie zu Windows-Einstellungen \> wechseln Sie zu Windows oder in der AutoUnattend.xml Datei (verwenden Sie den Windows System Image Manager von ADK, um die Änderung an der XML-Datei vorzunehmen).
  
> [!CAUTION]
> Achten Sie darauf, das Microsoft Teams rooms-Kennwort so bald wie möglich zu ändern. 
  
Sie können das Kennwort des lokalen Administrators auch verwalten, indem Sie eine Gruppenrichtlinie einrichten, in der Domänenadministratoren lokale Administratoren sind.
  
Das Kennwort des lokalen Administrators wird während des Setups nicht als Auswahlmöglichkeit angegeben.
  
### <a name="machine-account"></a>Computerkonto

Ähnlich wie bei einem beliebigen Windows-Gerät kann der Computer Name durch Klicken mit der rechten Maustaste in Einstellungen \> zum Umbenennen von PC umbenannt werden \> .
  
 Wenn Sie den Computer umbenennen möchten, nachdem Sie ihn einer Domäne hinzugefügt haben, verwenden Sie den Befehl Rename-Computer PowerShell gefolgt vom neuen Namen des Computers.
  
## <a name="related-topics"></a>Verwandte Themen

[Planen von Microsoft Teams-Räumen](rooms-plan.md)

[Voraussetzungen für Microsoft Teams-Räume](requirements.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Voraussetzungen für Microsoft Store for Business und Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
