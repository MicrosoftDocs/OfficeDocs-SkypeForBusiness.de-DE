---
title: 'Lync Server 2013: Ändern des Standard-URL-Filters'
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
ms.openlocfilehash: 975824faa6a567992001ae10cafec61ef2ea1370
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="5bbb5-102">Ändern des Standard-URL-Filters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bbb5-102">Modify the default URL filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bbb5-103">_**Letztes Änderungsdatum des Themas:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="5bbb5-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="5bbb5-104">Mithilfe des Instant Messaging-Filters (im) stellt lync Server 2013 einen globalen URL-Filter bereit, der bestimmte URLs blockiert, die in Chat Unterhaltungen zwischen Benutzern in ihrer lync Server 2013-Bereitstellung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="5bbb5-105">Mithilfe der lync Server-Systemsteuerung können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="5bbb5-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="5bbb5-106">Blockieren Sie alle oder eine Teilmenge der URLs in Sofortnachrichtenunterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="5bbb5-107">Alle URLs zulassen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-107">Allow all URLs.</span></span> <span data-ttu-id="5bbb5-108">Optional können Sie eine Benachrichtigung erstellen, die am Anfang jeder Chatnachricht eingefügt wird, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-108">As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="5bbb5-109">Zulassen bestimmter URLs und einbeziehen einer Warnung in jede Sofortnachricht, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="5bbb5-110">Darüber hinaus können Sie festlegen, dass URLs, die bestimmte Dateitypen enthalten, blockiert werden sollen, oder nur Internet-URLs blockieren, indem Sie URLs zulassen, die sich in der lokalen Intranetzone des Servers befinden – Intranet-URLs –, um den Server zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="5bbb5-111">Details zur URL-Filterung finden Sie unter [Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb5-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5bbb5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bbb5-112">See Also</span></span>


[<span data-ttu-id="5bbb5-113">Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bbb5-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="5bbb5-114">Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für eine bestimmte Website</span><span class="sxs-lookup"><span data-stu-id="5bbb5-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="5bbb5-115">Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="5bbb5-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="5bbb5-116">Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bbb5-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

