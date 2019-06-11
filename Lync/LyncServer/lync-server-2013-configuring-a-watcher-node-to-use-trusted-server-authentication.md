---
title: Konfigurieren eines Watcher-Knotens zur Verwendung der vertrauenswürdigen Server Authentifizierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="2b0e5-102">Konfigurieren eines Watcher-Knotens in lync Server 2013 zur Verwendung der vertrauenswürdigen Server Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2b0e5-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b0e5-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2b0e5-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2b0e5-104">Wenn sich Ihr Watcher-Knoten Computer im Umkreisnetzwerk befindet, kann mithilfe der vertrauenswürdigen Server Authentifizierung die Verwaltungs Steuern erheblich reduziert werden, um ein einzelnes Zertifikat statt zahlreicher Benutzerkonten Kennwörter zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="2b0e5-105">Der erste Schritt bei der Konfiguration der vertrauenswürdigen Server Authentifizierung ist das Erstellen eines vertrauenswürdigen Anwendungspools zum Hosten des Watcher-Knoten Computers.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="2b0e5-106">Nachdem der vertrauenswürdige Anwendungspool erstellt wurde, müssen Sie synthetische Transaktionen auf diesem Watcher-Knoten so konfigurieren, dass Sie als vertrauenswürdige Anwendung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2b0e5-107">Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, der der vertrauenswürdige Status für die Ausführung als Teil von lync Server 2013 zugewiesen ist, aber kein integrierter Teil des Produkts ist.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="2b0e5-108">Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="2b0e5-109">Zum Erstellen eines vertrauenswürdigen Anwendungspools öffnen Sie die lync Server 2013-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="2b0e5-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="2b0e5-110">Details zu den im vorhergehenden Befehl verwendeten Parametern geben Sie an der Eingabeaufforderung der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b0e5-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="2b0e5-111">Get-Help New-CsTrustedApplicationPool-Full | Weitere</span><span class="sxs-lookup"><span data-stu-id="2b0e5-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="2b0e5-112">Konfigurieren Sie nach dem Erstellen des vertrauenswürdigen Anwendungspools den Watcher-Knoten Computer, um synthetische Transaktionen als vertrauenswürdige Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="2b0e5-113">Dies erfolgt mithilfe des Cmdlets **New-CsTrustedApplication** und eines Befehls ähnlich wie hier:</span><span class="sxs-lookup"><span data-stu-id="2b0e5-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="2b0e5-114">Wenn der vorhergehende Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wurde, führen Sie Enable-CsTopology aus, um sicherzustellen, dass die Änderungen wirksam werden:</span><span class="sxs-lookup"><span data-stu-id="2b0e5-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="2b0e5-115">Nach dem Ausführen von enable-CsTopology empfehlen wir, den Computer neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="2b0e5-116">Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie Folgendes an der Eingabeaufforderung der lync Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="2b0e5-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="2b0e5-117">Konfigurieren eines Standardzertifikats auf dem Watcher-Knoten</span><span class="sxs-lookup"><span data-stu-id="2b0e5-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="2b0e5-118">Für jeden Watcher-Knoten muss ein Standardzertifikat mit dem lync Server-Bereitstellungs-Assistenten zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="2b0e5-119">**So weisen Sie ein Standardzertifikat zu**</span><span class="sxs-lookup"><span data-stu-id="2b0e5-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="2b0e5-120">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **lync Server**, und klicken Sie dann auf **lync Server**-Bereitstellungs-Assistent.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="2b0e5-121">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren** , und klicken Sie dann unter der Überschrift **anfordern, installieren oder Zertifikat zuweisen**auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="2b0e5-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2b0e5-122">Wenn die Schaltfläche <STRONG>Ausführen</STRONG> deaktiviert ist, müssen Sie möglicherweise zuerst auf <STRONG>Ausführen</STRONG> unter <STRONG>lokalen Konfigurationsspeicher installieren</STRONG>klicken.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="2b0e5-123">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2b0e5-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="2b0e5-124">Wenn Sie bereits über ein Zertifikat verfügen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf **Standard** , und klicken Sie dann auf **zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="2b0e5-125">Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="2b0e5-126">Wenn Sie ein Zertifikat anfordern müssen, um das Standardzertifikat zu verwenden, klicken Sie auf **anfordern** , und führen Sie dann die Schritte im Zertifikat Anforderungs-Assistenten aus, um dieses Zertifikat anzufordern.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="2b0e5-127">Wenn Sie die Standardwerte für das Webserverzertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="2b0e5-128">Installieren und Konfigurieren eines Watcher-Knotens</span><span class="sxs-lookup"><span data-stu-id="2b0e5-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="2b0e5-129">Nachdem Sie den Watcher-Knoten Computer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei Watchernode. msi ausführen.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="2b0e5-130">(Sie müssen Watchernode. msi auf einem Computer ausführen, auf dem sowohl die Operations Manager-Agentendateien als auch die Hauptkomponenten von lync Server 2013 installiert sind.)</span><span class="sxs-lookup"><span data-stu-id="2b0e5-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="2b0e5-131">**So installieren und konfigurieren Sie einen Watcher-Knoten**</span><span class="sxs-lookup"><span data-stu-id="2b0e5-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="2b0e5-132">Öffnen Sie die lync Server-Verwaltungsshell, indem Sie auf **Start**klicken, auf **Alle Programme**klicken, auf **lync Server**und dann auf **lync Server-Verwaltungsshell**klicken.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2b0e5-133">Geben Sie in der lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (geben Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode. msi an):</span><span class="sxs-lookup"><span data-stu-id="2b0e5-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2b0e5-134">Sie können Watchernode. msi auch über ein Befehlsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="2b0e5-135">Klicken Sie zum Öffnen eines Befehlsfensters auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG> und klicken Sie dann auf <STRONG>Als Administrator ausführen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="2b0e5-136">Wenn das Befehlsfenster geöffnet wird, geben Sie denselben vorhergehenden Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="2b0e5-137">Beachten Sie, dass das Name-Wert-Paar in der vorhergehenden Befehls Authentifizierung = TrustedServer die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="2b0e5-138">Sie müssen es genau wie gezeigt eingeben.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-138">You must type it exactly as shown.</span></span> <span data-ttu-id="2b0e5-139">Der folgende Befehl schlägt fehl, da er nicht das richtige Buchstaben Gehäuse verwendet:</span><span class="sxs-lookup"><span data-stu-id="2b0e5-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="2b0e5-140">C:\\Tools\\Watchernode. msi Authentication = trustedserver</span><span class="sxs-lookup"><span data-stu-id="2b0e5-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="2b0e5-141">Sie können den TrustedServer-Modus nur für Computer verwenden, die sich im Umkreisnetzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="2b0e5-142">Wenn ein Watcher-Knoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Testbenutzer Kennwörter auf dem Computer verwalten.</span><span class="sxs-lookup"><span data-stu-id="2b0e5-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

