---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging in Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="c94e3-102">Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c94e3-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c94e3-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c94e3-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c94e3-104">In diesem Thema wird beschrieben, wie Sie Exchange Unified Messaging (um) auf einem Microsoft Exchange-Server für die Verwendung mit Enterprise-VoIP konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c94e3-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c94e3-105">Die Cmdlet-Beispiele in diesem Thema enthalten Syntax für die Exchange 2007-Version der Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c94e3-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="c94e3-106">Wenn Sie Exchange 2010 oder Exchange 2013 ausführen, lesen Sie die entsprechende Dokumentation, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c94e3-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="c94e3-107">So konfigurieren Sie einen Server mit Exchange Server um</span><span class="sxs-lookup"><span data-stu-id="c94e3-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="c94e3-108">Erstellen Sie einen SIP-Wählplan (Uniform Resource Identifier) für jedes Ihrer Enterprise-VoIP-Standortprofile.</span><span class="sxs-lookup"><span data-stu-id="c94e3-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="c94e3-109">Wenn Sie die Exchange-Verwaltungskonsole verwenden möchten, erstellen Sie einen neuen Wählplan, wobei die Sicherheitseinstellung **gesichert (bevorzugt)** ist.</span><span class="sxs-lookup"><span data-stu-id="c94e3-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c94e3-110">Wenn Sie den Wert für die Sicherheitseinstellung auf <STRONG>SIP secured</STRONG> festgelegt haben, um die Verschlüsselung für den SIP-Datenverkehr zu erzwingen, wie zuvor empfohlen, beachten Sie, dass diese Sicherheitseinstellung für einen Wählplan unzureichend ist, wenn der Front-End-Pool so konfiguriert ist, dass eine Verschlüsselung erforderlich ist, was bedeutet, dass der Pool für SIP-und RTP-Datenverkehr verschlüsselt</span><span class="sxs-lookup"><span data-stu-id="c94e3-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="c94e3-111">Wenn die Sicherheitseinstellungen für Wählplan und Pool nicht kompatibel sind, schlagen alle Anrufe an Exchange um aus dem Front-End-Pool fehl, was zu einem Fehler führt, der besagt, dass Sie über eine "inkompatible Sicherheitseinstellung" verfügen.</span><span class="sxs-lookup"><span data-stu-id="c94e3-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="c94e3-112">Wenn Sie die Exchange-Verwaltungsshell verwenden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c94e3-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="c94e3-113">Ausführliche Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="c94e3-113">For details, see:</span></span>
    
      - <span data-ttu-id="c94e3-114">Informationen zu Office Communications Server 2007 finden Sie unter "Erstellen eines SIP-URI [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) -Wählplans für Unified Messaging" unter und "neu-UMDialplan: [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)Exchange 2007-Hilfe" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="c94e3-115">Informationen zu Exchange 2010 finden Sie unter "Erstellen eines um-Wählplans" [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) und unter "neu-UMDialplan: [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)Exchange 2010-Hilfe" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="c94e3-116">Informationen zu Exchange 2013 finden Sie unter "Unified Messaging [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c94e3-117">Ob Sie eine Sicherheitsstufe von <STRONG>SIPSecured</STRONG> oder <STRONG>gesichert</STRONG> auswählen, hängt davon ab, ob SRTP (Secure Real-Time Transport Protocol) für die Medienverschlüsselung aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c94e3-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="c94e3-118">Bei der lync Server 2010-Integration in Exchange um sollte dies der Verschlüsselungsstufe in der lync Server Media-Konfiguration entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c94e3-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="c94e3-119">Die lync Server Media-Konfiguration kann angezeigt werden, indem Sie das Cmdlet " <STRONG>Get-CsMediaConfiguration</STRONG> " ausführen.</span><span class="sxs-lookup"><span data-stu-id="c94e3-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="c94e3-120">Ausführliche Informationen finden Sie unter Get-CsMediaConfiguration in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c94e3-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="c94e3-121">Details zum Auswählen der geeigneten VoIP-Sicherheitseinstellung finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Bereitstellungsprozess für die Integration von lokalen Unified Messaging und lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c94e3-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="c94e3-122">Führen Sie das folgende Cmdlet aus, um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die einzelnen um-Wähleinstellungen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="c94e3-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="c94e3-123">Ausführliche Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="c94e3-123">For details, see:</span></span>
    
      - <span data-ttu-id="c94e3-124">Informationen zu Exchange 2007 finden Sie unter "Get-UMDialplan: Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)2007-Hilfe" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="c94e3-125">Informationen zu Exchange 2010 finden Sie unter "Get-UMDialplan: Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)2010-Hilfe" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="c94e3-126">Informationen zu Exchange 2013 finden Sie unter "Unified Messaging [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="c94e3-127">Notieren Sie den Namen des Wähl Plans für jeden um-Wählplan.</span><span class="sxs-lookup"><span data-stu-id="c94e3-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="c94e3-128">Je nach ihrer Version von Exchange Server müssen Sie möglicherweise den FQDN für jeden Wählplan später als Namen für den entsprechenden lync Server-Wählplan für den Wählplan verwenden, damit die Wähl Plan Namen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c94e3-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c94e3-129">Namen von lync Server-Wählplänen müssen nur dann mit um-Wähl Plan Namen übereinstimmen, wenn der um-Wählplan unter einer <EM>früheren</EM> Exchange-Version als Exchange 2010 SP1 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c94e3-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="c94e3-130">Fügen Sie den Wählplan dem Server mit Exchange um wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="c94e3-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="c94e3-131">Wenn Sie die Exchange-Verwaltungskonsole verwenden, können Sie den Wählplan über das Eigenschaftenfenster für den Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c94e3-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="c94e3-132">Spezifische Anweisungen finden Sie in der Exchange Server-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c94e3-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="c94e3-133">Informationen zu Exchange 2007 finden Sie unter "Hinzufügen eines Unified Messaging-Servers zu einem Wählplan [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="c94e3-134">Informationen zu Exchange 2010 finden Sie unter "anzeigen oder Konfigurieren der Eigenschaften eines um [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)-Servers" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="c94e3-135">Informationen zu Exchange 2013 finden Sie unter "Unified Messaging [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="c94e3-136">Wenn Sie die Exchange-Verwaltungsshell verwenden, führen Sie für jeden Ihrer Exchange um-Server die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c94e3-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c94e3-137">Bevor Sie den folgenden Schritt ausführen, stellen Sie sicher, dass alle Enterprise-VoIP-Benutzer mit einem Exchange Server-Postfach konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="c94e3-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="c94e3-138">Informationen zu Exchange 2007 finden Sie in <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>der TechNet-Bibliothek Exchange Server 2007 unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="c94e3-139">Informationen zu Exchange 2010 finden Sie in <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>der TechNet-Bibliothek Exchange Server 2010 unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="c94e3-140">Wenn Sie eine Postfachrichtlinie für jeden Wählplan angeben, den Sie in Schritt 1 erstellt haben, wählen Sie entweder die Standardrichtlinie oder eine aus, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c94e3-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="c94e3-141">Navigieren Sie \<zu Exchange-\>\\Installationsverzeichnis Skripts, und geben Sie Folgendes ein, wenn Exchange in einer einzelnen Gesamtstruktur bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="c94e3-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="c94e3-142">Wenn Exchange in mehreren Gesamtstrukturen bereitgestellt wird, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c94e3-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="c94e3-143">wobei Gesamtstruktur-FQDN die Gesamtstruktur angibt, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c94e3-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="c94e3-144">Wenn Sie über einen oder mehrere um-Wählpläne verfügen, die mehreren IP-Gateways zugeordnet sind, fahren Sie mit Schritt 6 fort.</span><span class="sxs-lookup"><span data-stu-id="c94e3-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="c94e3-145">Wenn Ihre Wählpläne jeweils nur einem einzigen IP-Gateway zugeordnet sind, überspringen Sie Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="c94e3-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c94e3-146">Stellen Sie sicher, dass der <STRONG>lync Server-Front-End-</STRONG> Dienst (RtcSrv. exe) <EM>nach</EM> der Ausführung von exchucutil. ps1 neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c94e3-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="c94e3-147">Andernfalls erkennt lync Server keine Unified Messaging-Funktion in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="c94e3-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="c94e3-148">Deaktivieren Sie entweder über die Exchange-Verwaltungsshell oder die Exchange-Verwaltungskonsole ausgehende Anrufe für alle IP-Gateways, die mit den einzelnen Wählplänen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c94e3-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c94e3-149">Dieser Schritt ist erforderlich, um sicherzustellen, dass ausgehende Anrufe des Servers, auf dem Exchange Server Unified Messaging ausgeführt wird, für externe Benutzer (beispielsweise wie bei Szenarien mit Wiedergabe auf dem Smartphone) die Unternehmensfirewall zuverlässig durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="c94e3-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c94e3-150">Wenn Sie das um-IP-Gateway auswählen, über das ausgehende Anrufe zugelassen werden sollen, wählen Sie diejenige aus, die wahrscheinlich den meisten Datenverkehr verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c94e3-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="c94e3-151">Lassen Sie ausgehenden Datenverkehr nicht über ein IP-Gateway zu, das eine Verbindung mit einem Pool von lync Server Directors herstellt.</span><span class="sxs-lookup"><span data-stu-id="c94e3-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="c94e3-152">Vermeiden Sie auch Pools in einem anderen zentralen Standort oder einer Zweigstelle.</span><span class="sxs-lookup"><span data-stu-id="c94e3-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="c94e3-153">Sie können eine der folgenden Methoden verwenden, um ausgehende Anrufe zu blockieren, indem Sie ein IP-Gateway durchlaufen:</span><span class="sxs-lookup"><span data-stu-id="c94e3-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="c94e3-154">Wenn Sie die Exchange-Verwaltungsshell verwenden, deaktivieren Sie die einzelnen IP-Gateways, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="c94e3-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="c94e3-155">Informationen zu Exchange 2007 finden Sie unter "einrichten-UMIPGateway: Exchange 2007- [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)Hilfe" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="c94e3-156">Informationen zu Exchange 2010 finden Sie unter "einrichten-UMIPGateway: Exchange 2010- [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)Hilfe" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="c94e3-157">Wenn Sie die Exchange-Verwaltungskonsole verwenden, deaktivieren Sie das Kontrollkästchen **ausgehende Anrufe über dieses IP-Gateway zulassen** .</span><span class="sxs-lookup"><span data-stu-id="c94e3-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c94e3-158">Wenn Ihr um-SIP-URI-Wählplan nur einem einzigen IP-Gateway zugeordnet ist, dürfen Sie ausgehende Anrufe über dieses Gateway nicht unterbinden.</span><span class="sxs-lookup"><span data-stu-id="c94e3-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="c94e3-159">Erstellen Sie für jeden lync Server-Wählplan eine automatische UM-Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="c94e3-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c94e3-160">Schließen Sie keine Leerzeichen in den Namen der automatischen Telefonzentrale ein.</span><span class="sxs-lookup"><span data-stu-id="c94e3-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="c94e3-161">Ausführliche Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="c94e3-161">For details, see:</span></span>
    
      - <span data-ttu-id="c94e3-162">Informationen zu Exchange 2007 finden Sie unter "New-UMAutoAttendant: Exchange 2007 Help [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="c94e3-163">Informationen zu Exchange 2010 finden Sie unter "New-UMAutoAttendant: Exchange 2010 Help [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="c94e3-164">Der folgende Schritt sollte für jeden Benutzer ausgeführt werden, nachdem Sie lync Server-Benutzer für Enterprise-VoIP aktiviert haben und deren SIP-URIs kennen.</span><span class="sxs-lookup"><span data-stu-id="c94e3-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="c94e3-165">Ordnen Sie Exchange um-Benutzern (die jeweils mit einem Exchange-e-Mail-Feld konfiguriert werden sollten) mit dem um-Wählplan zu, und erstellen Sie einen SIP-URI für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c94e3-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c94e3-166">Die <STRONG>SIPResourceIdentifier</STRONG> im folgenden Beispiel muss die SIP-Adresse des lync Server-Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="c94e3-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="c94e3-167">Ausführliche Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="c94e3-167">For details, see:</span></span>
    
      - <span data-ttu-id="c94e3-168">Informationen zu Exchange 2007 finden Sie unter "Enable-UMMailbox: Exchange 2007 Help [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="c94e3-169">Informationen zu Exchange 2010 finden Sie unter "Enable-UMMailbox: Exchange 2010 Help [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)" unter.</span><span class="sxs-lookup"><span data-stu-id="c94e3-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

