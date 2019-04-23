---
title: Bereitstellen Sie herunterladbare Webclients in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Zusammenfassung: Bereitstellung der Skype für Business Web App und Skype Besprechungen App mit Skype für Unternehmen verwendet.'
ms.openlocfilehash: c974ff9d202c56b0a32c9983706a60b5d73c4de6
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959560"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Bereitstellen Sie herunterladbare Webclients in Skype für Business Server

**Zusammenfassung:** Bereitstellen der Skype für Business 2015 Web App und Skype Besprechungen App mit Skype für Business Server verwendet.

Skype für Web-Geschäfts-App ist ein Webclient (Internet Information Services, IIS), die auf dem Server mit Skype für Business Server installiert ist, und standardmäßig wird es bei Bedarf für Meeting-Benutzer, die die Skype für Business-Client nicht noch bereitgestellt. Diese Besprechung Benutzer sind Abfragebegriff häufiger auftritt als nicht Herstellen einer Verbindung von außerhalb des Netzwerks. Wenn ein Benutzer klickt auf einer besprechungs-URL, aber keinen der Skype für Business-Client installiert, wird dem Benutzer mit der Option für die Teilnahme mit der neuesten Version von Skype für Web-Geschäfts-App, Skype Besprechungen App oder Skype für Unternehmen für Mac angezeigt.

Die Sprache, video und Freigabe-features in Skype für Web-Geschäfts-App erfordern ein Microsoft ActiveX-Steuerelement, das als Plug-in vom Browser des Benutzers verwendet wird. Sie können entweder installieren Sie das ActiveX-Steuerelement im Voraus zulassen, dass Benutzer auf, wenn Sie dazu aufgefordert werden, installiert werden beim ersten geschieht sie Skype für Web-Geschäfts-App verwenden oder beim ersten Zugriff auf ein Feature, das ActiveX-Steuerelement erfordert.

> [!NOTE]
> In Skype für Business Server Edge-Server-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk für Skype für den Clientzugriff Web-Geschäfts-App erforderlich. Außerdem müssen Sie einfache URLs veröffentlichen. Weitere Informationen hierzu finden Sie unter [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) und [DNS-Anforderungen für einfache URLs in Skype für Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Aktivieren Sie die mehrstufige Authentifizierung für Skype für Business Web App
<a name="MFA"> </a>

Skype für Web-Geschäfts-App, Skype Besprechungen App- und Skype für Unternehmen für Mac unterstützt Multi-Factor Authentication. Neben den Benutzernamen und das Kennwort können Sie zusätzliche Authentifizierungsmethoden, wie effizient Karten oder Stifte, zum Authentifizieren von Benutzern, die von externen Netzwerken teilnehmen möchten, wenn Skype für Business Besprechungen Anmeldung erfordern. Sie können die mehrstufige Authentifizierung aktivieren, durch die Bereitstellung von Active Directory-Verbunddienst (AD FS)-Verbundserver und Aktivieren der passiven Authentifizierung in Skype für Business Server. Wenn AD FS konfiguriert ist, eine AD FS Multi-Factor Authentication-Webseite, die den Benutzernamen enthält externe Benutzern, die versuchen, Skype für Business-Besprechungen teilnehmen angezeigt werden und Kennwort Abfrage zusammen mit zusätzlichen Authentifizierungsmethoden, die Sie konfiguriert haben.

> [!IMPORTANT]
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren

- Mehrstufige ADFS-Authentifizierung funktioniert, wenn der Besprechungsteilnehmer und der Organisator sich beide in der gleichen Organisation befinden oder beide aus einer AD FS-Partnerverbundorganisation stammen. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für Lync-Partnerverbundbenutzer, da sie von der Webinfrastruktur von Lync Server aktuell nicht unterstützt wird.

- Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, aktivieren Sie Dauerhaftigkeit von Cookies auf die Systeme zum Lastenausgleich, sodass alle Anforderungen aus der Skype für Business Web App oder Besprechungen App-Clients vom gleichen Front-End-Server verarbeitet werden.

- Wenn Sie eine Vertrauensstellung zwischen Skype für Business Server mit AD FS-Servern herstellen, weisen Sie ein token Leben, die lange genug sind, um die maximale Länge des Ihrer Skype für Business Besprechungen span ist. Normalerweise genügt eine Tokengültigkeitsdauer von 240 Minuten.

- Diese Konfiguration gilt nicht für mobile Lync-Clients.

### <a name="configure-multi-factor-authentication"></a>Konfigurieren der mehrstufigen Authentifizierung

1. Installieren Sie eine AD FS-Verbundserverrolle. Weitere Informationen hierzu finden Sie im [Active Directory Federation Services 2.0-Bereitstellungshandbuch](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Erstellen Sie Zertifikate für AD FS. Weitere Informationen finden Sie unter ["Zertifikate auf Verbundservern"](https://go.microsoft.com/fwlink/p/?LinkId=285376) im Abschnitt über das Planen und Bereitstellen von AD FS für die Verwendung mit Thema für einmaliges Anmelden.

3. Führen Sie von der Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl ein:

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Deaktivieren von BranchCache 
<a name="MFA"> </a>

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann Skype für Web-Geschäfts-App-Webkomponenten beeinträchtigen. Um Probleme für Skype für Business Web App-Benutzer zu verhindern, sicher, dass BranchCache nicht aktiviert ist.

Ausführliche Informationen zu BranchCache deaktivieren finden Sie im [Bereitstellungshandbuch für BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Überprüfen der Skype für Business Web App-Bereitstellung
<a name="MFA"> </a>

Mit dem Cmdlet „Test-CsUcwaConference“ können Sie überprüfen, ob zwei Testbenutzer über die Unified Communications-Web-API (UCWA) an einer Konferenz teilnehmen können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in der Skype Business Server-Verwaltungsshell-Dokumentation.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Problembehandlung von Plug-in-Installation unter Windows Server 2008 R2
<a name="MFA"> </a>

Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie die Internet Explorer-sicherheitseinstellung oder die DisableMSI-registrierungsschlüsseleinstellung ändern.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Ändern der Sicherheitseinstellung in Internet Explorer

1. Öffnen Sie Internet Explorer.

2. Klicken Sie auf **Extras**, auf **Internetoptionen** und anschließend auf **Erweitert**.

3. Scrollen Sie nach unten zum Abschnitt **Sicherheit**.

4. Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Wenn ausgewählt, verursacht diese Einstellung auch einen Fehler beim Versuch, eine Anlage von Skype für Business Web App herunterladen.

5. Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

### <a name="modify-the-disablemsi-registry-setting"></a>Ändern der Registrierungseinstellung für „DisableMSI“

1. Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2. Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3. Navigieren Sie zu "HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer".

4. Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG_DWORD hinzu, und legen Sie ihn auf "0" fest.

5. Nehmen Sie an der Besprechung erneut teil.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Aktivieren von Skype Besprechungen App zum Ersetzen von Skype für Business Web App (Optional, Skype für Business Server 2015 nur)
<a name="SMA_Enable"> </a>

Dieses Verfahren ist optional und gilt für Skype für Business Server 2015 CU5 oder höher. Wenn Sie nicht verwenden, weiterhin externe Benutzer zur Teilnahme an Besprechungen mit Skype für Web-Geschäfts-App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Aktivieren der vereinfachten Teilnahme an Besprechungen und der Skype-Besprechungs-App

1. Wenn Sie den Zugriff auf Content Delivery Network (CDN) ermöglichen, Benutzer haben die Möglichkeit zum Verbinden mit CDN online und holen Sie Skype Besprechungen App (unter Windows) und Skype für Mac (auf dem Macintosh) für Unternehmen und verwendet die vereinfachte meeting beitrittserlebnis.

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Zulassen von Client-Side Protokollierung Telemetrie aus der Besprechung teilnehmen, Webseite oder die Skype Besprechungen App an den Microsoft-Server (der Befehl standardmäßig False) gesendet werden.

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Informationen an Microsoft gesendet wird strikt [Skype für Geschäftspraktiken Daten-Auflistung](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Legen Sie den Timeoutwert vor zurückgreifen auf die lokal gehosteten Skype Business Web App wünschen Verbindung, wenn CDN nicht verfügbar ist. Der Standardwert entspricht 6 Sekunden. Wenn der Wert auf 0 festgelegt ist, tritt kein Timeout ein.

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Siehe auch
<a name="SMA_Enable"> </a>

[Planen von Besprechungen-Clients (Web App und Besprechungen App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services-Datenschutzrichtlinie](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Lizenzierung von Ausdrücken und Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
