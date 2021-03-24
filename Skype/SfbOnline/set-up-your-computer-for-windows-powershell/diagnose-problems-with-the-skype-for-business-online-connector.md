---
title: Diagnostizieren von Verbindungsproblemen mit dem Skype for Business Online-Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Problembehandlung beim Erstellen einer Remote-PowerShell-Sitzung zum Herstellen einer Verbindung mit Skype for Business Online, einschließlich Importmodul, gleichzeitiger Shell, Live-ID und Berechtigungsfehlern.
ms.openlocfilehash: 6edaa33244a3192f83289020fe12051ab5f9fb6b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097251"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostizieren von Verbindungsproblemen mit dem Skype for Business Online-Connector

Dieses Thema enthält Informationen, die Ihnen helfen sollen, Probleme zu diagnostizieren und zu beheben, die beim Versuch auftreten können, eine Microsoft PowerShell-Remotesitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt. Lesen Sie die folgenden Abschnitte:
  
- [„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Moderne Authentifizierung schlägt fehl, wenn die WinRM Basic-Authentifizierung deaktiviert wurde](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Fehler beim Herstellen der Verbindung mit dem Live ID-Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Fehler beim Laden des Live ID-Moduls](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Fehler bei der Anmeldung des Benutzers](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Die maximale Anzahl gleichzeitiger Shells für diesen Benutzer in Skype for Business Online wurde überschritten.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Die maximale Anzahl gleichzeitiger Shells für diesen Mandanten in Skype for Business Online wurde überschritten.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> Standardmäßig ist die Zeit für PowerShell-Sitzungen nach 60 Minuten aus. Um die Verbindung erneut herzustellen, müssen Sie die Sitzung schließen und eine neue PowerShell-Sitzung starten. Eine neue Version von [Skype for Business Online, Windows PowerShell Module (2046.123 – Veröffentlicht 02.10.2019),](https://www.microsoft.com/download/details.aspx?id=39366)wurde kürzlich gestartet, die ein neues Cmdlet mit dem Namen **Enable-CsOnlineSessionForReconnection** enthält, das das 60-Minuten-Time-Out-Problem entschärft.
> Die PowerShell-Sitzung wird erneut verbunden und authentifiziert, sodass sie erneut verwendet werden kann, ohne eine neue Instanz starten zu müssen, um die Verbindung erneut herzustellen.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie
<a name="BKMKPowerShellExecutionPolicy"> </a>

Mithilfe der PowerShell-Ausführungsrichtlinie kann ermittelt werden, welche Konfigurationsdateien in der PowerShell-Konsole geladen werden können und welche Skripts ein Benutzer über diese Konsole ausführen kann. Dabei gilt mindestens, dass das Skype for Business Online-Connectormodul nur importiert werden kann, wenn die Ausführungsrichtlinie auf „RemoteSigned" festgelegt ist. Wenn dies nicht der Fall ist, erhalten Sie beim Versuch, das Modul zu importieren, die folgende Fehlermeldung:
  
- **Fehler:** Importmodul: Datei C: Allgemeine Dateien des Programms <em>Microsoft Lync Server \\ \\ \\ 2013-Module \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 kann nicht geladen werden, da die Ausführung von Skripts auf diesem System deaktiviert ist. Weitere Informationen finden Sie unter about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 unter .</em>

- **Auflösung** Um dieses Problem zu beheben, starten Sie PowerShell als Administrator, und führen Sie dann den folgenden Befehl aus:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Details zur Ausführungsrichtlinie finden Sie unter [Informationen zu Ausführungsrichtlinien](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Das Skype for Business Online-Connectormodul kann nur in Windows PowerShell 3.0 ausgeführt werden. Beim Versuch, das Modul in einer früheren Version von PowerShell auszuführen, tritt beim Importprozess ein Fehler auf, und etwa die folgende Fehlermeldung wird angezeigt:
  
  - **Fehler:** *Importmodul: Die Version der geladenen PowerShell ist "2.0". Für das Modul "D: \\ Programme Common Files Microsoft Lync Server \\ \\ 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1" ist eine PowerShell-Mindestversion von \\ "3.0" erforderlich, um ausgeführt zu werden. Überprüfen Sie die Installation der PowerShell, und versuchen Sie es erneut.*

- **Lösung:** Die einzige Möglichkeit zum Beheben dieses Problems besteht in der Installation von Windows PowerShell 3.0, das im Microsoft Download Center unter zur Verfügung [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) steht.
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Moderne Authentifizierung schlägt fehl, wenn die WinRM Basic-Authentifizierung deaktiviert wurde
<a name="BKMKWinRMBasicAuth"> </a>

Die neueste Version des Skype for Business Online Connector-Moduls verwendet moderne Authentifizierung, aber der zugrunde liegende Windows Remote Management (WinRM)-Client muss so konfiguriert werden, dass die Standardauthentifizierung zulässig ist.  Bei der modernen Authentifizierung werden Bearertoken verwendet, die normalerweise im *Header Authorization: Bearer übergeben* werden. Windows PowerShell, auf der Skype for Business PowerShell aufgebaut ist, lässt keine Manipulation dieser Kopfzeile zu.  Stattdessen verwendet Skype for Business PowerShell den *Authorization:* Basic-Header, um das Bearertoken zu übergeben.

Unter [Herunterladen und Installieren Windows PowerShell](./download-and-install-windows-powershell-5-1.md) Anweisungen zum Aktivieren von WinRM für die Standardauthentifizierung.

## <a name="failed-to-connect-to-live-id-server"></a>Fehler beim Herstellen der Verbindung mit dem Live ID-Server
<a name="BKMKFailedConnect"> </a>

Es gibt drei typische Gründe, aus denen beim Verbindungsversuch Fehler auftreten und die folgende Fehlermeldung angezeigt wird:

  - **Fehler:** *Get-CsWebTicket: Fehler beim Verbinden von Live-ID-Servern. Stellen Sie sicher, dass der Proxy aktiviert ist oder der Computer über eine Netzwerkverbindung mit Live-ID-Servern verfügt.*

- **Lösung:** Häufig bedeutet dieser Fehler, dass der Microsoft Online Services-Assistent nicht ausgeführt wird. Sie können den Status dieses Diensts überprüfen, indem Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ausführen: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Wenn der Dienst nicht ausgeführt wird, starten Sie ihn mit diesem Befehl:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Wenn der Dienst ausgeführt wird, bestehen möglicherweise Probleme mit der Netzwerkverbindung zwischen Ihrem Computer und dem Microsoft Live ID-Authentifizierungsserver. Überprüfen Sie dies, indem Sie Internet Explorer öffnen und zu [https://login.microsoftonline.com/](https://login.microsoftonline.com/.) navigieren. Versuchen Sie, sich von dort aus bei Microsoft 365 oder Office 365 zu anmelden. Wenn dabei ein Fehler auftritt, liegen wahrscheinlich Probleme mit der Netzwerkverbindung vor.
  
    Eine weniger häufige Möglichkeit: Der Verbindungs-URI für den Microsoft Live ID-Authentifizierungsserver ist mit einem falschen Wert konfiguriert. Wenn Sie bereits festgestellt haben, dass der Anmeldeassistent ausgeführt wird und dass keine Probleme mit der Netzwerkkonnektivität vorliegen, kann dies die Ursache sein. Wenden Sie sich in diesem Fall an den Microsoft-Support.
  
## <a name="failed-to-load-live-id-module"></a>Fehler beim Laden des Live ID-Moduls
<a name="BKMKFailedLoad"> </a>

Als eine der Voraussetzungen für die Verwendung von PowerShell zum Verwalten von Skype for Business Online muss der Microsoft Online Services-Anmeldeassistent installiert sein. Wenn der Anmeldeassistent nicht installiert ist, erhalten Sie beim Versuch, eine Remotesitzung mit Skype for Business Online einzurichten, die folgende Fehlermeldung:

- **Fehler:** *Get-CsWebTicket : Das Modul "Live-Id" kann nicht geladen werden. Stellen Sie sicher, dass die richtige Version des Live Id-Anmelde-Assistenten installiert ist.*

- **Lösung:** Der Microsoft Online Services-Anmelde-Assistent steht im Microsoft Download Center unter [Microsoft Online Services Sign-In Assistant for IT Professionals RTW zur Verfügung.](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Fehler bei der Anmeldung des Benutzers
<a name="BKMKLogonFailed"> </a>

Wenn Sie versuchen, eine Remoteverbindung mit Skype for Business Online herzustellen, müssen Sie den Benutzernamen und das Kennwort eines gültigen Skype for Business Online-Benutzerkontos angeben. Anderenfalls tritt bei der Anmeldung ein Fehler auf, und etwa die folgende Fehlermeldung wird angezeigt:

- **Fehler:** Get-CsWebTicket: Fehler bei der Anmeldung für den Benutzer *"kenmyer@litwareinc.com". Erstellen Sie ein neues PSCredential-Objekt,* und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben.

- **Lösung:** Wenn Sie der Meinung sind, dass Sie ein gültiges Benutzerkonto verwenden und über das richtige Kennwort verfügen, versuchen Sie es erneut. Wenn dabei ein Fehler auftritt, versuchen Sie mit den gleichen Anmeldeinformationen, sich unter [https://login.microsoftonline.com/](https://login.microsoftonline.com/) anzumelden. Wenn Sie sich dort nicht anmelden können, wenden Sie sich an den Microsoft-Support. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten
<a name="BKMKUserPermission"> </a>

Sie müssen Mitglied der Gruppe „Mandantenadministratoren" sein, um eine PowerShell-Remoteverbindung mit Skype for Business Online herzustellen. Wenn dies nicht der Fall ist, tritt beim Verbindungsversuch ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler:** New-PSSession : [admin.vdomain.com] Das Verarbeiten von Daten von Remoteserver admin.vdomain.com ist mit der folgenden Fehlermeldung fehlgeschlagen: Der Benutzer "user@foo.com" verfügt nicht über die Berechtigung zum Verwalten dieses *Mandanten. Berechtigungen können erteilt werden, indem dem Benutzer die entsprechende RBAC-Rolle zugewiesen wird. Weitere Informationen finden Sie unter [Remotebehandlung](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Lösung:** Wenn Sie der Meinung sind, dass Sie Mitglied der Gruppe Mandantenadministratoren sind oder sein sollen, müssen Sie sich an den Microsoft-Support wenden.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert
<a name="BKMKAbilityConnect"> </a>

Damit Sie PowerShell mit Skype for Business Online verwalten können, muss die „EnableRemotePowerShellAccess"-Eigenschaft Ihrer PowerShell-Mandantenrichtlinie auf  `True` festgelegt sein. Wenn dies nicht der Fall ist, tritt bei der Verbindung ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler:** New-PSSession : [admin.vdomain.com] Das Verarbeiten von Daten von Remoteserver admin.vdomain.com ist mit der folgenden Fehlermeldung fehlgeschlagen: Die Möglichkeit zum Herstellen einer Verbindung mit diesem Mandanten mithilfe einer *Remote-PowerShell-Sitzung wurde deaktiviert. Wenden Sie sich an die Lync-Hilfe, um die Mandanten-Powershell-Richtlinie dieses Mandanten zu überprüfen. Weitere Informationen finden Sie unter [Remotebehandlung](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Lösung:** Wenn diese Fehlermeldung angezeigt wird, müssen Sie den Microsoft-Support kontaktieren und den Remotezugriff auf PowerShell aktivieren.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Benutzer in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsUser"> </a>

Jeder Administrator darf maximal drei gleichzeitige Remoteverbindungen mit Skype for Business Online herstellen. Wenn drei PowerShell-Remoteverbindungen aktiv sind, tritt beim Versuch, eine vierte gleichzeitige Verbindung herzustellen, ein Fehler auf. Dabei wird die folgende Fehlermeldung angezeigt:

- **Fehler:** New-PSSession : [admin.vdomain.com] Die Verbindung mit dem Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung fehlgeschlagen: Der WS-Management-Dienst kann die Anforderung *nicht verarbeiten. Die maximale Anzahl gleichzeitiger Shells für diesen Benutzer wurde überschritten. Schließen Sie vorhandene Shells, oder heben Sie das Kontingent für diesen Benutzer an. Weitere Informationen finden Sie unter [Remotebehandlung]( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Lösung:** Die einzige Möglichkeit, dieses Problem zu beheben, besteht in dem Schließen einer oder mehrerer vorheriger Verbindungen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Mandanten in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsTenant"> </a>

Obwohl jeder Administrator über bis zu drei gleichzeitige Verbindungen mit einem Skype for Business Online-Mandanten verfügen darf, darf kein einzelner Mandant mehr als 20 gleichzeitige Verbindungen haben. Beispielsweise können sechs Administratoren jeweils drei offene Sitzungen haben. Wenn ein vierter Administrator versucht, mehr als zwei Verbindungen herzustellen (was insgesamt 21 gleichzeitige Verbindungen zur Folge hat), tritt bei diesem Versuch ein Fehler auf, mit der folgenden Fehlermeldung:
  
- **Fehler:** New-PSSession : [admin.vdomain.com] Die Verbindung mit dem Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung fehlgeschlagen: Der WS-Management-Dienst kann die Anforderung *nicht verarbeiten. Die maximale Anzahl gleichzeitiger Shells für diesen Mandanten wurde überschritten. Schließen Sie vorhandene Shells, oder erhöhen Sie das Kontingent für diesen Mandanten. Weitere Informationen finden Sie unter [Remotebehandlung]( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Lösung:** Die einzige Möglichkeit, dieses Problem zu beheben, besteht in dem Schließen einer oder mehrerer vorheriger Verbindungen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.  
 
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für skype for business online management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
