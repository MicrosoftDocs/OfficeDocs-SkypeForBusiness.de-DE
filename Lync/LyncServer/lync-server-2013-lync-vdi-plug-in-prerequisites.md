---
title: 'Lync Server 2013: Voraussetzungen für das lync VDI-Plug-in'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a5cde1ba7acae400bce7dd7ddf03b96c0338f26
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="81805-102">Voraussetzungen für lync VDI-Plug-ins in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81805-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81805-103">_**Letztes Änderungsstand des Themas:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="81805-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="81805-104">In einer VDI-Umgebung (Virtual Desktop Infrastructure) müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="81805-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81805-p101">Informationen zum Installieren und Bereitstellen der virtualisierten Umgebung erhalten Sie von Ihrem Virtualisierungslösungsanbieter. Informationen zum Bereitstellen einer virtualisierten Umgebung basierend auf Hyper-V und Remotedesktopdiensten finden Sie in den folgenden Artikeln in der TechNet-Bibliothek von Microsoft:</span><span class="sxs-lookup"><span data-stu-id="81805-p101">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment. For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="81805-107">Hyper-V unter<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="81805-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="81805-108">Remote Desktop Dienste in Windows Server&nbsp;2008&nbsp;R2 unter<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="81805-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="81805-109">Für die virtuellen Maschinen, die auf dem Rechenzentrumscomputer ausgeführt werden, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="81805-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="81805-110">Virtuelle Computer müssen mit Windows 10, Windows 8.1, Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="81805-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="81805-111">Die folgenden Anforderungen gelten für den Benutzer und den lokalen Computer des Benutzers:</span><span class="sxs-lookup"><span data-stu-id="81805-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="81805-112">Der Benutzer muss in lync Server 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="81805-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="81805-113">Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1, Windows 8, Windows 8.1 eingebettet oder Windows 8.1 (nicht eingebettet) installiert sein.</span><span class="sxs-lookup"><span data-stu-id="81805-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="81805-114">Wenn Sie Remote Desktop Dienste verwenden, muss das lync VDI-Plug-in Bitanzahl (das heißt, ob es sich um 32-Bit-oder 64-Bit-Anwendungen handelt) mit dem Betriebssystem Bitanzahl des lokalen Computers übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="81805-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="81805-115">Die Bitanzahl des Betriebssystems auf dem lokalen Computer und das Betriebssystem auf dem virtuellen Computer müssen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="81805-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="81805-116">Wenn Sie eine andere Virtualisierungslösung oder Plattform verwenden, lesen Sie den Leitfaden Ihres Anbieters für die Virtualisierungslösung zu Bitanzahl Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="81805-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="81805-117">Auf dem lokalen Computer muss die neueste Version des Remotedesktopclients installiert sein.</span><span class="sxs-lookup"><span data-stu-id="81805-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="81805-118">Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft oder die neueste Remote Desktop-Client Software von Ihrem Anbieter für die Virtualisierung.</span><span class="sxs-lookup"><span data-stu-id="81805-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="81805-119">Die neuesten Updates für Remote Desktop Dienste finden Sie [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)unter.</span><span class="sxs-lookup"><span data-stu-id="81805-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="81805-120">Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="81805-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="81805-121">Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "so konfigurieren Sie Einstellungen für die Remotedesktopverbindung".</span><span class="sxs-lookup"><span data-stu-id="81805-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="81805-122">So konfigurieren Sie Einstellungen der Remotedesktopverbindung</span><span class="sxs-lookup"><span data-stu-id="81805-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="81805-123">Führen Sie die folgenden Schritte aus, um die Remote Desktop Verbindung in Windows für das lync VDI-Plug-in vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="81805-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="81805-124">Wenn der lokale Computer Windows 8 ausführt, überspringen Sie diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="81805-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="81805-125">Wenn der lokale Computer Windows 7 mit SP1 ausführt, installieren Sie die neueste Windows 8-Version des Remote Desktop Dienste-Clients, die [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)unter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="81805-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="81805-126">Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.</span><span class="sxs-lookup"><span data-stu-id="81805-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="81805-127">Klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="81805-127">Click **Options**.</span></span>

4.  <span data-ttu-id="81805-128">Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und führen Sie die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="81805-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="81805-129">Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.</span><span class="sxs-lookup"><span data-stu-id="81805-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="81805-130">Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.</span><span class="sxs-lookup"><span data-stu-id="81805-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="81805-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="81805-131">Click **OK**.</span></span>

5.  <span data-ttu-id="81805-132">Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.</span><span class="sxs-lookup"><span data-stu-id="81805-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="81805-133">Klicken Sie auf die Registerkarte **Allgemein**. Geben Sie im Feld **Computer** den Namen der virtuellen Maschine ein, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="81805-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

