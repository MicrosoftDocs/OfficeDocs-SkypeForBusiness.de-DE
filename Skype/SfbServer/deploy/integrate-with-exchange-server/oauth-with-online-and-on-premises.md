---
title: OAuth-Konfiguration zwischen Skype for Business Online und einer lokalen Bereitstellung von Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Konfigurieren von OAuth aktiviert-Authentifizierung zwischen Exchange lokal und Skype für Business Online die Skype für Geschäfts- und Exchange-Integration in featureunterstützung beschriebenen Features.
ms.openlocfilehash: fe1f6a56412706c658b2c686d2ca06d6a1b9e5d9
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684056"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>OAuth-Konfiguration zwischen Skype for Business Online und einer lokalen Bereitstellung von Exchange

Konfigurieren von OAuth ermöglicht die Authentifizierung zwischen Exchange lokal und Skype für Business Online die Skype für Geschäfts- und Integration von Exchange-Features beschrieben in [Feature zu unterstützen](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Dieses Thema bezieht sich auf Exchange Server 2016 und Exchange Server 2013.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie anfangen

- Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten

-  Sie müssen Berechtigungen zugewiesen werden, bevor Sie dieses Verfahren oder Verfahren ausführen können. Welche Berechtigungen Sie müssen finden Sie im Thema [Exchange and Shell Infrastructure Permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen in der Exchange-Verwaltungskonsole]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>Konfigurieren Sie OAuth-Authentifizierung zwischen Ihren lokalen Exchange- und Skype for Business-Organisationen.

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>Schritt 1: Erstellen eines Autorisierungsserverobjekts für Ihre Skype for Business Online-Organisation

Geben Sie eine überprüfte Domäne für Ihre Skype für Business Online-Organisation. Diese Domäne sollte dieselbe sein, die auch als primäre SIP-Domäne für die Cloud-basierte Konten verwendet wird. Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren.

Führen Sie den folgenden Befehl in der Exchange-Verwaltungsshell (Exchange PowerShell) in Ihrer lokalen Exchange-Organisation.

```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1"
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>Schritt 2: Aktivieren der Partneranwendung für Ihre Skype for Business Online-Organisation

Führen Sie den folgenden Befehl in der Exchange PowerShell in Ihrer lokalen Exchange-Organisation.

```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Schritt 3: Erstellen eines neuen E-Mail-Benutzerkontos für die Skype for Business Online-Partneranwendung 

Dieser Schritt wird lokal erledigt. Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen. Dieses Konto wird anschließend im nächsten Schritt gebraucht.

Geben Sie eine überprüfte Domäne für Ihre Exchange-Organisation. Diese Domäne sollte der gleichen Domäne wie die primäre SMTP-Domäne für den lokalen Exchange-Konten verwendet werden. Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren. Darüber hinaus die \<DomainControllerFQDN\> sollte der FQDN eines Domänencontrollers sein.

```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Dieser Befehl blendet den neuen E-Mail-Benutzer aus der Adressliste aus.

```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Die nächsten beiden Befehle weisen diesem neuen Konto die „UserApplication“- und die „ArchiveApplication“-Verwaltungsrolle zu.

```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Schritt 4: Erstellen und Aktivieren der Partneranwendung für Skype for Business Online

Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben. Führen Sie den folgenden Befehl in der Exchange PowerShell in Ihrer lokalen Exchange-Organisation.

```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>Schritt 5: Exportieren des lokalen Autorisierungszertifikats

Führen Sie ein PowerShell-Skript zum Exportieren des lokalen autorisierungszertifikats, die Sie an Ihre Skype für Business Online-Organisation im nächsten Schritt importieren werden.

Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, die Sie zum Beispiel „ExportAuthCert.ps1“ nennen können.

```
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

In Exchange PowerShell in Ihrer lokalen Exchange-Organisation führen die PowerShell-Skripts, die Sie gerade erstellt haben. Beispiel:.\ExportAuthCert.ps1

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Schritt 6: Hochladen des lokalen Autorisierungszertifikats nach Azure Active Directory ACS

Verwenden Sie im nächsten Schritt Windows PowerShell, um das im vorigen Schritt exportierte Autorisierungszertifikat auf Azure Active Directory Access Control Services (ACS) hochzuladen. Dafür muss das Azure Active Directory-Modul für Windows PowerShell-Cmdlets bereits installiert sein. Wenn dies nicht der Fall ist, fahren Sie mit [https://aka.ms/aadposh](https://aka.ms/aadposh) So installieren Sie die Azure Active Directory-Modul für Windows PowerShell. Schließen Sie die folgenden Schritte ab, nachdem das Azure Active Directory-Modul für Windows PowerShell installiert worden ist.

1. Klicken Sie auf die **Azure Active Directory-Modul für Windows PowerShell**-Verknüpfung, um einen Windows PowerShell-Arbeitsbereich mit den installierten Azure AD-Cmdlets zu öffnen. Alle Befehle in diesem Schritt werden mithilfe der Windows PowerShell für Azure Active Directory ausgeführt.

2. Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, z. B. `UploadAuthCert.ps1`.

   ```
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

### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a>Schritt 7: Registrieren der Hostname-Zertifizierungsstellen für die SMTP-Domäne

Geben Sie eine überprüfte Domäne für Ihre Exchange-Organisation. Diese Domäne sollte der gleichen Domäne wie die primäre SMTP-Domäne für den lokalen Exchange-Konten verwendet werden. Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren.

> [!NOTE]
> Die erfolgreiche Ausführung des folgenden Skripts setzt voraus, dass die Windows PowerShell für Azure Active Directory mit Ihrem Microsoft Online Azure AD-Mandanten verbunden ist, wie unter Schritt 4 im vorigen Abschnitt erläutert.

1. Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, die Sie zum Beispiel „RegisterEndpoints.ps1“ nennen können. In diesem Beispiel wird ein Platzhalter verwendet, um alle Endpunkte für „contoso.com“ zu registrieren. Ersetzen Sie <your Verified Domain> mit einer den FQDN für den lokalen Exchange-Server.

   ```
   $externalAuthority="*.<your Verified Domain>"
   $ServiceName = "00000002-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName;
   $spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority);
   $p.ServicePrincipalNames.Add($spn);
   Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames;
   ```

2. Führen Sie in Windows PowerShell für Azure Active Directory das Windows PowerShell-Skript aus, das Sie im vorigen Schritt erstellt haben. Zum Beispiel:`.\RegisterEndpoints.ps1`

### <a name="verify-your-success"></a>Überprüfen Ihres Erfolgs

Stellen Sie sicher, dass die OAuth-Konfiguration korrekt ist, indem Sie überprüfen, ob einige der Funktionen erfolgreich ausgeführt werden können, zum Beispiel, ob die aufgezeichneten Unterhaltungen für Mobilgeräte-Clients im Ordner der aufgezeichneten Outlook-Unterhaltungen sichtbar sind.

1. Starten Sie die Skype für mobile Geschäfts-app auf dem Windows Phone oder iOS-Gerät, und melden Sie sich als ein Skype für Business Online-Benutzer mit einem Exchange-2016 oder Exchange 2013 lokales Postfach.

2. Haben Sie eine Sofortnachrichtenunterhaltung mit einer anderen Skype für Business Online-Benutzer.

3. Schließen Sie das Chatunterhaltungsfenster.

4. Starten Sie Outlook für diesen Nutzer und überprüfen Sie, ob die Unterhaltung im Ordner der aufgezeichneten Outlook-Unterhaltungen sichtbar ist.

Betrachten Sie alternativ den Datenverkehr. Des Datenverkehrs in einem OAuth-Handshake ist wirklich charakteristischen (und nicht sehen, wie die Standardauthentifizierung), insbesondere zur Umgehung von Bereichen, wobei Sie Aussteller-Datenverkehr angezeigt, die folgendermaßen aussieht beginnen: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit einem / vor das @-Zeichen), in der Token, die übergeben werden. Benutzernamen und Kennwort an, das die Punkt OAuth wird nicht angezeigt. Aber sehen Sie den Aussteller 'Office' – in diesem Fall ist "4" Skype für Unternehmen – und dem Bereich Ihres Abonnements.

Wenn Sie sicherstellen möchten, dass Sie erfolgreich OAuth verwenden, stellen Sie sicher, dass Sie wissen, was zu erwarten und wissen, wie der Datenverkehr aussehen sollte. [Hier ist zu erwarten, dass](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)dies der Fall ist, hier ist ein ziemlich standard [Beispiel OAuth-Verkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (sehr nützlich zu lesen, obwohl es nicht Aktualisierungstoken verwendet), und es sind Fiddler-Erweiterungen, die Sie in Ihre OAuth JWT (JSON suchen können Web Token).

Es folgt ein [Beispiel für eine einrichten](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), jedoch können Sie diesen Prozess verpflichten sich gerne Netzwerk Tracing-Tools.

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
