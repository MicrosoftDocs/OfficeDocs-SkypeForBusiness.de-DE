---
title: 'Lync Server 2013: Ändern des standardmäßigen URL-Filters'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default URL filter
ms:assetid: 80a472b3-054e-45a6-80fc-9ee2bda28ee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182544(v=OCS.15)
ms:contentKeyID: 48184653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15511ea6b48697cddfebc40c671880a14a545557
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="d4aa2-102">Ändern des standardmäßigen URL-Filters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4aa2-102">Modify the default URL filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4aa2-103">_**Letztes Änderungsstand des Themas:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="d4aa2-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="d4aa2-104">Mit dem Filter "Instant Messaging (Sofortnachrichten)" stellt lync Server 2013 einen globalen URL-Filter bereit, der bestimmte URLs blockiert, die in Chat Unterhaltungen zwischen Benutzern in der gesamten lync Server 2013-Bereitstellung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d4aa2-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="d4aa2-105">Mithilfe von lync Server-Systemsteuerung können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="d4aa2-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="d4aa2-106">Blockieren aller oder einiger URLs in Sofortnachrichtenunterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="d4aa2-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="d4aa2-p102">Zulassen aller URLs. Optional können Sie einen Hinweis erstellen, der am Anfang einer Sofortnachricht eingefügt wird, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="d4aa2-p102">Allow all URLs. As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="d4aa2-109">Zulassen bestimmter URLs und Einfügen einer Warnung in Sofortnachrichten, die eine URL enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4aa2-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="d4aa2-110">Zusätzlich können Sie URLs blockieren, die bestimmte Dateitypen enthalten, oder lediglich Internet-URLs blockieren, indem Sie die Übermittlung von URLs in der lokalen Intranetzone des Servers – Intranet-URLs – zulassen.</span><span class="sxs-lookup"><span data-stu-id="d4aa2-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="d4aa2-111">Ausführliche Informationen zur URL-Filterung finden Sie unter [Configuring File Transfer and URL Filtering for Instant Messaging (Sofortnachrichten) in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="d4aa2-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d4aa2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4aa2-112">See Also</span></span>


[<span data-ttu-id="d4aa2-113">Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4aa2-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="d4aa2-114">Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort</span><span class="sxs-lookup"><span data-stu-id="d4aa2-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="d4aa2-115">Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="d4aa2-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="d4aa2-116">Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4aa2-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

