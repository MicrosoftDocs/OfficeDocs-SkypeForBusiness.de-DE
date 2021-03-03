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
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814415"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server

**Zusammenfassung:** Konfigurieren sie die zweistufige Authentifizierung in Skype for Business Server.

In den folgenden Abschnitten werden die Schritte beschrieben, die zum Konfigurieren der zweistufigen Authentifizierung für Ihre Bereitstellung erforderlich sind. Weitere Informationen zur zweistufigen Authentifizierung finden Sie unter Aktivieren der [mehrstufigen Office 365-Authentifizierung für Onlineadministratoren - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Konfigurieren einer Stammzertifizierungsstelle des Unternehmens zur Unterstützung der Smartcardauthentifizierung

In den folgenden Schritten wird beschrieben, wie Sie eine Unternehmensstammzertifizierungsstelle für die Unterstützung der Smartcardauthentifizierung konfigurieren:

Informationen zum Installieren einer Stammzertifizierungsstelle des Unternehmens finden Sie unter [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).

1. Melden Sie sich mit einem Domänenadministratorkonto am Computer der Unternehmens-Zertifizierungsstelle an.

2. Starten Sie System Manager, und stellen Sie sicher, dass die Rolle "Webregistrierung der Zertifizierungsstelle" installiert ist.

3. Öffnen Sie **im Menü "Verwaltung"** die **Verwaltungskonsole der** Zertifizierungsstelle.

4. Erweitern Sie im Navigationsbereich die **Zertifizierungsstelle**.

5. Klicken Sie mit der **rechten Maustaste auf Zertifikatvorlagen,** wählen **Sie "Neu"** und dann **"Zertifikatvorlage aus, die ausgestellt werden soll".**

6. Wählen **Sie Registrierungs-Agent,** **Smartcardbenutzer** und **Smartcardanmeldung aus.**

7. Klicken Sie auf **OK**.

8. Klicken Sie mit der rechten **Maustaste auf Zertifikatvorlagen.**

9. Wählen Sie **"Verwalten"** aus.

10. Öffnen Sie die Eigenschaften der Smartcard-Benutzervorlage.

11. Klicken Sie auf die **Registerkarte "Sicherheit".**

12. Ändern Sie die Berechtigungen wie folgt:

    - Fügen Sie einzelne Benutzer-AD-Konten mit Lese-/Registrierungsberechtigungen (Zulassen) hinzu, oder

    - Fügen Sie eine Sicherheitsgruppe hinzu, die Smartcardbenutzer mit Lese-/Registrierungsberechtigungen (Zulassen) enthält, oder

    - Hinzufügen der Gruppe "Domänenbenutzer" mit Lese-/Registrierungsberechtigungen (Zulassen)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Konfigurieren Windows 8 virtueller Smartcards

Ein faktor, der bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcardtechnologie zu berücksichtigen ist, sind die Kosten der Implementierung. Windows 8 bietet eine Reihe neuer Sicherheitsfunktionen, und eines der interessantesten neuen Features ist die Unterstützung virtueller Smartcards.

Für Computer mit einem Trusted Platform Module (TPM)-Chip, der der Spezifikationsversion 1.2 entspricht, können Organisationen jetzt die Vorteile der Smartcardanmeldung nutzen, ohne zusätzliche Investitionen in die Hardware zu tätigen. Weitere Informationen finden Sie unter [Verwenden virtueller Smartcards mit Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>So konfigurieren Windows 8 virtuelle Smartcards

1. Melden Sie sich am Windows 8 mit den Anmeldeinformationen eines Skype for Business-aktivierten Benutzers an.

2. Bewegen Sie Windows 8 bildschirmanfangsbildschirms den Cursor in die untere rechte Ecke des Bildschirms.

3. Wählen Sie **die Option "Suchen"** aus, und suchen Sie dann nach "Eingabeaufforderung".

4. Klicken Sie mit der **rechten Maustaste auf die** Eingabeaufforderung, und wählen Sie dann **"Als Administrator ausführen" aus.**

5. Öffnen Sie die TPM (Trusted Platform Module)-Verwaltungskonsole, indem Sie den folgenden Befehl ausführen:

  ```console
  Tpm.msc
  ```

6. Überprüfen Sie in der TPM-Verwaltungskonsole, ob die Version der TPM-Spezifikation mindestens 1.2 ist.

    > [!NOTE]
    > Wenn ein Dialogfeld mit der Meldung angezeigt wird, dass ein kompatibles TPM (Trust Platform Module) nicht gefunden werden kann, stellen Sie sicher, dass der Computer über ein kompatibles TPM-Modul verfügt und im System-BIOS aktiviert ist.

7. Schließen der TPM-Verwaltungskonsole

8. Erstellen Sie an der Eingabeaufforderung mithilfe des folgenden Befehls eine neue virtuelle Smartcard:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert bereitstellen möchten, verwenden Sie stattdessen die /pin-Eingabeaufforderung.

9. Öffnen Sie an der Eingabeaufforderung die Computerverwaltungskonsole, indem Sie den folgenden Befehl ausführen:

  ```console
  CompMgmt.msc
  ```

10. Wählen Sie in der Computerverwaltungskonsole **"Geräteverwaltung" aus.**

11. Erweitern **Sie Smartcardleser**.

12. Stellen Sie sicher, dass der neue virtuelle Smartcardleser erfolgreich erstellt wurde.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrieren von Benutzern für die Smartcardauthentifizierung

Im Allgemeinen gibt es zwei Methoden zum Registrieren von Benutzern für die Smartcardauthentifizierung. Die einfachere Methode umfasst die direkte Registrierung von Benutzern für die Smartcardauthentifizierung mithilfe der Webregistrierung, während die komplexere Methode die Verwendung eines Registrierungs-Agents umfasst. In diesem Thema liegt der Schwerpunkt auf der Selbstregistrierung für Smartcardzertifikate.

Weitere Informationen zur Registrierung im Namen von Benutzern als Registrierungs-Agent finden Sie unter "Registrieren für Zertifikate im [Auftrag anderer Benutzer".](https://go.microsoft.com/fwlink/p/?LinkID=313367)

### <a name="to-enroll-users-for-smart-card-authentication"></a>So registrieren Sie Benutzer für die Smartcardauthentifizierung

1. Melden Sie sich mit Windows 8 eines Skype for Business-aktivierten Benutzers an der Windows 8 an.

2. Starten Sie Internet Explorer.

3. Navigieren Sie zur **Seite "Zertifizierungsstelle-Webregistrierung"** (z. B. https://MyCA.contoso.com/certsrv) .

    > [!NOTE]
    > Wenn Sie eine Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.

4. Wählen Sie **auf der Willkommensseite** **"Zertifikat anfordern" aus.**

5. Wählen Sie als Nächstes **"Erweiterte Anforderung" aus.**

6. Wählen **Sie "Erstellen" aus, und senden Sie eine Anforderung an diese Zertifizierungsstelle.**

7. Wählen Sie im Abschnitt **"Zertifikatvorlage"** die Option **"Smartcardbenutzer"** aus, und schließen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten ab:

  - **Die wichtigsten Optionen** bestätigen die folgenden Einstellungen:

    - Wählen Sie das **Optionsfeld "Neuen Schlüsselsatz** erstellen" aus.

    - Wählen **Sie für CSP** **den Microsoft Base Smart Card Crypto Provider aus.**

    - Wählen **Sie für** die Schlüsselverwendung **Exchange** aus (dies ist die einzige verfügbare Option).

    - Geben **Sie für die Schlüsselgröße** 2048 ein.

    - Bestätigen, **dass der Name des automatischen Schlüsselcontainers** ausgewählt ist

    - Lassen Sie die anderen Kontrollkästchen deaktiviert.

  - Bestätigen **Sie unter "Zusätzliche Optionen"** die folgenden Werte:

    - Wählen **Sie für das Anforderungsformat** **CMC aus.**

    - For **Hash Algorithm** select **sha1**.

    - Geben **Sie für den Anzeigenamen** das Zertifikat "Smardcard" ein.

8. Wenn Sie einen physischen Smartcardleser verwenden, fügen Sie die Smartcard in das Gerät ein.

9. Klicken Sie **auf "Absenden",** um die Zertifikatanforderung zu übermitteln.

10. Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen Smartcard verwendet wurde.

    > [!NOTE]
    > Der standardmäßige virtuelle Smartcard-PIN-Wert ist "12345678".

11. Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **"Dieses Zertifikat installieren",** um den Registrierungsprozess abzuschließen.

    > [!NOTE]
    >  Wenn die Zertifikatanforderung mit der Fehlermeldung "Dieser Webbrowser unterstützt die Generierung von Zertifikatsanforderungen nicht" fehlschlägt, gibt es drei Möglichkeiten, das Problem zu beheben:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Konfigurieren von Active Directory Federation Services (AD FS 2.0)

Im folgenden Abschnitt wird beschrieben, wie Sie Active Directory Federation Services (AD FS 2.0) für die Unterstützung der mehrstufigen Authentifizierung konfigurieren. Informationen zum Installieren von AD FS 2.0 finden Sie unter [AD FS 2.0 Schritt-für-Schritt- und Anleitungen.](https://go.microsoft.com/fwlink/p/?LinkId=313374)

> [!NOTE]
> Verwenden Sie bei der Installation von AD FS 2.0 nicht den Windows Server Manager, um die Rolle "Active Directory-Verbunddienste" hinzuzufügen. Laden Sie stattdessen das [Active Directory Federation Services 2.0 -RTW-Paket herunter,](https://go.microsoft.com/fwlink/p/?LinkId=313375)und installieren Sie es.

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>So konfigurieren Sie AD FS für die zweistufige Authentifizierung

1. Melden Sie sich mit einem Domänenadministratorkonto am AD FS 2.0-Computer an.

2. Starten Sie Windows PowerShell.

3. Führen Sie an Windows PowerShell Befehlszeile den folgenden Befehl aus:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Richten Sie eine Partnerschaft mit jedem Server ein, der für die passive Authentifizierung aktiviert wird, indem Sie den folgenden Befehl ausführen und dabei den für Ihre Bereitstellung spezifischen Servernamen ersetzen:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Starten Sie im Menü "Verwaltung" die AD FS 2.0-Verwaltungskonsole.

6. Erweitern **Von Vertrauensstellungen**  >  **vertrauende Parteienvertrauensstellungen**.

7. Stellen Sie sicher, dass eine neue Vertrauensstellung für Ihren Skype for Business Server erstellt wurde.

8. Erstellen und weisen Sie eine Ausstellungsautorisierungsregel für Ihre Vertrauensstellung der vertrauenden Windows PowerShell, indem Sie die folgenden Befehle ausführen:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Erstellen und zuweisen Sie eine Ausstellungstransformationsregel für die Vertrauensstellung der vertrauenden Windows PowerShell, indem Sie die folgenden Befehle ausführen:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf die Vertrauensstellung Ihrer vertrauenden Seite, und wählen Sie **"Anspruchsregeln bearbeiten" aus.**

11. Wählen Sie die **Registerkarte "Ausstellungsautorisierungsregeln"** aus, und überprüfen Sie, ob die neue Autorisierungsregel erfolgreich erstellt wurde.

12. Wählen Sie die **Registerkarte Ausstellungstransformationsregeln** aus, und stellen Sie sicher, dass die neue Transformationsregel erfolgreich erstellt wurde.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Konfigurieren von AD FS 2.0 zur Unterstützung der Clientauthentifizierung

Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 die Authentifizierung mithilfe von Smartcards unterstützt:

- Formularbasierte Authentifizierung (FBA)

- Transport Layer Security Client Authentication

Mithilfe der formularbasierten Authentifizierung können Sie eine Webseite entwickeln, auf der Benutzer sich entweder mithilfe ihres Benutzernamens/Kennworts oder mithilfe ihrer Smartcard und PIN authentifizieren können. Dieser Schwerpunkt liegt auf der Implementierung der Transport Layer Security-Clientauthentifizierung mit AD FS 2.0. Weitere Informationen zu AD FS 2.0-Authentifizierungstypen finden Sie unter [AD FS 2.0: Ändern des lokalen Authentifizierungstyps.](https://go.microsoft.com/fwlink/p/?LinkId=313384)

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>So konfigurieren Sie AD FS 2.0 zur Unterstützung der Clientauthentifizierung

1. Melden Sie sich mit einem Domänenadministratorkonto am AD FS 2.0-Computer an.

2. Starten Sie Windows Explorer.

3. Navigieren Sie zu "C:\inetpub\adfs\ls"

4. Erstellen Sie eine Sicherungskopie der vorhandenen web.config Datei.

5. Öffnen Sie die vorhandene web.config mit Editor.

6. Wählen Sie in der Menüleiste **"Bearbeiten"** und dann **"Suchen" aus.**

7. Suchen Sie nach \<localAuthenticationTypes\> .

    Beachten Sie, dass vier Authentifizierungstypen aufgelistet sind, einer pro Zeile.

8. Verschieben Sie die Zeile mit dem Authentifizierungstyp "TLSClient" an den oberen Rand der Liste im Abschnitt.

9. Speichern und schließen Sie die web.config Datei.

10. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.

11. Starten Sie IIS neu, indem Sie den folgenden Befehl ausführen:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Konfigurieren der passiven Authentifizierung für Skype for Business Server

Im folgenden Abschnitt wird beschrieben, wie Sie Skype for Business Server für die Unterstützung der passiven Authentifizierung konfigurieren. Nach der Aktivierung müssen Benutzer, die für die zweistufige Authentifizierung aktiviert sind, eine physische oder virtuelle Smartcard und eine gültige PIN für die Anmeldung mit dem Skype for Business-Client verwenden.

> [!NOTE]
> Es wird dringend empfohlen, dass Kunden die passive Authentifizierung für Registrierungsstellen und Webdienste auf Dienstebene aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf globaler Ebene aktiviert ist, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit dem unterstützten Desktopclient anmelden.

### <a name="web-service-configuration"></a>Webdienstkonfiguration

In den folgenden Schritten wird beschrieben, wie Sie eine benutzerdefinierte Webdienstkonfiguration für Directors, Enterprise Pools und Standard Edition-Server erstellen, die für die passive Authentifizierung aktiviert werden.

### <a name="to-create-a-custom-web-service-configuration"></a>So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration

1. Melden Sie sich mit einem Skype for Business-Administratorkonto bei Ihrem Skype for Business Server-Front-End-Server an.

2. Starten Sie die Skype for Business Server-Verwaltungsshell.

3. Erstellen Sie über die Befehlszeile der Skype for Business Server-Verwaltungsshell eine neue Webdienstkonfiguration für jeden Director-, Enterprise-Pool- und Standard Edition-Server, der für die passive Authentifizierung aktiviert wird, indem Sie den folgenden Befehl ausführen:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > Der Wert für den WsFedPassiveMetadataUri-FQDN ist der Verbunddienstname Ihres AD FS 2.0-Servers. Der Wert des Verbunddienstnamens befindet sich in der AD FS 2.0-Verwaltungskonsole, indem Sie im Navigationsbereich mit der rechten Maustaste auf "Dienst" klicken und dann "Verbunddiensteigenschaften bearbeiten" **auswählen.** 

4. Stellen Sie sicher, dass die Werte "UseWsFedPassiveAuth" und "WsFedPassiveMetadataUri" richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Für Clients ist die passive Authentifizierung die am wenigsten bevorzugte Authentifizierungsmethode für die Webticketauthentifizierung. Für alle Directors, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, müssen alle anderen Authentifizierungstypen in Skype for Business Web Services durch Ausführen des folgenden Cmdlets deaktiviert werden:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Stellen Sie sicher, dass alle anderen Authentifizierungstypen erfolgreich deaktiviert wurden, indem Sie das folgende Cmdlet ausführen:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Proxykonfiguration

Wenn die Zertifikatauthentifizierung für Skype for Business Web Services deaktiviert ist, verwendet der Skype for Business-Client für die Authentifizierung beim Registrierungsdienst einen weniger bevorzugten Authentifizierungstyp, z. B. Kerberos oder NTLM. Die Zertifikatauthentifizierung ist weiterhin erforderlich, damit der Client ein Webticket abrufen kann. Kerberos und NTLM müssen jedoch für den Registrierungsdienst deaktiviert sein.

In den folgenden Schritten wird beschrieben, wie Sie eine benutzerdefinierte Proxykonfiguration für Edgepools, Unternehmenspools und Standard Edition-Server erstellen, die für die passive Authentifizierung aktiviert werden.

### <a name="to-create-a-custom-proxy-configuration"></a>So erstellen Sie eine benutzerdefinierte Proxykonfiguration

1. Erstellen Sie über die Befehlszeile der Skype for Business Server-Verwaltungsshell eine neue Proxykonfiguration für jeden Skype for Business Server-Edgepool, Unternehmenspool und Standard Edition-Server, der für die passive Authentifizierung aktiviert wird, indem Sie die folgenden Befehle ausführen:

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

## <a name="see-also"></a>Siehe auch

[Verwalten der zweistufigen Authentifizierung in Skype for Business Server](two-factor-authentication.md)

[Verwenden der zweistufigen Authentifizierung mit dem Skype for Business-Client und Skype for Business Server](use-two-factor.md)
