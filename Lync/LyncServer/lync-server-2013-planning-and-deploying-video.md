---
title: 'Lync Server 2013: Planen und Bereitstellen von Video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d22ebee3227577edea9f937dddc510424d021dd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="476a3-102">Planen und Bereitstellen von Videos in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476a3-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="476a3-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="476a3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="476a3-104">In lync Server 2013 werden die folgenden neuen Videofeatures vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="476a3-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="476a3-105">**HD-Video**   Benutzer können Auflösungen bis zu Full High Definition (HD) (1920 x 1080) in zwei-Parteien-anrufen und Konferenzen mit mehreren Teilnehmern durchführen.</span><span class="sxs-lookup"><span data-stu-id="476a3-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="476a3-106">**Galerieansicht**   in Videokonferenzen mit mehr als zwei Personen können Benutzer Videos von Teilnehmern in der Konferenz sehen.</span><span class="sxs-lookup"><span data-stu-id="476a3-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="476a3-107">Bei Konferenzen mit mehr als fünf Teilnehmern werden nur die Videos der aktivsten Teilnehmer in der obersten Reihe angezeigt, und für die anderen Teilnehmer wird ein Foto angezeigt.</span><span class="sxs-lookup"><span data-stu-id="476a3-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="476a3-108">**H. 264-Video**   der h. 264-Videocodec ist jetzt der Standard für die Codierung von Video auf lync 2013 Clients.</span><span class="sxs-lookup"><span data-stu-id="476a3-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="476a3-109">H.264-Video unterstützt mehr Auflösungen und Frameraten und verbessert die Videoskalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="476a3-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="476a3-110">Lync Server 2013 unterstützt weiterhin den VC1-Codec für die Interoperabilität mit früheren Versionen von lync.</span><span class="sxs-lookup"><span data-stu-id="476a3-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="476a3-111">Details und Hintergrundinformationen zum neuen Videocodec finden Sie im Blog Artikel "Video Interoperability in lync 2013" unter von Jeff Schertz <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span><span class="sxs-lookup"><span data-stu-id="476a3-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="476a3-112">In diesem Abschnitt wird beschrieben, wie Sie Bandbreite für Video in lync Server 2013 verwalten und Videofunktionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="476a3-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="476a3-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="476a3-113">In This Section</span></span>

  - [<span data-ttu-id="476a3-114">Konfigurieren der Videobandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476a3-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="476a3-115">Konfigurieren der Katalogansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476a3-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="476a3-116">Konfigurieren von Video Beispielszenarien für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476a3-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="476a3-117">Überlegungen zur Interoperabilität für Videokonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476a3-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

