---
title: 'Lync Server 2013: Komponenten und Topologien für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="99a0e-102">Komponenten und Topologien für Konferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99a0e-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99a0e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="99a0e-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="99a0e-104">Wenn Sie im Topologie-Generator Konferenzen auswählen, wird Conferencing als Teil des Front-End-Servers oder Standard Edition-Servers bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="99a0e-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="99a0e-105">Für Einwahlkonferenzen und PowerPoint-Freigabe sind zusätzliche Komponenten und Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99a0e-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="99a0e-106">In den folgenden Abschnitten werden die unterstützten Komponenten und Topologien für Webkonferenzen, A/V-Konferenzen und Einwahlkonferenzen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99a0e-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="99a0e-107">Unterstützte Komponenten</span><span class="sxs-lookup"><span data-stu-id="99a0e-107">Supported Components</span></span>

<span data-ttu-id="99a0e-108">Die einzigen Komponenten Webkonferenzen und A/V-Konferenzen erfordern die Front-End-Server Ihrer Organisation oder Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="99a0e-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="99a0e-109">Eine Liste der Hardware-und Softwareanforderungen für die Front-End-Server und die Standard Edition-Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) und [Server Software und Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="99a0e-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="99a0e-110">In lync Server 2013 werden Office Web Apps und der Office Web Apps-Server verwendet, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="99a0e-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="99a0e-111">Details zum Installieren und Konfigurieren des Office Web Apps-Servers finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="99a0e-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="99a0e-112">Zusätzlich zu den Anforderungen für Webkonferenzen und A/V-Konferenzen verwendet Einwahlkonferenzen die folgenden lync Server 2013-Komponenten:</span><span class="sxs-lookup"><span data-stu-id="99a0e-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="99a0e-113">**Application Service**   Application Service stellt eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen (UC) bereit.</span><span class="sxs-lookup"><span data-stu-id="99a0e-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="99a0e-114">Einwahlkonferenzen verwendet zwei UC-Anwendungen, die Anwendungsdienst erfordern: Konferenzzentrale und Konferenzankündigung.</span><span class="sxs-lookup"><span data-stu-id="99a0e-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="99a0e-115">Der Anwendungsdienst wird standardmäßig auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="99a0e-116">\*\*\*\*   Die Application Conferencing Attendant-Anwendung der Konferenzzentrale ist eine Unified Communications-Anwendung, die PSTN-Anrufe (Public Switched Telephone Network) akzeptiert, Aufforderungen wiedergibt und die Anrufe an eine a/V-Konferenz anschließt.</span><span class="sxs-lookup"><span data-stu-id="99a0e-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="99a0e-117">Die Conferencing Attendant-Anwendung wird standardmäßig installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="99a0e-118">**Konferenzankündigung**   Application Conferencing Ankündigung Application ist eine Unified Communications-Anwendung, die Töne und Aufforderungen an PSTN-Teilnehmer für bestimmte Aktionen abspielt, beispielsweise wenn Teilnehmer an einer Konferenz teilnehmen oder eine Konferenz beenden, Teilnehmer sind stumm geschaltet oder nicht stumm geschaltet, jemand wechselt in die Konferenz Lobby, oder die Konferenz ist gesperrt oder entriegelt.</span><span class="sxs-lookup"><span data-stu-id="99a0e-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="99a0e-119">Die APP für Konferenz Ankündigungen unterstützt auch DTMF-Befehle (Dual Tone MultiFrequency) über das Tastenfeld des Telefons.</span><span class="sxs-lookup"><span data-stu-id="99a0e-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="99a0e-120">Die APP für Konferenz Ankündigungen wird automatisch installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="99a0e-121">**Seite "Einstellungen für Einwahlkonferenzen**   " auf der Seite "Einstellungen für Einwahlkonferenzen" werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen angezeigt, Konferenz Informationen zugewiesen (also für Besprechungen, die nicht geplant werden müssen) und DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung von PIN (Personal Identification Number) und zugewiesene Konferenz Informationen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="99a0e-122">Die Seite Einstellungen für Einwahlkonferenzen wird automatisch als Teil von Webdiensten installiert.</span><span class="sxs-lookup"><span data-stu-id="99a0e-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="99a0e-123">**Für lync Server 2013, Vermittlungsserver und**   Einwahlkonferenzen für PSTN-Gateways ist ein Vermittlungsserver erforderlich, um Signalisierungen (und Medien in einigen Konfigurationen) zwischen lync Server 2013 und dem PSTN-Gateway zu übersetzen und ein PSTN-Gateway zu übersetzen. signalisieren und Medien zwischen dem Vermittlungs Server und dem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="99a0e-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="99a0e-124">Für Einwahlkonferenzen müssen Sie mindestens einen Vermittlungs Server und mindestens eine der folgenden Aktionen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="99a0e-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="99a0e-125">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="99a0e-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="99a0e-126">IP-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="99a0e-126">IP-PBX</span></span>
    
      - <span data-ttu-id="99a0e-127">Session Border Controller (SBC) (für einen Anbieter von Internettelefoniediensten, mit dem durch Konfigurieren eines SIP-Trunks eine Verbindung hergestellt wird)</span><span class="sxs-lookup"><span data-stu-id="99a0e-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99a0e-128">Wenn Sie auch Enterprise-VoIP bereitstellen, sind Vermittlungs Server und PSTN-Gateways Teil der Enterprise-VoIP-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="99a0e-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="99a0e-129">Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie mindestens einen Vermittlungs Server und mindestens ein PSTN-Gateway, IP-PBX oder SBC für Einwahlkonferenzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="99a0e-130">**Datei**   Speicherdatei Speicher wird für aufgezeichnete Namen-Audiodateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="99a0e-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="99a0e-131">Er ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="99a0e-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="99a0e-132">\*\*\*\* Benutzerspeicher Benutzerspeicher wird zum Speichern von Benutzer-lync Server 2013-Pins verwendet.   </span><span class="sxs-lookup"><span data-stu-id="99a0e-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="99a0e-133">Für PINs wird ein Hashalgorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="99a0e-133">PINs are hashed.</span></span> <span data-ttu-id="99a0e-134">Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="99a0e-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="99a0e-135">**Lync Server Control Panel**   einige Einwahleinstellungen können mithilfe der lync Server-Systemsteuerung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="99a0e-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="99a0e-136">**Lync Server-Verwaltungsshell**   alle Einwahleinstellungen können mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="99a0e-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="99a0e-137">Cmdlets für die lync Server-Verwaltungsshell sind für das bereitstellen, konfigurieren, ausführen, überwachen und behandeln von Problemen mit der Anwendungs-und Konferenz ansageanwendung für Conferencing Attendant verfügbar.</span><span class="sxs-lookup"><span data-stu-id="99a0e-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="99a0e-138">Details zu bestimmten Cmdlets finden Sie unter Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="99a0e-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="99a0e-139">Unterstützte Topologien</span><span class="sxs-lookup"><span data-stu-id="99a0e-139">Supported Topologies</span></span>

<span data-ttu-id="99a0e-140">In lync Server 2013 ist der Server, auf dem Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition-Servern verbunden.</span><span class="sxs-lookup"><span data-stu-id="99a0e-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="99a0e-141">Während der ersten Bereitstellung bietet Ihnen der Topology Builder die Möglichkeit, Konferenzen in Ihre Topologie einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="99a0e-142">Den Topologie-Generator können Sie außerdem nutzen, um die Konferenzfunktion zu einer vorhandenen Bereitstellung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="99a0e-143">Ausführliche Informationen finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="99a0e-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="99a0e-144">Einwahl in Konferenz Toplogies</span><span class="sxs-lookup"><span data-stu-id="99a0e-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="99a0e-145">Sie können Einwahlkonferenzen in den folgenden Topologien und Konfigurationen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="99a0e-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="99a0e-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="99a0e-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="99a0e-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="99a0e-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="99a0e-148">Mit oder ohne Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="99a0e-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="99a0e-149">Sie können Anwendungsdienst, Konferenz Aufsichts Anwendung und Konferenz Ankündigungs Anwendung an einer zentralen Website, aber nicht an einer Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99a0e-150">Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Sie in jedem Pool bereitstellen, in dem Sie die lync Server 2013-Konferenz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="99a0e-151">Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Funktion für Einwahlkonferenzen in jedem Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="99a0e-152">Diese Anforderung unterstützt das Feature "aufgezeichnete Namen", wenn ein Benutzer eine Zugriffsnummer aus einem Pool anruft, um an einer lync Server 2013-Konferenz in einem anderen Pool teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="99a0e-153">Unterstützte Topologien für lync Server 2013 und Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="99a0e-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="99a0e-154">Lync Server 2013 bietet die folgenden Möglichkeiten zum Konfigurieren von Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="99a0e-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="99a0e-155">Je nach Ihren Anforderungen können Sie:</span><span class="sxs-lookup"><span data-stu-id="99a0e-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="99a0e-156">**Installieren Sie lync Server 2013 und Office Web Apps Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.**</span><span class="sxs-lookup"><span data-stu-id="99a0e-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="99a0e-157">Bei dieser Topologie wird externer Zugriff auf Office Web Apps Server über den Reverse-Proxy Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="99a0e-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="99a0e-158">Sowohl lync Server 2013 als auch Office Web Apps Server (oder eine Office Web Apps-Serverfarm) sind lokal und hinter der Firewall Ihrer Organisation installiert.</span><span class="sxs-lookup"><span data-stu-id="99a0e-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="99a0e-159">Im Idealfall sollten Sie Office Web Apps Server in der gleichen Netzwerkzone wie lync Server installieren.</span><span class="sxs-lookup"><span data-stu-id="99a0e-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="99a0e-160">Externe lync-Clients können mithilfe eines Reverseproxy-Servers, der Anforderungen aus dem Internet anfordert und an das interne Netzwerk weiterleitet, eine Verbindung mit lync Server 2013 und Office Web Apps Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="99a0e-161">(Interne Clients müssen den Reverse Proxy Server nicht verwenden, da Sie eine direkte Verbindung mit Office Web Apps Server herstellen können.) Diese Topologie funktioniert am besten, wenn Sie eine dedizierte Office Web Apps-Server Farm verwenden möchten, die nur von lync Server 2013 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99a0e-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="99a0e-162">**Verwenden eines extern bereitgestellten Office Web Apps-Servers**</span><span class="sxs-lookup"><span data-stu-id="99a0e-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="99a0e-163">In dieser Topologie wird lync Server 2013 lokal bereitgestellt und verwendet einen Office Web Apps-Server, der außerhalb der lync Server-Netzwerkzone bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="99a0e-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="99a0e-164">Dies kann passieren, wenn der Office Web Apps-Server für mehrere Anwendungen im Unternehmen freigegeben und in einem Netzwerk bereitgestellt wird, in dem lync Server für die Verwendung der externen Schnittstelle von Office Web Apps Server und umgekehrt erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="99a0e-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="99a0e-165">Sie müssen keinen Reverse-Proxy-Server installieren; Stattdessen werden alle Anforderungen vom Office Web Apps-Server an lync Server 2013 über Ihren Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="99a0e-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="99a0e-166">Sowohl Ihre internen als auch Ihre externen lync-Clients stellen mithilfe der externen URL eine Verbindung mit Office Web Apps Server her.</span><span class="sxs-lookup"><span data-stu-id="99a0e-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="99a0e-167">Wenn der Office Web Apps-Server außerhalb ihrer internen Firewall bereitgestellt wird, wählen Sie die Option **Office Web Apps Server wird in einem externen Netzwerk (also Umkreis/Internet) im Topologie-Generator bereitgestellt** .</span><span class="sxs-lookup"><span data-stu-id="99a0e-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="99a0e-168">Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="99a0e-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="99a0e-169">Unabhängig von der ausgewählten Topologie ist es entscheidend, dass die korrekten Firewallports geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="99a0e-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="99a0e-170">Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht von Firewalls auf dem Office Web Apps-Server, dem Lastenausgleichsmodul oder lync Server blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="99a0e-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99a0e-171">Eine weitere Option für den externen Zugriff auf Office Web Apps Server ist die Bereitstellung des Servers im Umkreisnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="99a0e-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="99a0e-172">Wenn Sie sich dafür entscheiden, sollten Sie Bedenken, dass der Server Computer von Office Web Apps Server als Mitglied Ihrer Active Directory-Domäne verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="99a0e-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="99a0e-173">Sofern Ihre Netzwerkrichtlinie Computern im Umkreisnetzwerk keine Active Directory-Domänenmitglieder zulässt, wird empfohlen, dass Sie Office Web Apps Server im Umkreisnetzwerk nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="99a0e-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="99a0e-174">Stattdessen sollten Sie Office Web Apps Server im internen Netzwerk installieren und den Zugriff externer Benutzer über den Reverse-Proxy Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99a0e-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

