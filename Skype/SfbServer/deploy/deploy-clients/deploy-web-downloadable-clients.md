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
description: 'Zusammenfassung: Stellen Sie die Skype for Business Web App und die Skype -Besprechungs-App zur Verfügung, die mit Skype for Business verwendet wird.'
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122129"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Bereitstellen von herunterladbaren Webclients in Skype for Business Server

**Zusammenfassung:** Stellen Sie die Skype for Business 2015-Web-App und die Skype-Besprechungs-App zur Verfügung, die mit Skype for Business Server verwendet wird.

Skype for Business Web App ist ein INTERNET Information Services (IIS)-Webclient, der auf dem Server mit Skype for Business Server installiert ist und standardmäßig bei Bedarf für Besprechungsbenutzer bereitgestellt wird, die noch nicht über den Skype for Business-Client verfügen. Diese Besprechungsbenutzer stellen häufig keine Verbindung von außerhalb Ihres Netzwerks ein. Wenn ein Benutzer auf eine Besprechungs-URL klickt, der Skype for Business-Client jedoch nicht installiert ist, wird dem Benutzer die Möglichkeit angezeigt, der Besprechung mit der neuesten Version von Skype for Business Web App, Skype Meetings App oder Skype for Business für Mac bei der Besprechung teilzunehmen.

Die Sprach-, Video- und Freigabefunktionen in Skype for Business Web App erfordern ein Microsoft ActiveX-Steuerelement, das vom Browser des Benutzers als Plug-In verwendet wird. Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder Benutzern die Installation ermöglichen, wenn sie dazu aufgefordert werden. Dies geschieht, wenn sie Skype for Business Web App zum ersten Mal verwenden oder wenn sie zum ersten Mal auf ein Feature zugreifen, das das ActiveX erfordert.

> [!NOTE]
> In Skype for Business Server Edge Server-Bereitstellungen ist für den Skype for Business Web App-Clientzugriff ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich. Sie müssen zudem einfache URLs. Weitere Informationen finden Sie unter [Einrichten von Reverseproxyservern](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) und [DNS-Anforderungen für einfache URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Aktivieren der mehrstufigen Authentifizierung für Skype for Business Web App
<a name="MFA"> </a>

Skype for Business Web App, Skype Meetings App und Skype for Business für Mac unterstützen die mehrstufige Authentifizierung. Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder PINs benötigen, um Benutzer zu authentifizieren, die aus externen Netzwerken beitreten, wenn sie sich bei Skype for Business-Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Ad FS-Verbundserver (Active Directory Federation Service) bereitstellen und die passive Authentifizierung in Skype for Business Server aktivieren. Nach der Konfiguration von AD FS wird externen Benutzern, die versuchen, an Skype for Business-Besprechungen teilzunehmen, eine ad FS-mehrstufige Authentifizierungswebseite angezeigt, die den Benutzernamen und die Kennwortforderung sowie alle zusätzlichen Authentifizierungsmethoden enthält, die Sie konfiguriert haben.

> [!IMPORTANT]
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren

- Die mehrstufige ADFS-Authentifizierung funktioniert, wenn sich der Besprechungsteilnehmer und der Organisator in derselben Organisation befinden oder beide aus einer AD FS-Verbundorganisation kommen. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für Lync-Verbundbenutzer, da die Lync Server-Webinfrastruktur sie derzeit nicht unterstützt.

- Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, aktivieren Sie die Cookiepersistenz für die Lastenausgleichsgeräte, sodass alle Anforderungen von Skype for Business Web App- oder Besprechungs-App-Clients vom gleichen Front-End-Server verarbeitet werden.

- Wenn Sie eine Vertrauen vertrauende Partei zwischen Skype for Business Server und AD FS-Servern einrichten, weisen Sie eine Tokenlebensdauer zu, die lang genug ist, um die maximale Dauer Ihrer Skype for Business-Besprechungen zu umfassen. Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.

- Diese Konfiguration gilt nicht für mobile Lync-Clients.

### <a name="configure-multi-factor-authentication"></a>Konfigurieren der mehrstufigen Authentifizierung

1. Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle. Weitere Informationen finden Sie im Bereitstellungshandbuch für [Active Directory Federation Services 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. Erstellen sie Zertifikate für AD FS. Weitere Informationen finden Sie im Abschnitt ["Verbundserverzertifikate"](/previous-versions/azure/azure-services/jj205462(v=azure.100)) im Thema Plan for and deploy AD FS for use with single sign-on.

3. Führen Sie auf Windows PowerShell Befehlszeilenschnittstelle den folgenden Befehl aus:

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

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann die Skype for Business Web App-Webkomponenten beeinträchtigen. Stellen Sie sicher, dass BranchCache nicht aktiviert ist, um Probleme für Skype for Business Web App-Benutzer zu verhindern.

Weitere Informationen zum Deaktivieren von BranchCache finden Sie im [BranchCache-Bereitstellungshandbuch](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Überprüfen der Skype for Business Web App-Bereitstellung
<a name="MFA"> </a>

Sie können das Cmdlet "Test-CsUcwaConference" verwenden, um sicherzustellen, dass ein Paar von Testbenutzern in einer Konferenz unter Verwendung der Unified Communications-Web-API (UCWA) teilnehmen können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) in der Dokumentation zur Skype for Business Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Problembehandlung bei der Plug-In-Installation auf Windows Server 2008 R2
<a name="MFA"> </a>

Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Internet Explorer-Sicherheitseinstellung oder die DisableMSI-Registrierungsschlüsseleinstellung ändern.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Ändern der Sicherheitseinstellung in Internet Explorer

1. Öffnen Sie Internet Explorer.

2. Klicken Sie auf **Extras**, dann auf **Internetoptionen** und anschließend auf **Erweitert**.

3. Führen Sie einen Bildlauf zum Bereich **Sicherheit** durch.

4. Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Wenn diese Einstellung ausgewählt ist, wird auch beim Versuch, eine Anlage aus Skype for Business Web App herunterzuladen, ein Fehler verursacht.

5. Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

### <a name="modify-the-disablemsi-registry-setting"></a>Ändern der DisableMSI-Registrierungseinstellung

1. Klicken Sie auf **Start** und dann auf **Ausführen**.

2. Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3. Navigieren Sie zu "HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer".

4. Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG_DWORD hinzu, und legen Sie ihn auf "0" fest.

5. Nehmen Sie an der Besprechung erneut teil.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Aktivieren der Skype -Besprechungs-App zum Ersetzen von Skype for Business Web App (optional, nur Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Dieses Verfahren ist optional und gilt für Skype for Business Server 2015 CU5 und höher. Wenn Sie es nicht verwenden, nehmen externe Benutzer weiterhin mit Skype for Business Web App an Besprechungen teil.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Aktivieren der vereinfachten Besprechungsbesprechung und der Skype-Besprechungs-App

1. Wenn Sie den Zugriff auf das Inhaltszustellungsnetzwerk (Content Delivery Network, CDN) aktivieren, können Benutzer eine Verbindung mit CDN online herstellen und Skype Meetings App (unter Windows) und Skype for Business für Mac (auf Mac) erhalten und die vereinfachte Besprechungsbesprechungserfahrung verwenden.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Zulassen, dass die telemetrieseitige Protokollierung von der Webseite für den Besprechungs beitritt oder der Skype-Besprechungs-App an Microsoft-Server gesendet wird (der Befehl ist standardmäßig auf false festgelegt).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    An Microsoft gesendete Informationen sind in strikter Übereinstimmung mit [den Skype for Business-Datensammlungspraktiken .](/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Legen Sie das Timeout vor dem Fall zurück auf die lokal gehostete Skype for Business Web App-Erfahrung, wenn CDN nicht verfügbar ist. Der Standardwert ist 6 Sekunden. Wenn dieser Wert auf 0 festgelegt ist, gibt es kein Timeout.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Bei MeetingUxUseCdn in Skype for Business Server 2015 Kumulatives Update 5 wird der Standardwert auf False festgelegt. Dies führt zu einem Problem, bei dem der Skype for Business for Mac-Client nicht als Gast an Besprechungen von Nicht-Verbundpartnern teilnehmen kann, auch wenn Skype for Business Admin MeetingUxUseCdn auf True festgelegt hat. Damit dies funktioniert, muss Skype for Business Server 2015 über das kumulative Update 7, 6.0.9319.534 oder höher verfügen. Weitere Informationen finden Sie unter [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Siehe auch
<a name="SMA_Enable"> </a>

[Planen von Besprechungsclients (Web App und Besprechungs-App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Konfigurieren der Seite "Besprechungs beitreten" in Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Datenschutzerklärung von Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Lizenzierungsbedingungen und Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)