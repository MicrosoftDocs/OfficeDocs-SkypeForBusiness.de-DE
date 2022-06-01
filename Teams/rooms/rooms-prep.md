---
title: Vorbereiten ihrer Umgebung
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
description: Erfahren Sie, wie Sie Ihre Infrastruktur für die Bereitstellung von Microsoft Teams-Räume vorbereiten, damit Sie alle Features nutzen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0bedb70ade23f92424a14e4bea3f1462fc2cbccf
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823054"
---
# <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Dieser Abschnitt enthält eine Übersicht über die Schritte, die zum Vorbereiten Ihrer Umgebung erforderlich sind, damit Sie alle Features von Microsoft Teams-Räume verwenden können.
  
1. Bereiten Sie ein Ressourcenkonto für jede Microsoft Teams-Räume Konsole vor. Weitere Informationen [finden Sie unter Bereitstellen Microsoft Teams-Räume](rooms-deploy.md).
    
2. Stellen Sie sicher, dass eine funktionierende Netzwerk-/Internetverbindung vorhanden ist, die für das Gerät verwendet werden kann.
  
3. Microsoft erfasst Daten, um die Benutzerfreundlichkeit zu verbessern. Um Microsoft das Sammeln von Daten zu ermöglichen, lassen Sie diese Websites zu:

   - Telemetrie-Clientendpunkt: `https://vortex.data.microsoft.com/`
   - Endpunkt für Telemetrieeinstellungen:` https://settings.data.microsoft.com/`
    
### <a name="create-and-test-a-resource-account"></a>Erstellen und Testen eines Ressourcenkontos

Ein *Ressourcenkonto* ist ein Konto, das der Microsoft Teams-Räume Client verwendet, um auf Features von Exchange wie Kalender zuzugreifen und eine Verbindung mit Microsoft Teams herzustellen. Weitere Informationen [finden Sie unter Bereitstellen Microsoft Teams-Räume](rooms-deploy.md).
  
### <a name="check-network-availability"></a>Überprüfen der Netzwerkverfügbarkeit

Um ordnungsgemäß funktionieren zu können, müssen Microsoft Teams-Räume Zugriff auf ein kabelgebundenes Netzwerk haben, das die folgenden Anforderungen erfüllt:
  
- Zugriff auf Ihre Active Directory- oder Azure Active Directory-Instanz (Azure AD) sowie auf Microsoft Exchange und Microsoft Teams.

- Zugriff auf einen Server, der über DHCP eine IP-Adresse bereitstellen kann. Microsoft Teams-Räume kann beim ersten Gerätestart nicht mit einer statischen IP-Adresse konfiguriert werden.

- Zugriff auf die HTTP-Ports 80 und 443

- TCP- und UDP-Ports, die gemäß den [Port- und Protokollanforderungen für Server für](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) lokale Skype for Business Server-Implementierungen oder [Microsoft 365 und Office 365 URLs und IP-Adressbereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) für Microsoft Teams konfiguriert sind.

Wenn Sie in Ihrem Netzwerk einen Proxy verwenden, benötigen Sie außerdem die Proxyadresse oder Skriptinformationen.
    
> [!IMPORTANT]
> Microsoft Teams-Räume unterstützt keine Proxyauthentifizierung, da dies den normalen Betrieb des Raums beeinträchtigen kann. Stellen Sie sicher, dass Microsoft Teams-Räume von der Proxyauthentifizierung ausgenommen wurden, bevor Sie in die Produktion gehen.

> [!IMPORTANT]
> Verwenden Sie unbedingt eine 1-GBit/s-Kabelnetzwerkverbindung, um sicherzustellen, dass die benötigte Bandbreite verfügbar ist.

> [!NOTE]
> Softwareupdates für Microsoft Teams-Räume werden automatisch aus dem Microsoft Store für Unternehmen heruntergeladen. Weitere Informationen finden [Sie unter Voraussetzungen für Microsoft Store für Unternehmen und Bildungseinrichtungen](/microsoft-store/prerequisites-microsoft-store-for-business), um zu überprüfen, ob die Raumkonsole auf den Store zugreifen und sich selbst aktualisieren kann.
  
### <a name="certificates"></a>Zertifikate

Ihr Microsoft Teams-Räume Gerät verwendet Zertifikate für Exchange Webdienste, Microsoft Teams oder Skype for Business, Netzwerknutzung und Authentifizierung. Wenn die zugehörigen Server öffentliche Zertifikate verwenden, was bei Onlinebereitstellungen und einigen lokalen Bereitstellungen der Fall ist, sollte keine weitere Aktion seitens des Administrators zum Installieren von Zertifikaten erforderlich sein. Wenn es sich bei der Zertifizierungsstelle hingegen um eine private Zertifizierungsstelle handelt, muss das Gerät dieser Zertifizierungsstelle vertrauen. Dies bedeutet, dass die CA + CA-Kettenzertifikate auf dem Gerät installiert sind. Das Hinzufügen des Geräts zur Domäne kann diese Aufgabe möglicherweise automatisch ausführen.
  
Sie können Zertifikate genauso installieren wie für jeden anderen Windows-Client.

> [!IMPORTANT]
> Wenn Ihr Proxyserver intern signierte Zertifikate verwendet, müssen Sie die interne Zertifikatkette, einschließlich der Stammzertifizierungsstelle, auf dem Microsoft Teams-Räume Gerät installieren.
  
> [!NOTE]
> Zertifikate können erforderlich sein, damit Microsoft Teams-Räume Skype for Business Server verwenden können.
  
### <a name="proxy"></a>Proxy

Microsoft Teams-Räume ist so konzipiert, dass Proxyeinstellungen vom Windows Betriebssystem erben. Greifen Sie wie folgt auf das Windows-Betriebssystem zu:
  
1. Klicken Sie in der benutzeroberfläche Microsoft Teams-Räume auf das Zahnradsymbol Einstellungen, auf dem Sie zur Eingabe des lokalen Administratorkennworts auf dem Gerät aufgefordert werden (das Standardkennwort ist **sfb**).
2. Tippen Sie auf **Einstellungen** gefolgt von Tippen auf die Schaltfläche "**Gehe zu Windows**", tippen Sie dann auf die Schaltfläche "**Gehe zu Admin Anmelden**", und klicken Sie dann auf die Schaltfläche "**Administrator**" (wenn der Computer der Domäne beigetreten ist, wählen Sie "**Anderer Benutzer**" aus, und verwenden Sie dann ".\admin" als Benutzernamen).
3. Geben Sie im Feld **"Suchen Windows** unten links" "regedit" ein (drücken Sie entweder lange auf den Bildschirm, oder klicken Sie mit der rechten Maustaste, und wählen Sie "**Als Administrator ausführen") aus**.
4. Klicken Sie auf den Ordner HKEY_USERS. (Eine Liste der Computerbenutzer-SIDs wird angezeigt.) Stellen Sie sicher, dass der Stammordner HKEY_USERS ausgewählt ist.
       
5. Klicken Sie auf "Datei", und wählen Sie dann **"Struktur laden" aus.**
6. Navigieren Sie zum Ordner **"C:\Users\Skype**", geben Sie das Feld "Dateiname" "NTUSER.dat" ein, und drücken Sie die Schaltfläche "Öffnen".

7. Sie werden aufgefordert, einen Schlüsselnamen für Ihre neu geladene Struktur einzufordern. geben Sie Skype ein (jetzt sollten die Registrierungseinstellungen für den Skype Benutzer angezeigt werden).
 
8. Öffnen Sie den Skype Schlüssel, und navigieren Sie zu HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings stellen Sie dann sicher, dass diese Einstellungen eingegeben werden: 
    
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
    
11. Wählen Sie auf der Anmeldeseite den Benutzer **Skype** aus. Wenn alle vorherigen Schritte erfolgreich waren, wird sich das Microsoft Teams-Räume Gerät erfolgreich anmelden.
    
Ausführliche Informationen zu FQDNs, Ports und IP-Adressbereichen, die für Microsoft Teams-Räume erforderlich sind, finden Sie im Artikel zur [Netzwerksicherheit](./security.md#network-security).
  
### <a name="admin-group-management"></a>Admin Gruppenverwaltung

Wenn Sie sich für den Beitritt zu einer Domäne (Azure Active Directory oder Active Directory) entscheiden, können Sie Microsoft Endpoint Manager, Gruppenrichtlinie oder die verwaltung lokaler Computer verwenden, um eine Sicherheitsgruppe wie bei einem Windows-PC in Ihrer Domäne als lokaler Administrator festzulegen. Jeder, der Mitglied dieser Sicherheitsgruppe ist, kann seine Anmeldeinformationen eingeben und Einstellungen entsperren.
  
> [!NOTE]
> Wenn die Vertrauensstellung zwischen Ihrem Microsoft Teams Rooms-Gerät und der Domäne verloren geht (zum Beispiel, wenn Sie Microsoft Teams Rooms nach dem Domänenbeitritt aus der Domäne entfernen), können Sie sich nicht gegenüber dem Gerät authentifizieren und die Einstellungen öffnen. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
  
## <a name="local-accounts"></a>Lokale Konten

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams-Räume lokales Benutzerkonto

Teams-Räume enthält ein kennwortloses lokales Konto namens "Skype". Dieses Konto wird verwendet, um sich bei Windows anzumelden, um die Teams-Räume-App zu starten. Es wird nicht unterstützt, ein Kennwort auf dieses Konto anzuwenden. Weitere Informationen finden Sie [unter Microsoft Teams-Räume Sicherheit](security.md).
  
### <a name="admin---local-administrator-account"></a>"Admin" – Lokales Administratorkonto

Microsoft Teams-Räume Standardkennwort ist auf "sfb" festgelegt. Das Kennwort kann lokal über Admin Modus oder in der AutoUnattend.xml Datei geändert werden (verwenden Sie den Windows System Image Manager von ADK, um die Änderung an der XML-Datei vorzunehmen).
  
> [!CAUTION]
> Achten Sie darauf, das Kennwort für Microsoft Teams-Räume so bald wie möglich zu ändern. 
  
Das Kennwort für den lokalen Administrator ist während des Setups nicht als Auswahl enthalten.

Weitere Informationen zum Admin Konto finden Sie im Artikel [Microsoft Teams-Räume Sicherheit](security.md).
  
### <a name="machine-account"></a>Computerkonto

Ähnlich wie bei jedem Windows Gerät kann der Computername umbenannt werden, indem Sie mit der rechten Maustaste auf **Einstellungen** \> **"Computer** \> **umbenennen"** klicken.
  
Wenn Sie den Computer umbenennen möchten, nachdem Sie ihn einer Domäne hinzugefügt haben, verwenden Sie ["Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer)", einen PowerShell-Befehl, gefolgt vom neuen Namen des Computers.
  
## <a name="related-topics"></a>Verwandte Themen

[Planen Microsoft Teams-Räume](rooms-plan.md)

[Voraussetzungen für Microsoft Teams-Räume](requirements.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Voraussetzungen für Microsoft Store für Unternehmen und Bildung](/microsoft-store/prerequisites-microsoft-store-for-business)
