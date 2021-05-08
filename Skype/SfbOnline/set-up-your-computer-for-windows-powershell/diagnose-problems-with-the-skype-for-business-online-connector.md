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
description: Behandeln Sie Probleme beim Erstellen einer PowerShell-Remotesitzung, um eine Verbindung mit Skype for Business Online herzustellen, einschließlich Import-Module, gleichzeitiger Shell, Live ID und Berechtigungsfehlern.
ms.openlocfilehash: 02952ea878424cb0b5e84337051c30660101d144
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238896"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostizieren von Verbindungsproblemen mit dem Skype for Business Online-Connector

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Dieses Thema enthält Informationen, die Ihnen helfen sollen, Probleme zu diagnostizieren und zu beheben, die beim Versuch auftreten können, eine Microsoft PowerShell-Remotesitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt. Lesen Sie die folgenden Abschnitte:
  
- [„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Moderne Authentifizierung schlägt fehl, wenn die WinRM Basic-Authentifizierung deaktiviert wurde](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Fehler beim Herstellen der Verbindung mit dem Live ID-Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Fehler beim Laden des Live ID-Moduls](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Fehler bei der Anmeldung für den Benutzer](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Die maximale Anzahl gleichzeitiger Shells für diesen Benutzer in Skype for Business Online wurde überschritten.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Die maximale Anzahl von gleichzeitigen Shells für diesen Mandanten in Skype for Business Online wurde überschritten.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> Standardmäßig ist für PowerShell-Sitzungen ein Zeitausfall nach 60 Minuten festgelegt. Zum erneuten Verbinden müssen Sie die Sitzung schließen und eine neue PowerShell-Sitzung starten. In letzter Zeit wurde eine neue Version von [Skype for Business Online, Windows PowerShell Module (2046.123 – Veröffentlicht am 02.10.2019),](https://www.microsoft.com/download/details.aspx?id=39366)gestartet, die ein neues Cmdlet mit dem Namen **Enable-CsOnlineSessionForReconnection** enthält, das das Problem mit der Zeit nach 60 Minuten entschärft.
> Die PowerShell-Sitzung wird erneut verbunden und authentifiziert, sodass sie wieder verwendet werden kann, ohne eine neue Instanz zum erneuten Verbinden starten zu müssen.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie
<a name="BKMKPowerShellExecutionPolicy"> </a>

Mithilfe der PowerShell-Ausführungsrichtlinie kann ermittelt werden, welche Konfigurationsdateien in der PowerShell-Konsole geladen werden können und welche Skripts ein Benutzer über diese Konsole ausführen kann. Dabei gilt mindestens, dass das Skype for Business Online-Connectormodul nur importiert werden kann, wenn die Ausführungsrichtlinie auf „RemoteSigned" festgelegt ist. Wenn dies nicht der Fall ist, erhalten Sie beim Versuch, das Modul zu importieren, die folgende Fehlermeldung:
  
- **Fehler:** <em>Import-Modul:Datei C: Allgemeine Dateien Microsoft \\ Lync Server \\ \\ 2013-Module \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 können nicht geladen werden, da die Ausführung von Skripts auf diesem System deaktiviert ist. Weitere Informationen finden Sie unter about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Auflösung** Um dieses Problem zu beheben, starten Sie PowerShell als Administrator, und führen Sie dann den folgenden Befehl aus:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Details zur Ausführungsrichtlinie finden Sie unter [Informationen zu Ausführungsrichtlinien](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Das Skype for Business Online-Connectormodul kann nur in Windows PowerShell 3.0 ausgeführt werden. Wenn Sie versuchen, das Modul unter einer früheren Version von PowerShell zu importieren, tritt beim Importvorgang ein Fehler auf, und etwa diese Fehlermeldung wird angezeigt:
  
  - **Fehler:** *Import-Module: Die Version der geladenen PowerShell ist "2.0". Für das Modul "D: Programme – Allgemeine \\ \\ \\ Dateien" in Microsoft Lync Server 2013-Modulen \\ \\ LyncOnlineConnectorLyncOnlineConnector.psd1" ist eine \\ mindestens auszuführende PowerShell-Version von "3.0" erforderlich. Überprüfen Sie die Installation von PowerShell, und versuchen Sie es erneut.*

- **Lösung:** Die einzige Möglichkeit, dieses Problem zu beheben, besteht Windows PowerShell 3.0, das Sie im Microsoft Download Center unter [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) finden.
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Moderne Authentifizierung schlägt fehl, wenn die WinRM Basic-Authentifizierung deaktiviert wurde
<a name="BKMKWinRMBasicAuth"> </a>

Die neueste Version des Skype for Business Online Connector-Moduls verwendet moderne Authentifizierung, aber der zugrunde liegende Windows-Client für die Remoteverwaltung (WinRM) muss so konfiguriert werden, dass die Standardauthentifizierung zulässig ist.  Die moderne Authentifizierung verwendet Bearer-Token, die normalerweise im *Header Authorization: Bearer übergeben* werden. Windows PowerShell, auf der Skype for Business PowerShell erstellt wurde, lässt die Manipulation dieses Headers nicht zu.  Stattdessen verwendet Skype for Business PowerShell *den Header Authorization: Basic,* um das Bearer-Token zu übergeben.

Anweisungen zum Aktivieren von WinRM [für die](./download-and-install-windows-powershell-5-1.md) Standardauthentifizierung Windows PowerShell Unter Herunterladen und Installieren von E-Mail.

## <a name="failed-to-connect-to-live-id-server"></a>Fehler beim Herstellen der Verbindung mit dem Live ID-Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> Die Live ID-Authentifizierung wird für Skype For Business Online Connector nicht mehr unterstützt. Verwenden Sie das Teams PowerShell-Modul, um den Online-Mandanten zu verwalten. Führen Sie beim Verwalten von Hybridumgebungen ein Upgrade auf das neueste kumulative Update durch, oder verwenden Sie die OAuth-Authentifizierung.

Es gibt drei typische Gründe, aus denen beim Verbindungsversuch Fehler auftreten und die folgende Fehlermeldung angezeigt wird:

  - **Fehler:** *Get-CsWebTicket : Fehler beim Herstellen einer Verbindung mit Live ID-Servern. Stellen Sie sicher, dass der Proxy aktiviert ist oder der Computer über eine Netzwerkverbindung mit Live-ID-Servern verfügt.*

- **Lösung:** Dieser Fehler bedeutet häufig, dass Microsoft Online Services Anmeldeassistent nicht ausgeführt wird. Sie können den Status dieses Diensts überprüfen, indem Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ausführen: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Wenn der Dienst nicht ausgeführt wird, starten Sie ihn mit diesem Befehl:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Wenn der Dienst ausgeführt wird, bestehen möglicherweise Probleme mit der Netzwerkverbindung zwischen Ihrem Computer und dem Microsoft Live ID-Authentifizierungsserver. Überprüfen Sie dies, indem Sie Internet Explorer öffnen und zu [https://login.microsoftonline.com/](https://login.microsoftonline.com/.) navigieren. Versuchen Sie, sich bei Microsoft 365 oder Office 365 von dort aus zu vermelden. Wenn dabei ein Fehler auftritt, liegen wahrscheinlich Probleme mit der Netzwerkverbindung vor.
  
    Eine weniger häufige Möglichkeit: Der Verbindungs-URI für den Microsoft Live ID-Authentifizierungsserver ist mit einem falschen Wert konfiguriert. Wenn Sie bereits festgestellt haben, dass der Anmeldeassistent ausgeführt wird und dass keine Probleme mit der Netzwerkkonnektivität vorliegen, kann dies die Ursache sein. In diesem Fall wenden Sie sich an den Microsoft-Support.
  
## <a name="failed-to-load-live-id-module"></a>Fehler beim Laden des Live ID-Moduls
<a name="BKMKFailedLoad"> </a>

Als eine der Voraussetzungen für die Verwendung von PowerShell zum Verwalten von Skype for Business Online muss der Microsoft Online Services-Anmeldeassistent installiert sein. Wenn der Anmeldeassistent nicht installiert ist, erhalten Sie beim Versuch, eine Remotesitzung mit Skype for Business Online einzurichten, die folgende Fehlermeldung:

- **Fehler:** *Get-CsWebTicket: Das Live ID-Modul kann nicht geladen werden. Vergewissern Sie sich, dass die richtige Version des Live Id-Anmelde-Assistenten installiert ist.*

- **Lösung:** Der Microsoft Online Services-Anmeldeassistent steht im Microsoft Download Center [unter Microsoft Online Services Sign-In Assistant for IT Professionals RTW zur Verfügung.](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Fehler bei der Anmeldung des Benutzers
<a name="BKMKLogonFailed"> </a>

Wenn Sie versuchen, eine Remoteverbindung mit Skype for Business Online herzustellen, müssen Sie den Benutzernamen und das Kennwort eines gültigen Skype for Business Online-Benutzerkontos angeben. Andern falls nicht, tritt bei der Anmeldung ein Fehler auf, und etwa diese Fehlermeldung wird angezeigt:

- **Fehler:** Get-CsWebTicket : Fehler bei der Anmeldung für den *Benutzer kenmyer@litwareinc.com. Erstellen Sie ein neues PSCredential-Objekt,* und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben.

- **Lösung:** Wenn Sie glauben, dass Sie ein gültiges Benutzerkonto und das richtige Kennwort verwenden, versuchen Sie erneut, sich zu anmelden. Wenn dies fehlschlägt, verwenden Sie dieselben Anmeldeinformationen, und versuchen Sie, sich bei [https://login.microsoftonline.com/](https://login.microsoftonline.com/) anmelden. Wenn Sie sich dort nicht anmelden können, wenden Sie sich an den Microsoft-Support. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten
<a name="BKMKUserPermission"> </a>

Sie müssen Mitglied der Gruppe „Mandantenadministratoren" sein, um eine PowerShell-Remoteverbindung mit Skype for Business Online herzustellen. Wenn dies nicht der Fall ist, tritt beim Verbindungsversuch ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler:** New-PSSession : [admin.vdomain.com] Die Verarbeitung von Daten von Remoteserver admin.vdomain.com ist mit der folgenden Fehlermeldung fehlgeschlagen: Der Benutzer "user@foo.com" verfügt nicht über die Berechtigung zum Verwalten dieses *Mandanten. Berechtigungen können erteilt werden, indem dem Benutzer die entsprechende RBAC-Rolle zugewiesen wird. Weitere Informationen finden Sie unter [Remotebehandlung.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Lösung:** Wenn Sie der Meinung sind, dass Sie Mitglied der Gruppe der Mandantenadministratoren sind oder sein sollen, müssen Sie sich an den Microsoft-Support wenden.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert
<a name="BKMKAbilityConnect"> </a>

Damit Sie PowerShell mit Skype for Business Online verwalten können, muss die „EnableRemotePowerShellAccess"-Eigenschaft Ihrer PowerShell-Mandantenrichtlinie auf  `True` festgelegt sein. Wenn dies nicht der Fall ist, tritt bei der Verbindung ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler:** New-PSSession : [admin.vdomain.com] Die Verarbeitung von Daten von Remoteserver admin.vdomain.com ist mit der folgenden Fehlermeldung fehlgeschlagen: Die Möglichkeit, mithilfe einer PowerShell-Remotesitzung eine Verbindung mit diesem Mandanten herzustellen, wurde *deaktiviert. Wenden Sie sich an die Lync-Hilfe, um die Powershell-Mandantenrichtlinie dieses Mandanten zu überprüfen. Weitere Informationen finden Sie unter [Remotebehandlung.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Lösung:** Wenn diese Fehlermeldung angezeigt wird, müssen Sie sich an den Microsoft-Support wenden und den Remote-PowerShell-Zugriff aktivieren lassen.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Benutzer in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsUser"> </a>

Jeder Administrator darf maximal drei gleichzeitige Remoteverbindungen mit Skype for Business Online herstellen. Wenn drei PowerShell-Remoteverbindungen aktiv sind, tritt beim Versuch, eine vierte gleichzeitige Verbindung herzustellen, ein Fehler auf. Dabei wird die folgende Fehlermeldung angezeigt:

- **Fehler:** *New-PSSession : [admin.vdomain.com] Die Verbindung mit dem Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung ist fehlgeschlagen: Der WS-Management-Dienst kann die Anforderung nicht verarbeiten. Die maximale Anzahl gleichzeitiger Shells für diesen Benutzer wurde überschritten. Schließen Sie vorhandene Shells, oder erhöhen Sie das Kontingent für diesen Benutzer. Weitere Informationen finden Sie unter [Remotebehandlung]( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Lösung:** Dieses Problem können Sie nur beheben, wenn Sie mindestens eine der vorherigen Verbindungen schließen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Mandanten in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsTenant"> </a>

Obwohl jeder Administrator bis zu drei gleichzeitige Verbindungen mit einem Skype for Business Online-Mandanten haben darf, ist es nicht zulässig, dass ein einziger Mandant mehr als 20 gleichzeitige Verbindungen hat. So können beispielsweise sechs Administratoren jeweils drei geöffnete Sitzungen haben. Wenn ein vierter Administrator versucht, mehr als zwei Verbindungen herzustellen (wodurch sich insgesamt 21 gleichzeitige Verbindungen ergeben), tritt ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:
  
- **Fehler:** *New-PSSession : [admin.vdomain.com] Die Verbindung mit dem Remoteserver admin.vdomain.com mit der folgenden Fehlermeldung ist fehlgeschlagen: Der WS-Management-Dienst kann die Anforderung nicht verarbeiten. Die maximale Anzahl von gleichzeitigen Shells für diesen Mandanten wurde überschritten. Schließen Sie vorhandene Shells, oder erhöhen Sie das Kontingent für diesen Mandanten. Weitere Informationen finden Sie unter [Remotebehandlung]( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Lösung:** Dieses Problem können Sie nur beheben, wenn Sie mindestens eine der vorherigen Verbindungen schließen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.  
 
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Onlineverwaltung in Skype for Business mithilfe Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
