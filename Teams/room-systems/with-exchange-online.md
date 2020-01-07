---
title: Bereitstellen von Microsoft Teams-Raum mit Exchange online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Exchange Online.
ms.openlocfilehash: c9192dad3ffc8cb45a5b4a213865a1daa998075d
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952488"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange online

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Exchange Online und Skype for Business Server lokal.
  
Wenn Ihre Organisation über eine Kombination von Diensten verfügt, bei denen einige lokal gehostet werden und einige Online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. In diesem Thema werden hybridbereitstellungen für Microsoft Teams-Räume mit Exchange Hosted Online behandelt. Da es so viele unterschiedliche Variationen bei dieser Art der Bereitstellung gibt, ist es nicht möglich, detaillierte Anweisungen für alle zu liefern. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Prozess für Ihr Setup nicht richtig ist, empfehlen wir, dass Sie Windows PowerShell verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, und für andere Bereitstellungsoptionen.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht darin, Sie mithilfe der Windows PowerShell-Remotekonfiguration zu konfigurieren. Microsoft bietet [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, mit dem Sie neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Benutzerkonten machen können. Wenn Sie möchten, können Sie die folgenden Schritte ausführen, um die Konten zu konfigurieren, die von Ihrem Microsoft Teams rooms-Gerät verwendet werden.

## <a name="requirements"></a>Voraussetzungen

Bevor Sie Microsoft Teams-Räume mit Exchange Online bereitstellen, müssen Sie sicherstellen, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Anforderungen für Microsoft Teams-Chatrooms](requirements.md).
  
Zum Bereitstellen von Microsoft Teams-Räumen mit Exchange Online führen Sie die folgenden Schritte aus. Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen. 

   > [!NOTE]
   >  Das [Azure Active Directory-Modul für Windows PowerShell-Cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in diesem Abschnitt (beispielsweise "MsolUser") wurden beim Einrichten von Konten für Microsoft Teams rooms-Geräte getestet. Es ist möglich, dass andere Cmdlets funktionieren, jedoch in diesem speziellen Szenario nicht getestet wurden.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften

1. Starten Sie eine Windows PowerShell-Remotesitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange Online wie folgt her:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie können die Einstellungen für ein vorhandenes Raumpostfach ändern. Dadurch kann sich das Konto bei Microsoft Teams-Räumen authentifizieren.

   Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Wenn Sie ein neues Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Um die Besprechungs Erfahrung zu verbessern, müssen Sie die Exchange-Eigenschaften für das Benutzerkonto wie folgt festzulegen:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto

1. Klicken Sie im Tool **Active Directory-Benutzer und-Computer** mit der rechten Maustaste auf den Container oder die Organisationseinheit, in dem Ihre Microsoft Teams-Chatrooms-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.
2. Geben Sie den Anzeigenamen (-Identity) aus dem vorherigen Cmdlet (Satz-Postfach oder neues Postfach) im Feld **Vollständiger Name** und dem Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die Auswahl von " **Kennwort läuft nie ab** " ist eine Voraussetzung für Skype for Business Server in Microsoft Teams-Räumen. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Fall müssen Sie für jedes Microsoft Teams rooms-Benutzerkonto eine Ausnahme erstellen.
  
4. Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.
5. Nachdem Sie das Konto erstellt haben, führen Sie eine Verzeichnissynchronisierung aus. Dies kann mithilfe von " [MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) " in PowerShell erfolgen. Wenn dies abgeschlossen ist, wechseln Sie zur Seite "Benutzer", und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.

### <a name="assign-an-office-365-license"></a>Zuweisen einer Office 365-Lizenz

1. Stellen Sie zunächst eine Verbindung mit Azure AD her, um einige Kontoeinstellungen anzuwenden. Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt. 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. Das Benutzerkonto muss über eine gültige Office 365-Lizenz verfügen, um sicherzustellen, dass Exchange und Skype for Business Server funktionieren. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Benutzerkonto einen Verwendungsstandort zuweisen, um festzustellen, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie führen die Aufgabe in einem der folgenden Schritte aus.
3. Verwenden Sie als nächstes`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> , um eine Liste der verfügbaren SKUs für Ihren Office 365-Mandanten abzurufen.
4. Nachdem Sie die SKUs aufgelistet haben, können Sie eine Lizenz mit dem`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“). 

  ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Aktivieren des Benutzerkontos mit Skype for Business Server

1. Erstellen Sie eine Windows PowerShell-Remotesitzung wie folgt von einem PC:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Führen Sie den folgenden Befehl aus, um Ihr Microsoft Teams rooms-Konto für Skype for Business Server zu aktivieren:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Wenn Sie nicht sicher sind, welchen Wert Sie für den RegistrarPool-Parameter in Ihrer Umgebung verwenden sollen, können Sie den Wert eines vorhandenen Skype for Business Server-Benutzers über diesen Befehl abrufen.

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Zuweisen einer Skype for Business Server-Lizenz zum Microsoft Teams rooms-Konto

1. Melden Sie sich als mandantenadministrator an, öffnen Sie das Office 365-Verwaltungs Portal, und klicken Sie auf die Administrator-app.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie auf das Microsoft Teams rooms-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP in Microsoft Teams-Räumen verwenden möchten.
6. Klicken Sie auf **Speichern**.

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem Skype for Business-Client bei diesem Konto anzumelden.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft Teams-Chatrooms](room-systems-v2-configure-accounts.md)

[Planen von Microsoft Teams-Räumen](skype-room-systems-v2-0.md)
  
[Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)
  
[Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
