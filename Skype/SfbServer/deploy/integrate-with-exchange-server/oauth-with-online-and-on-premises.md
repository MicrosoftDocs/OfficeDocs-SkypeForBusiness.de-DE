---
title: Integration von Skype for Business Online und Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Wenn Sie die OAuth-Authentifizierung zwischen Exchange lokal und Skype for Business Online konfigurieren, werden die unter Funktionsunterstützung beschriebenen Funktionen für Skype for Business und die Exchange-Integration aktiviert.
ms.openlocfilehash: 35dc8777ddf5c7102e99d726f916f9b8f8bb4aae
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002895"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server 

Durch die Konfiguration der Integration zwischen Exchange Server und Skype for Business Online werden die unter [Funktionsunterstützung](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)beschriebenen Funktionen für Skype for Business und Exchange integriert.

Dieses Thema bezieht sich auf die Integration in Exchange Server 2013 bis 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie anfangen

- Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten

-  Sie müssen Berechtigungen zugewiesen sein, bevor Sie diese Schritte ausführen können. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie im Thema zu den [Berechtigungen für Exchange-und Shell-Infrastruktur](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten können, finden Sie unter [Tastenkombinationen im Exchange Admin Center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Informationen zur Kompatibilität finden Sie unter [Skype for Business-Kompatibilität mit Office-Apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Konfigurieren der Integration zwischen Exchange Server und Office 365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Schritt 1: Konfigurieren der OAuth-Authentifizierung zwischen Exchange Server und Office 365

Führen Sie die im folgenden Artikel aufgeführten Schritte aus:

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Schritt 2: Erstellen eines neuen e-Mail-Benutzerkontos für die Skype for Business Online-Partner Anwendung

Dieser Schritt erfolgt auf dem Exchange-Server. Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen. Dieses Konto wird anschließend im nächsten Schritt gebraucht.

Geben Sie eine verifizierte Domäne für Ihre Exchange-Organisation an. Diese Domäne sollte dieselbe Domäne sein wie die primäre SMTP-Domäne, die für die lokalen Exchange-Konten verwendet wird. Diese Domäne wird im folgenden \<Verfahren als Ihre\> überprüfte Domäne bezeichnet. Außerdem sollte der \<DomainControllerFQDN\> der FQDN eines Domänencontrollers sein.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Dieser Befehl blendet den neuen E-Mail-Benutzer aus der Adressliste aus.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Die nächsten beiden Befehle weisen diesem neuen Konto die „UserApplication“- und die „ArchiveApplication“-Verwaltungsrolle zu.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Schritt 3: Erstellen und Aktivieren einer Partner Anwendung für Skype for Business Online 

Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben. Führen Sie den folgenden Befehl in der Exchange-PowerShell in Ihrer lokalen Exchange-Organisation aus.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Schritt 4: Exportieren des lokalen Autorisierungs Zertifikats

Führen Sie ein PowerShell-Skript aus, um das lokale Autorisierungszertifikat zu exportieren, das Sie im nächsten Schritt in Ihre Skype for Business Online-Organisation importieren werden.

Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, die Sie zum Beispiel „ExportAuthCert.ps1“ nennen können.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

Führen Sie in Exchange PowerShell in Ihrer lokalen Exchange-Organisation das soeben erstellte PowerShell-Skript aus. Beispiel: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Schritt 5: Hochladen des lokalen Autorisierungs Zertifikats in Azure Active Directory ACS

Verwenden Sie im nächsten Schritt Windows PowerShell, um das im vorigen Schritt exportierte Autorisierungszertifikat auf Azure Active Directory Access Control Services (ACS) hochzuladen. Dafür muss das Azure Active Directory-Modul für Windows PowerShell-Cmdlets bereits installiert sein. Wenn Sie nicht installiert ist, wechseln [https://aka.ms/aadposh](https://aka.ms/aadposh) Sie zu installieren des Azure Active Directory-Moduls für Windows PowerShell. Schließen Sie die folgenden Schritte ab, nachdem das Azure Active Directory-Modul für Windows PowerShell installiert worden ist.

1. Klicken Sie auf die **Azure Active Directory-Modul für Windows PowerShell**-Verknüpfung, um einen Windows PowerShell-Arbeitsbereich mit den installierten Azure AD-Cmdlets zu öffnen. Alle Befehle in diesem Schritt werden mithilfe der Windows PowerShell für Azure Active Directory ausgeführt.

2. Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei mit dem Namen `UploadAuthCert.ps1`, beispielsweise.

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Führen Sie das PowerShell-Skript aus, das Sie im vorigen Schritt erstellt haben. Zum Beispiel:`.\UploadAuthCert.ps1`

4. Nach dem Start des Skripts wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt. Geben Sie die Anmeldeinformationen für das Mandantenadministratorkonto Ihrer Microsoft Online Azure AD-Organisation ein. Nachdem das Skript ausgeführt worden ist, lassen Sie die Windows PowerShell für die Azure AD-Sitzung offen. Sie brauchen sie, um im nächsten Schritt ein PowerShell-Skript auszuführen.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Schritt 6: überprüfen, ob das Zertifikat in den Skype for Business-Dienstprinzipal hochgeladen wurde
1. Führen Sie in der PowerShell, die in Azure Active Directory geöffnet und authentifiziert wurde, die folgenden Schritte aus:
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Drücken Sie die EINGABETASTE, wenn Sie zur ReturnKeyValues aufgefordert werden.
3. Bestätigen, dass ein Schlüssel mit Anfangsdatum und Enddaten angezeigt wird, die dem Start-und Enddatum Ihres Exchange OAuth-Zertifikats entsprechen

### <a name="verify-your-success"></a>Überprüfen Ihres Erfolgs

Überprüfen Sie, ob die Konfiguration korrekt ist, indem Sie sicherstellen, dass einige Features erfolgreich funktionieren. 

1. Bestätigen Sie, dass Skype for Business-Benutzer mit Cloud-Voicemaildienst in einer Organisation mit einer Exchange Server-Hybrid Konfiguration Ihre Voicemail-Grußformeln erfolgreich ändern können.

2. Der Konversations Verlauf für mobile Clients bestätigen ist im Outlook-Ordner "Konversations Verlauf" sichtbar.

3. Vergewissern Sie sich, dass archivierte Chatnachrichten im lokalen Postfach des Benutzers im Ordner "Säuberungen" unter Verwendung von [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)hinterlegt sind.

Schauen Sie sich alternativ Ihren Traffic an. Der Datenverkehr in einem OAuth-Handshake ist wirklich charakteristisch (und sieht nicht wie die Standardauthentifizierung aus), insbesondere in Bereichen, in denen Sie den Aussteller Datenverkehr sehen, der wie folgt aussieht: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit einem/vor dem @-Zeichen) in den Token, die übergeben werden. Sie sehen keinen Benutzernamen oder kein Kennwort, was der OAuth-Punkt ist. Sie sehen aber den Aussteller "Office" – in diesem Fall "4" ist Skype for Business – und das Reich Ihres Abonnements.

Wenn Sie sicher sein möchten, dass Sie OAuth erfolgreich verwenden, stellen Sie sicher, dass Sie wissen, was Sie erwarten und wissen, wie der Datenverkehr aussehen soll. Hier [sehen Sie also ein](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)ziemlich Standard [Beispiel für OAuth-Datenverkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (wirklich hilfreich zum Lesen, obwohl es keine Aktualisierungs Tokens verwendet), und es gibt Fiddler-Erweiterungen, mit denen Sie Ihr OAuth-JWT (JSON-webtoken) überprüfen können.

Hier ist ein [Beispiel für die Einrichtung](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), aber Sie können jedes Netzwerk-Tracing-Tool verwenden, mit dem Sie diesen Prozess durchführen möchten.

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
