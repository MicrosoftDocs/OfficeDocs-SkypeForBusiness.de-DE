---
title: Vorbereiten Ihrer Umgebung
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie Ihre Infrastruktur für Microsoft Teams-Räume Bereitstellung vorbereiten, damit Sie alle Features nutzen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5003bbb3554436ca388990aeebfec4ce6dfb9f57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58577959"
---
# <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Dieser Abschnitt enthält eine Übersicht über die Schritte, die erforderlich sind, um Ihre Umgebung so vorzubereiten, dass Sie alle Features ihrer Microsoft Teams-Räume.
  
1. Bereiten Sie ein Gerätekonto für jede Microsoft Teams-Räume vor. Weitere [Informationen finden Microsoft Teams-Räume](rooms-deploy.md) bereitstellen.
    
2. Stellen Sie sicher, dass eine funktionierende Netzwerk-/Internetverbindung vorhanden ist, die für das Gerät verwendet werden kann. 
    
   Es muss eine IP-Adresse über DHCP empfangen können. (Microsoft Teams-Räume kann beim ersten Start der Einheit nicht mit einer statischen IP-Adresse konfiguriert werden, anschließend kann jedoch eine statische IP-Adresse für das Gerät auf dem Gerät oder auf dem Upstreamschalter oder Router konfiguriert werden.)

   Diese Ports müssen geöffnet sein (zusätzlich zu den normalen Medienports):
   - HTTPS: 443
   - HTTP: 80

   Wenn Sie in Ihrem Netzwerk einen Proxy verwenden, benötigen Sie außerdem die Proxyadresse oder Skriptinformationen.
    
   > [!IMPORTANT]
   > Microsoft Teams-Räume unterstützt keine Proxyauthentifizierung, da dies den normalen Betrieb des Raum beeinträchtigen kann. Stellen Sie sicher, Microsoft Teams-Räume von der Proxyauthentifizierung ausgenommen wurden, bevor Sie in die Produktion gehen.
  
3. Microsoft erfasst Daten, um die Benutzerfreundlichkeit zu verbessern. Um Microsoft das Sammeln von Daten zu ermöglichen, lassen Sie diese Websites zu:

   - Telemetrieclientendpunkt: https://vortex.data.microsoft.com/
   - Endpunkt für Telemetrieeinstellungen: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Erstellen und Testen eines Gerätekontos

Ein *Gerätekonto ist* ein Konto, das der Microsoft Teams-Räume-Client für den Zugriff auf Features von Exchange, z. B. Kalender, und zum Aktivieren von Skype for Business. Weitere [Informationen finden Microsoft Teams-Räume](rooms-deploy.md) bereitstellen.
  
### <a name="check-network-availability"></a>Überprüfen der Netzwerkverfügbarkeit

Um ordnungsgemäß funktionieren zu können, muss Microsoft Teams-Räume Gerät Zugriff auf ein verkabeltes Netzwerk haben, das diese Anforderungen erfüllt:
  
- Zugriff auf Ihre Active Directory- oder Azure Active Directory-Instanz (Azure AD) sowie auf Ihre Server mit Microsoft Exchange und Skype for Business Server

- Zugriff auf einen Server, der über DHCP eine IP-Adresse bereitstellen kann. Microsoft Teams-Räume kann beim ersten Komponentenstart nicht mit einer statischen IP-Adresse konfiguriert werden.

- Zugriff auf die HTTP-Ports 80 und 443

- DIE TCP- und UDP-Ports sind wie unter [Port-](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) und Protokollanforderungen für Server für lokale Skype for Business Server-Implementierungen oder Microsoft 365- und [Office 365-URLs](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) und IP-Adressbereiche für Microsoft Teams- oder Skype for Business-Onlineimplementierungen beschrieben konfiguriert.

> [!IMPORTANT]
> Verwenden Sie unbedingt eine 1-GBit/s-Kabelnetzwerkverbindung, um sicherzustellen, dass die benötigte Bandbreite verfügbar ist.

> [!NOTE]
> Softwareupdates für Microsoft Teams-Räume werden automatisch von der App Microsoft Store für Unternehmen. Unter [Voraussetzungen für Microsoft Store für Unternehmen und Education](/microsoft-store/prerequisites-microsoft-store-for-business) können Sie überprüfen, ob die Raumkonsole auf den Store zugreifen und die App selbst aktualisieren kann.
  
### <a name="certificates"></a>Zertifikate

Ihr Microsoft Teams-Räume verwendet Zertifikate für Exchange-Webdienste, Microsoft Teams- Skype for Business, Netzwerkverwendung und Authentifizierung. Wenn die zugehörigen Server öffentliche Zertifikate verwenden (dies gilt für Online- und einige lokale Bereitstellungen), sollte vom Administrator keine weiteren Schritte zum Installieren von Zertifikaten erforderlich sein. Wenn es sich bei der Zertifizierungsstelle hingegen um eine private Zertifizierungsstelle handelt (was für lokale Bereitstellungen typisch ist), muss das Gerät dieser Zertifizierungsstelle vertrauen, d. h., die Zertifikatkette für Zertifizierungsstellen und Zertifizierungsstellen muss auf dem Gerät installiert sein. Wenn Sie das Gerät zur Domäne hinzufügen, wird diese Aufgabe möglicherweise automatisch ausgeführt.
  
Sie können Zertifikate genauso installieren wie für jeden anderen Windows-Client. 
  
> [!NOTE]
> Zertifikate sind möglicherweise erforderlich, um ihre Microsoft Teams-Räume verwenden Skype for Business Server.
  
### <a name="proxy"></a>Proxy

Microsoft Teams-Räume -Version ist so konzipiert, dass sie Proxyeinstellungen vom Betriebssystem Windows erbt. Greifen Sie wie folgt auf das Windows-Betriebssystem zu:
  
1. Klicken Sie Microsoft Teams-Räume der Benutzeroberfläche "Benutzer" auf das Zahnradsymbol Einstellungen, wo Sie aufgefordert werden, das lokale Administratorkennwort auf dem Gerät einzugeben (das Standardkennwort ist **sfb**).
2. Tippen Sie auf **Einstellungen** gefolgt von der Schaltfläche Gehe zu **Windows.** Tippen  Sie dann auf die Schaltfläche Zur Administratoranmelden wechseln, und klicken Sie dann auf die Schaltfläche **Administrator** (wenn der Computer Mitglied der Domäne ist, wählen Sie Anderer Benutzer **aus,** und verwenden Sie dann .\admin als Benutzernamen).
3. Geben Sie **unten Windows** im Feld Suche nach links regedit ein (drücken Sie entweder lange den Bildschirm, oder klicken Sie mit der rechten Maustaste, und wählen Sie Als Administrator **ausführen aus).**
4. Klicken Sie auf den Ordner HKEY_USERS. (Eine Liste der Computerbenutzer-SIDs wird angezeigt.) Stellen Sie sicher, dass der Stammordner HKEY_USERS ausgewählt ist.
       
5. Klicken Sie auf Datei, und wählen Sie **Struktur laden aus.**
6. Navigieren Sie zum Ordner **"C:\Benutzer\Skype",** geben Sie im Feld Dateiname den Namen "N TINER.dat" ein, und drücken Sie die Schaltfläche "Öffnen".

7. Sie werden zur Eingabe eines Schlüsselnamens für die neu geladene Struktur aufgefordert. geben Sie Skype ein (nun sollten die Registrierungseinstellungen für den Benutzer Skype werden).
 
8. Öffnen Sie die Skype taste, navigieren Sie zu HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings stellen Sie dann sicher, dass die folgenden Einstellungen eingegeben werden: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Wenn „ProxyServer“ nicht vorhanden ist, müssen Sie diesen Schlüssel möglicherweise als Zeichenfolge hinzufügen. Ändern Sie „xx.xx.xx.xx:8080“ zu IP/Host und Port Ihres Proxyservers.
 
    Wenn der Kunde eine PAC-Datei verwendet, würde die Konfiguration wie im folgenden Beispiel aussehen:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Markieren Sie nach Abschluss Ihrer Änderungen den Skype-Benutzerschlüssel (Stammordner für Skype), und wählen Sie aus dem Dateimenü „Registrierung“ die Option „Struktur entladen“ aus. (Sie müssen dies durch Auswahl von **Ja** bestätigen.)
    
10. Schließen Sie nun den Registrierungs-Editor, und geben Sie in das Feld der Windows-Suche „Abmelden“ ein.
    
11. Wählen Sie auf der Anmeldeseite den Benutzer **Skype** aus. Wenn alle vorherigen Schritte erfolgreich waren, kann Microsoft Teams-Räume erfolgreich anmelden.
    
Im Artikel [netzwerksicherheit finden](./security.md#network-security) Sie ausführliche Informationen zu FQDNs, Ports und IP-Adressbereichen, die für die Microsoft Teams-Räume.
  
  
### <a name="create-provisioning-packages"></a>Erstellen von Bereitstellungspaketen

Sie verwenden Bereitstellungspakete zur Authentifizierung bei Exchange Server, Microsoft 365 oder Office 365.
  
### <a name="admin-group-management"></a>Verwaltung von Administratorgruppen

Nach dem Beitritt zur Domäne können Sie gruppenrichtlinien oder die Verwaltung lokaler Computer verwenden, um eine Sicherheitsgruppe wie einen Windows-PC in Ihrer Domäne als lokalen Administrator zu festlegen. Jeder Benutzer, der Mitglied dieser Sicherheitsgruppe ist, kann seine Anmeldeinformationen eingeben und die Sperrung Einstellungen.
  
> [!NOTE]
> Wenn die Vertrauensstellung zwischen Ihrem Microsoft Teams Rooms-Gerät und der Domäne verloren geht (zum Beispiel, wenn Sie Microsoft Teams Rooms nach dem Domänenbeitritt aus der Domäne entfernen), können Sie sich nicht gegenüber dem Gerät authentifizieren und die Einstellungen öffnen. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
  
## <a name="local-accounts"></a>Lokale Konten

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams-Räume Lokales Benutzerkonto

Für das Gerätekonto wird in der Regel kein Kennwort verwendet. Es ist möglich, ihr ein Kennwort zu geben, doch es gibt Konsequenzen, einschließlich der Möglichkeit, dass Benutzer aus der Konsolenanwendung ausgeschlossen werden, wenn das Kennwort abläuft. Daher sollte der Administrator sicherstellen, dass das Kennwort nicht abläuft.
  
### <a name="admin---local-administrator-account"></a>"Administrator" – Lokales Administratorkonto

Microsoft Teams-Räume Standardkennwort ist auf "sfb" festgelegt. Das Kennwort kann lokal geändert werden, indem Sie zu Windows Einstellungen Zu Windows wechseln oder in der AutoUnattend.xml-Datei (verwenden Sie den \> Windows-Systembild-Manager von ADK, um die Änderung an der XML-Datei zu ändern).
  
> [!CAUTION]
> Vergessen Sie nicht, Microsoft Teams-Räume Kennwort so schnell wie möglich zu ändern. 
  
Sie können das Kennwort für den lokalen Administrator auch verwalten, indem Sie eine Gruppenrichtlinie einrichten, in der Domänenadministratoren zu lokalen Administratoren werden.
  
Das Kennwort für den lokalen Administrator ist während des Setups nicht als Option enthalten.
  
### <a name="machine-account"></a>Computerkonto

Ähnlich wie jedes Windows Gerät kann der Computername umbenannt werden, indem mit der rechten Maustaste **in** das Einstellungen About Rename PC \> **geklickt** \> **wird.**
  
Wenn Sie den Computer nach dem Beitritt zu einer Domäne umbenennen möchten, verwenden Sie **Rename-Computer**, einen PowerShell-Befehl, gefolgt vom neuen Namen des Computers.
  
## <a name="related-topics"></a>Verwandte Themen

[Planen Microsoft Teams-Räume](rooms-plan.md)

[Voraussetzungen für Microsoft Teams-Räume](requirements.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Voraussetzungen für Microsoft Store für Unternehmen und Bildungseinrichtungen](/microsoft-store/prerequisites-microsoft-store-for-business)