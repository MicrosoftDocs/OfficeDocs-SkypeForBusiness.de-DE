---
title: 'Lync Server 2013: Voraussetzungen für das Lync VDI-Plug-In'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae32480e5a3dbfbdfc22c4dbde59c62383c9587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="94a75-102">Voraussetzungen für das Lync VDI-Plug-In in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94a75-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94a75-103">_**Letztes Änderungsdatum des Themas:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="94a75-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="94a75-104">In einer VDI-Umgebung (Virtual Desktop Infrastructure) müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="94a75-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94a75-105">Informationen zum Installieren und Bereitstellen der virtualisierten Umgebung finden Sie in Ihrem Anbieter von Virtualisierungslösungen.</span><span class="sxs-lookup"><span data-stu-id="94a75-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="94a75-106">Informationen zum Bereitstelleneiner virtualisierten Umgebung, die auf Hyper-V und Remote Desktop Diensten basiert, finden Sie in den folgenden Artikeln in der Microsoft TechNet-Bibliothek:</span><span class="sxs-lookup"><span data-stu-id="94a75-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="94a75-107">Hyper-V at<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="94a75-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="94a75-108">Remote Desktop Dienste in Windows Server&nbsp;2008&nbsp;R2 unter<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="94a75-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="94a75-109">Die folgenden Anforderungen gelten für die virtuellen Computer, die auf dem Rechenzentrums Computer ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="94a75-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="94a75-110">Virtuelle Computer müssen mit Windows 10, Windows 8,1, Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="94a75-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="94a75-111">Die folgenden Anforderungen gelten für den Benutzer und den lokalen Computer des Benutzers:</span><span class="sxs-lookup"><span data-stu-id="94a75-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="94a75-112">Der Benutzer muss sich in lync Server 2013 befinden.</span><span class="sxs-lookup"><span data-stu-id="94a75-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="94a75-113">Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1, Windows 8, Windows 8,1 Embedded oder Windows 8,1 (nicht eingebettet) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="94a75-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="94a75-114">Wenn Sie Remote Desktop Dienste verwenden, muss das lync VDI-Plug-in Bitanzahl (das heißt, ob es sich um eine 32-Bit-oder 64-Bit-Anwendung handelt) dem Betriebssystem Bitanzahl des lokalen Computers entsprechen.</span><span class="sxs-lookup"><span data-stu-id="94a75-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="94a75-115">Die Bitanzahl des Betriebssystems auf dem lokalen Computer und das Betriebssystem auf dem virtuellen Computer müssen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="94a75-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="94a75-116">Wenn Sie eine andere Virtualisierungslösung oder Plattform verwenden, finden Sie Informationen zu den Bitanzahl-Anforderungen unter Anleitung Ihres Virtualisierungslösung-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="94a75-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="94a75-117">Auf dem lokalen Computer muss die neueste Version des Remotedesktopclients ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="94a75-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="94a75-118">Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft oder der neuesten Remote Desktop-Client Software Ihres Virtualisierungslösung-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="94a75-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="94a75-119">Die neuesten Updates für Remote Desktop Dienste finden Sie [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)unter.</span><span class="sxs-lookup"><span data-stu-id="94a75-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="94a75-120">Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="94a75-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="94a75-121">Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "so konfigurieren Sie die Einstellungen für Remotedesktopverbindung".</span><span class="sxs-lookup"><span data-stu-id="94a75-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="94a75-122">So konfigurieren Sie die Einstellungen für Remote Desktop Verbindung</span><span class="sxs-lookup"><span data-stu-id="94a75-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="94a75-123">Führen Sie die folgenden Schritte aus, um die Remote Desktop Verbindung in Windows für das lync VDI-Plug-in vorzubereiten:</span><span class="sxs-lookup"><span data-stu-id="94a75-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="94a75-124">Wenn auf dem lokalen Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="94a75-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="94a75-125">Wenn auf dem lokalen Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie die neueste Version von Windows 8 des Remote Desktop Dienste-Clients [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032), die unter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="94a75-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="94a75-126">Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.</span><span class="sxs-lookup"><span data-stu-id="94a75-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="94a75-127">Klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="94a75-127">Click **Options**.</span></span>

4.  <span data-ttu-id="94a75-128">Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="94a75-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="94a75-129">Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.</span><span class="sxs-lookup"><span data-stu-id="94a75-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="94a75-130">Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.</span><span class="sxs-lookup"><span data-stu-id="94a75-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="94a75-131">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94a75-131">Click **OK**.</span></span>

5.  <span data-ttu-id="94a75-132">Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.</span><span class="sxs-lookup"><span data-stu-id="94a75-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="94a75-133">Klicken Sie auf die Registerkarte **Allgemein** . Geben Sie in **Computer**den Namen des virtuellen Computers ein, und klicken Sie dann auf **verbinden**.</span><span class="sxs-lookup"><span data-stu-id="94a75-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

