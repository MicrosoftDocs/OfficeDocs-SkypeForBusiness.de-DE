---
title: Bereitstellen von Webdownload-Clients in Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Zusammenfassung: Bereitstellen der mit Skype for Business verwendeten Skype for Business-Webanwendung und der Skype-Besprechungs-app.'
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429421"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Bereitstellen von Webdownload-Clients in Skype for Business Server

**Zusammenfassung:** Stellen Sie die mit Skype for Business Server verwendete Skype for Business 2015-Webanwendung und Skype-Besprechungs-App bereit.

Skype for Business-Webanwendung ist ein Internet Information Services (IIS)er WebClient, der auf dem Server mit Skype for Business Server installiert ist und standardmäßig bei Bedarf für Besprechungs Benutzer bereitgestellt wird, die nicht bereits über den Skype for Business-Client verfügen. Diese Besprechungs Benutzer verbinden häufiger als keine Verbindung von außerhalb Ihres Netzwerks. Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber der Skype for Business-Client nicht installiert ist, wird dem Benutzer die Möglichkeit geboten, an der Besprechung teilzunehmen, indem er die neueste Version von Skype for Business-Webanwendung, Skype-Besprechungs-APP oder Skype for Business für Mac verwendet.

Für die sprach-, Video-und Freigabefunktionen in Skype for Business-Webanwendung ist ein Microsoft-ActiveX-Steuerelement erforderlich, das vom Browser des Benutzers als Plugin verwendet wird. Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder Benutzern erlauben, es zu installieren, wenn Sie dazu aufgefordert werden, was geschieht, wenn Sie Skype for Business-Webanwendung zum ersten Mal verwenden oder wenn Sie erstmals auf ein Feature zugreifen, für das das ActiveX-Steuerelement erforderlich ist.

> [!NOTE]
> In Skype for Business Server Edgeserver-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk für den Zugriff auf Skype for Business webapp-Client erforderlich. Sie müssen zudem einfache URLs. Ausführliche Informationen finden Sie unter [Setting up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS Requirements for Simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Aktivieren der mehrstufigen Authentifizierung für Skype for Business-Webanwendung
<a name="MFA"> </a>

Skype for Business-Webanwendung, Skype-Besprechungs-APP und Skype for Business für Mac unterstützen die mehrstufige Authentifizierung. Neben Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins zur Authentifizierung von Benutzern benötigen, die von externen Netzwerken beitreten, wenn Sie sich bei Skype for Business Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Verbundserver Active Directory Verbunddienst (AD FS) bereitstellen und die passive Authentifizierung in Skype for Business Server aktivieren. Nachdem AD FS konfiguriert wurde, werden externe Benutzer, die versuchen, an Skype for Business Besprechungen teilzunehmen, mit einer AD FS-mehrstufigen Authentifizierungs Webseite angezeigt, die die Benutzernamen-und Kenn Wort Herausforderung sowie alle weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält.

> [!IMPORTANT]
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren

- Die mehrstufige ADFS-Authentifizierung funktioniert, wenn sich der Besprechungsteilnehmer und der Organisator sowohl in derselben Organisation als auch in einer AD FS-Verbundorganisation befinden. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für lync-Verbundbenutzer, da Sie von der lync Server-Webinfrastruktur derzeit nicht unterstützt wird.

- Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies für die Lastenausgleichsmodule, damit alle Anforderungen von den App-Clients für Skype for Business-Webanwendungen oder-Besprechungen von derselben Front-End-Server verarbeitet werden.

- Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen Skype for Business Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die lang genug ist, um die maximale Länge Ihrer Skype for Business Besprechungen zu überspannen. Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.

- Diese Konfiguration gilt nicht für lync Mobile-Clients.

### <a name="configure-multi-factor-authentication"></a>Konfigurieren der mehrstufigen Authentifizierung

1. Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle. Ausführliche Informationen finden Sie im [Bereitstellungshandbuch für Active Directory Verbunddienste 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Erstellen von Zertifikaten für AD FS. Weitere Informationen finden Sie im Abschnitt ["Verbundserver Zertifikate"](https://go.microsoft.com/fwlink/p/?LinkId=285376) im Thema Planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden.

3. Führen Sie über die Befehlszeilenschnittstelle Windows PowerShell den folgenden Befehl aus:

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

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann die Webkomponenten von Skype for Business Webanwendung stören. Stellen Sie sicher, dass BranchCache nicht aktiviert ist, um Probleme für Skype for Business-Webanwendung-Benutzer zu vermeiden.

Ausführliche Informationen zum Deaktivieren von BranchCache finden Sie im [BranchCache-Bereitstellungshandbuch](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Überprüfen Skype for Business Webanwendungs-Bereitstellung
<a name="MFA"> </a>

Sie können das Cmdlet "Test-CsUcwaConference" verwenden, um sicherzustellen, dass ein Paar von Testbenutzern in einer Konferenz unter Verwendung der Unified Communications-Web-API (UCWA) teilnehmen können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in der Dokumentation zur Skype for Business Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Problembehandlung bei der Plug-in-Installation auf Windows Server 2008 R2
<a name="MFA"> </a>

Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Einstellung Internet Explorer Security oder die Einstellung des Registrierungsschlüssels DisableMSI ändern.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Ändern der Sicherheitseinstellung in Internet Explorer

1. Öffnen Sie Internet Explorer.

2. Klicken Sie auf **Extras**, dann auf **Internetoptionen** und anschließend auf **Erweitert**.

3. Führen Sie einen Bildlauf zum Bereich **Sicherheit** durch.

4. Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Wenn diese Einstellung aktiviert ist, wird beim Versuch, eine Anlage aus Skype for Business-Webanwendung herunterzuladen, auch ein Fehler ausgelöst.

5. Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

### <a name="modify-the-disablemsi-registry-setting"></a>Ändern der Registrierungseinstellung für DisableMSI

1. Klicken Sie auf **Start** und dann auf **Ausführen**.

2. Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3. Navigieren Sie zu "HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer".

4. Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG_DWORD hinzu, und legen Sie ihn auf "0" fest.

5. Nehmen Sie an der Besprechung erneut teil.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Skype-Besprechungs-App aktivieren, um Skype for Business-Webanwendung zu ersetzen (optional, nur Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Dieses Verfahren ist optional und gilt für Skype for Business Server 2015 CU5 und höher. Wenn Sie Sie nicht verwenden, werden externe Benutzer weiterhin mit Skype for Business-Webanwendung an Besprechungen teilnehmen.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Aktivieren der APP für vereinfachte Besprechungsteilnahme und Skype-Besprechungen

1. Wenn Sie den Zugriff auf das Inhalts Zustellungs Netzwerk (CDN) aktivieren, haben Benutzer die Möglichkeit, eine Verbindung mit CDN Online herzustellen und die Skype-Besprechungs-app (unter Windows) und Skype for Business für Mac (auf dem Mac) zu erhalten, und die vereinfachte Teilnahme an einem besprechungsbeitritt wird verwendet.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Clientseitige Protokollierung von Telemetrie über die Besprechungs Mitgliedschafts Webseite oder die Skype-Besprechungs-APP an Microsoft-Server senden lassen (der Befehl ist standardmäßig auf "false" festgelegt).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Informationen, die an Microsoft gesendet werden, unterliegen der strikten Einhaltung von [Datenschutzbestimmungen und Microsoft Teams](../../../../Teams/teams-privacy.md).

3. Legen Sie das Timeout fest, bevor Sie auf das Lokal gehostete Skype for Business-Webanwendungs Erlebnis zurückgreifen, wenn CDN nicht verfügbar ist. Der Standardwert ist 6 Sekunden. Wenn dieser Wert auf 0 festgelegt ist, wird kein Timeout verwendet.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Bei MeetingUxUseCdn in Skype for Business Server 2015 kumulativen Update 5 wird der Standardwert auf false festgelegt. Dies führt zu einem Problem, bei dem Skype for Business für Mac-Client nicht als Gast an Besprechungen von nicht-Verbundpartnern teilnehmen kann, auch wenn Skype for Business Administrator MeetingUxUseCdn auf true festgelegt hat. Damit dies funktioniert, muss Skype for Business Server 2015 das kumulative Update 7, 6.0.9319.534 oder höher haben. Weitere Informationen finden Sie unter [Aktivieren der Skype-Besprechungs-App zum Ersetzen Skype for Business-Webanwendung in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Siehe auch
<a name="SMA_Enable"> </a>

[Planen von Besprechungs Clients (app für Webanwendungen und Besprechungen)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Konfigurieren der Seite für den besprechungsbeitritt in Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Datenschutzerklärung von Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Lizenzierungsbedingungen und Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
