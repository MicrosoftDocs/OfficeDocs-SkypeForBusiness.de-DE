---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
description: 'Lync Server 2013: Vorbereiten der Gesamtstruktur.'
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
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580001"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="cb154-103">Vorbereiten der Gesamtstruktur auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb154-103">Preparing the forest for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb154-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cb154-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cb154-105">Bei der Gesamtstrukturvorbereitung werden Active Directory globale Einstellungen und Objekte und Active Directory universelle Gruppen für die Verwendung durch lync Server 2013 erstellt, und es werden geeignete Zugriffsberechtigungen für die Active Directory-Objekte erteilt.</span><span class="sxs-lookup"><span data-stu-id="cb154-105">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="cb154-106">Eine Beschreibung der universellen Gruppen und der globalen Einstellungen und Objekte, die von der Gesamtstrukturvorbereitung erstellt werden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommen](lync-server-2013-changes-made-by-forest-preparation.md)wurden.</span><span class="sxs-lookup"><span data-stu-id="cb154-106">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="cb154-107">Bei der Gesamtstrukturvorbereitung werden auch Objekte erstellt, die Eigenschaftensätze und Anzeigebezeichner enthalten, die von lync Server 2013 verwendet werden, und diese im Konfigurationscontainer speichern.</span><span class="sxs-lookup"><span data-stu-id="cb154-107">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb154-108">Stellen Sie sicher, dass Änderungen der Schemavorbereitung auf alle Domänencontroller repliziert wurden, bevor Sie das Verfahren zur Gesamtstrukturvorbereitung durchführen.</span><span class="sxs-lookup"><span data-stu-id="cb154-108">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="cb154-109">Wenn die Replikation noch nicht abgeschlossen wurde, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="cb154-109">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="cb154-110">Wenn Sie eine neue lync Server-Bereitstellung durchführen, müssen Sie globale Einstellungen im Konfigurationscontainer speichern.</span><span class="sxs-lookup"><span data-stu-id="cb154-110">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="cb154-111">Wenn Sie ein Upgrade von einer früheren Version durchführen und globale Einstellungen weiterhin im Systemcontainer speichern, können Sie weiterhin den Systemcontainer verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb154-111">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="cb154-112">Zum Durchführen dieses Verfahrens müssen Sie ein Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die Stammdomäne der Gesamtstruktur sein.</span><span class="sxs-lookup"><span data-stu-id="cb154-112">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb154-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cb154-113">In This Section</span></span>

  - [<span data-ttu-id="cb154-114">Laufende Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb154-114">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="cb154-115">Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb154-115">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

