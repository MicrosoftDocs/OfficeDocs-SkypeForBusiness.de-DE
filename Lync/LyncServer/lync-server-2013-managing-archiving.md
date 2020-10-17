---
title: 'Lync Server 2013: Verwalten der Archivierung'
description: 'Lync Server 2013: Verwalten der Archivierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c7010645f36a7144ea508447d2c628bc8feacb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566471"
---
# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="43cce-103">Verwalten der Lync Server 2013-Archivierung</span><span class="sxs-lookup"><span data-stu-id="43cce-103">Managing Lync Server 2013 Archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43cce-104">_**Letztes Änderungsstand des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="43cce-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="43cce-105">Die ursprüngliche Konfiguration wird beim Bereitstellen der Archivierung in Ihrer Organisation vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="43cce-105">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="43cce-106">Zu einem späteren Zeitpunkt kann es jedoch wünschenswert oder notwendig sein, die Implementierung der Archivierungsunterstützung an alltägliche Verwaltungsvorgänge oder neue Herausforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="43cce-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="43cce-107">Beispielsweise kann es sein, dass Sie die Archivierungsunterstützung für einen bestimmten Standort, einen bestimmten Pool oder bestimmte Benutzer in Ihrer Organisation verändern müssen.</span><span class="sxs-lookup"><span data-stu-id="43cce-107">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="43cce-108">Für Benutzer, die in lync Server 2013 verwaltet werden, müssen Sie die Archivierungsrichtlinien und-Konfigurationen erstellen und anpassen.</span><span class="sxs-lookup"><span data-stu-id="43cce-108">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="43cce-109">Wenn Sie Microsoft Exchange Integration verwenden, müssen Sie auch Exchange 2013 Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="43cce-109">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="43cce-110">In diesem Abschnitt finden Sie Informationen und Verfahren, mit denen Sie Änderungen an Ihrer Archivierungsbereitstellung vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="43cce-110">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="43cce-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="43cce-111">In This Section</span></span>

  - [<span data-ttu-id="43cce-112">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43cce-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="43cce-113">Verwalten der Archivierung von interner und externer Kommunikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43cce-113">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="43cce-114">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Standorte und Pools</span><span class="sxs-lookup"><span data-stu-id="43cce-114">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="43cce-115">Ändern von Archivierungsdatenbank Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43cce-115">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="43cce-116">Exportieren archivierter Daten aus lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43cce-116">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

