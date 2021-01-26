---
title: Bereitstellen von herunterladbaren Webclients in Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Zusammenfassung: Bereitstellen der Skype for Business Web App und der Skype-Besprechungs-App, die mit Skype for Business verwendet wird.'
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805925"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Bereitstellen von herunterladbaren Webclients in Skype for Business Server

**Zusammenfassung:** Bereitstellen der Skype for Business 2015 Web App und der Skype-Besprechungs-App, die mit Skype for Business Server verwendet werden.

Skype for Business Web App ist ein IiS(Internet Information Services)-Webclient, der auf dem Server mit Skype for Business Server installiert ist und standardmäßig bei Bedarf für Besprechungsbenutzer bereitgestellt wird, die noch nicht über den Skype for Business-Client verfügen. Diese Besprechungsbenutzer stellen häufig keine Verbindung von außerhalb Ihres Netzwerks. Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber den Skype for Business-Client nicht installiert hat, wird dem Benutzer die Option angezeigt, mit der neuesten Version von Skype for Business Web App, Skype Meetings App oder Skype for Business für Mac an der Besprechung teilzunehmen.

Die Sprach-, Video- und Freigabefunktionen in Skype for Business Web App erfordern ein Microsoft ActiveX-Steuerelement, das vom Browser des Benutzers als Plug-In verwendet wird. Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder benutzern die Installation gestatten, wenn sie dazu aufgefordert werden. Dies geschieht, wenn sie Skype for Business Web App zum ersten Mal verwenden oder wenn sie zum ersten Mal auf eine Funktion zugreifen, für die das ActiveX ist.

> [!NOTE]
> In Skype for Business Server Edge Server-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk für den Skype for Business Web App-Clientzugriff erforderlich. Sie müssen zudem einfache URLs. Weitere Informationen finden Sie unter [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and DNS requirements for simple [URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Aktivieren der mehrstufigen Authentifizierung für Skype for Business Web App
<a name="MFA"> </a>

Skype for Business Web App, Skype Meetings App und Skype for Business für Mac unterstützen die mehrstufige Authentifizierung. Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder PINs benötigen, um Benutzer zu authentifizieren, die aus externen Netzwerken beitreten, wenn sie sich bei Skype for Business-Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie einen Ad FS (Active Directory Federation Service)-Verbundserver bereitstellen und die passive Authentifizierung in Skype for Business Server aktivieren. Nachdem AD FS konfiguriert wurde, wird externen Benutzern, die versuchen, an Skype for Business-Besprechungen teilzunehmen, eine AD FS-Webseite mit mehrstufiger Authentifizierung angezeigt, die den Benutzernamen und die Kennwortforderung zusammen mit allen zusätzlichen Authentifizierungsmethoden enthält, die Sie konfiguriert haben.

> [!IMPORTANT]
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren

- Die mehrstufige ADFS-Authentifizierung funktioniert, wenn sich der Besprechungsteilnehmer und der Organisator in derselben Organisation befinden oder beide aus einer AD FS-Verbundorganisation kommen. Die mehrstufige ADFS-Authentifizierung funktioniert für Lync-Verbundbenutzer nicht, da sie von der Lync Server-Webinfrastruktur derzeit nicht unterstützt wird.

- Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, aktivieren Sie die Cookiepersistenz auf den Lastenausgleichskomponenten, damit alle Anforderungen von den Skype for Business Web App- oder Besprechungs-App-Clients vom gleichen Front-End-Server verarbeitet werden.

- Wenn Sie eine Vertrauensstellung einer vertrauenden Partei zwischen Skype for Business Server und AD FS-Servern einrichten, weisen Sie eine Tokenlebensdauer zu, die lang genug ist, um die maximale Dauer Ihrer Skype for Business-Besprechungen zu umfassen. Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.

- Diese Konfiguration gilt nicht für mobile Lync-Clients.

### <a name="configure-multi-factor-authentication"></a>Konfigurieren der mehrstufigen Authentifizierung

1. Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle. Weitere Informationen finden Sie im Bereitstellungshandbuch für [Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Erstellen Sie Zertifikate für AD FS. Weitere Informationen finden Sie im Abschnitt ["Verbundserverzertifikate"](https://go.microsoft.com/fwlink/p/?LinkId=285376) des Themas "Planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden".

3. Führen Sie an Windows PowerShell Befehlszeilenschnittstelle den folgenden Befehl aus:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Deaktivieren von BranchCache
<a name="MFA"> </a>

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann zu Interferenz mit Skype for Business Web App-Webkomponenten führen. Um Probleme für Skype for Business Web App-Benutzer zu verhindern, stellen Sie sicher, dass BranchCache nicht aktiviert ist.

Weitere Informationen zum Deaktivieren von BranchCache finden Sie im [BranchCache-Bereitstellungshandbuch.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Überprüfen der Skype for Business Web App-Bereitstellung
<a name="MFA"> </a>

Sie können das Cmdlet "Test-CsUcwaConference" verwenden, um sicherzustellen, dass ein Paar von Testbenutzern in einer Konferenz unter Verwendung der Unified Communications-Web-API (UCWA) teilnehmen können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter ["Test-CsUcwaConference"](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Problembehandlung bei der Plug-In-Installation auf Windows Server 2008 R2
<a name="MFA"> </a>

Wenn die Installation des Plug-ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Sicherheitseinstellung von Internet Explorer oder die Einstellung für den Registrierungsschlüssel "DisableMSI" ändern.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Ändern der Sicherheitseinstellung in Internet Explorer

1. Öffnen Sie Internet Explorer.

2. Klicken Sie auf **Extras**, dann auf **Internetoptionen** und anschließend auf **Erweitert**.

3. Führen Sie einen Bildlauf zum Bereich **Sicherheit** durch.

4. Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Wenn diese Einstellung ausgewählt ist, verursacht sie auch einen Fehler beim Versuch, eine Anlage von Skype for Business Web App herunterzuladen.

5. Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

### <a name="modify-the-disablemsi-registry-setting"></a>Ändern der Registrierungseinstellung "DisableMSI"

1. Klicken Sie auf **Start** und dann auf **Ausführen**.

2. Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3. Navigieren Sie zu "HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer".

4. Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG_DWORD hinzu, und legen Sie ihn auf "0" fest.

5. Nehmen Sie an der Besprechung erneut teil.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Aktivieren der Skype-Besprechungs-App zum Ersetzen von Skype for Business Web App (optional, nur Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Dieses Verfahren ist optional und gilt für Skype for Business Server 2015 CU5 und höher. Wenn Sie es nicht verwenden, nehmen externe Benutzer weiterhin mit Skype for Business Web App an Besprechungen teil.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Aktivieren der vereinfachten Besprechungsbesprechung und der Skype-Besprechungs-App

1. Wenn Sie den Zugriff auf das Content Delivery Network (CDN) aktivieren, können Benutzer online eine Verbindung mit CDN herstellen und die Skype-Besprechungs-App (unter Windows) und Skype for Business für Mac (für Mac) erhalten und die vereinfachte Besprechungsteilnahme verwenden.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Zulassen, dass die Telemetrie der clientseitigen Protokollierung von der Webseite für den Besprechungs beitritt oder von der Skype-Besprechungs-App an die Server von Microsoft gesendet wird (der Befehl ist standardmäßig auf "false" festgelegt).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    An Microsoft gesendete Informationen sind streng mit den Methoden der [Skype for Business-Datensammlungspraktiken in Einklang.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Legen Sie das Timeout vor dem Fall back to the locally hosted Skype for Business Web App experience if CDN isn't available. Der Standardwert beträgt 6 Sekunden. Wenn dieser Wert auf 0 festgelegt ist, gibt es kein Timeout.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Bei MeetingUxUseCdn im kumulativen Update 5 für Skype for Business Server 2015 ist der Standardwert auf "False" festgelegt. Dies führt zu einem Problem, bei dem der Skype for Business für -Mac-Client nicht als Gast an Besprechungen von Nicht-Verbundpartnern teilnehmen kann, auch wenn der Skype for Business-Administrator "MeetingUxUseCdn" auf "True" festgelegt hat. Damit dies funktioniert, muss Skype for Business Server 2015 über das kumulative Update 7, 6.0.9319.534 oder höher verfügen. Siehe ["Skype-Besprechungs-App aktivieren", um Skype for Business Web App in Skype for Business Server 2015 zu ersetzen.](https://support.microsoft.com/kb/4132312)


## <a name="see-also"></a>Siehe auch
<a name="SMA_Enable"> </a>

[Planen von Besprechungsclients (Web App und Besprechungs-App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Konfigurieren der Seite für den Besprechungs beitritt in Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Datenschutzerklärung von Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Lizenzierungsbedingungen und Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
