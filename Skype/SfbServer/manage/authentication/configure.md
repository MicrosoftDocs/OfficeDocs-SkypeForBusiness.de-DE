---
title: Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Summary: Configure two-factor authentication in Skype for Business Server 2015.'
ms.openlocfilehash: edd32559a136573e7b3cf1fe5dc3a153ce0eb61c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server-2015"></a>Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server 2015
 
**Summary:** Configure two-factor authentication in Skype for Business Server 2015.
  
In den folgenden Abschnitten werden die erforderlichen Schritte beschrieben, um für eine Bereitstellung zweistufige Authentifizierungen zu konfigurieren. For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).
  
## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung

In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung beschrieben:
  
For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).
  
1. Melden Sie sich beim CA-Computer des Unternehmens mit dem Konto eines Domänenadministrators an.
    
2. Starten Sie den System-Manager und überprüfen Sie, ob die Zertifizierungsstellen-Webregistrierungsrolle installiert ist.
    
3. Öffnen Sie im Menü **Verwaltungstools** die Verwaltungskonsole **Zertifizierungsstelle**.
    
4. Erweitern Sie im Navigationsbereich den Knoten **Zertifizierungsstelle**.
    
5. Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **Neu** und anschließend **Auszustellende Zertifikatvorlage** aus.
    
6. Wählen Sie **Enrollment Agent**, **SmartCard-Benutzer** und **SmartCard-Anmeldung** aus.
    
7. Klicken Sie anschließend auf **OK**.
    
8. Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.
    
9. Wählen Sie **Verwalten** aus.
    
10. Öffnen Sie die Eigenschaften der Vorlage „SmartCard-Benutzer“.
    
11. Klicken Sie auf die Registerkarte **Sicherheit**.
    
12. Ändern Sie die Berechtigungen wie folgt:
    
    - Fügen Sie einzelne AD-Konten mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ hinzu, oder
    
    - Fügen Sie eine Sicherheitsgruppe hinzu, die SmartCard-Benutzer mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ enthält, hinzu, oder
    
    - Fügen Sie die Gruppe „Domänenbenutzer“ mit den Berechtigungen „Lesen/Registrieren (Zulassen“) hinzu
    
## <a name="configure-windows-8-for-virtual-smart-cards"></a>Konfigurieren von Windows 8 für virtuelle Smartcards

Ein zu berücksichtigender Faktor bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcardtechnologie sind die Kosten der Implementierung. Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.
  
Bei Computern, die mit einem TPM-Chip (Trusted Platform Module) ausgerüstet sind, der die Spezifikationen von Version 1.2 erfüllt, können Organisationen nun die Vorteile einer Smartcardanmeldung nutzen, ohne in zusätzliche Hardware investieren zu müssen. For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).
  
### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>So konfigurieren Sie Windows 8 für virtuelle Smartcards

1. Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.
    
2. Bewegen Sie den Cursor auf der Windows 8-Startseite in die untere rechte Ecke des Bildschirms.
    
3. Select the **Search** option, and then search forCommand Prompt.
    
4. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und wählen Sie dann **Als Administrator ausführen** aus.
    
5. Öffnen Sie die TPM-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:
    
  ```
  Tpm.msc
  ```

6. Vergewissern Sie sich in der TPM-Verwaltungskonsole, dass die TPM-Spezifikationsversion mindestens 1.2 ist.
    
    > [!NOTE]
    > Wird ein Dialogfeld angezeigt, in dem gemeldet wird, dass kein kompatibles Trusted Platform Module (TPM) gefunden wurde, sollten Sie sich vergewissern, dass der Computer ein kompatibles TPM hat und dass dieses im System-BIOS aktiviert ist. 
  
7. Schließen Sie die TPM-Verwaltungskonsole.
    
8. Erstellen Sie über die Eingabeaufforderung eine neue virtuelle Smartcard, indem Sie folgenden Befehl ausführen:
    
  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert bereitstellen möchten, verwenden Sie „/pin prompt“ anstelle von „/pin default“. 
  
9. Öffnen Sie über die Eingabeaufforderung die Computerverwaltungskonsole, indem Sie den folgenden Befehl ausführen:
    
  ```
  CompMgmt.msc
  ```

10. Wählen Sie in der Computerverwaltungskonsole den Eintrag **Geräte-Manager** aus.
    
11. Erweitern Sie **Smartcard-Leser**.
    
12. Vergewissern Sie sich, dass der neue virtuelle Smartcardleser erfolgreich erstellt wurde.
    
## <a name="enroll-users-for-smart-card-authentication"></a>Registrieren von Benutzern für die SmartCard-Authentifizierung

Allgemein bestehen zwei Verfahren für das Registrieren von Benutzern für die SmartCard-Authentifizierung. Das einfachere Verfahren sieht die direkte Registrierung der Benutzer für die SmartCard-Authentifizierung mithilfe der Webregistrierung vor, während bei der komplexeren Methode ein Enrollment Agent verwendet wird. Dieses Thema legt den Schwerpunkt auf die Selbstregistrierung der Benutzer für SmartCard-Zertifikate.
  
For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).
  
### <a name="to-enroll-users-for-smart-card-authentication"></a>So registrieren Sie Benutzer für die SmartCard-Authentifizierung

1. Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.
    
2. Starten Sie Internet Explorer.
    
3. Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).
    
    > [!NOTE]
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen. 
  
4. Wählen Sie auf der Seite **Willkommen** die Option **Zertifikat anfordern** aus.
    
5. Wählen Sie im nächsten Schritt **Erweiterte Anforderung** aus.
    
6. Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** aus.
    
7. Wählen Sie im Abschnitt **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus und füllen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten aus:
    
  - **Schlüsseloptionen** – bestätigen Sie die folgenden Einstellungen:
    
    - Aktivieren Sie das Optionsfeld **Neuen Schlüsselsatz erstellen**
    
    - Wählen Sie für **CSP** die Option **Microsoft Basis-SmartCard-Krypto-Anbieter**
    
    - Wählen Sie für **Schlüsselverwendung** den Wert **Exchange** aus (dies ist die einzige verfügbare Option).
    
    - For **Key Size**, enter 2048
    
    - Überprüfen Sie, ob **Automatischer Schlüsselcontainername** aktiviert ist
    
    - Lassen Sie die anderen Felder deaktiviert.
    
  - Bestätigen Sie unter **Weitere Optionen** die folgenden Werte:
    
    - Wählen Sie für **Anforderungsformat** den Wert **CMC** aus.
    
    - Wählen Sie für **Hashalgorithmus** den Wert **sha1** aus.
    
    - For **Friendly Name** enterSmardcard Certificate.
    
8. Wenn Sie ein physisches Smartcard-Lesegerät verwenden, setzen Sie die SmartCard in das Gerät ein.
    
9. Klicken Sie auf **Senden**, um die Zertifikatanforderung einzureichen.
    
10. Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen SmartCard verwendet wurde.
    
    > [!NOTE]
    > The default virtual smart card PIN value is '12345678'. 
  
11. Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.
    
    > [!NOTE]
    >  If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:
  
        a. Enable Compatibility View in Internet Explorer 
        b. Enable the Turn on Intranet settings option in Internet Explorer 
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.
  
## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Konfigurieren von Active Directory-Partnerverbunddiensten (AD FS 2.0)

Im folgenden Abschnitt wird beschrieben, wie Active Directory-Partnerverbunddienste (AD FS 2.0) konfiguriert werden muss, damit die mehrstufige Authentifizierung unterstützt wird. For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).
  
> [!NOTE]
> Wenn Sie AD FS 2.0 installieren, dürfen Sie nicht den Windows Server Manager verwenden, um die Active Directory-Partnerverbunddienste-Rolle hinzuzufügen. Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375). 
  
### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>So konfigurieren Sie AD FS für die zweistufige Authentifizierung

1. Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.
    
2. Starten Sie Windows PowerShell.
    
3. Führen Sie aus der Windows PowerShell-Befehlszeile den folgenden Befehl aus:
    
  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Richten Sie eine Partnerschaft mit jedem Server ein, der für die passive Authentifizierung aktiviert werden soll, indem Sie den folgenden Befehl ausführen, und ersetzen Sie den für Ihre Bereitstellung spezifischen Servernamen:
    
  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Starten Sie aus dem Menü „Verwaltung“ die AD FS 2.0-Verwaltungskonsole.
    
6. Expand **Trust Relationships** > **Relying Party Trusts**.
    
7. Verify that a new trust has been created for your Skype for Business Server.
    
8. Erstellen Sie eine Ausstellungsautorisierungsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:
    
  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth 
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Erstellen Sie eine Ausstellungstransformationsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:
    
  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf Ihre Vertrauensstellung der vertrauenden Seite und wählen Sie **Anspruchsregeln bearbeiten** aus.
    
11. Wählen Sie die Registerkarte **Ausstellungsautorisierungsregeln** aus und vergewissern Sie sich, dass die neue Autorisierungsregel erfolgreich erstellt wurde.
    
12. Wählen Sie die Registerkarte **Ausstellungstransformationsregeln** aus und vergewissern Sie sich, dass die neue Transformationsregel erfolgreich erstellt wurde.
    
## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Konfigurieren von AD FS 2.0 zur Unterstützung der Clientauthentifizierung

Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 Authentifizierung über Smartcards unterstützen kann:
  
- Formularbasierte Authentifizierung (FBA)
    
- Transport Layer Security-Clientauthentifizierung
    
Wenn Sie formularbasierte Authentifizierung verwenden, können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mit der Kombination aus Benutzername und Kennwort oder mit Smartcard und PIN zu authentifizieren. Im vorliegenden Thema wird beschrieben, wie Transport Layer Security-Clientauthentifizierung mit AD FS 2.0 implementiert wird. For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).
  
### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>So konfigurieren Sie AD FS 2.0, sodass Clientauthentifizierung unterstützt wird

1. Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.
    
2. Starten Sie Windows-Explorer.
    
3. Navigieren Sie zu „C:\inetpub\adfs\ls“
    
4. Erstellen Sie eine Sicherungskopie von der vorhandenen Datei „web.config“.
    
5. Öffnen Sie die vorhandene Datei „web.config“ im Editor.
    
6. Wählen Sie in der Menüleiste das Menü **Bearbeiten** und anschließend **Suchen** aus.
    
7. Search for \<localAuthenticationTypes\>.
    
    Es werden vier Authentifizierungstypen aufgelistet (je ein Typ pro Zeile).
    
8. Verschieben Sie die Zeile, die den Authentifizierungstyp „TLSClient“ enthält, an den Anfang der Liste im Abschnitt.
    
9. Speichern Sie die Datei „web.config“ und beenden Sie den Editor.
    
10. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
    
11. Starten Sie IIS neu, indem Sie folgenden Befehl ausführen:
    
  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Konfigurieren der passiven Authentifizierung für Skype for Business Server

The following section describes how to configure Skype for Business Server 2015 to support passive authentication. Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.
  
> [!NOTE]
> Kunden wird dringend empfohlen, die passive Authentifizierung für Registrierungsstellen und Webdienste auf Dienstebene zu aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf der globalen Ebene aktiviert wird, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit dem unterstützten Desktopclient anmelden. 
  
### <a name="web-service-configuration"></a>Webdienstkonfiguration

In den folgenden Schritten wird die Erstellung einer angepassten Webdienstkonfiguration für Directorserver, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.
  
### <a name="to-create-a-custom-web-service-configuration"></a>So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration

1. Log in to your Skype for Business Server 2015 Front End server using a Skype for Business administrator account.
    
2. Launch the Skype for Business Server Management Shell.
    
3. From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:
    
  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > Der Wert für den vollqualifizierten Domänennamen in „WsFedPassiveMetadataUri“ ist der Name des Partnerverbunddiensts Ihres AD FS 2.0-Servers. Sie können den Wert des Namens des Partnerverbunddiensts in der AD FS 2.0-Verwaltungskonsole abrufen, indem Sie im Navigationsbereich auf **Dienst** klicken und dann **Eigenschaften des Verbunddiensts bearbeiten** auswählen. 
  
4. Überprüfen Sie, ob die Werte von „UseWsFedPassiveAuth“ und „WsFedPassiveMetadataUri“ richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:
    
  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Für Clients stellt die passive Authentifizierung die am wenigsten vorzuziehende Authentifizierungsmethode für die Authentifizierung mithilfe von Webtickets dar. For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:
    
  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Überprüfen Sie, ob alle anderen Authentifizierungsarten erfolgreich deaktiviert wurden, indem Sie das folgende Cmdlet ausführen:
    
  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Proxykonfiguration

When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service. Die Zertifikatauthentifizierung ist nach wie vor erforderlich, um dem Client das Abrufen eines Webtickets zu ermöglichen, jedoch müssen Kerberos und NTLM für den Registrierungsstellendienst deaktiviert werden.
  
In den folgenden Schritten wird die Erstellung einer angepassten Proxykonfiguration für Edge Pools, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.
  
### <a name="to-create-a-custom-proxy-configuration"></a>So erstellen Sie eine benutzerdefinierte Proxykonfiguration

1. From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server 2015 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:
    
  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
-UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" 
-UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Überprüfen Sie, ob alle anderen Proxyauthentifizierungsarten erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    
  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com"
 | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Siehe auch

#### 

[Manage two-factor authentication in Skype for Business Server 2015](two-factor-authentication.md)
  
[Use two-factor authentication with Skype for Business client and Skype for Business Server 2015](use.md)

