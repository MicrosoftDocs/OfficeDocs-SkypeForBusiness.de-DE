---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging für Microsoft Exchange'
description: 'Lync Server 2013: Configure Unified Messaging on Microsoft Exchange.'
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
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577521"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="938bd-103">Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="938bd-103">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="938bd-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="938bd-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="938bd-105">In diesem Thema wird beschrieben, wie Sie Exchange Unified Messaging (um) auf einem Exchange Server für die Verwendung mit Enterprise-VoIP konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="938bd-105">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="938bd-106">Die Cmdlet-Beispiele in diesem Thema bieten Syntax für die Exchange 2007 Version von Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="938bd-106">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="938bd-107">Wenn Sie Exchange 2010 oder Exchange 2013 betreiben, lesen Sie die entsprechende Dokumentation, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="938bd-107">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="938bd-108">So konfigurieren Sie einen Server mit Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="938bd-108">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="938bd-p102">Erstellen Sie einen Satz mit UM-SIP-URI-Wähleinstellungen (Session Initiation Protocol, SIP; Uniform Resource Identifier, URI) für jedes Enterprise-VoIP-Standortprofil. Wenn Sie sich zur Verwendung der Exchange-Verwaltungskonsole entscheiden, erstellen Sie neue Wähleinstellungen mit der Sicherheitseinstellung **Secured (bevorzugt)**.</span><span class="sxs-lookup"><span data-stu-id="938bd-p102">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles. If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="938bd-111">Wenn Sie den Wert für die Sicherheitseinstellung auf <STRONG>SIP-gesichert</STRONG> festlegen, um nur die Verschlüsselung für den SIP-Datenverkehr zu erzwingen (wie zuvor empfohlen), beachten Sie, dass diese Sicherheitseinstellung für einen Wählplan unzureichend ist, wenn der Front-End-Pool für die Verschlüsselung konfiguriert ist, was bedeutet, dass der Pool für SIP-und RTP-Datenverkehr verschlüsselt werden muss.</span><span class="sxs-lookup"><span data-stu-id="938bd-111">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="938bd-112">Wenn die Einstellungen für den Wählplan und die Pool Sicherheit nicht kompatibel sind, tritt bei allen Aufrufen von Exchange um aus dem Front-End-Pool ein Fehler auf, der darauf hinweist, dass eine "inkompatible Sicherheitseinstellung" vorliegt.</span><span class="sxs-lookup"><span data-stu-id="938bd-112">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="938bd-113">Wenn Sie die Exchange-Verwaltungsshell verwenden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="938bd-113">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="938bd-114">Ausführliche Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="938bd-114">For details, see:</span></span>
    
      - <span data-ttu-id="938bd-115">Informationen zu Office Communications Server 2007 finden Sie unter "Erstellen eines SIP-URI-Wählplans für Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) und "New-UMDialplan: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .</span><span class="sxs-lookup"><span data-stu-id="938bd-115">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="938bd-116">Informationen zum Exchange 2010 finden Sie unter "Erstellen eines um-Wählplans" unter [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) und "New-UMDialplan: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .</span><span class="sxs-lookup"><span data-stu-id="938bd-116">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="938bd-117">Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="938bd-117">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="938bd-118">Ob Sie die Sicherheitsstufe <STRONG>SIPSecured</STRONG> oder <STRONG>Secured</STRONG> auswählen, hängt davon ab, ob SRTP (Secure Real-time Transport Protocol) für die Medienverschlüsselung aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="938bd-118">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="938bd-119">Für die lync Server 2010 Integration in Exchange um sollte dies der Verschlüsselungsstufe in der lync Server Medienkonfiguration entsprechen.</span><span class="sxs-lookup"><span data-stu-id="938bd-119">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="938bd-120">Die lync Server Medienkonfiguration kann durch Ausführen des Cmdlets <STRONG>Get-CsMediaConfiguration</STRONG> angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="938bd-120">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="938bd-121">Ausführliche Informationen finden Sie unter Get-CsMediaConfiguration in der lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="938bd-121">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="938bd-122">Ausführliche Informationen zum Auswählen der geeigneten VoIP-Sicherheitseinstellung finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment Process for Integration on-premises Unified Messaging and lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="938bd-122">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="938bd-123">Führen Sie das folgende Cmdlet aus, um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die einzelnen UM-Wähleinstellungen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="938bd-123">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="938bd-124">Ausführliche Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="938bd-124">For details, see:</span></span>
    
      - <span data-ttu-id="938bd-125">Informationen zu Exchange 2007 finden Sie unter "Get-UMDialplan: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .</span><span class="sxs-lookup"><span data-stu-id="938bd-125">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="938bd-126">Informationen zu Exchange 2010 finden Sie unter "Get-UMDialplan: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .</span><span class="sxs-lookup"><span data-stu-id="938bd-126">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="938bd-127">Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="938bd-127">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="938bd-128">Notieren Sie die Namen aller UM-Wählpläne.</span><span class="sxs-lookup"><span data-stu-id="938bd-128">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="938bd-129">Je nach ihrer Version von Exchange Server müssen Sie möglicherweise den FQDN der einzelnen Wähl Plan Namen später als Namen für die entsprechenden lync Server Wähleinstellungen für die um-Wähleinstellungen verwenden, damit die Wähl Plan Namen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="938bd-129">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="938bd-130">Lync Server Wähl Plan Namen müssen nur dann mit um-Wähl Plan Namen übereinstimmen, wenn die um-Wähleinstellungen auf einer <EM>früheren</EM> Exchange-Version als Exchange 2010 SP1 durchführen.</span><span class="sxs-lookup"><span data-stu-id="938bd-130">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="938bd-131">Fügen Sie den Wählplan dem Server mit Exchange um wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="938bd-131">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="938bd-p106">Wenn Sie sich zur Verwendung der Exchange-Verwaltungskonsole entscheiden, können Sie die Wähleinstellungen aus der Eigenschaftenseite des Servers hinzufügen. Genaue Anweisungen finden Sie in der Exchange Server-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="938bd-p106">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server. For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="938bd-134">Informationen zum Exchange 2007 finden Sie unter "Hinzufügen eines Unified Messaging-Servers zu Wähleinstellungen" unter [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .</span><span class="sxs-lookup"><span data-stu-id="938bd-134">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="938bd-135">Informationen zu Exchange 2010 finden Sie unter "anzeigen oder Konfigurieren der Eigenschaften eines um-Servers" unter [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .</span><span class="sxs-lookup"><span data-stu-id="938bd-135">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="938bd-136">Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="938bd-136">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="938bd-137">Wenn Sie die Exchange-Verwaltungsshell verwenden, führen Sie für jeden Exchange UM-Server den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="938bd-137">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="938bd-138">Vergewissern Sie sich vor dem Ausführen des folgenden Schritts, dass für alle Enterprise-VoIP-Benutzer ein Exchange Server-Postfach konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="938bd-138">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="938bd-139">Informationen zu Exchange 2007 finden Sie in der Exchange Server 2007 TechNet-Bibliothek unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .</span><span class="sxs-lookup"><span data-stu-id="938bd-139">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="938bd-140">Informationen zu Exchange 2010 finden Sie in der Exchange Server 2010 TechNet-Bibliothek unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .</span><span class="sxs-lookup"><span data-stu-id="938bd-140">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="938bd-141">Wenn Sie eine Postfachrichtlinie für jeden in Schritt 1 erstellten Satz mit Wähleinstellungen festlegen, verwenden Sie entweder die Standardrichtlinie oder eine von Ihnen selbst erstellte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="938bd-141">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="938bd-142">Navigieren Sie zu \<Exchange installation directory\> \\ Skripts, und geben Sie Folgendes ein, wenn Exchange in einer einzelnen Gesamtstruktur bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="938bd-142">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="938bd-143">Oder geben Sie Folgendes ein, falls Exchange in mehreren Gesamtstrukturen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="938bd-143">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="938bd-144">Dabei gibt Gesamtstruktur-FQDN die Gesamtstruktur an, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="938bd-144">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="938bd-p107">Falls Sie über einen oder mehrere Sätze mit UM-Wähleinstellungen verfügen, die mehreren IP-Gateways zugeordnet sind, fahren Sie mit Schritt 6 fort. Falls Ihre Wähleinstellungen jeweils nur einem IP-Gateway zugeordnet sind, überspringen Sie Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="938bd-p107">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6. If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="938bd-147">Starten Sie den Dienst <STRONG>Lync Server Front-End</STRONG> (rtcsrv.exe) neu, <EM>nachdem</EM> Sie "exchucutil.ps1" ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="938bd-147">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="938bd-148">Andernfalls werden von lync Server Unified Messaging in der Topologie nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="938bd-148">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="938bd-149">Deaktivieren Sie über die Exchange-Verwaltungsshell oder -Verwaltungskonsole ausgehende Anrufe für alle IP-Gateways, mit Ausnahme des Ihren Wähleinstellungen zugeordneten IP-Gateways.</span><span class="sxs-lookup"><span data-stu-id="938bd-149">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="938bd-150">Dieser Schritt ist erforderlich, um sicherzustellen, dass ausgehende Anrufe des Servers, der Exchange Server Unified Messaging ausführt, an externe Benutzer (beispielsweise wie bei Szenarien mit "Play-on-Phone") zuverlässig die Unternehmensfirewall durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="938bd-150">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="938bd-151">Wählen Sie als UM-IP-Gateway für ausgehende Anrufe das Gerät aus, das voraussichtlich den meisten Datenverkehr verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="938bd-151">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="938bd-152">Lassen Sie ausgehenden Datenverkehr über ein IP-Gateway nicht zu, das eine Verbindung mit einem Pool von lync Server Directors herstellt.</span><span class="sxs-lookup"><span data-stu-id="938bd-152">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="938bd-153">Vermeiden Sie auch Pools an einem anderen zentralen Standort oder einem Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="938bd-153">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="938bd-154">Verhindern Sie mithilfe einer der folgenden Methoden, dass ausgehende Anrufe über ein IP-Gateway geleitet werden:</span><span class="sxs-lookup"><span data-stu-id="938bd-154">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="938bd-155">Wenn Sie die Exchange-Verwaltungsshell verwenden, deaktivieren Sie die einzelnen IP-Gateways mit folgendem Befehl:</span><span class="sxs-lookup"><span data-stu-id="938bd-155">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="938bd-156">Informationen zu Exchange 2007 finden Sie unter "festlegen-UMIPGateway: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .</span><span class="sxs-lookup"><span data-stu-id="938bd-156">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="938bd-157">Informationen zu Exchange 2010 finden Sie unter "festlegen-UMIPGateway: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .</span><span class="sxs-lookup"><span data-stu-id="938bd-157">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="938bd-158">Wenn Sie die Exchange-Verwaltungskonsole verwenden, deaktivieren Sie das Kontrollkästchen **Ausgehende Anrufe über dieses IP-Gateway zulassen**.</span><span class="sxs-lookup"><span data-stu-id="938bd-158">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="938bd-159">Falls Ihre UM-SIP-URI-Wähleinstellungen nur einem einzigen IP-Gateway zugeordnet sind, dürfen Sie ausgehende Anrufe über dieses Gateway nicht sperren.</span><span class="sxs-lookup"><span data-stu-id="938bd-159">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="938bd-160">Erstellen Sie eine automatische UM-Telefonzentrale für jeden lync Server Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="938bd-160">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="938bd-161">Verwenden Sie im Namen der automatischen Telefonzentrale keine Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="938bd-161">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="938bd-162">Ausführliche Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="938bd-162">For details, see:</span></span>
    
      - <span data-ttu-id="938bd-163">Informationen zu Exchange 2007 finden Sie unter "New-UMAutoAttendant: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .</span><span class="sxs-lookup"><span data-stu-id="938bd-163">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="938bd-164">Informationen zu Exchange 2010 finden Sie unter "New-UMAutoAttendant: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .</span><span class="sxs-lookup"><span data-stu-id="938bd-164">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="938bd-165">Der folgende Schritt sollte für jeden Benutzer ausgeführt werden, nachdem Sie lync Server Benutzer für Enterprise-VoIP aktiviert und deren SIP-URIs kennen.</span><span class="sxs-lookup"><span data-stu-id="938bd-165">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="938bd-166">Ordnen Sie den UM-Wähleinstellungen Exchange UM-Benutzer zu (von denen jeder mit einem Exchange-Postfach konfiguriert sein sollte), und erstellen Sie einen SIP-URI für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="938bd-166">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="938bd-167">Das <STRONG>SIPResourceIdentifier</STRONG> im folgenden Beispiel muss die SIP-Adresse des lync Server Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="938bd-167">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="938bd-168">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="938bd-168">For details, see:</span></span>
    
      - <span data-ttu-id="938bd-169">Informationen zu Exchange 2007 finden Sie unter "Enable-UMMailbox: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .</span><span class="sxs-lookup"><span data-stu-id="938bd-169">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="938bd-170">Informationen zu Exchange 2010 finden Sie unter "Enable-UMMailbox: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .</span><span class="sxs-lookup"><span data-stu-id="938bd-170">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

