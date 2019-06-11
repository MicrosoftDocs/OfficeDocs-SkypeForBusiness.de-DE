---
title: 'Lync Server 2013: Bereitstellen der lync Windows Store-App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b22880b230acda74c7485010550d5576ea200c61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="20405-102">Bereitstellen der lync Windows Store-App in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20405-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20405-103">_**Letztes Änderungsdatum des Themas:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="20405-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="20405-104">Bevor Sie die lync Windows Store-App für Benutzer verfügbar machen, stellen Sie sicher, dass Ihre Bereitstellung die [lync Windows Store-App-Anforderungen für lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="20405-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="20405-105">Details zum Konfigurieren von lync Server 2013 zur Unterstützung der lync Windows Store-App finden Sie im NextHop-Blog Artikel "lync Server-AutoErmittlung und der lync Windows [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Store-App" unter.</span><span class="sxs-lookup"><span data-stu-id="20405-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="20405-106">Nachdem Sie die Server Umgebung ordnungsgemäß konfiguriert haben, können Sie die Benutzer anweisen, die lync-App aus dem Windows Store herunterzuladen, indem Sie nach "lync" suchen.</span><span class="sxs-lookup"><span data-stu-id="20405-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="20405-107">Aktivieren der mehrstufigen Authentifizierung für die lync Windows Store-App</span><span class="sxs-lookup"><span data-stu-id="20405-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="20405-108">Kumulative Updates für lync Server 2013: Juni 2013 fügt Unterstützung für die mehrstufige Authentifizierung für lync Windows Store-App-Clients hinzu.</span><span class="sxs-lookup"><span data-stu-id="20405-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="20405-109">Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins anfordern, um externe Benutzer bei der Anmeldung bei lync-Besprechungen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="20405-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="20405-110">Zum Aktivieren der mehrstufigen Authentifizierung stellen Sie den Active Directory Federation Service (AD FS)-Verbundserver bereit, und aktivieren Sie die passive Authentifizierung in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20405-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="20405-111">Nach der Konfiguration von AD FS werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-Website mit mehrstufiger Authentifizierung angezeigt, die die Herausforderung Benutzername und Kennwort zusammen mit allen weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält. .</span><span class="sxs-lookup"><span data-stu-id="20405-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="20405-112">Im folgenden sind wichtige Überlegungen zu berücksichtigen, wenn Sie die Konfiguration von AD FS für die mehrstufige Authentifizierung für die lync Windows Store-App planen:</span><span class="sxs-lookup"><span data-stu-id="20405-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="20405-113">Lync Server 2013 mit kumulativen Updates für lync Server 2013: Juni 2013 ist mindestens erforderlich.</span><span class="sxs-lookup"><span data-stu-id="20405-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="20405-114">Lync 2013-Desktop Clients erfordern keine kumulativen Updates für lync Server 2013: Juni 2013, daher kann es vorkommen, dass die passive Authentifizierung funktioniert, weil lync 2013-Clients authentifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="20405-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="20405-115">Der Authentifizierungsprozess für lync Windows Store-App-Clients wird jedoch nicht abgeschlossen, und es wird keine Benachrichtigung oder Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20405-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="20405-116">Der Server muss so konfiguriert sein, dass die passive Authentifizierung der einzige von Ihnen bereitgestellte Authentifizierungstyp ist.</span><span class="sxs-lookup"><span data-stu-id="20405-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="20405-117">Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Beibehaltung von Cookies auf den Lastenausgleichsgeräten, damit alle Anforderungen vom lync Windows Store-App-Client vom gleichen Front-End-Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="20405-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="20405-118">Wenn Sie eine vertrauende Vertrauensstellung zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die lang genug ist, um die maximale Länge ihrer lync-Besprechungen zu überspannen.</span><span class="sxs-lookup"><span data-stu-id="20405-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="20405-119">Normalerweise genügt eine Tokengültigkeitsdauer von 240 Minuten.</span><span class="sxs-lookup"><span data-stu-id="20405-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="20405-120">**So konfigurieren Sie die mehrstufige Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="20405-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="20405-121">Installieren Sie eine AD FS-Verbundserverrolle.</span><span class="sxs-lookup"><span data-stu-id="20405-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="20405-122">Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory-Verbund <http://go.microsoft.com/fwlink/p/?linkid=267511>Dienste 2,0 unter.</span><span class="sxs-lookup"><span data-stu-id="20405-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="20405-123">Erstellen Sie Zertifikate für AD FS.</span><span class="sxs-lookup"><span data-stu-id="20405-123">Create certificates for AD FS.</span></span> <span data-ttu-id="20405-124">Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" im Abschnitt Planen und Bereitstellen von AD FS für die Verwendung mit dem Thema für einmaliges [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)anmelden unter.</span><span class="sxs-lookup"><span data-stu-id="20405-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="20405-125">Führen Sie über die Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="20405-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    
        add-pssnapin Microsoft.Adfs.powershell

4.  <span data-ttu-id="20405-126">Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:</span><span class="sxs-lookup"><span data-stu-id="20405-126">Establish a partnership by running the following command:</span></span>
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  <span data-ttu-id="20405-127">Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:</span><span class="sxs-lookup"><span data-stu-id="20405-127">Set the following relying party rules:</span></span>
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="20405-128">Bekannte Probleme, die eine Anmeldung verhindern können</span><span class="sxs-lookup"><span data-stu-id="20405-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="20405-129">Die Uhrzeit und das Datum sind auf dem Gerät, auf dem die lync Windows Store-App ausgeführt wird, nicht genau eingestellt.</span><span class="sxs-lookup"><span data-stu-id="20405-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="20405-130">Die Zeiteinstellung auf dem Gerät muss mit der Zeiteinstellung auf dem Server synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="20405-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="20405-131">Dies ist besonders wichtig für Geräte wie Microsoft Surface und andere Geräte mit Windows RT, die nicht mit einer Domäne verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="20405-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="20405-132">Wenn Sie die Uhrzeit auf diesen Geräten automatisch von einem Zeitserver einstellen möchten, führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten auf dem Gerät aus:</span><span class="sxs-lookup"><span data-stu-id="20405-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>

    w32tm /resync

</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="20405-133">Lync Windows Store-App kann nicht auf lync-Server oder-Dienste zugreifen</span><span class="sxs-lookup"><span data-stu-id="20405-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="20405-134">Die lync Windows Store-App kann möglicherweise nicht über Netzwerkadapter, wie etwa 4G LTE-USB-Modems, auf lync-Server oder-Dienste zugreifen, die nicht bei Windows 8 als physikalische Geräte registriert sind.</span><span class="sxs-lookup"><span data-stu-id="20405-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="20405-135">Bei der lync Windows Store-App kann dieses Problem auftreten, selbst wenn die Desktop-Apps und Browser auf andere Server und Websites zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="20405-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="20405-136">Lync Windows Store-App kann sich nicht mit lync Server 2010 und Office Communications Server 2007 R2 Edge-Server anmelden</span><span class="sxs-lookup"><span data-stu-id="20405-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="20405-137">Wenn Ihre Topologie aus lync Server 2010 mit Office Communications Server 2007 R2 Edge Server besteht, müssen Sie die aktualisierte Version des Topologie-Generators ausführen, die im kumulativen Update für lync Server 2010: Juli 2013 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="20405-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="20405-138">In früheren Versionen des Topologie-Generators wird nicht die erforderliche Zuordnung zu Office Communications Server 2007-Edgeserver erstellt, sodass sich lync Windows Store-App-Clients nicht anmelden können.</span><span class="sxs-lookup"><span data-stu-id="20405-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="20405-139">Die folgenden Schritte sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="20405-139">The following steps are required:</span></span>

1.  <span data-ttu-id="20405-140">Installieren Sie das kumulative Update für lync Server 2010: Juli 2013 in lync Server 2010-Pools und lync Server 2010-Directors.</span><span class="sxs-lookup"><span data-stu-id="20405-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="20405-141">Aktualisieren Sie die lync-AutoErmittlungskonfiguration, um anzugeben, dass der externe SIP-Einstiegspunkt die Edgeserver-Adresse ist, indem Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="20405-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="20405-142">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="20405-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="20405-143">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="20405-143">Run the following command:</span></span>
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="20405-144">Die lync Windows Store-App kann aufgrund eines Zertifikatsnamen-Validierungsfehlers nicht angemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="20405-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="20405-145">Ein Anmeldeproblem kann für Office 365-Benutzer auftreten, die nicht die neueste Version der lync Windows Store-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="20405-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="20405-146">Dieses Problem tritt in der Regel bei der Verwendung mehrerer Domänen auf (beispielsweise, wenn der SIP-URI **UserA@domainZ.com** ist, der Edgeserver aber **SIP.domainX.com**ist).</span><span class="sxs-lookup"><span data-stu-id="20405-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="20405-147">Um das Problem zu beheben, sollten Benutzer die neueste Version der lync Windows Store-App installieren, für die auch Windows 8,1 erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="20405-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="20405-148">Verwenden von lync Windows Store-App-Protokollen zur Behandlung von Problemen</span><span class="sxs-lookup"><span data-stu-id="20405-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="20405-149">Sie können die auf dem Gerät generierten Protokolle verwenden, um Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="20405-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="20405-150">Die Protokolle werden im folgenden Ordner gespeichert:</span><span class="sxs-lookup"><span data-stu-id="20405-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="20405-151">% LocalAppData%\\Pakete\\Microsoft. LyncMX\_8wekyb3d8bbwe\\LocalState\\-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="20405-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="20405-152">Bevor Sie die Protokolle eines Benutzers abrufen, stellen Sie sicher, dass die Protokollierung aktiviert ist, und bitten Sie den Benutzer, die Protokolle zu speichern, damit alle im Arbeitsspeicher gespeicherten Informationen auch in Dateien auf der Festplatte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="20405-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="20405-153">**So aktivieren Sie die Protokollierung**</span><span class="sxs-lookup"><span data-stu-id="20405-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="20405-154">Öffnen Sie die lync Windows Store-App auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="20405-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="20405-155">Wischen Sie auf der rechten Seite des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="20405-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="20405-156">Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="20405-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="20405-157">Wählen Sie **Einstellungen**aus, wählen Sie **Optionen**aus, und legen Sie dann **Diagnoseprotokolle** auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="20405-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="20405-158">Wenn **Diagnoseprotokolle** zuvor deaktiviert wurden, müssen Sie lync erneut starten.</span><span class="sxs-lookup"><span data-stu-id="20405-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="20405-159">Führen Sie eine der folgenden Aktionen aus, um lync erneut zu starten:</span><span class="sxs-lookup"><span data-stu-id="20405-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="20405-160">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="20405-160">Restart the device.</span></span>
    
      - <span data-ttu-id="20405-161">Beenden Sie die lync-Aufgabe, und starten Sie die APP erneut.</span><span class="sxs-lookup"><span data-stu-id="20405-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="20405-162">Um die Aufgabe zu beenden, öffnen Sie den Windows Task-Manager, wählen Sie **lync**aus, und tippen Sie dann auf **Aufgabe beenden**.</span><span class="sxs-lookup"><span data-stu-id="20405-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="20405-163">Wenn lync nicht aufgeführt ist, tippen Sie auf **Weitere Details** , und suchen Sie unter **Hintergrundprozesse**nach lync.</span><span class="sxs-lookup"><span data-stu-id="20405-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="20405-164">**So speichern Sie die Protokolle**</span><span class="sxs-lookup"><span data-stu-id="20405-164">**To save the logs**</span></span>

1.  <span data-ttu-id="20405-165">Öffnen Sie die lync Windows Store-App auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="20405-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="20405-166">Versuchen Sie, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="20405-166">Try signing in.</span></span>

3.  <span data-ttu-id="20405-167">Wischen Sie auf der rechten Seite des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="20405-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="20405-168">Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="20405-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="20405-169">Wählen Sie **Einstellungen**aus, wählen Sie **Info**aus, und wählen Sie dann **Protokolle speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="20405-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

