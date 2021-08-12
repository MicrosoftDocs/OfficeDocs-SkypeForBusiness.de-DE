---
title: Integration zwischen Skype for Business Online und Exchange Server
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Das Konfigurieren der OAuth-Authentifizierung zwischen Exchange lokal und Skype for Business Online ermöglicht die in der Featureunterstützung beschriebenen integrationsfeatures Skype for Business und Exchange.
ms.openlocfilehash: 8342fefa10fcd66cd7cd10c121b787a05a7a0401d5235bbc70b2412bb538e5e4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300281"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Konfigurieren der Integration und OAuth zwischen Skype for Business Online und Exchange Server 

Das Konfigurieren der Integration zwischen Exchange Server und Skype for Business Online ermöglicht die in der [Featureunterstützung](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)beschriebenen Skype for Business- und Exchange Integrationsfeatures.

Dieses Thema bezieht sich auf die Integration in Exchange Server 2013 bis 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 15 Minuten

-  Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den benötigten Berechtigungen finden Sie im Thema [Exchange und Shell-Infrastrukturberechtigungen.](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)

- Informationen zu Tastenkombinationen für die Verfahren in diesem Thema finden Sie unter [Tastenkombinationen in der Exchange-Verwaltungskonsole]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Informationen zur Kompatibilität finden Sie unter [Skype for Business Kompatibilität mit Office Apps.](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)

## <a name="configure-integration-between-exchange-server-and-o365"></a>Konfigurieren der Integration zwischen Exchange Server und O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Schritt 1: Konfigurieren der OAuth-Authentifizierung zwischen Exchange Server und O365

Führen Sie die Schritte im folgenden Artikel aus:

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Schritt 2: Erstellen eines neuen E-Mail-Benutzerkontos für die Skype for Business Online-Partneranwendung

Dieser Schritt wird auf dem Exchange Server ausgeführt. Er erstellt einen E-Mail-Benutzer und weist ihm die entsprechenden Verwaltungsrollenrechte zu. Dieses Konto wird dann im nächsten Schritt verwendet.

Geben Sie eine überprüfte Domäne für Ihre Exchange Organisation an. Diese Domäne sollte dieselbe Sein wie die primäre SMTP-Domäne, die für die lokalen Exchange Konten verwendet wird. Diese Domäne wird \<your Verified Domain\> im folgenden Verfahren bezeichnet. Außerdem sollte es \<DomainControllerFQDN\> sich um den FQDN eines Domänencontrollers handeln.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Mit diesem Befehl wird der neue E-Mail-Benutzer in Adresslisten ausgeblendet.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Diese beiden nächsten Befehle weisen diesem neuen Konto die Verwaltungsrolle "UserApplication" und "ArchiveApplication" zu.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Schritt 3: Erstellen und Aktivieren einer Partneranwendung für Skype for Business Online 

Erstellen Sie eine neue Partneranwendung und verwenden Sie das soeben erstellte Konto. Führen Sie den folgenden Befehl in der Exchange PowerShell in Ihrer lokalen Exchange-Organisation aus.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Schritt 4: Exportieren des lokalen Autorisierungszertifikats

Führen Sie ein PowerShell-Skript aus, um das lokale Autorisierungszertifikat zu exportieren, das Sie im nächsten Schritt in Ihre Skype for Business Online-Organisation importieren.

Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, die etwa ExportAuthCert.ps1 benannt werden kann.

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

Führen Sie in Exchange PowerShell in Ihrer lokalen Exchange Organisation das soeben erstellte PowerShell-Skript aus. Beispiel: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Schritt 5: Hochladen des lokalen Autorisierungszertifikats an Azure Active Directory ACS

Verwenden Sie als Nächstes Windows PowerShell, um das lokale Autorisierungszertifikat hochzuladen, das Sie im vorherigen Schritt in Azure Active Directory Access Control Services (ACS) exportiert haben. Hierzu muss das Azure Active Directory Modul für Windows PowerShell Cmdlets bereits installiert sein. Sollten diese noch nicht installiert sein, navigieren Sie zu [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)), um das Azure Active Directory-Modul für Windows PowerShell zu installieren. Führen Sie die folgenden Schritte aus, nachdem Sie das Azure Active Directory-Modul für Windows PowerShell installiert haben.

1. Klicken Sie auf die Verknüpfung **Azure Active Directory-Modul für Windows PowerShell**, um einen Windows PowerShell-Arbeitsbereich zu öffnen, in dem die Azure AD-Cmdlets installiert sind. Alle Befehle in diesem Schritt werden unter Verwendung der Windows PowerShell für die Azure Active Directory-Konsole ausgeführt.

2. Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei mit dem Namen,  `UploadAuthCert.ps1` z. B. .

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

3. Führen Sie das PowerShell-Skript aus, welches Sie im vorherigen Schritt erstellt haben. Beispiel:  `.\UploadAuthCert.ps1`

4. Nachdem Sie das Skript gestartet haben, wird ein Dialogfeld für Anmeldeinformationen angezeigt. Geben Sie die Anmeldeinformationen für das Mandantenadministratorkonto Ihrer Microsoft Online Azure AD-Organisation ein. Lassen Sie Windows PowerShell nach der Ausführung des Skripts für die Azure AD-Sitzung geöffnet. Sie werden diese zum Ausführen eines PowerShell-Skripts im nächsten Schritt erneut nutzen.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Schritt 6: Überprüfen, ob das Zertifikat in den Skype for Business Dienstprinzipal hochgeladen wurde
1. Führen Sie in der geöffneten und für Azure Active Directory authentifizierten PowerShell Folgendes aus:
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Drücken Sie die EINGABETASTE, wenn Sie zur Eingabe von ReturnKeyValues aufgefordert werden.
3. Vergewissern Sie sich, dass ein Schlüssel mit Start- und Enddaten aufgeführt ist, die mit Ihrem Exchange Oauth-Zertifikat-Start- und -Enddatum übereinstimmen

### <a name="verify-your-success"></a>Überprüfen Ihres Erfolgs

Stellen Sie sicher, dass die Konfiguration korrekt ist, indem Sie überprüfen, ob einige der Features erfolgreich funktionieren. 

1. Vergewissern Sie sich, dass Skype for Business Benutzer mit Cloud-Voicemail Dienst in einer Organisation mit hybrider Exchange Server Konfiguration ihre Voicemail-Begrüßungen erfolgreich ändern können.

2. Bestätigen Sie, dass der Unterhaltungsverlauf für mobile Clients im Ordner Outlook Unterhaltungsverlauf angezeigt wird.

3. Vergewissern Sie sich, dass archivierte Chatnachrichten im lokalen Postfach des Benutzers im Ordner "Löschvorgänge" mithilfe von [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)abgelegt werden.

Sehen Sie sich alternativ Ihren Datenverkehr an. Der Datenverkehr in einem OAuth-Handshake ist wirklich charakteristisch (und sieht nicht wie die Standardauthentifizierung aus), insbesondere in Bereichen, in denen Der Ausstellerdatenverkehr wie folgt aussieht: 000000004-0000-0ff1-ce00-000000000000@ (manchmal mit einem / vor dem @-Zeichen) in den übergebenen Token. Es wird kein Benutzername oder Kennwort angezeigt, was der Punkt von OAuth ist. Sie sehen jedoch den Aussteller "Office" – in diesem Fall ist "4" Skype for Business – und den Bereich Ihres Abonnements.

Wenn Sie sicherstellen möchten, dass Sie OAuth erfolgreich verwenden, stellen Sie sicher, dass Sie wissen, was Sie erwarten sollten und wie der Datenverkehr aussehen sollte. Hier [sehen](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)Sie also ein ziemlich standardmäßiges [Beispiel für OAuth-Datenverkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (sehr hilfreich zum Lesen, obwohl es keine Aktualisierungstoken verwendet), und es gibt Fiddler-Erweiterungen, mit denen Sie ihre OAuth-JWT (JSON Web Token) untersuchen können.

Hier ist ein [Beispiel für die Einrichtung,](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)sie können jedoch ein beliebiges Netzwerkablaufverfolgungstool verwenden, das Sie für diesen Vorgang verwenden möchten.

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)