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
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Ihre Infrastruktur für die Bereitstellung von Microsoft Teams Rooms vorbereiten, damit Sie alle Features nutzen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117423"
---
# <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Dieser Abschnitt enthält eine Übersicht über die Schritte, die zum Vorbereiten Ihrer Umgebung erforderlich sind, damit Sie alle Features von Microsoft Teams Rooms verwenden können.
  
1. Bereiten Sie ein Gerätekonto für jede Microsoft Teams Rooms-Konsole vor. Weitere Informationen finden Sie unter Bereitstellen [von Microsoft Teams-Räumen.](rooms-deploy.md)
    
2. Stellen Sie sicher, dass eine funktionierende Netzwerk-/Internetverbindung vorhanden ist, die für das Gerät verwendet werden kann. 
    
   Sie muss in der Lage sein, mithilfe von DHCP eine IP-Adresse zu empfangen. (Microsoft Teams Rooms kann beim ersten Gerätestart nicht mit einer statischen IP-Adresse konfiguriert werden, aber anschließend kann eine statische IP-Adresse für das Gerät auf dem Gerät oder auf dem Upstreamschalter oder Router konfiguriert werden.)

   Diese Ports müssen geöffnet sein (zusätzlich zum Öffnen der normalen Ports für Medien):
   - HTTPS: 443
   - HTTP: 80

   Wenn Sie in Ihrem Netzwerk einen Proxy verwenden, benötigen Sie außerdem die Proxyadresse oder Skriptinformationen.
    
   > [!IMPORTANT]
   > Microsoft Teams Rooms unterstützt keine Proxyauthentifizierung, da dies den normalen Betrieb des Raum stören kann. Stellen Sie sicher, dass Microsoft Teams Rooms von der Proxyauthentifizierung ausgenommen wurden, bevor Sie in die Produktion gehen.
  
3. Microsoft erfasst Daten, um die Benutzerfreundlichkeit zu verbessern. Damit Microsoft Daten sammeln kann, lassen Sie diese Websites zu:

   - Telemetrieclientendpunkt: https://vortex.data.microsoft.com/
   - Endpunkt der Telemetrieeinstellungen: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Erstellen und Testen eines Gerätekontos

Ein  *Gerätekonto ist*  ein Konto, das vom Microsoft Teams Rooms-Client verwendet wird, um auf Features von Exchange wie Kalender zu zugreifen und Skype for Business zu aktivieren. Weitere Informationen finden Sie unter Bereitstellen [von Microsoft Teams-Räumen.](rooms-deploy.md)
  
### <a name="check-network-availability"></a>Überprüfen der Netzwerkverfügbarkeit

Damit das Microsoft Teams Rooms-Gerät ordnungsgemäß funktioniert, muss es Zugriff auf ein kabelgebundenes Netzwerk haben, das die folgenden Anforderungen erfüllt:
  
- Zugriff auf Ihre Active Directory- oder Azure Active Directory-Instanz (Azure AD) sowie auf Ihre Server mit Microsoft Exchange und Skype for Business Server

- Zugriff auf einen Server, der über DHCP eine IP-Adresse bereitstellen kann. Microsoft Teams Rooms kann beim ersten Start der Einheit nicht mit einer statischen IP-Adresse konfiguriert werden.

- Zugriff auf die HTTP-Ports 80 und 443

- TCP- und UDP-Ports, die wie unter [Port-](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) und Protokollanforderungen für Server für lokale Skype for Business Server-Implementierungen oder [Microsoft 365- und Office 365-URLs](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) und IP-Adressbereiche für Microsoft Teams- oder Skype for Business-Onlineimplementierungen beschrieben konfiguriert sind.

> [!IMPORTANT]
> Verwenden Sie unbedingt eine 1-GBit/s-Kabelnetzwerkverbindung, um sicherzustellen, dass die benötigte Bandbreite verfügbar ist.

> [!NOTE]
> Softwareupdates für Microsoft Teams Rooms werden automatisch aus dem Microsoft Store für Unternehmen heruntergeladen. Unter [Voraussetzungen für Microsoft Store for Business und Education](/microsoft-store/prerequisites-microsoft-store-for-business) können Sie überprüfen, ob die Raumkonsole auf den Store zugreifen und sich selbst aktualisieren kann.
  
### <a name="certificates"></a>Zertifikate

Ihr Microsoft Teams Rooms-Gerät verwendet Zertifikate für Exchange Web Services, Microsoft Teams oder Skype for Business, Netzwerknutzung und Authentifizierung. Wenn die zugehörigen Server öffentliche Zertifikate verwenden, wie dies bei Online und einigen lokalen Bereitstellungen der Fall ist, sollte der Administrator keine weiteren Schritte zum Installieren von Zertifikaten ergreifen. Wenn es sich bei der Zertifizierungsstelle dagegen um eine private Zertifizierungsstelle (typisch für lokale Bereitstellungen) handelt, muss das Gerät dieser Zertifizierungsstelle vertrauen, was bedeutet, dass die Zertifizierungsstellen- und CA-Kettenzertifikate auf dem Gerät installiert sind. Wenn Sie das Gerät zur Domäne hinzufügen, wird diese Aufgabe möglicherweise automatisch ausgeführt.
  
Sie können Zertifikate genauso installieren wie für jeden anderen Windows-Client. 
  
> [!NOTE]
> Möglicherweise sind Zertifikate erforderlich, damit Microsoft Teams Rooms Skype for Business Server verwendet.
  
### <a name="proxy"></a>Proxy

Microsoft Teams Rooms ist darauf ausgelegt, Proxyeinstellungen vom Windows OS zu erben. Greifen Sie wie folgt auf das Windows-Betriebssystem zu:
  
1. Klicken Sie in der Benutzeroberfläche von Microsoft Teams Rooms auf das Zahnradsymbol Einstellungen, in dem Sie zum lokalen Administratorkennwort auf dem Gerät aufgefordert werden (das Standardkennwort ist **sfb**).
2. Tippen  Sie auf Einstellungen, und tippen Sie dann auf  die Schaltfläche Zu **Windows wechseln,** tippen Sie dann auf die Schaltfläche Administratoranmelden, und klicken Sie dann auf die Schaltfläche **Administrator** (wenn der Computer der Domäne beigetreten ist, wählen Sie Anderer Benutzer **aus,** und verwenden Sie dann .\admin als Benutzernamen).
3. Geben Sie **im Feld Windows durchsuchen** unten links in regedit ein (drücken Sie entweder lange den Bildschirm, oder klicken Sie mit der rechten Maustaste, und wählen Sie Als Administrator ausführen **aus).**
4. Klicken Sie auf den Ordner HKEY_USERS. (Eine Liste der Computerbenutzer-SIDs wird angezeigt.) Stellen Sie sicher, dass der Stammordner HKEY_USERS ausgewählt ist.
       
5. Klicken Sie auf Datei, und wählen Sie **dann Hive laden aus.**
6. Navigieren Sie zum **Ordner C:\Benutzer\Skype,** geben Sie das Feld Dateiname NTUSER.dat ein, und drücken Sie die Schaltfläche "Öffnen".

7. Sie werden zur Eingabe eines Schlüsselnamens für den neu geladenen Hive aufgefordert. in Skype eingeben (nun sollten die Registrierungseinstellungen für den Skype-Benutzer angezeigt werden).
 
8. Öffnen Sie die Skype-Taste, und navigieren Sie zu HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings und stellen Sie dann sicher, dass diese Einstellungen eingegeben werden: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Wenn „ProxyServer“ nicht vorhanden ist, müssen Sie diesen Schlüssel möglicherweise als Zeichenfolge hinzufügen. Ändern Sie „xx.xx.xx.xx:8080“ zu IP/Host und Port Ihres Proxyservers.
 
    Wenn der Kunde eine PAC-Datei verwendet, sieht die Konfiguration wie im folgenden Beispiel aus:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Markieren Sie nach Abschluss Ihrer Änderungen den Skype-Benutzerschlüssel (Stammordner für Skype), und wählen Sie aus dem Dateimenü „Registrierung“ die Option „Struktur entladen“ aus. (Sie müssen dies durch Auswahl von **Ja** bestätigen.)
    
10. Schließen Sie nun den Registrierungs-Editor, und geben Sie in das Feld der Windows-Suche „Abmelden“ ein.
    
11. Wählen Sie auf der Anmeldeseite den Benutzer **Skype** aus. Wenn alle vorherigen Schritte erfolgreich waren, wird sich das Microsoft Teams Rooms-Gerät erfolgreich anmelden.
    
Ausführliche Informationen [zu](./security.md#network-security) FQDNs, Ports und IP-Adressbereichen, die für Microsoft Teams Rooms erforderlich sind, finden Sie im Artikel Netzwerksicherheit.
  
  
### <a name="create-provisioning-packages"></a>Erstellen von Bereitstellungspaketen

Sie verwenden Bereitstellungspakete, um sich bei Exchange Server, Microsoft 365 oder Office 365 zu authentifizieren.
  
### <a name="admin-group-management"></a>Verwaltung von Administratorgruppen

Nach dem Beitritt zur Domäne können Sie mithilfe der Gruppenrichtlinie oder der Lokalen Computerverwaltung eine Sicherheitsgruppe wie für einen Windows-PC in Ihrer Domäne als lokalen Administrator festlegen. Jeder, der Mitglied dieser Sicherheitsgruppe ist, kann seine Anmeldeinformationen eingeben und Einstellungen entsperren.
  
> [!NOTE]
> Wenn die Vertrauensstellung zwischen Ihrem Microsoft Teams Rooms-Gerät und der Domäne verloren geht (zum Beispiel, wenn Sie Microsoft Teams Rooms nach dem Domänenbeitritt aus der Domäne entfernen), können Sie sich nicht gegenüber dem Gerät authentifizieren und die Einstellungen öffnen. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
  
## <a name="local-accounts"></a>Lokale Konten

### <a name="microsoft-teams-rooms-local-user-account"></a>Lokales Microsoft Teams Rooms-Benutzerkonto

Für das Gerätekonto wird in der Regel kein Kennwort verwendet. Es ist möglich, ihr ein Kennwort zu geben, aber es gibt Konsequenzen, einschließlich der Möglichkeit, dass Benutzer bei Ablauf dieses Kennworts aus der Konsolenanwendung gesperrt werden. Daher sollte der Administrator sicherstellen, dass das Kennwort nicht ablaufen darf.
  
### <a name="admin---local-administrator-account"></a>"Administrator" – Lokales Administratorkonto

Das Standardkennwort von Microsoft Teams Rooms ist auf "sfb" festgelegt. Das Kennwort kann lokal geändert werden, indem Sie zu Windows-Einstellungen Wechseln zu Windows oder in der Datei AutoUnattend.xml wechseln (verwenden Sie den Windows System Image Manager von ADK, um die Änderung an der XML-Datei \> zu vornehmen).
  
> [!CAUTION]
> Achten Sie darauf, das Microsoft Teams Rooms-Kennwort so schnell wie möglich zu ändern. 
  
Sie können auch das Kennwort für den lokalen Administrator verwalten, indem Sie eine Gruppenrichtlinie einrichten, in der Domänenadministratoren zu lokalen Administratoren gemacht werden.
  
Das Kennwort für den lokalen Administrator ist während des Setups nicht als Auswahl enthalten.
  
### <a name="machine-account"></a>Computerkonto

Ähnlich wie bei jedem Windows-Gerät kann auch der Computername umbenannt werden, indem mit der rechten Maustaste unter **Einstellungen** \> **zum Umbenennen von** PC \> **geklickt wird.**
  
Wenn Sie den Computer nach dem Beitritt zu einer Domäne umbenennen möchten, verwenden Sie **Rename-Computer**, einen PowerShell-Befehl, gefolgt vom neuen Namen des Computers.
  
## <a name="related-topics"></a>Verwandte Themen

[Planen von Microsoft Teams-Räumen](rooms-plan.md)

[Voraussetzungen für Microsoft Teams-Räume](requirements.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Voraussetzungen für den Microsoft Store für Unternehmen und Bildungseinrichtungen](/microsoft-store/prerequisites-microsoft-store-for-business)