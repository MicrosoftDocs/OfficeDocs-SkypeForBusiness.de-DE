---
title: 'Lync Server 2013: Ändern der Webdienste-URL'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed7e61d62857f11c780798a8704aa5aa9fe808a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="2ebff-102">Ändern der Webdienste-URL in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ebff-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ebff-103">_**Letztes Änderungsstand des Themas:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="2ebff-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="2ebff-104">Bei der Einrichtung von Front-End-Pools und Standard Edition-Servern können Sie einen externen Webfarm-FQDN sowie entsprechende Ports konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2ebff-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="2ebff-105">Wenn Sie diese URL nicht konfiguriert haben, als Sie den lync Server-Bereitstellungs-Assistenten ausgeführt haben, müssen Sie diese Einstellungen manuell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2ebff-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="2ebff-106">Ein Administrator muss diese Einstellungen normalerweise nicht ändern, da bereits die empfohlenen Standardports eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="2ebff-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ebff-107">Beim Konfigurieren eines Standard Edition-Server wurde der folgende Screenshot ausgeführt, sodass die Option FQDN außer Kraft setzen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2ebff-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="2ebff-108">Diese Option ist aktiviert, wenn ein Enterprise Edition-Server in einem Front-End-Pool konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="2ebff-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="2ebff-109">![Bearbeiten von Webdienste Pool Einstellungen](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Bearbeiten von Webdienste Pool Einstellungen")</span><span class="sxs-lookup"><span data-stu-id="2ebff-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="2ebff-110">So konfigurieren Sie Webdienste</span><span class="sxs-lookup"><span data-stu-id="2ebff-110">To configure web services</span></span>

1.  <span data-ttu-id="2ebff-111">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="2ebff-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2ebff-112">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="2ebff-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="2ebff-113">Wählen Sie im Topologie-Generator in der Konsolenstruktur unter **Front-End-Server der Standard Edition**, **Enterprise Edition-Front-End-Pools**und **Verzeichnis Pools**den Namen des Pools aus.</span><span class="sxs-lookup"><span data-stu-id="2ebff-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="2ebff-114">Klicken Sie mit der rechten Maustaste auf den Namen, dann auf **Eigenschaften bearbeiten** und schließlich auf **Webdienste**.</span><span class="sxs-lookup"><span data-stu-id="2ebff-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="2ebff-115">Fügen Sie unter **Externer FQDN für Webdienste** den FQDN hinzu bzw. bearbeiten Sie ihn, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ebff-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2ebff-116">Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="2ebff-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="2ebff-117">Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ebff-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="2ebff-118">Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2ebff-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="2ebff-119">Stellen Sie sicher, dass die Überwachungs- und veröffentlichten Ports für Ihre Umgebung korrekt konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="2ebff-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="2ebff-120">Wiederholen Sie diese Schritte für alle Standard Edition-Server, Front-End-Pools und Director-Pools in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="2ebff-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="2ebff-121">Klicken Sie in der Konsolenstruktur auf **Lync Server 2013**, und klicken Sie anschließend im Bereich **Aktionen** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="2ebff-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="2ebff-122">Bei der Konfiguration der Überwachungs- und veröffentlichten Ports sollten Sie folgende Anforderungen beachten:</span><span class="sxs-lookup"><span data-stu-id="2ebff-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="2ebff-123">Die angezeigten Überwachungsports entsprechen den Ports, die für die Internetinformationsdienste (Internet Information Services, IIS) auf jedem Front-End-Server konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="2ebff-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="2ebff-p105">Der interne und der externe Überwachungsport müssen für IIS unterschiedlich lauten. Bei den externen Überwachungsports stimmen diese in der Regel überein, da ein Port das Hardwaregerät zum Lastenausgleich für den internen Webdatenverkehr und ein Port den Reverseproxyserver für den externen Webdatenverkehr repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="2ebff-p105">The internal and external listening ports must be different for IIS. For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="2ebff-126">Sie können die internen Webdienste auf einer Front-End-Pool, einem Director oder einem Directorpool außer Kraft setzen und ihren eigenen FQDN definieren.</span><span class="sxs-lookup"><span data-stu-id="2ebff-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2ebff-127">Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2ebff-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="2ebff-128">Die veröffentlichten Ports müssen auf dem Reverseproxy oder auf dem Hardwaregerät zum Lastenausgleich als Überwachungsports konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2ebff-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="2ebff-p106">Für einen Front-End-Pool (nicht im Beispiel gezeigt) muss sich der interne FQDN für den SIP-Pool von dem internen FQDN der Webdienste unterscheiden, da der Webdatenverkehr über das Hardwaregerät zum Lastenausgleich und der interne Datenverkehr des SIP-Pools über den DNS-Lastenausgleich verläuft. Diese Anforderung muss erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="2ebff-p106">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer. This requirement must be met.</span></span>

  - <span data-ttu-id="2ebff-131">Bei einer lync Server Standard Edition-Bereitstellung muss kein interner FQDN für Webdienste außer Kraft gesetzt werden, da dieser Server nicht Lastenausgleich sein kann.</span><span class="sxs-lookup"><span data-stu-id="2ebff-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="2ebff-132">Wenn in Ihrer Umgebung ein Hardwaregerät zum Lastenausgleich vorhanden ist, das Sie sowohl für den internen als auch für den Webdatenverkehr verwenden, kann der Topologie-Generator diese Unterscheidung nicht vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2ebff-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="2ebff-133">Webdienst-FQDNs sollten leicht voneinander unterschieden werden; Dadurch wird sichergestellt, dass die URL-Umleitung Clients auf den entsprechenden Server verweist.</span><span class="sxs-lookup"><span data-stu-id="2ebff-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="2ebff-134">Wenn Sie beispielsweise zwei FQDNs haben, sollten Sie eine Meeting.contoso.com und die andere Conferencing.contoso.com benennen.</span><span class="sxs-lookup"><span data-stu-id="2ebff-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="2ebff-135">Möglicherweise treten Umleitungs Probleme auf, wenn Sie FQDNs mit ähnlicheren Namen wie meet1.contoso.com und meet2.contoso.com haben.</span><span class="sxs-lookup"><span data-stu-id="2ebff-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="2ebff-136">Die externen Webdienste funktionieren zusammen mit einem Reverseproxy im Umkreisnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="2ebff-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="2ebff-137">Es stellt Clients externen Zugriff auf mithilfe dieser Webdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="2ebff-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="2ebff-138">Die an dieser Stelle konfigurierten FQDNs werden an Clients gesendet, wenn diese sich anmelden, und sie werden bei einer Remoteverbindung zum Herstellen einer HTTPS-Verbindung zurück zum Reverseproxy eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="2ebff-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="2ebff-139">Der Reverseproxyserver leitet den FQDN für den externen Webdienst an ein internes Hardwaregerät zum Lastenausgleich oder direkt an den Pool weiter.</span><span class="sxs-lookup"><span data-stu-id="2ebff-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="2ebff-140">Der Reverseproxy muss in der Lage sein, den externen FQDN für die Webdienste in die IP-Adresse des internen Webservers aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="2ebff-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="2ebff-141">Der FQDN für externe Webdienste muss im öffentlichen Internet auflösbar sein.</span><span class="sxs-lookup"><span data-stu-id="2ebff-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="2ebff-142">Wenn es sich bei dem internen Server um einen Standard Edition-Server handelt, handelt es sich bei dem internen FQDN um den Standard Edition-Server-FQDN.</span><span class="sxs-lookup"><span data-stu-id="2ebff-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="2ebff-143">Handelt es sich bei Ihrem internen Server um einen Front-End-Pool, entspricht der FQDN einer virtuellen IP (VIP) für das Hardwaregerät zum Lastenausgleich, das den Lastenausgleich für die internen Webfarmserver durchführt.</span><span class="sxs-lookup"><span data-stu-id="2ebff-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="2ebff-144">Ein Hardwaregerät zum Lastenausgleich ist in einem Front-End-Pool mit mehreren Enterprise Edition-Servern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2ebff-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="2ebff-145">Für einen Standard Edition-Server oder einen einzelnen Front-End-Server der Enterprise Edition ist kein Lastenausgleichssystem erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2ebff-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

