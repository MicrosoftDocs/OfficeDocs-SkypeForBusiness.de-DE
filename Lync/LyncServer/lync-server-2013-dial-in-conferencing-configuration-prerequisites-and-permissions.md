---
title: Voraussetzungen und Berechtigungen für die Konfiguration von Einwahlkonferenzen
description: Voraussetzungen und Berechtigungen für die Konfiguration von Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eced67f33e35c711c4fcd31120480b6d5c2e41ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576171"
---
# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="b8de3-103">Voraussetzungen und Berechtigungen für die Einwahlkonferenz Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8de3-103">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8de3-104">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b8de3-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b8de3-105">Einwahlkonferenzen sind eine optionale Komponente der Arbeitsauslastung von lync Server 2013 Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-105">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="b8de3-106">Die Komponenten, die Sie installieren müssen, bevor Sie Einwahlkonferenzen konfigurieren können, werden bereitgestellt, wenn Sie den Topologie-Generator verwenden, um Ihre Topologie zu entwerfen und dann Ihre Front-End-Pool oder Standard Edition-Server einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b8de3-106">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="b8de3-107">In diesem Thema wird beschrieben, welche Aufgaben vor der Konfiguration von Einwahlkonferenzen ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-107">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="b8de3-108">Es wird davon ausgegangen, dass Sie die Planungsdokumentation im Zusammenhang mit Konferenzen und insbesondere mit Einwahlkonferenzen gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="b8de3-108">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="b8de3-109">Voraussetzungen für die Konfiguration von Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b8de3-109">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="b8de3-110">Für Einwahlkonferenzen sind die folgenden lync Server 2013 Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b8de3-110">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="b8de3-111">Unified Communications-Anwendungsdienst (auch nur *Anwendungsdienst* genannt)</span><span class="sxs-lookup"><span data-stu-id="b8de3-111">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="b8de3-112">Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="b8de3-112">Conferencing Attendant application</span></span>

  - <span data-ttu-id="b8de3-113">Konferenzankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="b8de3-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="b8de3-114">Webseite mit Einstellungen für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b8de3-114">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="b8de3-115">Mindestens ein lync Server 2013 Vermittlungsserver und mindestens ein PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="b8de3-115">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="b8de3-116">Sie stellen diese Komponenten bereit, wenn Sie den Topologie-Generator verwenden, um die Topologie zu definieren und zu veröffentlichen und anschließend eine Front-End-Pool oder ein Standard Edition-Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-116">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="b8de3-117">Wenn Sie Enterprise-VoIP bereitstellen, sollten Sie es vor dem Konfigurieren von Einwahlkonferenzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-117">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="b8de3-118">Wenn Sie Enterprise-VoIP nicht bereitstellen, können Sie eine Vermittlungsserver und ein PSTN-Gateway (Public Switched Telephone Network) bereitstellen, wenn Sie Ihre Front-End-Pool oder Standard Edition-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-118">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b8de3-119">Wenn Sie ein Upgrade von Office Communications Server 2007 R2 auf lync Server 2013 durchführen, stellen Sie Einwahlkonferenzen in jedem Pool bereit, den Sie zum Hosten von lync Server 2013 Konferenzen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b8de3-119">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="b8de3-120">Ausführliche Informationen zum Migrieren von Einwahlkonferenzen finden Sie unter <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8de3-120">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b8de3-121">Dieser Abschnitt setzt voraus, dass Sie die folgenden Schritte ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="b8de3-121">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="b8de3-122">Die neuesten Updates wurden auf Ihre Office Communications Server 2007 R2 Umgebung angewendet, wenn Sie zu lync Server 2013 migrieren.</span><span class="sxs-lookup"><span data-stu-id="b8de3-122">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="b8de3-123">Verwenden Sie den Topologie-Generator, um Ihre Topologie zu entwerfen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b8de3-123">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="b8de3-124">Bei der Angabe der Arbeitsauslastung für Konferenzen haben Sie die Option Einwahlkonferenzen ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="b8de3-124">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="b8de3-125">Ausführliche Informationen zum Definieren Ihrer Topologie finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b8de3-125">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="b8de3-126">Die Topologie veröffentlicht sowie den Front-End-Pool oder Standard Edition-Server eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="b8de3-126">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="b8de3-127">Ausführliche Informationen zum Veröffentlichen der Topologie und zum Installieren von lync Server 2013 finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b8de3-127">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b8de3-128">Bei der Installation Ihrer veröffentlichten Topologie wird die Webseite mit Einstellungen für Einwahlkonferenzen als Teil der Webdienste auf dem Front-End-Server oder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="b8de3-128">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b8de3-129">Wenn Sie den Pfad für den Dateispeicher im Topologie-Generator ändern, nachdem Sie lync Server 2013 bereitgestellt haben, müssen Sie die Konferenzzentrale und die Konferenz Ankündigungs Anwendungen neu starten, um den neuen Pfad zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8de3-129">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="b8de3-130">Bereitstellung von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="b8de3-130">Deployed Enterprise Voice.</span></span> <span data-ttu-id="b8de3-131">Wenn Sie Enterprise-VoIP nicht bereitstellen, haben Sie entweder eine Vermittlungsserver im Enterprise Edition-Front-End-Server oder im Standard Edition-Server oder ein eigenständiges Vermittlungsserver bereitgestellt und ein PSTN-Gateway bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b8de3-131">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="b8de3-132">Ausführliche Informationen zur Bereitstellung von Enterprise-VoIP finden Sie unter [Deploying Enterprise Voice in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b8de3-132">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="b8de3-133">Ausführliche Informationen zum Installieren eines eigenständigen Vermittlungsserver und eines PSTN-Gateways finden Sie unter [Deploying Mediation Servers and Definition Peers in lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b8de3-133">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b8de3-134">Das folgende Flussdiagramm zeigt die Schritte, die erfolgen müssen, bevor Sie Einwahlkonferenzen konfigurieren können, und die Schritte, die Sie zum Konfigurieren von Einwahlkonferenzen ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-134">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="b8de3-135">**Bereitstellen von Einwahlkonferenzen**</span><span class="sxs-lookup"><span data-stu-id="b8de3-135">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="b8de3-136">![Flussdiagramm zur Bereitstellung von Einwahlkonferenzen](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Flussdiagramm zur Bereitstellung von Einwahlkonferenzen")</span><span class="sxs-lookup"><span data-stu-id="b8de3-136">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="b8de3-137">Berechtigungen für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b8de3-137">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="b8de3-138">Zum Konfigurieren von Einwahlkonferenzen müssen Sie die folgenden Verwaltungsprogramme verwenden:</span><span class="sxs-lookup"><span data-stu-id="b8de3-138">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="b8de3-139">Lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b8de3-139">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="b8de3-140">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b8de3-140">Lync Server Management Shell</span></span>

<span data-ttu-id="b8de3-141">Mithilfe dieser Verwaltungsprogramme konfigurieren Sie die Einwahlkonferenzeinstellungen, Wähleinstellungen, Richtlinien und anderen Einstellungen, die für Einwahlkonferenzen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b8de3-141">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="b8de3-142">Für das Konfigurieren von Einwahlkonferenzen ist, je nach Aufgabe, eine der folgenden Administratorrollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b8de3-142">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="b8de3-143">**CsVoiceAdministrator**     Diese Administratorrolle kann VoIP-bezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="b8de3-143">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="b8de3-144">**CsUserAdministrator**     Diese Administratorrolle kann Benutzer für lync Server aktivieren und deaktivieren und Benutzern vorhandene Richtlinien wie Konferenzrichtlinien und PIN-Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-144">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="b8de3-145">**CsAdministrator**     Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator und CsUserAdministrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="b8de3-145">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8de3-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8de3-146">See Also</span></span>


[<span data-ttu-id="b8de3-147">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8de3-147">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

