---
title: Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Zusammenfassung: Konfigurieren einer zweistufigen Authentifizierung in Skype für Business Server.'
ms.openlocfilehash: 3b77a6cbbbeb7be83bb4a27491982d97939e1936
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969526"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server
 
**Zusammenfassung:** Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server.
  
In den folgenden Abschnitten werden die erforderlichen Schritte beschrieben, um für eine Bereitstellung zweistufige Authentifizierungen zu konfigurieren. Weitere Informationen zur zweistufigen Authentifizierung finden Sie unter [Aktivieren von Office 365 mehrstufige Authentifizierung für online-Administratoren - Raster Benutzer Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).
  
## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung

In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung beschrieben:
  
Informationen zum Installieren einer Stammzertifizierungsstelle für die Zertifizierungsstelle finden Sie unter [Installieren einer Stammzertifizierungsstelle der Organisation](https://go.microsoft.com/fwlink/p/?LinkID=313364).
  
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

Ein zu berücksichtigender Faktor bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcardtechnologie sind die Kosten der Implementierung. Windows 8 bietet eine Reihe von neuen Sicherheitsfunktionen, und eine der interessantesten neuen Features Unterstützung für virtuelle Smart Karten ist.
  
Bei Computern, die mit einem TPM-Chip (Trusted Platform Module) ausgerüstet sind, der die Spezifikationen von Version 1.2 erfüllt, können Organisationen nun die Vorteile einer Smartcardanmeldung nutzen, ohne in zusätzliche Hardware investieren zu müssen. Weitere Informationen finden Sie unter [Using virtuelle Smart Karten mit Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).
  
### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>So konfigurieren Sie Windows 8 für virtuelle Smartcards

1. Melden Sie sich an den Windows 8-Computer mit den Anmeldeinformationen des einen Skype für Business-aktivierten Benutzer.
    
2. Bewegen Sie den Cursor auf der Windows 8-Startseite in die untere rechte Ecke des Bildschirms.
    
3. Wählen Sie eine **Suchoption** aus, und suchen Sie anschließend nach Aufforderung ForCommand.
    
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
  
Weitere Informationen zum Registrieren von als Registrierungs-Agent im Namen von Benutzern finden Sie unter [Registrieren für Zertifikate im Namen von anderen Benutzern](https://go.microsoft.com/fwlink/p/?LinkID=313367).
  
### <a name="to-enroll-users-for-smart-card-authentication"></a>So registrieren Sie Benutzer für die SmartCard-Authentifizierung

1. Melden Sie sich an der Windows 8-Arbeitsstation mit den Anmeldeinformationen des einen Skype für Business-aktivierten Benutzer.
    
2. Starten Sie Internet Explorer.
    
3. Wechseln Sie zur Seite **Certificate Authority Web-Registrierung** (z. B. https://MyCA.contoso.com/certsrv).
    
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
    
    - Geben Sie unter **Schlüsselgröße** den Wert 2048 ein
    
    - Überprüfen Sie, ob **Automatischer Schlüsselcontainername** aktiviert ist
    
    - Lassen Sie die anderen Felder deaktiviert.
    
  - Bestätigen Sie unter **Weitere Optionen** die folgenden Werte:
    
    - Wählen Sie für **Anforderungsformat** den Wert **CMC** aus.
    
    - Wählen Sie für **Hashalgorithmus** den Wert **sha1** aus.
    
    - Für **Anzeigename** EnterSmardcard Zertifikat.
    
8. Wenn Sie ein physisches Smartcard-Lesegerät verwenden, setzen Sie die SmartCard in das Gerät ein.
    
9. Klicken Sie auf **Senden**, um die Zertifikatanforderung einzureichen.
    
10. Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen SmartCard verwendet wurde.
    
    > [!NOTE]
    > Der Standardwert für virtuelle Smartcard PIN ist "12345678". 
  
11. Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.
    
    > [!NOTE]
    >  Schlägt der zertifikatanforderung den Fehler "in Webbrowser unterstützt nicht die Generierung von zertifikatanforderungen", gibt es drei verschiedene Arten zur Behebung des Problems:
  
        a. Enable Compatibility View in Internet Explorer 
        b. Enable the Turn on Intranet settings option in Internet Explorer 
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.
  
## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Konfigurieren von Active Directory-Partnerverbunddiensten (AD FS 2.0)

Im folgenden Abschnitt wird beschrieben, wie Active Directory-Partnerverbunddienste (AD FS 2.0) konfiguriert werden muss, damit die mehrstufige Authentifizierung unterstützt wird. Informationen zum Installieren von AD FS 2.0 finden Sie unter [AD FS 2.0 schrittweise und wie an Führungslinien](https://go.microsoft.com/fwlink/p/?LinkId=313374).
  
> [!NOTE]
> Wenn Sie AD FS 2.0 installieren, dürfen Sie nicht den Windows Server Manager verwenden, um die Active Directory-Partnerverbunddienste-Rolle hinzuzufügen. Stattdessen herunterladen Sie und installieren Sie das [Active Directory Federation Services 2.0 RTW-Paket](https://go.microsoft.com/fwlink/p/?LinkId=313375). 
  
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
    
6. Erweitern Sie **Vertrauensstellungen** > **Relying Party Trusts**.
    
7. Stellen Sie sicher, dass eine neue Vertrauensstellung für Ihre Skype für Business Server erstellt wurde.
    
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
    
Wenn Sie formularbasierte Authentifizierung verwenden, können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mit der Kombination aus Benutzername und Kennwort oder mit Smartcard und PIN zu authentifizieren. Im vorliegenden Thema wird beschrieben, wie Transport Layer Security-Clientauthentifizierung mit AD FS 2.0 implementiert wird. Weitere Informationen zu AD FS 2.0 Authentifizierungstypen, finden Sie unter [AD FS 2.0: Ändern Sie den lokalen Authentifizierungstyp](https://go.microsoft.com/fwlink/p/?LinkId=313384).
  
### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>So konfigurieren Sie AD FS 2.0, sodass Clientauthentifizierung unterstützt wird

1. Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.
    
2. Starten Sie Windows-Explorer.
    
3. Navigieren Sie zu „C:\inetpub\adfs\ls“
    
4. Erstellen Sie eine Sicherungskopie von der vorhandenen Datei „web.config“.
    
5. Öffnen Sie die vorhandene Datei „web.config“ im Editor.
    
6. Wählen Sie in der Menüleiste das Menü **Bearbeiten** und anschließend **Suchen** aus.
    
7. Suchen Sie nach \<LocalAuthenticationTypes\>.
    
    Es werden vier Authentifizierungstypen aufgelistet (je ein Typ pro Zeile).
    
8. Verschieben Sie die Zeile, die den Authentifizierungstyp „TLSClient“ enthält, an den Anfang der Liste im Abschnitt.
    
9. Speichern Sie die Datei „web.config“ und beenden Sie den Editor.
    
10. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
    
11. Starten Sie IIS neu, indem Sie folgenden Befehl ausführen:
    
  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Konfigurieren der passiven Authentifizierung für Skype for Business Server

Im folgende Abschnitt wird beschrieben, wie Skype für Business Server zur Unterstützung der passiven Authentifizierung zu konfigurieren. Nach der Aktivierung werden von einer physischen oder virtuellen Smartcard und eine gültige PIN zum Melden Sie sich über die Skype für Business Client erforderlich Benutzer, die für die zweistufige Authentifizierung aktiviert ist.
  
> [!NOTE]
> Kunden wird dringend empfohlen, die passive Authentifizierung für Registrierungsstellen und Webdienste auf Dienstebene zu aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf der globalen Ebene aktiviert wird, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit dem unterstützten Desktopclient anmelden. 
  
### <a name="web-service-configuration"></a>Webdienstkonfiguration

In den folgenden Schritten wird die Erstellung einer angepassten Webdienstkonfiguration für Directorserver, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.
  
### <a name="to-create-a-custom-web-service-configuration"></a>So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration

1. Melden Sie sich bei Ihrer Skype für Business Server-Front-End-Server mit einer Skype für Business-Administratorkonto an.
    
2. Starten Sie die Skype für Business Server-Verwaltungsshell.
    
3. Erstellen Sie über die Skype für Business Server-Verwaltungsshell Command-Line eine neue Konfiguration für den Webdienst für jeden Director, Enterprise-Pool und Standard Edition-Server, die für passiven Authentifizierung mithilfe des folgenden Befehls aktiviert werden sollen:
    
  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > Der Wert für den vollqualifizierten Domänennamen in „WsFedPassiveMetadataUri“ ist der Name des Partnerverbunddiensts Ihres AD FS 2.0-Servers. Sie können den Wert des Namens des Partnerverbunddiensts in der AD FS 2.0-Verwaltungskonsole abrufen, indem Sie im Navigationsbereich auf **Dienst** klicken und dann **Eigenschaften des Verbunddiensts bearbeiten** auswählen. 
  
4. Überprüfen Sie, ob die Werte von „UseWsFedPassiveAuth“ und „WsFedPassiveMetadataUri“ richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:
    
  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Für Clients stellt die passive Authentifizierung die am wenigsten vorzuziehende Authentifizierungsmethode für die Authentifizierung mithilfe von Webtickets dar. Für alle Directors, Enterprise-Pools und Standard Edition-Servern, die für passiven Authentifizierung aktiviert werden sollen, müssen alle Authentifizierungstypen in Skype für Webdienste Business deaktiviert werden durch das folgende Cmdlet ausführen:
    
  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Überprüfen Sie, ob alle anderen Authentifizierungsarten erfolgreich deaktiviert wurden, indem Sie das folgende Cmdlet ausführen:
    
  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Proxykonfiguration

Wenn Zertifikatauthentifizierung für Business-Webdienste für Skype deaktiviert ist, wird die Skype für Business-Client eine weniger bevorzugten Authentifizierungstyp wie Kerberos oder NTLM verwenden, um auf den Registrierungsdienst authentifizieren. Die Zertifikatauthentifizierung ist nach wie vor erforderlich, um dem Client das Abrufen eines Webtickets zu ermöglichen, jedoch müssen Kerberos und NTLM für den Registrierungsstellendienst deaktiviert werden.
  
In den folgenden Schritten wird die Erstellung einer angepassten Proxykonfiguration für Edge Pools, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.
  
### <a name="to-create-a-custom-proxy-configuration"></a>So erstellen Sie eine benutzerdefinierte Proxykonfiguration

1. Erstellen Sie aus der Skype für Business Server-Verwaltungsshell Command-Line eine neue Proxykonfiguration für jede Skype für Edge-Serverpool Business, Enterprise-Pool und Standard Edition-Server, die für passiven Authentifizierung durch Ausführen des folgenden aktiviert werden sollen Befehle:
    
  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Überprüfen Sie, ob alle anderen Proxyauthentifizierungsarten erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    
  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Siehe auch

[Verwalten der zweistufigen Authentifizierung in Skype für Business Server](two-factor-authentication.md)
  
[Verwenden Sie zweistufige Authentifizierung mit Skype für Business Client- und Skype für Business Server](use.md)