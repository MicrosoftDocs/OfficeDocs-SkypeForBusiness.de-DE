---
title: Diagnostizieren von Verbindungsproblemen mit dem Skype for Business Online-Connector
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: 651afa58513819eb57914bfa1cd92bc38a46298f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372904"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostizieren von Verbindungsproblemen mit dem Skype for Business Online-Connector

Dieses Thema enthält Informationen, die Ihnen helfen sollen, Probleme zu diagnostizieren und zu beheben, die beim Versuch auftreten können, eine Microsoft PowerShell-Remotesitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt. Lesen Sie die folgenden Abschnitte:
  
- [„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Fehler beim Herstellen der Verbindung mit dem Live ID-Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Fehler beim Laden des Live ID-Moduls](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Fehler bei der Anmeldung des Benutzers](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Die maximale Anzahl von gleichzeitigen Shells für den Benutzer in Skype for Business Online wurde überschritten ](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [Die maximale Anzahl von gleichzeitigen Shells für den Mandanten in Skype for Business Online wurde überschritten ](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>„Import-Module"-Fehler aufgrund der Windows PowerShell-Ausführungsrichtlinie
<a name="BKMKPowerShellExecutionPolicy"> </a>

Mithilfe der PowerShell-Ausführungsrichtlinie kann ermittelt werden, welche Konfigurationsdateien in der PowerShell-Konsole geladen werden können und welche Skripts ein Benutzer über diese Konsole ausführen kann. Dabei gilt mindestens, dass das Skype for Business Online-Connectormodul nur importiert werden kann, wenn die Ausführungsrichtlinie auf „RemoteSigned" festgelegt ist. Wenn dies nicht der Fall ist, erhalten Sie beim Versuch, das Modul zu importieren, die folgende Fehlermeldung:
  
- **Fehler**: <em>Import-Module: Datei C:\\Program Files\\gemeinsame Dateien\\Microsoft Lync Server 2013\\Module\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 kann nicht geladen werden, da ausgeführt Skripts ist auf diesem System deaktiviert. Weitere Informationen finden Sie unter About_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Lösung** Um dieses Problem zu beheben, starten Sie PowerShell als Administrator, und führen Sie dann den folgenden Befehl aus:
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Details zur Ausführungsrichtlinie finden Sie unter [Informationen zu Ausführungsrichtlinien](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>„Import-Module"-Fehler aufgrund einer falschen Version von Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Das Skype for Business Online-Connectormodul kann nur in Windows PowerShell 3.0 ausgeführt werden. Beim Versuch, das Modul in einer früheren Version von PowerShell auszuführen, tritt beim Importprozess ein Fehler auf, und etwa die folgende Fehlermeldung wird angezeigt:
  
  - **Fehler**: *Import-Module: die Version des geladenen PowerShell ist "2.0". Das Modul ' D:\\Program Files\\gemeinsame Dateien\\Microsoft Lync Server 2013\\Module\\LyncOnlineConnector\\LyncOnlineConnector.psd1' erfordert eine minimale PowerShell-Version von '3.0' ausführen. Überprüfen Sie die Installation des PowerShell, und versuchen Sie es erneut.*

- **Lösung**: ist die einzige Möglichkeit zur Behebung dieses Problems auf Windows PowerShell 3.0 installiert werden aus dem Microsoft Download Center unter verfügbar ist [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>Fehler beim Herstellen der Verbindung mit dem Live ID-Server
<a name="BKMKFailedConnect"> </a>

Es gibt drei typische Gründe, aus denen beim Verbindungsversuch Fehler auftreten und die folgende Fehlermeldung angezeigt wird:

  - **Fehler**: Get-CsWebTicket *: Fehler beim live Id-Servern verbinden. Stellen Sie sicher, Proxy aktiviert ist oder Computer-Verbindung zu live Id-Server verfügt.*

- **Lösung**: Dieser Fehler bedeutet oftmals, dass die Microsoft Online Services-Anmeldeassistenten nicht ausgeführt wird. Sie können den Status dieses Diensts überprüfen, indem Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ausführen: 
    ```
    Get-Service "msoidsvc"
    ```
    Wenn der Dienst nicht ausgeführt wird, starten Sie ihn mit diesem Befehl:
    ```
    Start-Service "msoidsvc"
    ```

    Wenn der Dienst ausgeführt wird, bestehen möglicherweise Probleme mit der Netzwerkverbindung zwischen Ihrem Computer und dem Microsoft Live ID-Authentifizierungsserver. Überprüfen Sie dies, indem Sie Internet Explorer öffnen und zu [https://login.microsoftonline.com/](https://login.microsoftonline.com/.) navigieren. Versuchen Sie, sich von dort bei Office 365 anzumelden. Wenn dabei ein Fehler auftritt, liegen wahrscheinlich Probleme mit der Netzwerkverbindung vor.
  
    Eine weniger häufige Möglichkeit: Der Verbindungs-URI für den Microsoft Live ID-Authentifizierungsserver ist mit einem falschen Wert konfiguriert. Wenn Sie bereits festgestellt haben, dass der Anmeldeassistent ausgeführt wird und dass keine Probleme mit der Netzwerkkonnektivität vorliegen, kann dies die Ursache sein. Wenden Sie sich in diesem Fall an den Office 365-Support.
  
## <a name="failed-to-load-live-id-module"></a>Fehler beim Laden des Live ID-Moduls
<a name="BKMKFailedLoad"> </a>

Als eine der Voraussetzungen für die Verwendung von PowerShell zum Verwalten von Skype for Business Online muss der Microsoft Online Services-Anmeldeassistent installiert sein. Wenn der Anmeldeassistent nicht installiert ist, erhalten Sie beim Versuch, eine Remotesitzung mit Skype for Business Online einzurichten, die folgende Fehlermeldung:

- **Fehler**: Get-CsWebTicket *: Live Id-Modul kann nicht geladen werden. Stellen Sie sicher, dass die richtige Version von Live ID-Anmelde-Assistent installiert ist.*

- **Lösung**: der Microsoft Online Services-Anmeldeassistenten steht im Microsoft Download Center unter [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Fehler bei der Anmeldung des Benutzers
<a name="BKMKLogonFailed"> </a>

Wenn Sie versuchen, eine Remoteverbindung mit Skype for Business Online herzustellen, müssen Sie den Benutzernamen und das Kennwort eines gültigen Skype for Business Online-Benutzerkontos angeben. Anderenfalls tritt bei der Anmeldung ein Fehler auf, und etwa die folgende Fehlermeldung wird angezeigt:

- **Fehler**: Get-CsWebTicket *: Fehler bei der Anmeldung für den Benutzer "kenmyer@litwareinc.com". Erstellen Sie ein neues PSCredential-Objekt, und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das Kennwort verwendet haben.*

- **Lösung**: Wenn Sie glauben, dass Sie ein gültiges Konto und, verwenden Sie haben das richtige Kennwort erneut anmelden. Wenn dabei ein Fehler auftritt, versuchen Sie mit den gleichen Anmeldeinformationen, sich unter [https://login.microsoftonline.com/](https://login.microsoftonline.com/) anzumelden. Wenn Sie sich dort nicht anmelden können, wenden Sie sich an den Office 365-Support. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>Der Benutzer verfügt nicht über die Berechtigung zum Verwalten dieses Mandanten
<a name="BKMKUserPermission"> </a>

Sie müssen Mitglied der Gruppe „Mandantenadministratoren" sein, um eine PowerShell-Remoteverbindung mit Skype for Business Online herzustellen. Wenn dies nicht der Fall ist, tritt beim Verbindungsversuch ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler**: New-PSSession *: [admin.vdomain.com] Verarbeitung der Daten aus Remoteserver admin.vdomain.com konnte nicht mit die folgende Fehlermeldung angezeigt: der Benutzer 'user@foo.com' verfügt nicht über die Berechtigung zum Verwalten von diesen Mandanten. Berechtigungen können erteilt werden, indem Sie die entsprechenden RBAC-Rolle den Benutzer zuweisen. Weitere Informationen finden Sie unter der [Fehlersuche](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Lösung**: Wenn Sie annehmen, dass Sie sind, oder ein Mitglied der Gruppe Mandantenadministratoren werden sollen müssen Sie kontaktieren des Supports für Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Die Möglichkeit, Verbindungen mit dem Mandanten herzustellen, wurde in Skype for Business Online deaktiviert
<a name="BKMKAbilityConnect"> </a>

Damit Sie PowerShell mit Skype for Business Online verwalten können, muss die „EnableRemotePowerShellAccess"-Eigenschaft Ihrer PowerShell-Mandantenrichtlinie auf  `True` festgelegt sein. Wenn dies nicht der Fall ist, tritt bei der Verbindung ein Fehler auf, und die folgende Fehlermeldung wird angezeigt:

- **Fehler**: New-PSSession *: [admin.vdomain.com] Verarbeitung der Daten aus Remoteserver admin.vdomain.com konnte nicht mit die folgende Fehlermeldung angezeigt: die Möglichkeit, verbinden Sie diesen Mandanten mithilfe einer remote-PowerShell-Sitzung deaktiviert wurde. Wenden Sie sich an Lync-Hilfe-Mandanten Powershell-Richtlinie von diesen Mandanten zu überprüfen. Weitere Informationen finden Sie unter der [Fehlersuche](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Lösung**: Wenn diese Fehlermeldung angezeigt wird, müssen Sie zum Kontaktieren des Supports für Office 365 und erhalten Sie remote PowerShell-Zugriff aktiviert.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Benutzer in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsUser"> </a>

Jeder Administrator darf maximal drei gleichzeitige Remoteverbindungen mit Skype for Business Online herstellen. Wenn drei PowerShell-Remoteverbindungen aktiv sind, tritt beim Versuch, eine vierte gleichzeitige Verbindung herzustellen, ein Fehler auf. Dabei wird die folgende Fehlermeldung angezeigt:

- **Fehler**: New-PSSession *: [admin.vdomain.com] Herstellen einer Verbindung mit dem Remoteserver admin.vdomain.com konnte nicht mit die folgende Fehlermeldung angezeigt: der WS-Verwaltungsdienst kann die Anforderung nicht verarbeiten. Die maximale Anzahl von gleichzeitigen nutzt für diesen Benutzer wurde überschritten. Schließen Sie vorhandene nutzt oder lösen Sie das Kontingent für diesen Benutzer aus. Weitere Informationen finden Sie unter der [Remote Troubleshooting] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Lösung**: ist die einzige Möglichkeit zum Beheben dieses Problems, um eine oder mehrere der vorherigen Verbindungen zu schließen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Die maximale Anzahl von gleichzeitigen Shells für den Mandanten in Skype for Business Online wurde überschritten
<a name="BKMKMaxNumberShellsTenant"> </a>

Obwohl jeder Administrator bis zu drei gleichzeitige Verbindungen zu einem Skype für Business Online Mandanten verfügbar sind darf, dürfen keine einzelnen Mandanten mehr als 20 gleichzeitige Verbindungen haben. Beispielsweise können jeweils sechs Administratoren drei geöffneter Sitzungen verwendet. Wenn ein vierter Administrator versucht, mehr als 2 (was insgesamt 21 gleichzeitige Verbindungen) Verbindungen herstellen, schlägt dieser Versuch fehl, mit die folgende Fehlermeldung angezeigt:
  
- **Fehler**: New-PSSession *: [admin.vdomain.com] Herstellen einer Verbindung mit dem Remoteserver admin.vdomain.com konnte nicht mit die folgende Fehlermeldung angezeigt: der WS-Verwaltungsdienst kann die Anforderung nicht verarbeiten. Die maximale Anzahl von gleichzeitigen nutzt für diesen Mandanten wurde überschritten. Schließen Sie vorhandene nutzt, oder erhöhen Sie das Kontingent für diesen Mandanten. Weitere Informationen finden Sie unter der [Remote Troubleshooting] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Lösung**: ist die einzige Möglichkeit zum Beheben dieses Problems, um eine oder mehrere der vorherigen Verbindungen zu schließen. Wenn Sie mit einer Skype for Business Online-Sitzung fertig sind, sollten Sie die Sitzung mit dem Cmdlet **Remove-PSSession** beenden. Damit können Sie das Problem vermeiden.  
 
## <a name="related-topics"></a>Verwandte Themen
[Einrichten des Computers für Skype für das Business online Management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
