---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9ab1ea2180c8fa4ba4f40cbf621816fe41ea7f9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="f2d84-102">Vorbereiten der Gesamtstruktur auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2d84-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f2d84-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f2d84-104">Bei der Gesamtstrukturvorbereitung werden Active Directory globale Einstellungen und Objekte und Active Directory universelle Gruppen für die Verwendung durch lync Server 2013 erstellt, und es werden geeignete Zugriffsberechtigungen für die Active Directory-Objekte erteilt.</span><span class="sxs-lookup"><span data-stu-id="f2d84-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="f2d84-105">Eine Beschreibung der universellen Gruppen und der globalen Einstellungen und Objekte, die von der Gesamtstrukturvorbereitung erstellt werden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommen](lync-server-2013-changes-made-by-forest-preparation.md)wurden.</span><span class="sxs-lookup"><span data-stu-id="f2d84-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="f2d84-106">Bei der Gesamtstrukturvorbereitung werden auch Objekte erstellt, die Eigenschaftensätze und Anzeigebezeichner enthalten, die von lync Server 2013 verwendet werden, und diese im Konfigurationscontainer speichern.</span><span class="sxs-lookup"><span data-stu-id="f2d84-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2d84-107">Stellen Sie sicher, dass Änderungen der Schemavorbereitung auf alle Domänencontroller repliziert wurden, bevor Sie das Verfahren zur Gesamtstrukturvorbereitung durchführen.</span><span class="sxs-lookup"><span data-stu-id="f2d84-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="f2d84-108">Wenn die Replikation noch nicht abgeschlossen wurde, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f2d84-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="f2d84-109">Wenn Sie eine neue lync Server-Bereitstellung durchführen, müssen Sie globale Einstellungen im Konfigurationscontainer speichern.</span><span class="sxs-lookup"><span data-stu-id="f2d84-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="f2d84-110">Wenn Sie ein Upgrade von einer früheren Version durchführen und globale Einstellungen weiterhin im Systemcontainer speichern, können Sie weiterhin den Systemcontainer verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2d84-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="f2d84-111">Zum Durchführen dieses Verfahrens müssen Sie ein Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die Stammdomäne der Gesamtstruktur sein.</span><span class="sxs-lookup"><span data-stu-id="f2d84-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f2d84-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2d84-112">In This Section</span></span>

  - [<span data-ttu-id="f2d84-113">Laufende Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="f2d84-114">Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

