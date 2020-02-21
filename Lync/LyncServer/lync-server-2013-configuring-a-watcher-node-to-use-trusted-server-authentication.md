---
title: Konfigurieren eines Watcher-Knotens für die Verwendung der vertrauenswürdigen Server Authentifizierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8272dc0097205749ca3c0e5d613bc3da853fc7ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="5028e-102">Konfigurieren eines Watcher-Knotens in lync Server 2013 zur Verwendung der vertrauenswürdigen Server Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5028e-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5028e-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5028e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5028e-104">Wenn sich Ihr Watcher-Knoten-Computer innerhalb des Umkreisnetzes befindet, können die Administrationsaufgaben zur Beibehaltung eines einzelnen Zertifikats anstelle zahlreicher Kennwörter für Benutzerkonten mithilfe der Trusted Server-Authentifizierung stark reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="5028e-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="5028e-p101">Der erste Schritt bei der Konfiguration der Trusted Server-Authentifizierung ist die Erstellung eines Pools vertrauenswürdiger Anwendungen zum Hosten des Watcher-Knoten-Computers. Nach der Erstellung des Pools vertrauenswürdiger Anwendungen müssen Sie synthetische Transaktionen auf diesem Watcher-Knoten erstellen, die als vertrauenswürdige Anwendungen ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5028e-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5028e-107">Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die als Teil der lync Server 2013 als vertrauenswürdiger Status ausgeführt wird, aber kein integrierter Bestandteil des Produkts ist.</span><span class="sxs-lookup"><span data-stu-id="5028e-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="5028e-108">Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="5028e-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="5028e-109">Öffnen Sie zum Erstellen eines vertrauenswürdigen Anwendungspools die lync Server 2013-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="5028e-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="5028e-110">Ausführliche Informationen zu den Parametern, die im vorherigen Befehl verwendet werden, geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5028e-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="5028e-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="5028e-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="5028e-112">Konfigurieren Sie nach der Erstellung des Pools vertrauenswürdiger Anwendungen, den Watcher-Knoten-Computer für die Ausführung synthetischer Transaktionen als vertrauenswürdige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5028e-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="5028e-113">Verwenden Sie dazu das **New-CsTrustedApplication**-Cmdlet und einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="5028e-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="5028e-114">Wenn der vorstehende Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wurde, führen Sie "Enable-CsTopology" aus, um sicherzustellen, dass die Änderungen wirksam werden:</span><span class="sxs-lookup"><span data-stu-id="5028e-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="5028e-115">Nach Ausführung von "Enable-CsTopology" wird empfohlen, den Computer neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="5028e-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="5028e-116">Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie an der lync Server-Verwaltungsshell-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5028e-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="5028e-117">Konfigurieren eines Standardzertifikats auf dem Watcher-Knoten</span><span class="sxs-lookup"><span data-stu-id="5028e-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="5028e-118">Jeder Watcher-Knoten muss mit dem lync Server-Bereitstellungs-Assistenten ein Standardzertifikat zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="5028e-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="5028e-119">**So weisen Sie ein Standardzertifikat zu**</span><span class="sxs-lookup"><span data-stu-id="5028e-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="5028e-120">Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **lync Server**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="5028e-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="5028e-121">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren** , und klicken Sie dann unter der Überschrift **Anforderung, installieren oder Zuweisen eines Zertifikats**auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="5028e-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5028e-122">Wenn die Schaltfläche <STRONG>Ausführen</STRONG> deaktiviert ist, müssen Sie möglicherweise zunächst unter <STRONG>Lokalen Konfigurationsspeicher installieren</STRONG> auf <STRONG>Ausführen</STRONG> klicken.</span><span class="sxs-lookup"><span data-stu-id="5028e-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="5028e-123">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5028e-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="5028e-p104">Wenn Sie bereits ein Zertifikat besitzen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf **Standard** und anschließend auf **Zuweisen**. Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="5028e-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="5028e-p105">Wenn Sie ein Zertifikat für die Verwendung als Standardzertifikat anfordern müssen, klicken Sie auf **Anforderung**, und folgen Sie den Schritten im Zertifikatanforderungs-Assistenten, um das Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserver-Zertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="5028e-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="5028e-128">Installieren und Konfigurieren eines Watcher-Knotens</span><span class="sxs-lookup"><span data-stu-id="5028e-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="5028e-129">Nachdem Sie den Watcher-Knoten-Computer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei "Watchernode.msi" ausführen.</span><span class="sxs-lookup"><span data-stu-id="5028e-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="5028e-130">(Sie müssen Watchernode. msi auf einem Computer ausführen, auf dem sowohl die Operations Manager-Agent-Dateien als auch die lync Server 2013 Kernkomponenten installiert sind.)</span><span class="sxs-lookup"><span data-stu-id="5028e-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="5028e-131">**So installieren und konfigurieren Sie einen Watcher-Knoten**</span><span class="sxs-lookup"><span data-stu-id="5028e-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="5028e-132">Öffnen Sie das lync Server-Verwaltungsshell, indem Sie auf **Start**, auf **Alle Programme**, auf **lync Server**und dann auf **lync Server-Verwaltungsshell**klicken.</span><span class="sxs-lookup"><span data-stu-id="5028e-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5028e-133">Geben Sie im lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (geben Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode. msi an):</span><span class="sxs-lookup"><span data-stu-id="5028e-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5028e-p107">Sie können "Watchernode.msi" auch aus einem Befehlsfenster ausführen. Um ein Befehlsfenster zu öffnen, klicken Sie auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG>, und klicken Sie auf <STRONG>Als Administrator ausführen</STRONG>. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben vorstehenden Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="5028e-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="5028e-p108">Beachten Sie, dass beim Namen/Wertpaar im vorstehenden Befehl "Authentication=TrustedServer" Groß-/Kleinschreibung beachtet wird. Geben Sie es genau wie angezeigt ein. Bei der Ausführung des folgenden Befehls tritt ein Fehler auf, weil nicht die richtige Folge von Klein- und Großbuchstaben verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="5028e-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="5028e-140">C:\\Tools\\Watchernode. msi Authentication = trustedserver</span><span class="sxs-lookup"><span data-stu-id="5028e-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="5028e-p109">Sie können den TrustedServer-Modus nur auf Computern verwenden, die sich im Umkreisnetzwerk befinden. Wenn ein Watcher-Knoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Kennwörter für Testbenutzer auf dem Computer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5028e-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

