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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Problembehandlung beim Erstellen einer PowerShell-Remotesitzung zum Herstellen einer Verbindung mit Skype for Business Online, einschließlich Import-Module, gleichzeitiger Shell, Live-ID und Berechtigungsfehlern.
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913393"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostizieren von Verbindungsproblemen mit dem Skype for Business Online-Connector

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Dieses Thema enthält Informationen, die Ihnen helfen sollen, Probleme zu diagnostizieren und zu beheben, die beim Versuch auftreten können, eine Microsoft PowerShell-Remotesitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt. Lesen Sie die folgenden Abschnitte:
  
- [„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Die moderne Authentifizierung schlägt fehl, wenn die WinRM-Standardauthentifizierung deaktiviert wurde.](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Fehler beim Herstellen der Verbindung mit dem Live ID-Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [Fehler bei der Anmeldung für den Benutzer.](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Die maximale Anzahl gleichzeitiger Shells für diesen Benutzer in Skype for Business Online wurde überschritten.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Die maximale Anzahl gleichzeitiger Shells für diesen Mandanten in Skype for Business Online wurde überschritten.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie
<a name="BKMKPowerShellExecutionPolicy"> </a>

Mithilfe der PowerShell-Ausführungsrichtlinie kann ermittelt werden, welche Konfigurationsdateien in der PowerShell-Konsole geladen werden können und welche Skripts ein Benutzer über diese Konsole ausführen kann. Dabei gilt mindestens, dass das Skype for Business Online-Connectormodul nur importiert werden kann, wenn die Ausführungsrichtlinie auf „RemoteSigned" festgelegt ist. Wenn dies nicht der Fall ist, erhalten Sie beim Versuch, das Modul zu importieren, die folgende Fehlermeldung:
  
- **Fehler**: <em>Import-Module : Datei C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 kann nicht geladen werden, da das Ausführen von Skripts auf diesem System deaktiviert ist. Weitere Informationen finden Sie unter about_Execution_Policies unter https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Auflösung** Um dieses Problem zu beheben, starten Sie PowerShell als Administrator, und führen Sie dann den folgenden Befehl aus:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Details zur Ausführungsrichtlinie finden Sie unter [Informationen zu Ausführungsrichtlinien](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Das Skype for Business Online-Connectormodul kann nur in Windows PowerShell 3.0 ausgeführt werden. Wenn Sie versuchen, das Modul unter einer früheren Version von PowerShell zu importieren, schlägt der Importvorgang mit einer Fehlermeldung ähnlich der folgenden Meldung fehl:
  
  - **Fehler**: *Import-Module : Die Version der geladenen PowerShell ist "2.0". Das Modul "D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1" erfordert eine PowerShell-Mindestversion von "3.0", um ausgeführt zu werden. Überprüfen Sie die Installation von PowerShell, und versuchen Sie es erneut.*

- **Lösung**: Die einzige Möglichkeit, dieses Problem zu beheben, ist die Installation von Windows PowerShell 3.0, die im Microsoft Download Center unter [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)verfügbar ist.
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Die moderne Authentifizierung schlägt fehl, wenn die WinRM-Standardauthentifizierung deaktiviert wurde.
<a name="BKMKWinRMBasicAuth"> </a>

Die neueste Version des Skype for Business Online Connector-Moduls verwendet moderne Authentifizierung, aber der zugrunde liegende Windows Remote Management (WinRM)-Client muss so konfiguriert werden, dass die Standardauthentifizierung zulässig ist.  Die moderne Authentifizierung verwendet Bearertoken, die normalerweise im *Header "Authorization: Bearer"* übergeben werden. Windows PowerShell, auf dem Skype for Business PowerShell basiert, lässt keine Manipulation dieses Headers zu.  Stattdessen verwendet Skype for Business PowerShell den *Header "Authorization: Basic* ", um das Bearertoken zu übergeben.

Anweisungen zum Aktivieren von WinRM für die Standardauthentifizierung finden Sie unter [Herunterladen und Installieren von Windows PowerShell](./download-and-install-windows-powershell-5-1.md) .

## <a name="failed-to-connect-to-live-id-server"></a>Fehler beim Herstellen der Verbindung mit dem Live ID-Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> Die Live-ID-Authentifizierung ist für Skype For Business Online Connector veraltet. Verwenden Sie das Teams PowerShell-Modul, um den Onlinemandanten zu verwalten. Aktualisieren Sie beim Verwalten von Hybridumgebungen auf das neueste kumulative Update, oder verwenden Sie die oAuth-Authentifizierung.

Es gibt drei typische Gründe, aus denen beim Verbindungsversuch Fehler auftreten und die folgende Fehlermeldung angezeigt wird:

  - **Fehler**: *Get-CsWebTicket: Fehler beim Verbinden von Live-ID-Servern. Stellen Sie sicher, dass der Proxy aktiviert ist oder der Computer über eine Netzwerkverbindung mit Live-ID-Servern verfügt.*

- **Lösung**: Dieser Fehler bedeutet häufig, dass der Microsoft Online Services-Anmelde-Assistent nicht ausgeführt wird. Sie können den Status dieses Diensts überprüfen, indem Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ausführen: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Wenn der Dienst nicht ausgeführt wird, starten Sie ihn mit diesem Befehl:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Wenn der Dienst ausgeführt wird, bestehen möglicherweise Probleme mit der Netzwerkverbindung zwischen Ihrem Computer und dem Microsoft Live ID-Authentifizierungsserver. Überprüfen Sie dies, indem Sie Internet Explorer öffnen und zu [https://login.microsoftonline.com/](https://login.microsoftonline.com/.) navigieren. Versuchen Sie, sich von dort aus bei Microsoft 365 oder Office 365 anzumelden. Wenn dabei ein Fehler auftritt, liegen wahrscheinlich Probleme mit der Netzwerkverbindung vor.
  
    Eine weniger häufige Möglichkeit: Der Verbindungs-URI für den Microsoft Live ID-Authentifizierungsserver ist mit einem falschen Wert konfiguriert. Wenn Sie bereits festgestellt haben, dass der Anmeldeassistent ausgeführt wird und dass keine Probleme mit der Netzwerkkonnektivität vorliegen, kann dies die Ursache sein. Wenden Sie sich in diesem Fall an den Microsoft-Support.
  
## <a name="logon-failed-for-the-user"></a>Fehler bei der Anmeldung des Benutzers
<a name="BKMKLogonFailed"> </a>

Wenn Sie versuchen, eine Remoteverbindung mit Skype for Business Online herzustellen, müssen Sie den Benutzernamen und das Kennwort eines gültigen Skype for Business Online-Benutzerkontos angeben. Andernfalls schlägt die Anmeldung zusammen mit einer Fehlermeldung fehl, die der folgenden Meldung ähnelt:

- **Fehler**: *Get-CsWebTicket: Fehler bei der Anmeldung für den Benutzer "kenmyer@litwareinc.com". Erstellen Sie ein neues PSCredential-Objekt, und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben.*

- **Lösung**: Wenn Sie der Meinung sind, dass Sie ein gültiges Benutzerkonto verwenden und über das richtige Kennwort verfügen, versuchen Sie erneut, sich anzumelden. Wenn dies fehlschlägt, verwenden Sie die gleichen Anmeldeinformationen, und versuchen Sie, sich bei [https://login.microsoftonline.com/](https://login.microsoftonline.com/)anzumelden. Wenn Sie sich dort nicht anmelden können, wenden Sie sich an den Microsoft-Support. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten
<a name="BKMKUserPermission"> </a>

Sie müssen Mitglied der Gruppe „Mandantenadministratoren" sein, um eine PowerShell-Remoteverbindung mit Skype for Business Online herzustellen. Wenn dies nicht der Fall ist, tritt beim Verbindungsversuch ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler**: *New-PSSession : [admin.vdomain.com] Fehler bei der Verarbeitung von Daten vom Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung: Der Benutzer "user@foo.com" verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten. Berechtigungen können erteilt werden, indem dem Benutzer die entsprechende RBAC-Rolle zugewiesen wird. Weitere Informationen finden Sie in der [Remoteproblembehandlung](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Lösung**: Wenn Sie der Meinung sind, dass Sie Mitglied der Gruppe "Mandantenadministratoren" sind oder sein sollten, müssen Sie sich an den Microsoft-Support wenden.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert
<a name="BKMKAbilityConnect"> </a>

Damit Sie PowerShell mit Skype for Business Online verwalten können, muss die „EnableRemotePowerShellAccess"-Eigenschaft Ihrer PowerShell-Mandantenrichtlinie auf  `True` festgelegt sein. Wenn dies nicht der Fall ist, tritt bei der Verbindung ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler**: *New-PSSession : [admin.vdomain.com] Fehler bei der Verarbeitung von Daten vom Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung: Die Möglichkeit, eine Verbindung mit diesem Mandanten mithilfe einer Remote-PowerShell-Sitzung herzustellen, wurde deaktiviert. Wenden Sie sich an die Lync-Hilfe, um die PowerShell-Richtlinie dieses Mandanten zu überprüfen. Weitere Informationen finden Sie in der [Remoteproblembehandlung](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Lösung**: Wenn diese Fehlermeldung angezeigt wird, müssen Sie sich an den Microsoft-Support wenden und den Remote-PowerShell-Zugriff aktivieren.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Benutzer in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsUser"> </a>

Jeder Administrator darf maximal drei gleichzeitige Remoteverbindungen mit Skype for Business Online herstellen. Wenn drei PowerShell-Remoteverbindungen aktiv sind, tritt beim Versuch, eine vierte gleichzeitige Verbindung herzustellen, ein Fehler auf. Dabei wird die folgende Fehlermeldung angezeigt: 

- **Fehler**: *New-PSSession : [admin.vdomain.com] Fehler beim Herstellen einer Verbindung mit einem Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung: Der WS-Management-Dienst kann die Anforderung nicht verarbeiten. Die maximale Anzahl gleichzeitiger Shells für diesen Benutzer wurde überschritten. Schließen Sie vorhandene Shells, oder erhöhen Sie das Kontingent für diesen Benutzer. Weitere Informationen finden Sie in der [Remoteproblembehandlung](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Lösung**: Die einzige Möglichkeit, dieses Problem zu beheben, besteht darin, eine oder mehrere der vorherigen Verbindungen zu schließen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Mandanten in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsTenant"> </a>

Obwohl jeder Administrator bis zu drei gleichzeitige Verbindungen mit einem Skype for Business Online-Mandanten haben darf, darf kein einzelner Mandant mehr als 20 gleichzeitige Verbindungen haben. Beispielsweise können sechs Administratoren jeweils drei offene Sitzungen haben. Wenn ein vierter Administrator versucht, mehr als zwei Verbindungen herzustellen (was insgesamt 21 gleichzeitige Verbindungen zur Folge hat), tritt bei diesem Versuch ein Fehler auf, wobei die folgende Fehlermeldung angezeigt wird:
  
- **Fehler**: *New-PSSession : [admin.vdomain.com] Fehler beim Herstellen einer Verbindung mit dem Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung: Der WS-Management-Dienst kann die Anforderung nicht verarbeiten. Die maximale Anzahl gleichzeitiger Shells für diesen Mandanten wurde überschritten. Schließen Sie vorhandene Shells, oder erhöhen Sie das Kontingent für diesen Mandanten. Weitere Informationen finden Sie in der [Remoteproblembehandlung](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Lösung**: Die einzige Möglichkeit, dieses Problem zu beheben, besteht darin, eine oder mehrere der vorherigen Verbindungen zu schließen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.  
 
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Onlineverwaltung von Skype for Business mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
