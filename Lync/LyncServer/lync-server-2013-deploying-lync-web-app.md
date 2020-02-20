---
title: 'Lync Server 2013: Bereitstellen von lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a7a78c67b94084c59ebad63baa12c3a7aa3df2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="b6a5a-102">Bereitstellen von lync Web App in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6a5a-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6a5a-103">_**Letztes Änderungsstand des Themas:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="b6a5a-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="b6a5a-104">Lync Web App ist ein Internet Information Services (IIS)-WebClient, der mit lync Server 2013 installiert wird und standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="b6a5a-105">Es sind keine weiteren Schritte erforderlich, um entweder lync Web App auf dem Server zu aktivieren oder den WebClient für Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="b6a5a-106">Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber der lync 2013-Client nicht installiert ist, wird dem Benutzer die Möglichkeit geboten, an der Besprechung teilzunehmen, indem er die neueste Version von lync Web App verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="b6a5a-107">Für die VoIP-, Video-und Freigabefunktionen in lync Web App ist ein Microsoft ActiveX-Steuerelement erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="b6a5a-108">Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder Benutzern erlauben, es zu installieren, wenn Sie dazu aufgefordert werden, was geschieht, wenn Sie das erste Mal lync Web App oder beim ersten Zugriff auf ein Feature, für das das ActiveX-Steuerelement erforderlich ist, verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="b6a5a-109">In lync Server 2013 Edgeserver-Bereitstellungen ist für lync Web App Clientzugriff ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="b6a5a-110">Sie müssen zudem einfache URLs.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-110">You must also publish simple URLs.</span></span> <span data-ttu-id="b6a5a-111">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse Proxyservern für lync Server 2013</A> und <A href="lync-server-2013-planning-for-simple-urls.md">Planen für einfache URLs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="b6a5a-112">Aktivieren der mehrstufigen Authentifizierung für lync Web App</span><span class="sxs-lookup"><span data-stu-id="b6a5a-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="b6a5a-113">Die lync Server 2013 Version von lync Web App unterstützt die mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="b6a5a-114">Neben Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins zur Authentifizierung von Benutzern benötigen, die von externen Netzwerken beitreten, wenn Sie sich bei lync-Besprechungen anmelden.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="b6a5a-115">Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Verbundserver Active Directory Verbunddienst (AD FS) bereitstellen und die passive Authentifizierung in lync Server 2013 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="b6a5a-116">Nachdem AD FS konfiguriert wurde, werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-mehrstufigen Authentifizierungs Webseite angezeigt, die den Benutzernamen und das Kennwort sowie alle weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält. .</span><span class="sxs-lookup"><span data-stu-id="b6a5a-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b6a5a-117">Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b6a5a-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b6a5a-118">Die mehrstufige ADFS-Authentifizierung funktioniert, wenn sich der Besprechungsteilnehmer und der Organisator sowohl in derselben Organisation als auch in einer AD FS-Verbundorganisation befinden.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-118">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="b6a5a-119">Die mehrstufige ADFS-Authentifizierung funktioniert nicht für lync-Verbundbenutzer, da Sie von der lync Server-Webinfrastruktur derzeit nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-119">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="b6a5a-120">Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies für die Lastenausgleichsmodule, damit alle Anforderungen des lync Web App Clients von derselben Front-End-Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="b6a5a-121">Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die sich über die maximale Länge ihrer lync-Besprechungen erstrecken kann.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="b6a5a-122">Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="b6a5a-123">Diese Konfiguration gilt nicht für lync Mobile-Clients.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="b6a5a-124">**Konfigurieren der mehrstufigen Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="b6a5a-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="b6a5a-125">Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="b6a5a-126">Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory Verbunddienste 2,0 unter<https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="b6a5a-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="b6a5a-127">Erstellen von Zertifikaten für AD FS.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-127">Create certificates for AD FS.</span></span> <span data-ttu-id="b6a5a-128">Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" des Themas planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden unter [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span><span class="sxs-lookup"><span data-stu-id="b6a5a-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="b6a5a-129">Führen Sie über die Befehlszeilenschnittstelle Windows PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b6a5a-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="b6a5a-130">Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:</span><span class="sxs-lookup"><span data-stu-id="b6a5a-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="b6a5a-131">Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:</span><span class="sxs-lookup"><span data-stu-id="b6a5a-131">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="b6a5a-132">BranchCache-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b6a5a-132">BranchCache Configuration</span></span>

<span data-ttu-id="b6a5a-133">Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann mit lync Web App Webkomponenten in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="b6a5a-134">Um Probleme für lync Web App Benutzer zu vermeiden, stellen Sie sicher, dass BranchCache nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="b6a5a-135">Ausführliche Informationen zum Deaktivieren von BranchCache finden Sie im BranchCache-Bereitstellungshandbuch, das im Microsoft Download Center im [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) und im HTML-Format in der technischen Bibliothek von [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789)Windows Server 2008 R2 unter im Word-Format verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="b6a5a-136">Überprüfen der lync Web App-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b6a5a-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="b6a5a-137">Sie können das Cmdlet "Test-CsUcwaConference" verwenden, um sicherzustellen, dass ein Paar von Testbenutzern in einer Konferenz unter Verwendung der Unified Communications-Web-API (UCWA) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b6a5a-138">Ausführliche Informationen zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="b6a5a-139">Problembehandlung bei der Plug-in-Installation auf Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b6a5a-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="b6a5a-140">Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Einstellung Internet Explorer Security oder die Einstellung des Registrierungsschlüssels DisableMSI ändern.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="b6a5a-141">**Ändern der Sicherheitseinstellung in Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="b6a5a-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="b6a5a-142">Öffnen Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="b6a5a-143">Klicken Sie auf **Extras**, dann auf **Internetoptionen** und anschließend auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="b6a5a-144">Führen Sie einen Bildlauf zum Bereich **Sicherheit** durch.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="b6a5a-145">Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b6a5a-146">Wenn diese Einstellung aktiviert ist, tritt bei dem Versuch, eine Anlage aus lync Web App herunterzuladen, auch ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="b6a5a-147">Nehmen Sie an der Besprechung erneut teil.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-147">Rejoin the meeting.</span></span> <span data-ttu-id="b6a5a-148">Das Plug-In sollte ohne Fehler Elemente herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="b6a5a-149">**Ändern der "DisableMSI"-Registrierungseinstellung**</span><span class="sxs-lookup"><span data-stu-id="b6a5a-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="b6a5a-150">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="b6a5a-151">Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="b6a5a-152">Navigieren Sie zu\_HKEY\_local\\Machine\\Software\\\\Policies\\Microsoft Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="b6a5a-153">Bearbeiten oder fügen Sie den Registrierungsschlüssel DisableMSI vom Typ\_reg DWORD hinzu, und legen Sie ihn auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="b6a5a-154">Nehmen Sie an der Besprechung erneut teil.</span><span class="sxs-lookup"><span data-stu-id="b6a5a-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b6a5a-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6a5a-155">See Also</span></span>


[<span data-ttu-id="b6a5a-156">Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6a5a-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="b6a5a-157">Lync Web App unterstützte Plattformen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6a5a-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

