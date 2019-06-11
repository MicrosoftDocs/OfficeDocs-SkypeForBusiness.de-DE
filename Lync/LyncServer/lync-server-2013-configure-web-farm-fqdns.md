---
title: 'Lync Server 2013: Konfigurieren von Webfarm-FQDNs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517e00baef63e3597c2f5b2b6621e62efb02ca62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="5a7f3-102">Konfigurieren von Webfarm-FQDNs für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a7f3-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a7f3-103">_**Letztes Änderungsdatum des Themas:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="5a7f3-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="5a7f3-104">Wenn Sie die Konfiguration des Standard Edition-Servers, des Front-End-Pools, des Director-oder Director-Pools in Topology Builder definiert haben, konfigurieren Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für externe Webdienste.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="5a7f3-105">Während des Anmeldeprozesses eines Clients, der sich im Standard Edition-Server oder-Front-End-Pool befindet, werden die konfigurierten Webdienste-FQDNs über die in-Band-Bereitstellung gesendet.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="5a7f3-106">Wenn Sie die externe Webdienste-URL hinzufügen oder ändern müssen, verwenden Sie den Topologie-Generator, um die Webdienstkonfiguration mithilfe des in diesem Thema beschriebenen Verfahrens zu konfigurieren oder neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="5a7f3-107">So konfigurieren Sie einen externen Pool-FQDN für Webdienste</span><span class="sxs-lookup"><span data-stu-id="5a7f3-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="5a7f3-108">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="5a7f3-109">Klicken Sie im Topologie-Generator in der Konsolenstruktur unter **Front Ends der Standard Edition**, **Enterprise Edition-Front-Ends**und **Directors**mit der rechten Maustaste auf den Namen des Pools, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5a7f3-110">Fügen Sie im Abschnitt **Webdienst** den **FQDN externer**Webdienste hinzu, oder bearbeiten Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="5a7f3-111">Überprüfen und Anpassen der **Abhör Anschlüsse** für http und HTTPS</span><span class="sxs-lookup"><span data-stu-id="5a7f3-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="5a7f3-112">Die Standardeinstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5a7f3-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="5a7f3-113">**Abhör Anschlüsse:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="5a7f3-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="5a7f3-114">**Veröffentlichte Ports:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="5a7f3-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="5a7f3-115">Hierbei handelt \*\*\*\* es sich um den Port, in dem die externen Webdienste so konfiguriert werden, dass Sie Anforderungen vom Reverse-Proxy empfangen, und die **veröffentlichten** Ports sind die Ports, die extern vom Reverse-Proxy veröffentlicht werden und an Clients während der in-Band-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="5a7f3-116">Wenn Sie Ihre Ergänzungen und Updates abgeschlossen haben, klicken Sie auf **OK** , um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="5a7f3-117">Klicken Sie mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5a7f3-118">Nachdem die Veröffentlichung erfolgreich abgeschlossen wurde, wird möglicherweise ein Link angezeigt, der Sie darüber informiert, dass weitere Schritte ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="5a7f3-119">Wenn Sie auf den Link klicken, wird eine Liste der Server geöffnet, die von den im Topologie-Generator vorgenommenen Änderungen betroffen sind, die erfordern, dass Sie den lync Server-Bereitstellungs-Assistenten auf jedem aufgelisteten Server erneut ausführen, um die Konfiguration für hinzugefügte, entfernte oder geänderte Komponenten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="5a7f3-120">Wiederholen Sie diese Schritte für jeden Standard Edition-Server, Front-End-Pool, Director-oder Director-Pool in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

