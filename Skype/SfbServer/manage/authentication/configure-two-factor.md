---
title: Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Zusammenfassung: Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server.'
ms.openlocfilehash: 128ae4fcc1a9e7cd9817e73539b1bf1290883a1d
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234640"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server

**Zusammenfassung:** Konfigurieren Sie die zweistufige Authentifizierung in Skype for Business Server.

In den folgenden Abschnitten werden die Schritte beschrieben, die zum Konfigurieren der zweistufigen Authentifizierung für Ihre Bereitstellung erforderlich sind. Weitere Informationen zur zweistufigen Authentifizierung finden Sie unter [Aktivieren Office 365 mehrstufiger Authentifizierung für Onlineadministratoren – Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Konfigurieren einer Enterprise Stammzertifizierungsstelle zur Unterstützung der Smartcardauthentifizierung

In den folgenden Schritten wird beschrieben, wie Sie eine Enterprise Stammzertifizierungsstelle zur Unterstützung der Smartcardauthentifizierung konfigurieren:

Informationen zum Installieren einer Enterprise Stammzertifizierungsstelle finden Sie unter [Installieren einer Enterprise Stammzertifizierungsstelle.](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))

1. Melden Sie sich mit einem Domänenadministratorkonto beim Computer der Enterprise Zertifizierungsstelle an.

2. Starten Sie System-Manager, und stellen Sie sicher, dass die Rolle "Zertifizierungsstelle-Webregistrierung" installiert ist.

3. Öffnen Sie im Menü **"Verwaltungstools"** die Verwaltungskonsole der **Zertifizierungsstelle.**

4. Erweitern Sie im Navigationsbereich die **Zertifizierungsstelle.**

5. Klicken Sie mit der rechten Maustaste auf **"Zertifikatvorlagen",** wählen Sie **"Neu"** und dann **"Zertifikatvorlage ausstellen"** aus.

6. Wählen Sie **"Registrierungs-Agent",** **"Smartcard-Benutzer"** und **"Smartcard-Anmeldung" aus.**

7. Klicken Sie auf **OK**.

8. Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen.**

9. Wählen Sie **"Verwalten" aus.**

10. Öffnen Sie die Eigenschaften der Smartcard-Benutzervorlage.

11. Klicken Sie auf die Registerkarte **"Sicherheit".**

12. Ändern Sie die Berechtigungen wie folgt:

    - Fügen Sie einzelne AD-Benutzerkonten mit Berechtigungen zum Lesen/Registrieren (Zulassen) hinzu, oder

    - Fügen Sie eine Sicherheitsgruppe hinzu, die Smartcardbenutzer mit Berechtigungen zum Lesen/Registrieren (Zulassen) enthält, oder

    - Hinzufügen der Gruppe "Domänenbenutzer" mit Berechtigungen zum Lesen/Registrieren (Zulassen)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Konfigurieren Windows 8 für virtuelle Smartcards

Ein Faktor, der bei der Bereitstellung von zweistufiger Authentifizierung und Smartcardtechnologie berücksichtigt werden muss, sind die Implementierungskosten. Windows 8 bietet eine Reihe neuer Sicherheitsfunktionen, und eines der interessanten neuen Features ist die Unterstützung virtueller Smartcards.

Für Computer, die mit einem TPM-Chip (Trusted Platform Module) ausgestattet sind, der die Spezifikationsversion 1.2 erfüllt, können Organisationen jetzt die Vorteile der Smartcardanmeldung nutzen, ohne zusätzliche Investitionen in Hardware zu tätigen. Weitere Informationen finden Sie unter [Verwenden virtueller Smartcards mit Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>So konfigurieren Sie Windows 8 für virtuelle Smartcards

1. Melden Sie sich mit den Anmeldeinformationen eines Skype for Business aktivierten Benutzers beim Windows 8 Computer an.

2. Bewegen Sie den Cursor am Windows 8 Startbildschirm in die untere rechte Ecke des Bildschirms.

3. Wählen Sie die **Suchoption** aus, und suchen Sie dann nach "Eingabeaufforderung".

4. Klicken Sie mit der rechten Maustaste auf **die Eingabeaufforderung,** und wählen Sie **"Als Administrator ausführen"** aus.

5. Öffnen Sie die Tpm-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:

   ```console
   Tpm.msc
   ```

6. Stellen Sie in der TPM-Verwaltungskonsole sicher, dass die TPM-Spezifikationsversion mindestens 1.2 ist.

    > [!NOTE]
    > Wenn Sie ein Dialogfeld erhalten, das besagt, dass ein kompatibles Trust Platform Module (TPM) nicht gefunden werden kann, stellen Sie sicher, dass der Computer über ein kompatibles TPM-Modul verfügt und im System-BIOS aktiviert ist.

7. Schließen der TPM-Verwaltungskonsole

8. Erstellen Sie an der Eingabeaufforderung mit dem folgenden Befehl eine neue virtuelle Smartcard:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

   > [!NOTE]
   > Um beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert bereitzustellen, verwenden Sie stattdessen die /pin-Eingabeaufforderung.

9. Öffnen Sie an der Eingabeaufforderung die Computerverwaltungskonsole, indem Sie den folgenden Befehl ausführen:

  ```console
  CompMgmt.msc
  ```

10. Wählen Sie in der Computerverwaltungskonsole die Option **"Geräteverwaltung" aus.**

11. Erweitern Sie **Smartcardleser.**

12. Stellen Sie sicher, dass der neue virtuelle Smartcardleser erfolgreich erstellt wurde.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrieren von Benutzern für die Smartcardauthentifizierung

Es gibt im Allgemeinen zwei Methoden zum Registrieren von Benutzern für die Smartcardauthentifizierung. Die einfachere Methode umfasst die direkte Registrierung von Benutzern für die Smartcardauthentifizierung mithilfe der Webregistrierung, während die komplexere Methode die Verwendung eines Registrierungs-Agents umfasst. In diesem Thema geht es um die Selbstregistrierung für Smartcard-Zertifikate.

Weitere Informationen zur Registrierung im Namen von Benutzern als Registrierungs-Agent finden Sie unter ["Registrieren für Zertifikate im Namen anderer Benutzer".](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))

### <a name="to-enroll-users-for-smart-card-authentication"></a>So registrieren Sie Benutzer für die Smartcardauthentifizierung

1. Melden Sie sich mit den Anmeldeinformationen eines Skype for Business aktivierten Benutzers bei der Windows 8 Arbeitsstation an.

2. Starten Sie Internet Explorer.

3. Navigieren Sie zur Registrierungsseite der **Zertifizierungsstelle** (z. B. https://MyCA.contoso.com/certsrv) .

    > [!NOTE]
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.

4. Wählen Sie auf der **Willkommensseite** **"Zertifikat anfordern"** aus.

5. Wählen Sie als Nächstes **"Erweiterte Anforderung"** aus.

6. Wählen Sie **"Erstellen" aus, und senden Sie eine Anforderung an diese Zertifizierungsstelle.**

7. Wählen Sie **"Smartcard-Benutzer"** im Abschnitt **"Zertifikatvorlage"** aus, und schließen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten ab:

  - **Wichtige Optionen** bestätigen, dass er die folgenden Einstellungen verwendet:

    - Wählen Sie das Optionsfeld **"Neuen Schlüsselsatz erstellen"** aus.

    - Wählen Sie **für CSP** **den Kryptoanbieter "Microsoft Base Smart Card" aus.**

    - Wählen Sie für **die Schlüsselverwendung** **Exchange** aus (dies ist die einzige verfügbare Option).

    - Geben Sie für **die Schlüsselgröße** 2048 ein.

    - Vergewissern Sie sich, dass der Name des **automatischen Schlüsselcontainers** ausgewählt ist.

    - Lassen Sie die anderen Kontrollkästchen deaktiviert.

  - Bestätigen Sie unter **"Zusätzliche Optionen"** die folgenden Werte:

    - Wählen Sie für **das Anforderungsformat** **CMC** aus.

    - Wählen Sie für **Hashalgorithmus** **sha1** aus.

    - Geben Sie für **"Anzeigename"** das Zertifikat "Smardcard" ein.

8. Wenn Sie einen physischen Smartcardleser verwenden, fügen Sie die Smartcard in das Gerät ein.

9. Klicken Sie auf **"Absenden",** um die Zertifikatanforderung zu übermitteln.

10. Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen Smartcard verwendet wurde.

    > [!NOTE]
    > Der STANDARDMÄßIGE PIN-Wert für virtuelle Smartcards lautet "12345678".

11. Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **"Dieses Zertifikat installieren",** um den Registrierungsprozess abzuschließen.

    > [!NOTE]
    >  Wenn die Zertifikatanforderung mit dem Fehler "Dieser Webbrowser unterstützt nicht die Generierung von Zertifikatanforderungen" fehlschlägt, gibt es drei möglichkeiten, das Problem zu beheben:
    >- Aktivieren Sie die Kompatibilitätsansicht in Internet Explorer.
    >- Aktivieren Sie die Option "Intraneteinstellungen aktivieren" in Internet Explorer.
    >- Wählen Sie im Menü "Internet Explorer-Optionen" auf der Registerkarte "Sicherheit" die Einstellung "Alle Zonen auf Standardebene zurücksetzen" aus.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Konfigurieren von Active Directory-Verbunddiensten (AD FS 2.0)

Im folgenden Abschnitt wird beschrieben, wie Active Directory-Verbunddienste (AD FS 2.0) zur Unterstützung der mehrstufigen Authentifizierung konfiguriert werden. Informationen zum Installieren von AD FS 2.0 finden Sie unter [AD FS 2.0 Schritt-für-Schritt und Anleitungen.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))

> [!NOTE]
> Verwenden Sie bei der Installation von AD FS 2.0 nicht den Windows Server-Manager, um die Active Directory-Verbunddienste-Rolle hinzuzufügen. Laden Sie stattdessen das [RTW-Paket für Active Directory-Verbunddienste 2.0](https://go.microsoft.com/fwlink/p/?LinkId=313375)herunter, und installieren Sie es.

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>So konfigurieren Sie AD FS für die zweistufige Authentifizierung

1. Melden Sie sich mit einem Domänenadministratorkonto beim AD FS 2.0-Computer an.

2. Starten Sie Windows PowerShell.

3. Führen Sie in der befehlszeile Windows PowerShell den folgenden Befehl aus:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Richten Sie eine Partnerschaft mit jedem Server ein, der für die passive Authentifizierung aktiviert wird, indem Sie den folgenden Befehl ausführen und den serverspezifischen Namen für Ihre Bereitstellung ersetzen:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Starten Sie im Menü "Verwaltungstools" die AD FS 2.0-Verwaltungskonsole.

6. Erweitern Sie **Vertrauensstellungen**  >  **der vertrauenden Seite.**

7. Stellen Sie sicher, dass eine neue Vertrauensstellung für Ihre Skype for Business Server erstellt wurde.

8. Erstellen und zuweisen Sie eine Ausstellungsautorisierungsregel für die Vertrauensstellung der vertrauenden Seite mithilfe Windows PowerShell, indem Sie die folgenden Befehle ausführen:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Erstellen und zuweisen Sie eine Ausstellungstransformationsregel für die Vertrauensstellung der vertrauenden Seite mithilfe Windows PowerShell, indem Sie die folgenden Befehle ausführen:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf die Vertrauensstellung der vertrauenden Seite, und wählen Sie **"Anspruchsregeln bearbeiten"** aus.

11. Wählen Sie die Registerkarte **"Ausstellungsautorisierungsregeln"** aus, und überprüfen Sie, ob die neue Autorisierungsregel erfolgreich erstellt wurde.

12. Wählen Sie die Registerkarte **"Ausstellungstransformationsregeln"** aus, und stellen Sie sicher, dass die neue Transformationsregel erfolgreich erstellt wurde.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Konfigurieren von AD FS 2.0 zur Unterstützung der Clientauthentifizierung

Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 die Authentifizierung mithilfe von Smartcards unterstützt:

- Formularbasierte Authentifizierung (FBA)

- Clientauthentifizierung mit Transport Layer Security

Mithilfe der formularbasierten Authentifizierung können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mit ihrem Benutzernamen/Kennwort oder mithilfe ihrer Smartcard und PIN zu authentifizieren. In diesem Thema geht es um die Implementierung der Clientauthentifizierung mit Transport Layer Security mit AD FS 2.0. Weitere Informationen zu AD FS 2.0-Authentifizierungstypen finden Sie unter [AD FS 2.0: So ändern Sie den lokalen Authentifizierungstyp.](https://go.microsoft.com/fwlink/p/?LinkId=313384)

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>So konfigurieren Sie AD FS 2.0 zur Unterstützung der Clientauthentifizierung

1. Melden Sie sich mit einem Domänenadministratorkonto beim AD FS 2.0-Computer an.

2. Starten Sie Windows Explorer.

3. Navigieren Sie zu "C:\inetpub\adfs\ls"

4. Erstellen Sie eine Sicherungskopie der vorhandenen web.config Datei.

5. Öffnen Sie die vorhandene web.config-Datei mit Editor.

6. Wählen Sie in der Menüleiste **"Bearbeiten"** und dann **"Suchen"** aus.

7. Suchen nach \<localAuthenticationTypes\>.

    Beachten Sie, dass vier Authentifizierungstypen aufgelistet sind, eine pro Zeile.

8. Verschieben Sie die Zeile, die den TLSClient-Authentifizierungstyp enthält, an den Anfang der Liste im Abschnitt.

9. Speichern und schließen Sie die web.config Datei.

10. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.

11. Starten Sie IIS neu, indem Sie den folgenden Befehl ausführen:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Konfigurieren Skype for Business Server passiven Authentifizierung

Im folgenden Abschnitt wird beschrieben, wie sie Skype for Business Server konfigurieren, um die passive Authentifizierung zu unterstützen. Nach der Aktivierung müssen Benutzer, die für die zweistufige Authentifizierung aktiviert sind, eine physische oder virtuelle Smartcard und eine gültige PIN verwenden, um sich mit dem Skype for Business Client anzumelden.

> [!NOTE]
> Es wird dringend empfohlen, dass Kunden die passive Authentifizierung für Registrierungsstellen und Webdienste auf Dienstebene aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf globaler Ebene aktiviert ist, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit dem unterstützten Desktopclient anmelden.

### <a name="web-service-configuration"></a>Webdienstkonfiguration

In den folgenden Schritten wird beschrieben, wie Sie eine benutzerdefinierte Webdienstkonfiguration für Directors, Enterprise Pools und Standard Edition Server erstellen, die für die passive Authentifizierung aktiviert werden.

### <a name="to-create-a-custom-web-service-configuration"></a>So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration

1. Melden Sie sich mit einem Skype for Business Administratorkonto bei Ihrem Skype for Business Server Front-End-Server an.

2. Starten Sie die Skype for Business Server-Verwaltungsshell.

3. Erstellen Sie in der Befehlszeile der Skype for Business Server Verwaltungsshell eine neue Webdienstkonfiguration für jeden Director, Enterprise Pool und Standard Edition Server, der für die passive Authentifizierung aktiviert wird, indem Sie den folgenden Befehl ausführen:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > Der Wert für den WsFedPassiveMetadataUri-FQDN ist der Verbunddienstname Ihres AD FS 2.0-Servers. Der Wert des Verbunddienstnamens finden Sie in der AD FS 2.0-Verwaltungskonsole, indem Sie im Navigationsbereich mit der rechten Maustaste auf **"Dienst"** klicken und dann **"Verbunddiensteigenschaften bearbeiten"** auswählen.

4. Stellen Sie sicher, dass die Werte "UseWsFedPassiveAuth" und "WsFedPassiveMetadataUri" richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Für Clients ist die passive Authentifizierung die am wenigsten bevorzugte Authentifizierungsmethode für die Webticket-Authentifizierung. Für alle Directors-, Enterprise pools und Standard Edition Server, die für die passive Authentifizierung aktiviert werden, müssen alle anderen Authentifizierungstypen in Skype for Business Webdiensten deaktiviert werden, indem Sie das folgende Cmdlet ausführen:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Stellen Sie sicher, dass alle anderen Authentifizierungstypen erfolgreich deaktiviert wurden, indem Sie das folgende Cmdlet ausführen:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Proxykonfiguration

Wenn die Zertifikatauthentifizierung für Skype for Business Webdienste deaktiviert ist, verwendet der Skype for Business-Client einen weniger bevorzugten Authentifizierungstyp wie Kerberos oder NTLM, um sich beim Registrierungsstellendienst zu authentifizieren. Die Zertifikatauthentifizierung ist weiterhin erforderlich, damit der Client ein Webticket abrufen kann. Kerberos und NTLM müssen jedoch für den Registrierungsstellendienst deaktiviert sein.

In den folgenden Schritten wird beschrieben, wie Sie eine benutzerdefinierte Proxykonfiguration für Edgepools, Enterprise Pools und Standard Edition Server erstellen, die für die passive Authentifizierung aktiviert werden.

### <a name="to-create-a-custom-proxy-configuration"></a>So erstellen Sie eine benutzerdefinierte Proxykonfiguration

1. Erstellen Sie über die Befehlszeile der Skype for Business Server Verwaltungsshell eine neue Proxykonfiguration für jeden Skype for Business Server Edgepool, Enterprise Pool und Standard Edition Server, der für die passive Authentifizierung aktiviert wird, indem Sie die folgenden Befehle ausführen:

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Stellen Sie sicher, dass alle anderen Proxyauthentifizierungstypen erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Weitere Artikel

[Verwalten der zweistufigen Authentifizierung in Skype for Business Server](two-factor-authentication.md)

[Verwenden der zweistufigen Authentifizierung mit Skype for Business Client und Skype for Business Server](use-two-factor.md)
