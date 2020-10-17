---
title: 'Lync Server 2013: Bereitstellen der lync Windows Store-App'
description: 'Lync Server 2013: Bereitstellen der lync Windows Store-App.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9260d656079fb694a14aadf5049ca36241830c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571711"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="23eca-103">Bereitstellen der lync Windows Store-App in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23eca-103">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23eca-104">_**Letztes Änderungsstand des Themas:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="23eca-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="23eca-105">Bevor Sie die lync Windows Store-App für Benutzer verfügbar machen, müssen Sie sicherstellen, dass Ihre Bereitstellung die [lync Windows Store-App-Anforderungen für lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="23eca-105">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="23eca-106">Ausführliche Informationen zum Konfigurieren von lync Server 2013 zur Unterstützung der lync Windows Store-App finden Sie im NextHop-Blog Artikel "lync Server AutoErmittlung und der lync Windows Store-App" unter [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) .</span><span class="sxs-lookup"><span data-stu-id="23eca-106">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="23eca-107">Nachdem die Server Umgebung ordnungsgemäß konfiguriert wurde, können Sie Benutzer anweisen, die lync-App aus dem Windows Store herunterzuladen, indem Sie nach "lync" suchen.</span><span class="sxs-lookup"><span data-stu-id="23eca-107">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="23eca-108">Aktivieren der mehrstufigen Authentifizierung für lync Windows Store-App</span><span class="sxs-lookup"><span data-stu-id="23eca-108">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="23eca-109">Kumulative Updates für lync Server 2013: Juni 2013 fügt Unterstützung für mehrstufige Authentifizierung für lync Windows Store-App-Clients hinzu.</span><span class="sxs-lookup"><span data-stu-id="23eca-109">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="23eca-110">Neben Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins zur Authentifizierung externer Benutzer bei der Anmeldung an lync-Besprechungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="23eca-110">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="23eca-111">Zum Aktivieren der mehrstufigen Authentifizierung stellen Sie Active Directory Verbunddienst (AD FS)-Verbundserver bereit und aktivieren die passive Authentifizierung in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23eca-111">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="23eca-112">Nachdem AD FS konfiguriert wurde, werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-mehrstufigen Authentifizierungs Webseite angezeigt, die den Benutzernamen und die Kennwortabfrage sowie alle weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält.</span><span class="sxs-lookup"><span data-stu-id="23eca-112">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="23eca-113">Im folgenden sind wichtige Überlegungen aufgeführt, wenn Sie AD FS für die mehrstufige Authentifizierung für die lync Windows Store-App konfigurieren möchten:</span><span class="sxs-lookup"><span data-stu-id="23eca-113">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="23eca-114">Lync Server 2013 mit kumulativen Updates für lync Server 2013: Juni 2013 wird mindestens benötigt.</span><span class="sxs-lookup"><span data-stu-id="23eca-114">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="23eca-115">Lync 2013 Desktop Clients keine kumulativen Updates für lync Server 2013: Juni 2013 benötigen, scheint es möglicherweise, dass die passive Authentifizierung funktioniert, da sich lync 2013 Clients authentifizieren können.</span><span class="sxs-lookup"><span data-stu-id="23eca-115">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="23eca-116">Der Authentifizierungsprozess für lync Windows Store-App-Clients kann jedoch nicht abgeschlossen werden, und es wird keine Benachrichtigung oder Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23eca-116">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="23eca-117">Der Server muss so konfiguriert werden, dass die passive Authentifizierung der einzige verfügbare Authentifizierungstyp ist.</span><span class="sxs-lookup"><span data-stu-id="23eca-117">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="23eca-118">Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies für die Lastenausgleichsmodule, damit alle Anforderungen vom lync Windows Store-App-Client von derselben Front-End-Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="23eca-118">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="23eca-119">Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die sich über die maximale Länge ihrer lync-Besprechungen erstrecken kann.</span><span class="sxs-lookup"><span data-stu-id="23eca-119">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="23eca-120">Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.</span><span class="sxs-lookup"><span data-stu-id="23eca-120">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="23eca-121">**Konfigurieren der mehrstufigen Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="23eca-121">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="23eca-122">Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle.</span><span class="sxs-lookup"><span data-stu-id="23eca-122">Install an AD FS federation server role.</span></span> <span data-ttu-id="23eca-123">Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory Verbunddienste 2,0 unter <https://go.microsoft.com/fwlink/p/?linkid=267511> .</span><span class="sxs-lookup"><span data-stu-id="23eca-123">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="23eca-124">Erstellen von Zertifikaten für AD FS.</span><span class="sxs-lookup"><span data-stu-id="23eca-124">Create certificates for AD FS.</span></span> <span data-ttu-id="23eca-125">Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" des Themas planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden unter [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="23eca-125">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="23eca-126">Führen Sie über die Befehlszeilenschnittstelle Windows PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="23eca-126">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="23eca-127">Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:</span><span class="sxs-lookup"><span data-stu-id="23eca-127">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="23eca-128">Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:</span><span class="sxs-lookup"><span data-stu-id="23eca-128">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="23eca-129">Bekannte Probleme, die die Anmeldung verhindern können</span><span class="sxs-lookup"><span data-stu-id="23eca-129">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="23eca-130">Die Uhrzeit und das Datum werden auf dem Gerät, auf dem die lync Windows Store-App läuft, nicht genau festgelegt.</span><span class="sxs-lookup"><span data-stu-id="23eca-130">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="23eca-131">Die Zeiteinstellung auf dem Gerät muss mit der Zeiteinstellung auf dem Server synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="23eca-131">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="23eca-132">Dies ist insbesondere für Geräte wie Microsoft Surface und andere Geräte mit Windows RT wichtig, die nicht mit einer Domäne verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="23eca-132">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="23eca-133">Um die Uhrzeit auf diesen Geräten automatisch von einem Zeitserver festzulegen, führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten auf dem Gerät aus:</span><span class="sxs-lookup"><span data-stu-id="23eca-133">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="23eca-134">Lync Windows Store-App kann nicht auf lync Server oder Dienste zugreifen</span><span class="sxs-lookup"><span data-stu-id="23eca-134">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="23eca-135">Die lync Windows Store-App kann möglicherweise nicht über Netzwerkadapter wie 4G LTE-USB-Modems auf lync Server oder-Dienste zugreifen, die sich nicht bei Windows 8 als physikalische Geräte registrieren können.</span><span class="sxs-lookup"><span data-stu-id="23eca-135">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="23eca-136">Die lync Windows Store-App hat dieses Problem möglicherweise auch dann, wenn die Desktop-Apps und Browser auf andere Server und Websites zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="23eca-136">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="23eca-137">Die lync Windows Store-App kann sich nicht mit lync Server 2010 und Office Communications Server 2007 R2 anmelden Edgeserver</span><span class="sxs-lookup"><span data-stu-id="23eca-137">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="23eca-138">Wenn Ihre Topologie aus lync Server 2010 mit Office Communications Server 2007 R2 Edgeserver besteht, müssen Sie die aktualisierte Version des Topologie-Generators ausführen, die im kumulativen Update für lync Server 2010: July 2013 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="23eca-138">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="23eca-139">In früheren Versionen des Topologie-Generators wird nicht die erforderliche Zuordnung zu Office Communications Server 2007 Edgeserver erstellt, sodass lync Windows Store-App-Clients sich nicht anmelden können.</span><span class="sxs-lookup"><span data-stu-id="23eca-139">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="23eca-140">Die folgenden Schritte sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="23eca-140">The following steps are required:</span></span>

1.  <span data-ttu-id="23eca-141">Installieren Sie das kumulative Update für lync Server 2010: Juli 2013 auf lync Server 2010 Pools und lync Server 2010 Directors.</span><span class="sxs-lookup"><span data-stu-id="23eca-141">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="23eca-142">Aktualisieren Sie die lync-AutoErmittlungskonfiguration, um anzugeben, dass der externe SIP-Einstiegspfad die Edgeserver-Adresse ist, indem Sie folgendermaßen vorgehen:</span><span class="sxs-lookup"><span data-stu-id="23eca-142">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="23eca-143">Öffnen Sie lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="23eca-143">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="23eca-144">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="23eca-144">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="23eca-145">Lync Windows Store-App kann sich aufgrund eines Zertifikatsnamen Überprüfungsfehlers nicht anmelden</span><span class="sxs-lookup"><span data-stu-id="23eca-145">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="23eca-146">Ein Anmeldeproblem kann für Microsoft 365 oder Office 365 Benutzer auftreten, die nicht die neueste Version der lync Windows Store-App ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="23eca-146">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="23eca-147">Dieses Problem tritt im Allgemeinen auf, wenn mehrere Domänen verwendet werden (beispielsweise, wenn der SIP-URI **UserA@domainZ.com** ist, die Edgeserver jedoch **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="23eca-147">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="23eca-148">Um das Problem zu beheben, sollten Benutzer die neueste Version der lync Windows Store-App installieren, die auch Windows 8.1 erfordert.</span><span class="sxs-lookup"><span data-stu-id="23eca-148">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="23eca-149">Verwenden von lync Windows Store-App-Protokollen zur Behandlung von Problemen</span><span class="sxs-lookup"><span data-stu-id="23eca-149">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="23eca-150">Sie können die auf dem Gerät generierten Protokolle verwenden, um Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="23eca-150">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="23eca-151">Die Protokolle werden im folgenden Ordner gespeichert:</span><span class="sxs-lookup"><span data-stu-id="23eca-151">The logs are stored in the following folder:</span></span>

<span data-ttu-id="23eca-152">% LocalAppData% \\ Pakete \\ Microsoft. LyncMX \_ 8wekyb3d8bbwe \\ LocalState- \\ Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="23eca-152">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="23eca-153">Bevor Sie die Protokolle von einem Benutzer erhalten, stellen Sie sicher, dass die Protokollierung aktiviert ist, und bitten Sie den Benutzer, die Protokolle zu speichern, damit alle im Arbeitsspeicher gespeicherten Informationen auch in Dateien auf der Festplatte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="23eca-153">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="23eca-154">**So aktivieren Sie die Protokollierung**</span><span class="sxs-lookup"><span data-stu-id="23eca-154">**To turn on logging**</span></span>

1.  <span data-ttu-id="23eca-155">Öffnen Sie die lync Windows Store-App auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="23eca-155">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="23eca-156">Streichen Sie von der rechten Seite des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="23eca-156">Swipe from the right side of the screen.</span></span> <span data-ttu-id="23eca-157">Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="23eca-157">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="23eca-158">Wählen Sie **Einstellungen**aus, wählen Sie **Optionen**aus, und legen Sie dann **Diagnoseprotokolle** **auf ein**fest.</span><span class="sxs-lookup"><span data-stu-id="23eca-158">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="23eca-159">Wenn **Diagnoseprotokolle** zuvor deaktiviert waren, müssen Sie lync neu starten.</span><span class="sxs-lookup"><span data-stu-id="23eca-159">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="23eca-160">Führen Sie einen der folgenden Schritte aus, um lync neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="23eca-160">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="23eca-161">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="23eca-161">Restart the device.</span></span>
    
      - <span data-ttu-id="23eca-162">Beenden Sie die lync-Aufgabe, und starten Sie die APP erneut.</span><span class="sxs-lookup"><span data-stu-id="23eca-162">End the Lync task and launch the app again.</span></span> <span data-ttu-id="23eca-163">Um die Aufgabe zu beenden, öffnen Sie den Windows-Task-Manager, wählen Sie **lync**aus, und tippen Sie dann auf **Aufgabe beenden**.</span><span class="sxs-lookup"><span data-stu-id="23eca-163">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="23eca-164">Wenn lync nicht aufgeführt ist, tippen Sie auf **Weitere Details** , und suchen Sie unter **Hintergrundprozesse**nach lync.</span><span class="sxs-lookup"><span data-stu-id="23eca-164">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="23eca-165">**So speichern Sie die Protokolle**</span><span class="sxs-lookup"><span data-stu-id="23eca-165">**To save the logs**</span></span>

1.  <span data-ttu-id="23eca-166">Öffnen Sie die lync Windows Store-App auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="23eca-166">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="23eca-167">Versuchen Sie, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="23eca-167">Try signing in.</span></span>

3.  <span data-ttu-id="23eca-168">Streichen Sie von der rechten Seite des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="23eca-168">Swipe from the right side of the screen.</span></span> <span data-ttu-id="23eca-169">Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="23eca-169">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="23eca-170">Wählen Sie **Einstellungen**aus, wählen Sie **Info**aus, und wählen Sie dann **Protokolle speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="23eca-170">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

