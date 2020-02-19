---
title: 'Lync Server 2013: Bearbeiten oder konfigurieren einfacher URLs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1618ca331b66612051b2a824aa5ebd2adfac043a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="be382-102">Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be382-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be382-103">_**Letztes Änderungsstand des Themas:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="be382-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="be382-p101">Für dieses Verfahren ist keine Mitgliedschaft in einer lokalen Administratorgruppe oder einer Domänengruppe mit besonderen Rechten erforderlich. Melden Sie sich als Standardbenutzer bei einem Computer an.</span><span class="sxs-lookup"><span data-stu-id="be382-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="be382-106">Lync Server 2013 verwendet einfache URLs, um interne und externe Aufrufe von Diensten auf der Front-End-Server oder auf dem Director direkt zu leiten, sofern ein solcher bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="be382-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="be382-107">Weitere Informationen zu einfachen URLs finden Sie unter [Planning for Simple URLs in lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="be382-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="be382-108">Sie können das Format für ihre einfachen URLs aus mehreren Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="be382-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="be382-109">Ausführliche Informationen zu diesen Optionen finden Sie unter [DNS Requirements for Simple URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="be382-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="be382-110">Standardmäßig werden einfache URLs in Form von konfiguriert (beispielsweise die einfache URL für die Einwahl): https://dialin.\<SIP Domäne\></span><span class="sxs-lookup"><span data-stu-id="be382-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="be382-111">So konfigurieren Sie einfache URLs</span><span class="sxs-lookup"><span data-stu-id="be382-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="be382-112">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Knoten **lync Server** , und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="be382-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="be382-113">Wählen Sie im Bereich **einfache URLs** entweder **Telefon Zugriffs-URLs:** (Einwahl) oder **Besprechungs-URLs:** (Meet) zum Bearbeiten aus, und klicken Sie dann auf **URL bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="be382-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="be382-114">Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK**, um die bearbeitete URL zu speichern.</span><span class="sxs-lookup"><span data-stu-id="be382-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="be382-115">Das hier gezeigte Beispiel hat die Einwahl-URL https://pool01.contoso.net/dialinin geändert.</span><span class="sxs-lookup"><span data-stu-id="be382-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="be382-116">Bearbeiten Sie ggf. auch die Besprechungs-URL, indem Sie dieselben Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="be382-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="be382-117">So definieren Sie die optionale einfache URL für den administrativen Zugriff</span><span class="sxs-lookup"><span data-stu-id="be382-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="be382-118">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Knoten **lync Server** , und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="be382-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="be382-119">Geben Sie im Feld **Administrative Zugriffs-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf lync Server 2013 Systemsteuerung wünschen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="be382-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="be382-120">Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="be382-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="be382-121">Die einfachste Option ist <STRONG> https://admin.</STRONG> &lt;Domäne&gt;.</span><span class="sxs-lookup"><span data-stu-id="be382-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="be382-122">Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge (Domain Name System) und Zertifikate für einfache URLs bewusst sein.</span><span class="sxs-lookup"><span data-stu-id="be382-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="be382-123">Wenn die Änderung sich auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und Zertifikate ändern.</span><span class="sxs-lookup"><span data-stu-id="be382-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="be382-124">Wenn beispielsweise von https://lync.contoso.com/Meet in https://meet.contoso.com geändert wird, wird die Basis-URL von lync.contoso.com in Meet.contoso.com geändert, sodass Sie die DNS-Einträge und Zertifikate für den Verweis auf Meet.contoso.com ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="be382-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="be382-125">Wenn Sie die einfache URL von https://lync.contoso.com/Meet in https://lync.contoso.com/Meetingsgeändert haben, bleibt die Basis-URL von lync.contoso.com unverändert, sodass keine DNS-oder Zertifikat Änderungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="be382-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="be382-126">Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie das Cmdlet <STRONG>enable-CsComputer</STRONG> für jeden Director ausführen und Front-End-Server, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="be382-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="be382-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be382-127">See Also</span></span>


[<span data-ttu-id="be382-128">Planen von einfachen URLs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be382-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

