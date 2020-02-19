---
title: 'Lync Server 2013: Konfigurieren von Webfarm-FQDNs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50813855e4181add65ff279933a952116768dcec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="3042d-102">Konfigurieren von Webfarm-FQDNs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3042d-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3042d-103">_**Letztes Änderungsstand des Themas:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="3042d-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="3042d-104">Wenn Sie die Konfiguration der Standard Edition-Server, Front-End-Pool, Director oder Directorpool im Topologie-Generator definiert haben, konfigurieren Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für externe Webdienste.</span><span class="sxs-lookup"><span data-stu-id="3042d-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="3042d-105">Während des Anmeldeprozesses eines Clients, der in der Standard Edition-Server oder Front-End-Pool verwaltet wird, werden die konfigurierten FQDNs der Webdienste über die in-Band-Bereitstellung gesendet.</span><span class="sxs-lookup"><span data-stu-id="3042d-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="3042d-106">Wenn Sie die URL für externe Webdienste hinzufügen oder ändern müssen, verwenden Sie den Topologie-Generator, um die Webdienstkonfiguration mit dem Verfahren in diesem Thema zu konfigurieren oder neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3042d-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="3042d-107">So konfigurieren Sie einen externen Pool-FQDN für Webdienste</span><span class="sxs-lookup"><span data-stu-id="3042d-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="3042d-108">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="3042d-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="3042d-109">Klicken Sie im Topologie-Generator in der Konsolenstruktur unter **Standard Edition-Front-End**, **Enterprise Edition-Front-End**und **Directors**mit der rechten Maustaste auf den Namen des Pools, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3042d-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="3042d-110">Fügen Sie im Abschnitt **Webdienste** den **externen Webdienste-FQDN**hinzu, oder bearbeiten Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="3042d-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="3042d-111">Überprüfen und Anpassen der **Überwachungs Ports** für http und HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3042d-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="3042d-112">Die Standardeinstellungen sind:</span><span class="sxs-lookup"><span data-stu-id="3042d-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="3042d-113">**Abhör-Ports:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="3042d-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="3042d-114">**Veröffentlichte Ports:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="3042d-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="3042d-115">Dabei handelt es sich bei den **abhörenden Ports** um den Port, für den die externen Webdienste für den Empfang von Anforderungen vom Reverseproxy konfiguriert werden, und die **veröffentlichten** Ports sind die Ports, die extern vom Reverseproxy veröffentlicht werden und den Clients während der in-Band-Bereitstellung mitgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="3042d-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="3042d-116">Wenn Sie Ihre Ergänzungen und Updates abgeschlossen haben, klicken Sie auf **OK** , um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="3042d-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="3042d-117">Klicken Sie mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="3042d-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3042d-118">Nachdem die Veröffentlichung erfolgreich abgeschlossen wurde, wird möglicherweise ein Link angezeigt, in dem Sie darüber informiert werden, dass zusätzliche Schritte ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3042d-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="3042d-119">Wenn Sie auf den Link klicken, wird eine Liste der Server geöffnet, die von den im Topologie-Generator vorgenommenen Änderungen betroffen sind, sodass Sie den lync Server-Bereitstellungs-Assistenten auf jedem aufgelisteten Server erneut ausführen müssen, um die Konfiguration für hinzugefügte, entfernte oder geänderte Komponenten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3042d-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="3042d-120">Wiederholen Sie diese Schritte für jeden Standard Edition-Server, Front-End-Pool, Director oder Directorpool in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="3042d-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

