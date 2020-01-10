---
title: Bereitstellen von Webdownload-Clients in Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Zusammenfassung: Bereitstellen der Skype for Business Web App-und Skype-Besprechungs-APP, die mit Skype for Business verwendet wird.'
ms.openlocfilehash: eb939ddf394ff62b9173939622a8ef3f20faaca9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003525"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Bereitstellen von Webdownload-Clients in Skype for Business Server

**Zusammenfassung:** Stellen Sie die Skype for Business 2015 Web App und die Skype-Besprechungs-App bereit, die mit Skype for Business Server verwendet wird.

Skype for Business Web App ist ein Internet-Informationsdienste (IIS)-WebClient, der auf dem Server installiert ist, auf dem Skype for Business Server ausgeführt wird, und wird standardmäßig bei Bedarf für Besprechungs Benutzer bereitgestellt, die noch nicht über den Skype for Business-Client verfügen. Diese Besprechungs Benutzer verbinden sich häufiger als außerhalb Ihres Netzwerks. Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber nicht über den Skype for Business-Client verfügt, wird dem Benutzer die Möglichkeit angezeigt, mit der neuesten Version von Skype for Business Web App, Skype-Besprechungs-APP oder Skype for Business für Mac an der Besprechung teilzunehmen.

Die sprach-, Video-und Freigabefunktionen in Skype for Business Web App erfordern ein Microsoft ActiveX-Steuerelement, das vom Browser des Benutzers als Plug-in verwendet wird. Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder es Benutzern gestatten, es zu installieren, wenn Sie dazu aufgefordert werden, was geschieht, wenn Sie Skype for Business Web App zum ersten Mal verwenden oder wenn Sie zum ersten Mal auf ein Feature zugreifen, das das ActiveX-Steuerelement erfordert.

> [!NOTE]
> Bei der Bereitstellung von Skype for Business Server Edge Server ist für den Skype for Business Web App-Clientzugriff ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich. Außerdem müssen Sie einfache URLs veröffentlichen. Ausführliche Informationen finden Sie unter [Einrichten von Reverse-Proxy Servern](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) und [DNS-Anforderungen für einfache URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Aktivieren der mehrstufigen Authentifizierung für Skype for Business Web App
<a name="MFA"> </a>

Skype for Business Web App, Skype-Besprechungs-APP und Skype for Business für Mac unterstützen die mehrstufige Authentifizierung. Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins anfordern, um Benutzer zu authentifizieren, die von externen Netzwerken beitreten, wenn Sie sich bei Skype for Business-Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Active Directory Federation Service (AD FS)-Verbundserver bereitstellen und die passive Authentifizierung in Skype for Business Server aktivieren. Nach der Konfiguration von AD FS werden externe Benutzer, die versuchen, an Skype for Business-Besprechungen teilzunehmen, mit einer AD FS-Website für mehrstufige Authentifizierung angezeigt, die die Herausforderung Benutzername und Kennwort zusammen mit allen weiteren Authentifizierungsmethoden enthält, die Sie konfiguriert haben.

> [!IMPORTANT]
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren

- Mehrstufige ADFS-Authentifizierung funktioniert, wenn der Besprechungsteilnehmer und der Organisator sich beide in der gleichen Organisation befinden oder beide aus einer AD FS-Partnerverbundorganisation stammen. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für Lync-Partnerverbundbenutzer, da sie von der Webinfrastruktur von Lync Server aktuell nicht unterstützt wird.

- Wenn Sie Hardware-Lastenausgleichsgeräte verwenden, aktivieren Sie die Cookie-Persistenz auf den Lastenausgleichsgeräten, damit alle Anfragen von den Skype for Business Web App-oder Besprechungs-App-Clients vom gleichen Front-End-Server verarbeitet werden.

- Wenn Sie eine vertrauende Vertrauensstellung zwischen Skype for Business Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die lang genug ist, um die maximale Länge Ihrer Skype for Business-Besprechungen zu überspannen. Normalerweise genügt eine Tokengültigkeitsdauer von 240 Minuten.

- Diese Konfiguration gilt nicht für mobile Lync-Clients.

### <a name="configure-multi-factor-authentication"></a>Konfigurieren der mehrstufigen Authentifizierung

1. Installieren Sie eine AD FS-Verbundserverrolle. Ausführliche Informationen finden Sie im [Bereitstellungshandbuch für Active Directory-Verbunddienste 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Erstellen Sie Zertifikate für AD FS. Weitere Informationen finden Sie im Abschnitt ["Verbundserver Zertifikate"](https://go.microsoft.com/fwlink/p/?LinkId=285376) im Abschnitt Planen und Bereitstellen von AD FS zur Verwendung mit dem Thema für einmaliges Anmelden.

3. Führen Sie über die Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl aus:

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

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann die Web-Komponenten von Skype for Business Web App stören. Wenn Sie Probleme mit Skype for Business Web App-Benutzern vermeiden möchten, stellen Sie sicher, dass BranchCache nicht aktiviert ist.

Details zum Deaktivieren von BranchCache finden Sie im [BranchCache-Bereitstellungshandbuch](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Überprüfen der Bereitstellung von Skype for Business Web App
<a name="MFA"> </a>

Mit dem Cmdlet „Test-CsUcwaConference“ können Sie überprüfen, ob zwei Testbenutzer über die Unified Communications-Web-API (UCWA) an einer Konferenz teilnehmen können. Details zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Problembehandlung der Plug-in-Installation unter Windows Server 2008 R2
<a name="MFA"> </a>

Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Internet Explorer-Sicherheitseinstellung oder die DisableMSI-Registrierungsschlüsseleinstellung ändern.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Ändern der Sicherheitseinstellung in Internet Explorer

1. Öffnen Sie Internet Explorer.

2. Klicken Sie auf **Extras**, auf **Internetoptionen** und anschließend auf **Erweitert**.

3. Scrollen Sie nach unten zum Abschnitt **Sicherheit**.

4. Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Wenn diese Option ausgewählt ist, wird auch bei dem Versuch, eine Anlage von Skype for Business Web App herunterzuladen, ein Fehler verursacht.

5. Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

### <a name="modify-the-disablemsi-registry-setting"></a>Ändern der Registrierungseinstellung für „DisableMSI“

1. Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2. Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3. Navigieren Sie zu "HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer".

4. Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG_DWORD hinzu, und legen Sie ihn auf "0" fest.

5. Nehmen Sie an der Besprechung erneut teil.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Aktivieren der Skype-Besprechungs-App zum Ersetzen von Skype for Business Web App (optional, nur Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Diese Vorgehensweise ist optional und gilt für Skype for Business Server 2015 CU5 und höher. Wenn Sie Sie nicht verwenden, werden externe Benutzer weiterhin mit Skype for Business Web App an Besprechungen teilnehmen.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Aktivieren der vereinfachten Teilnahme an Besprechungen und der Skype-Besprechungs-App

1. Wenn Sie den Zugriff auf das Content Delivery Network (CDN) aktivieren, haben Benutzer die Möglichkeit, eine Verbindung mit CDN Online herzustellen und die Skype-Besprechungs-app (unter Windows) und Skype for Business für Mac (unter Mac) zu erhalten und die vereinfachte Besprechung zu nutzen.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Clientseitige Protokollierung der Telemetrie über die Besprechungsteilnahme-Webseite oder die Skype-Besprechungs-APP an Microsoft-Server senden (der Befehl wird standardmäßig auf "falsch" festgelegt).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Informationen, die an Microsoft gesendet werden, unterliegen der strikten Einhaltung der [Skype for Business-Datensammlungsmethoden](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Stellen Sie das Timeout ein, bevor Sie auf die lokal gehostete Skype for Business Web App-Umgebung zurückgreifen, wenn CDN nicht verfügbar ist. Der Standardwert entspricht 6 Sekunden. Wenn der Wert auf 0 festgelegt ist, tritt kein Timeout ein.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Bei MeetingUxUseCdn in Skype for Business Server 2015 Kumulatives Update 5 ist der Standardwert auf false festgelegt. Dies führt zu einem Problem, bei dem Skype for Business für Mac-Client nicht in der Lage ist, als Gast an den Besprechungen von nicht verbundenen Partnern teilzunehmen, selbst wenn der Skype for Business-Administrator MeetingUxUseCdn auf "true" festgelegt hat. Damit dies funktioniert, muss Skype for Business Server 2015 über das kumulative Update 7, 6.0.9319.534 oder höher verfügen. Weitere Informationen finden Sie unter [Aktivieren der Skype-Besprechungs-APP, um Skype for Business Web App in Skype for Business Server 2015 zu ersetzen](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Siehe auch
<a name="SMA_Enable"> </a>

[Planen von Besprechungs Clients (app für Web App und Besprechungen)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Konfigurieren der Seite "Besprechungsteilnahme" in Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Datenschutzbestimmungen für Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Lizenzierungsbestimmungen und-Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
