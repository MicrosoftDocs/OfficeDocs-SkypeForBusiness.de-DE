---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="9c9f7-102">Ändern einfacher URLs nach der Migration</span><span class="sxs-lookup"><span data-stu-id="9c9f7-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c9f7-103">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="9c9f7-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="9c9f7-104">Lync Server unterstützt drei einfache URLs:</span><span class="sxs-lookup"><span data-stu-id="9c9f7-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="9c9f7-105">**Meet** wird als Basis-URL für alle Konferenzen auf der Website oder Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="9c9f7-106">Mit der einfachen URL für Besprechungen sind Links zu Besprechungen einfach zu verstehen und einfach zu kommunizieren und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="9c9f7-107">**Einwahl** ermöglicht den Zugriff auf die Webseite für Einwahlkonferenzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="9c9f7-108">Die Einwahl einfache URL ist in allen Besprechungseinladungen enthalten, damit Benutzer, die sich in die Besprechung einwählen möchten, auf die erforderlichen Telefonnummern und PIN-Informationen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="9c9f7-109">Der **Administrator** ermöglicht den schnellen Zugriff auf die lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="9c9f7-110">Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="9c9f7-111">Nach der Migration zu lync Server 2013 müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="9c9f7-112">Wenn der Legacy-lync Server 2010-Director in der Topologie weiterhin verwendet wird, sind keine Änderungen an ihren einfachen URLs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="9c9f7-113">Wenn der lync Server 2010-Director nach der Migration aus der Topologie entfernt wird, müssen die einfachen URL-DNS-Einträge so aktualisiert werden, dass Sie auf einen der lync Server 2013-Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="9c9f7-114">Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie Enable-CsComputer auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="9c9f7-115">Ändern einfacher URLs nach der Migration</span><span class="sxs-lookup"><span data-stu-id="9c9f7-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="9c9f7-116">**So aktualisieren Sie die einfache URL für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="9c9f7-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="9c9f7-117">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="9c9f7-118">Wählen Sie im linken Bereich und dann unter Besprechungs- **URLs** **einfache URLs** aus: Wählen Sie die URL erfüllen aus, und klicken Sie dann auf **URL bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="9c9f7-119">Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie dann auf **OK** , um die bearbeitete URL zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="9c9f7-120">**So aktualisieren Sie die einfache Administrator-URL**</span><span class="sxs-lookup"><span data-stu-id="9c9f7-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="9c9f7-121">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="9c9f7-122">Wählen Sie im linken Bereich **einfache URLs** aus, und geben Sie dann unter **Administratorzugriff-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf die lync Server 2013-Systemsteuerung benötigen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="9c9f7-123">Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="9c9f7-124">Die einfachste Option ist <STRONG> https://admin.</STRONG> &lt;Domäne&gt;aus.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c9f7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c9f7-125">See Also</span></span>


[<span data-ttu-id="9c9f7-126">Planung für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c9f7-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

