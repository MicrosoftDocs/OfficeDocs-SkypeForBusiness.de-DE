---
title: 'Lync Server 2013: Bearbeiten oder Konfigurieren einfacher URLs'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="c7b68-102">Bearbeiten oder Konfigurieren einfacher URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7b68-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7b68-103">_**Letztes Änderungsdatum des Themas:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="c7b68-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="c7b68-104">Für dieses Verfahren ist keine Mitgliedschaft in einem lokalen Administrator oder einer privilegierten Domänengruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c7b68-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="c7b68-105">Melden Sie sich als Standardbenutzer an einem Computer an.</span><span class="sxs-lookup"><span data-stu-id="c7b68-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="c7b68-106">Lync Server 2013 verwendet einfache URLs, um interne und externe Anrufe an Dienste auf dem Front-End-Server oder an den Director weiterzuleiten, falls einer bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c7b68-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="c7b68-107">Weitere Informationen zu einfachen URLs finden Sie unter [Planen einfacher URLs in lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7b68-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="c7b68-108">Sie können das Format für ihre einfachen URLs aus verschiedenen Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="c7b68-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="c7b68-109">Ausführliche Informationen zu diesen Optionen finden Sie unter [DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7b68-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="c7b68-110">Standardmäßig werden einfache URLs in Form von (beispielsweise der Einwahl einfachen URL) konfiguriert: https://dialin.\<SIP Domäne\></span><span class="sxs-lookup"><span data-stu-id="c7b68-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="c7b68-111">So konfigurieren Sie einfache URLs</span><span class="sxs-lookup"><span data-stu-id="c7b68-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="c7b68-112">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den **lync Server** -Knoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c7b68-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c7b68-113">Wählen Sie im Bereich **Einfache URLs** entweder **Telefonzugriff-URLs:** (Dialin) oder **Besprechungs-URLs:** (Meet) aus und klicken Sie anschließend auf **URL bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c7b68-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="c7b68-114">Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie dann auf **OK** , um die bearbeitete URL zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c7b68-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="c7b68-115">Das hier gezeigte Beispiel hat die Einwahl-URL https://pool01.contoso.net/dialinin geändert.</span><span class="sxs-lookup"><span data-stu-id="c7b68-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="c7b68-116">Bearbeiten Sie ggf. auch die Besprechungs-URL, indem Sie dieselben Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="c7b68-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="c7b68-117">So definieren Sie die optionale einfache URL für den administrativen Zugriff</span><span class="sxs-lookup"><span data-stu-id="c7b68-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="c7b68-118">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den **lync Server** -Knoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c7b68-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c7b68-119">Geben Sie im Feld **Administratorzugriff-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf die lync Server 2013-Systemsteuerung benötigen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7b68-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c7b68-120">Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7b68-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="c7b68-121">Die einfachste Option ist <STRONG> https://admin.</STRONG> &lt;Domäne&gt;aus.</span><span class="sxs-lookup"><span data-stu-id="c7b68-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c7b68-122">Wenn Sie eine einfache URL nach der ersten Bereitstellung ändern, müssen Sie beachten, welche Änderungen sich auf Ihre DNS-Datensätze und -Zertifikate für einfache URLs auswirken.</span><span class="sxs-lookup"><span data-stu-id="c7b68-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="c7b68-123">Wenn die Änderung Auswirkungen auf die Basis einer einfachen URL hat, müssen Sie auch die DNS-Einträge und Zertifikate ändern.</span><span class="sxs-lookup"><span data-stu-id="c7b68-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="c7b68-124">Wenn Sie beispielsweise https://lync.contoso.com/Meet https://meet.contoso.com die Basis-URL von lync.contoso.com in Meet.contoso.com ändern, müssen Sie die DNS-Einträge und Zertifikate so ändern, dass Sie auf Meet.contoso.com verweisen.</span><span class="sxs-lookup"><span data-stu-id="c7b68-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="c7b68-125">Wenn Sie die einfache URL von https://lync.contoso.com/Meet in https://lync.contoso.com/Meetingsgeändert haben, bleibt die Basis-URL von lync.contoso.com unverändert, sodass keine DNS-oder Zertifikat Änderungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c7b68-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="c7b68-126">Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie das Cmdlet <STRONG>enable-CsComputer</STRONG> auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c7b68-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7b68-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7b68-127">See Also</span></span>


[<span data-ttu-id="c7b68-128">Planung für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7b68-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

