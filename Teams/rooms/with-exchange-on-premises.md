---
title: Bereitstellen von Microsoft Teams-Räumen mit Exchange lokal
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-mar2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen in einer Hybridumgebung mit Exchange lokal.
ms.openlocfilehash: 0efed0a07024f0f1fcfeea7168c4f78c66fecd64
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141008"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange vor Ort

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen in einer Hybridumgebung mit Exchange lokal und Microsoft Teams oder Skype for Business Online.
  
Wenn Ihre Organisation über eine Kombination von Diensten verfügt, bei denen einige lokal gehostet werden und einige Online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. In diesem Thema werden hybridbereitstellungen für Microsoft Teams-Räume mit Exchange gehostet, die lokal gehostet werden. Da es so viele unterschiedliche Variationen bei dieser Art der Bereitstellung gibt, ist es nicht möglich, detaillierte Anweisungen für alle zu liefern. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Prozess für Ihr Setup nicht richtig ist, empfehlen wir, dass Sie Windows PowerShell verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, und für andere Bereitstellungsoptionen.

Microsoft bietet [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, mit dem Sie neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Benutzerkonten machen können. Wenn Sie möchten, können Sie die folgenden Schritte ausführen, um die Konten zu konfigurieren, die von Ihrem Microsoft Teams rooms-Gerät verwendet werden.
  
## <a name="requirements"></a>Voraussetzungen

Stellen Sie sicher, dass Sie die Anforderungen erfüllt haben, bevor Sie Microsoft Teams-Räume mit Exchange lokal bereitstellen. Weitere Informationen finden Sie unter [Anforderungen für Microsoft Teams-Chatrooms](requirements.md).
  
Wenn Sie Microsoft Teams-Räume mit Exchange lokal bereitstellen, verwenden Sie die Active Directory-Verwaltungstools, um eine e-Mail-Adresse für Ihr lokales Domänenkonto hinzuzufügen. Dieses Konto wird mit Office 365 synchronisiert. Sie müssen die folgenden Schritte ausführen:
  
- Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

- Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.

- Weisen Sie eine Office 365-Lizenz zu.

- Aktivieren Sie das Geräte Konto in Skype for Business Server. Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:

  - Sie müssen Skype for Business Online (Plan 2) oder höher in Ihrem Office 365-Plan haben. Der Plan muss die Konferenzfunktion unterstützen.
  
  - Wenn Sie Enterprise-VoIP (PSTN-Telefonie) mit Telefoniedienst-Anbietern für Microsoft Teams-Räume benötigen, benötigen Sie Skype for Business Online (Plan 3).
  
  - Ihre Mandanten Benutzer müssen über Exchange-Postfächer verfügen.
  
  - Für Ihr Microsoft Teams rooms-Konto ist eine Lizenz für Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3) erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich.

- Weisen Sie Ihrem Microsoft Teams rooms-Konto eine Skype for Business Server-Lizenz zu.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

1. Klicken Sie im Tool **Active Directory-Benutzer und-Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in dem Ihre Microsoft Teams-Chatrooms-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.

2. Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.

3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die Auswahl von " **Kennwort läuft nie ab** " ist eine Voraussetzung für Skype for Business Server in Microsoft Teams-Räumen. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. Wenn dies der Fall ist, müssen Sie für jedes Microsoft Teams rooms-Geräte Konto eine Ausnahme erstellen.
  
4. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wenn Sie fertig sind, wechseln Sie zur Seite "Benutzer" im Microsoft 365 Admin Center, und überprüfen Sie, ob das in den vorherigen Schritten erstellte Konto mit Online verbunden wurde.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. [Öffnen Sie die Exchange-Verwaltungsshell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) , oder stellen [Sie mithilfe von Remote-PowerShell eine Verbindung mit Ihrem Exchange-Server her](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. Erstellen Sie in Exchange PowerShell ein Postfach für das Konto (Postfach aktivieren Sie das Konto), indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [aktivieren-Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. Konfigurieren Sie in Exchange PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungs Erfahrung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Raum Reservierungs Entscheidung direkt ohne menschliche Intervention: kostenlos = akzeptieren; busy = ablehnen.)

   - AddOrganizerToSubject: $false (der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Text im Nachrichtentext der eingehenden Besprechungsanfragen behalten.)

   - Dem DeleteSubject können: $false (Betreff der eingehenden Besprechungsanfragen beibehalten.)

   - RemovePrivateProperty: $false (stellt sicher, dass das private Flag, das vom Organisator der Besprechung in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (der durch den AdditionalResponse-Parameter angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist ein Skype-Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01 konfiguriert.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Satz-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Zuweisen einer Office 365-Lizenz

1. Stellen Sie eine Verbindung mit Azure Active Directory her. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt. 

2. Das Geräte Konto muss über eine gültige Office 365-Lizenz verfügen, oder Exchange und Microsoft Teams funktionieren nicht. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Geräte Konto einen Verwendungsstandort zuweisen, um festzustellen, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> , um eine Liste der verfügbaren SKUs abzurufen.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Als nächstes können Sie eine Lizenz hinzufügen, indem Sie die`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Aktivieren des Geräte Kontos

Skype for Business Online PowerShell wird verwendet, um Dienste für Microsoft Teams und Skype for Business Online zu verwalten.

1. Erstellen Sie eine Windows PowerShell-Remotesitzung wie folgt von einem PC:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. SIP-Adresse des Kontos abrufen:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Führen Sie den folgenden Befehl aus, um Ihr Microsoft Teams rooms-Konto zu aktivieren:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Wenn Sie nicht sicher sind, welchen Wert Sie für den RegistrarPool-Parameter in Ihrer Umgebung verwenden möchten, können Sie den Wert eines vorhandenen Benutzers mit diesem Befehl abrufen:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Zuweisen einer Lizenz zu Ihrem Microsoft Teams rooms-Konto

1. Melden Sie sich als mandantenadministrator an, öffnen Sie das Office 365-Verwaltungs Portal, und klicken Sie auf die Administrator-app.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie auf das Microsoft Teams rooms-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP in Ihren Microsoft Teams-Räumen verwenden möchten.
6. Klicken Sie auf **Speichern**.

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem beliebigen Client bei diesem Konto anzumelden.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft Teams-Chatrooms](rooms-configure-accounts.md)

[Planen von Microsoft Teams-Räumen](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räumen](rooms-deploy.md)
  
[Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](rooms-manage.md)
