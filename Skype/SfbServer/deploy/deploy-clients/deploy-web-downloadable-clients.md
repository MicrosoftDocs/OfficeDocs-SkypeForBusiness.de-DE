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
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="62795-103">Bereitstellen von Webdownload-Clients in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="62795-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="62795-104">**Zusammenfassung:** Stellen Sie die mit Skype for Business Server verwendete Skype for Business 2015-Webanwendung und Skype-Besprechungs-App bereit.</span><span class="sxs-lookup"><span data-stu-id="62795-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="62795-105">Skype for Business-Webanwendung ist ein Internet Information Services (IIS)er WebClient, der auf dem Server mit Skype for Business Server installiert ist und standardmäßig bei Bedarf für Besprechungs Benutzer bereitgestellt wird, die nicht bereits über den Skype for Business-Client verfügen.</span><span class="sxs-lookup"><span data-stu-id="62795-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="62795-106">Diese Besprechungs Benutzer verbinden häufiger als keine Verbindung von außerhalb Ihres Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="62795-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="62795-107">Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber der Skype for Business-Client nicht installiert ist, wird dem Benutzer die Möglichkeit geboten, an der Besprechung teilzunehmen, indem er die neueste Version von Skype for Business-Webanwendung, Skype-Besprechungs-APP oder Skype for Business für Mac verwendet.</span><span class="sxs-lookup"><span data-stu-id="62795-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="62795-108">Für die sprach-, Video-und Freigabefunktionen in Skype for Business-Webanwendung ist ein Microsoft-ActiveX-Steuerelement erforderlich, das vom Browser des Benutzers als Plugin verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62795-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="62795-109">Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder Benutzern erlauben, es zu installieren, wenn Sie dazu aufgefordert werden, was geschieht, wenn Sie Skype for Business-Webanwendung zum ersten Mal verwenden oder wenn Sie erstmals auf ein Feature zugreifen, für das das ActiveX-Steuerelement erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="62795-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="62795-110">In Skype for Business Server Edgeserver-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk für den Zugriff auf Skype for Business webapp-Client erforderlich.</span><span class="sxs-lookup"><span data-stu-id="62795-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="62795-111">Sie müssen zudem einfache URLs.</span><span class="sxs-lookup"><span data-stu-id="62795-111">You must also publish simple URLs.</span></span> <span data-ttu-id="62795-112">Ausführliche Informationen finden Sie unter [Setting up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS Requirements for Simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="62795-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="62795-113">Aktivieren der mehrstufigen Authentifizierung für Skype for Business-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="62795-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="62795-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="62795-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="62795-115">Skype for Business-Webanwendung, Skype-Besprechungs-APP und Skype for Business für Mac unterstützen die mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="62795-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="62795-116">Neben Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins zur Authentifizierung von Benutzern benötigen, die von externen Netzwerken beitreten, wenn Sie sich bei Skype for Business Besprechungen anmelden.</span><span class="sxs-lookup"><span data-stu-id="62795-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="62795-117">Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Verbundserver Active Directory Verbunddienst (AD FS) bereitstellen und die passive Authentifizierung in Skype for Business Server aktivieren.</span><span class="sxs-lookup"><span data-stu-id="62795-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="62795-118">Nachdem AD FS konfiguriert wurde, werden externe Benutzer, die versuchen, an Skype for Business Besprechungen teilzunehmen, mit einer AD FS-mehrstufigen Authentifizierungs Webseite angezeigt, die die Benutzernamen-und Kenn Wort Herausforderung sowie alle weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält.</span><span class="sxs-lookup"><span data-stu-id="62795-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62795-119">Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="62795-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="62795-120">Die mehrstufige ADFS-Authentifizierung funktioniert, wenn sich der Besprechungsteilnehmer und der Organisator sowohl in derselben Organisation als auch in einer AD FS-Verbundorganisation befinden.</span><span class="sxs-lookup"><span data-stu-id="62795-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="62795-121">Die mehrstufige ADFS-Authentifizierung funktioniert nicht für lync-Verbundbenutzer, da Sie von der lync Server-Webinfrastruktur derzeit nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="62795-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="62795-122">Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies für die Lastenausgleichsmodule, damit alle Anforderungen von den App-Clients für Skype for Business-Webanwendungen oder-Besprechungen von derselben Front-End-Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="62795-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="62795-123">Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen Skype for Business Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die lang genug ist, um die maximale Länge Ihrer Skype for Business Besprechungen zu überspannen.</span><span class="sxs-lookup"><span data-stu-id="62795-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="62795-124">Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.</span><span class="sxs-lookup"><span data-stu-id="62795-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="62795-125">Diese Konfiguration gilt nicht für lync Mobile-Clients.</span><span class="sxs-lookup"><span data-stu-id="62795-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="62795-126">Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="62795-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="62795-127">Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle.</span><span class="sxs-lookup"><span data-stu-id="62795-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="62795-128">Ausführliche Informationen finden Sie im [Bereitstellungshandbuch für Active Directory Verbunddienste 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="62795-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="62795-129">Erstellen von Zertifikaten für AD FS.</span><span class="sxs-lookup"><span data-stu-id="62795-129">Create certificates for AD FS.</span></span> <span data-ttu-id="62795-130">Weitere Informationen finden Sie im Abschnitt ["Verbundserver Zertifikate"](https://go.microsoft.com/fwlink/p/?LinkId=285376) im Thema Planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden.</span><span class="sxs-lookup"><span data-stu-id="62795-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="62795-131">Führen Sie über die Befehlszeilenschnittstelle Windows PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="62795-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="62795-132">Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:</span><span class="sxs-lookup"><span data-stu-id="62795-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="62795-133">Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:</span><span class="sxs-lookup"><span data-stu-id="62795-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="62795-134">Deaktivieren von BranchCache</span><span class="sxs-lookup"><span data-stu-id="62795-134">Disable BranchCache</span></span>
<span data-ttu-id="62795-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="62795-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="62795-136">Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann die Webkomponenten von Skype for Business Webanwendung stören.</span><span class="sxs-lookup"><span data-stu-id="62795-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="62795-137">Stellen Sie sicher, dass BranchCache nicht aktiviert ist, um Probleme für Skype for Business-Webanwendung-Benutzer zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="62795-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="62795-138">Ausführliche Informationen zum Deaktivieren von BranchCache finden Sie im [BranchCache-Bereitstellungshandbuch](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="62795-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="62795-139">Überprüfen Skype for Business Webanwendungs-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="62795-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="62795-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="62795-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="62795-141">Sie können das Cmdlet "Test-CsUcwaConference" verwenden, um sicherzustellen, dass ein Paar von Testbenutzern in einer Konferenz unter Verwendung der Unified Communications-Web-API (UCWA) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="62795-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="62795-142">Ausführliche Informationen zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in der Dokumentation zur Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="62795-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="62795-143">Problembehandlung bei der Plug-in-Installation auf Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="62795-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="62795-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="62795-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="62795-145">Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Einstellung Internet Explorer Security oder die Einstellung des Registrierungsschlüssels DisableMSI ändern.</span><span class="sxs-lookup"><span data-stu-id="62795-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="62795-146">Ändern der Sicherheitseinstellung in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="62795-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="62795-147">Öffnen Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="62795-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="62795-148">Klicken Sie auf **Extras**, dann auf **Internetoptionen** und anschließend auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="62795-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="62795-149">Führen Sie einen Bildlauf zum Bereich **Sicherheit** durch.</span><span class="sxs-lookup"><span data-stu-id="62795-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="62795-150">Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62795-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="62795-151">Wenn diese Einstellung aktiviert ist, wird beim Versuch, eine Anlage aus Skype for Business-Webanwendung herunterzuladen, auch ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="62795-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="62795-152">Nehmen Sie an der Besprechung erneut teil.</span><span class="sxs-lookup"><span data-stu-id="62795-152">Rejoin the meeting.</span></span> <span data-ttu-id="62795-153">Das Plug-In sollte ohne Fehler Elemente herunterladen.</span><span class="sxs-lookup"><span data-stu-id="62795-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="62795-154">Ändern der Registrierungseinstellung für DisableMSI</span><span class="sxs-lookup"><span data-stu-id="62795-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="62795-155">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="62795-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="62795-156">Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="62795-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="62795-157">Navigieren Sie zu "HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer".</span><span class="sxs-lookup"><span data-stu-id="62795-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="62795-158">Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG_DWORD hinzu, und legen Sie ihn auf "0" fest.</span><span class="sxs-lookup"><span data-stu-id="62795-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="62795-159">Nehmen Sie an der Besprechung erneut teil.</span><span class="sxs-lookup"><span data-stu-id="62795-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="62795-160">Skype-Besprechungs-App aktivieren, um Skype for Business-Webanwendung zu ersetzen (optional, nur Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="62795-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="62795-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="62795-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="62795-162">Dieses Verfahren ist optional und gilt für Skype for Business Server 2015 CU5 und höher.</span><span class="sxs-lookup"><span data-stu-id="62795-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="62795-163">Wenn Sie Sie nicht verwenden, werden externe Benutzer weiterhin mit Skype for Business-Webanwendung an Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="62795-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="62795-164">Aktivieren der APP für vereinfachte Besprechungsteilnahme und Skype-Besprechungen</span><span class="sxs-lookup"><span data-stu-id="62795-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="62795-165">Wenn Sie den Zugriff auf das Inhalts Zustellungs Netzwerk (CDN) aktivieren, haben Benutzer die Möglichkeit, eine Verbindung mit CDN Online herzustellen und die Skype-Besprechungs-app (unter Windows) und Skype for Business für Mac (auf dem Mac) zu erhalten, und die vereinfachte Teilnahme an einem besprechungsbeitritt wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="62795-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="62795-166">Clientseitige Protokollierung von Telemetrie über die Besprechungs Mitgliedschafts Webseite oder die Skype-Besprechungs-APP an Microsoft-Server senden lassen (der Befehl ist standardmäßig auf "false" festgelegt).</span><span class="sxs-lookup"><span data-stu-id="62795-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="62795-167">Informationen, die an Microsoft gesendet werden, unterliegen der strikten Einhaltung von [Datenschutzbestimmungen und Microsoft Teams](../../../../Teams/teams-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="62795-167">Information sent to Microsoft is in strict compliance with [Privacy and Microsoft Teams](../../../../Teams/teams-privacy.md).</span></span>

3. <span data-ttu-id="62795-168">Legen Sie das Timeout fest, bevor Sie auf das Lokal gehostete Skype for Business-Webanwendungs Erlebnis zurückgreifen, wenn CDN nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="62795-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="62795-169">Der Standardwert ist 6 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="62795-169">The default value is 6 seconds.</span></span> <span data-ttu-id="62795-170">Wenn dieser Wert auf 0 festgelegt ist, wird kein Timeout verwendet.</span><span class="sxs-lookup"><span data-stu-id="62795-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="62795-171">Bei MeetingUxUseCdn in Skype for Business Server 2015 kumulativen Update 5 wird der Standardwert auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="62795-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="62795-172">Dies führt zu einem Problem, bei dem Skype for Business für Mac-Client nicht als Gast an Besprechungen von nicht-Verbundpartnern teilnehmen kann, auch wenn Skype for Business Administrator MeetingUxUseCdn auf true festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="62795-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="62795-173">Damit dies funktioniert, muss Skype for Business Server 2015 das kumulative Update 7, 6.0.9319.534 oder höher haben.</span><span class="sxs-lookup"><span data-stu-id="62795-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="62795-174">Weitere Informationen finden Sie unter [Aktivieren der Skype-Besprechungs-App zum Ersetzen Skype for Business-Webanwendung in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span><span class="sxs-lookup"><span data-stu-id="62795-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="62795-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62795-175">See also</span></span>
<span data-ttu-id="62795-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="62795-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="62795-177">Planen von Besprechungs Clients (app für Webanwendungen und Besprechungen)</span><span class="sxs-lookup"><span data-stu-id="62795-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="62795-178">Konfigurieren der Seite für den besprechungsbeitritt in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="62795-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="62795-179">Datenschutzerklärung von Microsoft</span><span class="sxs-lookup"><span data-stu-id="62795-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="62795-180">Lizenzierungsbedingungen und Dokumentation</span><span class="sxs-lookup"><span data-stu-id="62795-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
