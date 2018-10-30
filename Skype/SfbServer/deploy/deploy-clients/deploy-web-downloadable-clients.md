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
ms.openlocfilehash: 13facacfc2e42ec45e29aae1c1006c792ef6ac1e
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839226"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="01880-103">Bereitstellen Sie herunterladbare Webclients in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="01880-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="01880-104">**Zusammenfassung:** Bereitstellen der Skype für Business 2015 Web App und Skype Besprechungen App mit Skype für Business Server 2015 verwendet.</span><span class="sxs-lookup"><span data-stu-id="01880-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server 2015.</span></span>

<span data-ttu-id="01880-105">Skype für Web-Geschäfts-App ist ein Webclient (Internet Information Services, IIS), die auf dem Server mit Skype für Business Server 2015 installiert ist, und standardmäßig wird es bei Bedarf für Meeting-Benutzer, die die Skype für Business-Client nicht noch bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="01880-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server 2015 and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="01880-106">Diese Besprechung Benutzer sind Abfragebegriff häufiger auftritt als nicht Herstellen einer Verbindung von außerhalb des Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="01880-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="01880-107">Wenn ein Benutzer klickt auf einer besprechungs-URL, aber keinen der Skype für Business-Client installiert, wird der Benutzer mit der Option für die Teilnahme mithilfe der neuesten Version von Skype für Business Web App oder Skype Besprechungen App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01880-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App or Skype Meetings App.</span></span>

<span data-ttu-id="01880-108">Die Sprache, video und Freigabe-features in Skype für Web-Geschäfts-App erfordern ein Microsoft ActiveX-Steuerelement, das als Plug-in vom Browser des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="01880-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="01880-109">Sie können entweder installieren Sie das ActiveX-Steuerelement im Voraus zulassen, dass Benutzer auf, wenn Sie dazu aufgefordert werden, installiert werden beim ersten geschieht sie Skype für Web-Geschäfts-App verwenden oder beim ersten Zugriff auf ein Feature, das ActiveX-Steuerelement erfordert.</span><span class="sxs-lookup"><span data-stu-id="01880-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="01880-110">In Skype für Business Server 2015 Edge-Server-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk für Skype für den Clientzugriff Web-Geschäfts-App erforderlich.</span><span class="sxs-lookup"><span data-stu-id="01880-110">In Skype for Business Server 2015 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="01880-111">Außerdem müssen Sie einfache URLs veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="01880-111">You must also publish simple URLs.</span></span> <span data-ttu-id="01880-112">Weitere Informationen hierzu finden Sie unter [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) und [DNS-Anforderungen für einfache URLs in Skype für Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="01880-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="01880-113">Aktivieren Sie die mehrstufige Authentifizierung für Skype für Business Web App</span><span class="sxs-lookup"><span data-stu-id="01880-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="01880-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="01880-114"></span></span>

<span data-ttu-id="01880-115">Die Skype für Business Web App und Skype Besprechungen App unterstützen mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="01880-115">The Skype for Business Web App and Skype Meetings App support multi-factor authentication.</span></span> <span data-ttu-id="01880-116">Neben den Benutzernamen und das Kennwort können Sie zusätzliche Authentifizierungsmethoden, wie effizient Karten oder Stifte, zum Authentifizieren von Benutzern, die von externen Netzwerken teilnehmen möchten, wenn Skype für Business Besprechungen Anmeldung erfordern.</span><span class="sxs-lookup"><span data-stu-id="01880-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="01880-117">Sie können die mehrstufige Authentifizierung aktivieren, durch die Bereitstellung von Active Directory-Verbunddienst (AD FS)-Verbundserver und Aktivieren der passiven Authentifizierung in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="01880-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="01880-118">Wenn AD FS konfiguriert ist, eine AD FS Multi-Factor Authentication-Webseite, die den Benutzernamen enthält externe Benutzern, die versuchen, Skype für Business-Besprechungen teilnehmen angezeigt werden und Kennwort Abfrage zusammen mit zusätzlichen Authentifizierungsmethoden, die Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="01880-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01880-119">Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="01880-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="01880-p105">Mehrstufige ADFS-Authentifizierung funktioniert, wenn der Besprechungsteilnehmer und der Organisator sich beide in der gleichen Organisation befinden oder beide aus einer AD FS-Partnerverbundorganisation stammen. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für Lync-Partnerverbundbenutzer, da sie von der Webinfrastruktur von Lync Server aktuell nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="01880-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="01880-122">Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, aktivieren Sie Dauerhaftigkeit von Cookies auf die Systeme zum Lastenausgleich, sodass alle Anforderungen aus der Skype für Business Web App oder Besprechungen App-Clients vom gleichen Front-End-Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="01880-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="01880-123">Wenn Sie eine Vertrauensstellung zwischen Skype für Business Server mit AD FS-Servern herstellen, weisen Sie ein token Leben, die lange genug sind, um die maximale Länge des Ihrer Skype für Business Besprechungen span ist.</span><span class="sxs-lookup"><span data-stu-id="01880-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="01880-124">Normalerweise genügt eine Tokengültigkeitsdauer von 240 Minuten.</span><span class="sxs-lookup"><span data-stu-id="01880-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="01880-125">Diese Konfiguration gilt nicht für mobile Lync-Clients.</span><span class="sxs-lookup"><span data-stu-id="01880-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="01880-126">Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="01880-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="01880-127">Installieren Sie eine AD FS-Verbundserverrolle.</span><span class="sxs-lookup"><span data-stu-id="01880-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="01880-128">Weitere Informationen hierzu finden Sie im [Active Directory Federation Services 2.0-Bereitstellungshandbuch](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="01880-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="01880-129">Erstellen Sie Zertifikate für AD FS.</span><span class="sxs-lookup"><span data-stu-id="01880-129">Create certificates for AD FS.</span></span> <span data-ttu-id="01880-130">Weitere Informationen finden Sie unter ["Zertifikate auf Verbundservern"](https://go.microsoft.com/fwlink/p/?LinkId=285376) im Abschnitt über das Planen und Bereitstellen von AD FS für die Verwendung mit Thema für einmaliges Anmelden.</span><span class="sxs-lookup"><span data-stu-id="01880-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="01880-131">Führen Sie von der Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="01880-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="01880-132">Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:</span><span class="sxs-lookup"><span data-stu-id="01880-132">Establish a partnership by running the following command:</span></span>

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="01880-133">Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:</span><span class="sxs-lookup"><span data-stu-id="01880-133">Set the following relying party rules:</span></span>

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="01880-134">Deaktivieren von BranchCache </span><span class="sxs-lookup"><span data-stu-id="01880-134">Disable BranchCache</span></span>
<span data-ttu-id="01880-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="01880-135"></span></span>

<span data-ttu-id="01880-136">Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann Skype für Web-Geschäfts-App-Webkomponenten beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="01880-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="01880-137">Um Probleme für Skype für Business Web App-Benutzer zu verhindern, sicher, dass BranchCache nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="01880-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="01880-138">Ausführliche Informationen zu BranchCache deaktivieren finden Sie im [Bereitstellungshandbuch für BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="01880-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="01880-139">Überprüfen der Skype für Business Web App-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="01880-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="01880-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="01880-140"></span></span>

<span data-ttu-id="01880-141">Mit dem Cmdlet „Test-CsUcwaConference“ können Sie überprüfen, ob zwei Testbenutzer über die Unified Communications-Web-API (UCWA) an einer Konferenz teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="01880-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="01880-142">Ausführliche Informationen zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in der Skype Business Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="01880-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="01880-143">Problembehandlung von Plug-in-Installation unter Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="01880-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="01880-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="01880-144"></span></span>

<span data-ttu-id="01880-145">Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie die Internet Explorer-sicherheitseinstellung oder die DisableMSI-registrierungsschlüsseleinstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="01880-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="01880-146">Ändern der Sicherheitseinstellung in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="01880-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="01880-147">Öffnen Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="01880-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="01880-148">Klicken Sie auf **Extras**, auf **Internetoptionen** und anschließend auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="01880-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="01880-149">Scrollen Sie nach unten zum Abschnitt **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="01880-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="01880-150">Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="01880-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01880-151">Wenn ausgewählt, verursacht diese Einstellung auch einen Fehler beim Versuch, eine Anlage von Skype für Business Web App herunterladen.</span><span class="sxs-lookup"><span data-stu-id="01880-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="01880-p111">Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.</span><span class="sxs-lookup"><span data-stu-id="01880-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="01880-154">Ändern der Registrierungseinstellung für „DisableMSI“</span><span class="sxs-lookup"><span data-stu-id="01880-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="01880-155">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="01880-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="01880-156">Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="01880-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="01880-157">Navigieren Sie zu "HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer".</span><span class="sxs-lookup"><span data-stu-id="01880-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="01880-158">Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG_DWORD hinzu, und legen Sie ihn auf "0" fest.</span><span class="sxs-lookup"><span data-stu-id="01880-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="01880-159">Nehmen Sie an der Besprechung erneut teil.</span><span class="sxs-lookup"><span data-stu-id="01880-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="01880-160">Aktivieren von Skype Besprechungen App zum Ersetzen von Skype für Business Web App (Optional, Skype für Business Server 2015 nur)</span><span class="sxs-lookup"><span data-stu-id="01880-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="01880-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="01880-161"></span></span>

<span data-ttu-id="01880-162">Dieses Verfahren ist optional und gilt für Skype für Business Server 2015 CU5 oder höher.</span><span class="sxs-lookup"><span data-stu-id="01880-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="01880-163">Wenn Sie nicht verwenden, weiterhin externe Benutzer zur Teilnahme an Besprechungen mit Skype für Web-Geschäfts-App.</span><span class="sxs-lookup"><span data-stu-id="01880-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="01880-164">Aktivieren der vereinfachten Teilnahme an Besprechungen und der Skype-Besprechungs-App</span><span class="sxs-lookup"><span data-stu-id="01880-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="01880-165">Wenn Sie den Zugriff auf Content Delivery Network (CDN) ermöglichen, Benutzer haben die Möglichkeit zum Verbinden mit CDN online und Skype Besprechungen App abrufen und verwendet die vereinfachte meeting beitrittserlebnis.</span><span class="sxs-lookup"><span data-stu-id="01880-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App, and will use the simplified meeting join experience.</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="01880-166">Zulassen von Client-Side Protokollierung Telemetrie aus der Besprechung teilnehmen, Webseite oder die Skype Besprechungen App an den Microsoft-Server (der Befehl standardmäßig False) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="01880-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="01880-167">Die an Microsoft gesendeten Informationen entsprechen genau den Angaben unter [Skype for Business-Datensammlungsmethoden](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span><span class="sxs-lookup"><span data-stu-id="01880-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="01880-168">Legen Sie den Timeoutwert vor zurückgreifen auf die lokal gehosteten Skype Business Web App wünschen Verbindung, wenn CDN nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="01880-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="01880-169">Der Standardwert entspricht 6 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="01880-169">The default value is 6 seconds.</span></span> <span data-ttu-id="01880-170">Wenn der Wert auf 0 festgelegt ist, tritt kein Timeout ein.</span><span class="sxs-lookup"><span data-stu-id="01880-170">If this value is set to 0, there will be no timeout.</span></span>

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="01880-171">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="01880-171">See also</span></span>
<span data-ttu-id="01880-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="01880-172"></span></span>

[<span data-ttu-id="01880-173">Planen von Besprechungen-Clients (Web App und Besprechungen App)</span><span class="sxs-lookup"><span data-stu-id="01880-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="01880-174">Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="01880-174">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="01880-175">Microsoft Online Services-Datenschutzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="01880-175">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="01880-176">Lizenzierung von Ausdrücken und Dokumentation</span><span class="sxs-lookup"><span data-stu-id="01880-176">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)