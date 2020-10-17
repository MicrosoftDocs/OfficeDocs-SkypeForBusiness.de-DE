---
title: Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden
description: Stellen Sie sicher, dass alle Exchange um Kontaktobjekte aus dem vorversionspool entfernt werden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555511"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="9b6b5-103">Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden</span><span class="sxs-lookup"><span data-stu-id="9b6b5-103">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b6b5-104">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="9b6b5-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9b6b5-105">Verwenden Sie entweder das **OCSUmUtil** -Tool oder das Cmdlet **Get-CsExumContact** , um sicherzustellen, dass Exchange um Kontaktobjekte aus dem Legacy Office Communications Server 2007 R2-Pool entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-105">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="9b6b5-106">**OCSUmUtil** ist im folgenden Ordner gespeichert:</span><span class="sxs-lookup"><span data-stu-id="9b6b5-106">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="9b6b5-107">% Programmdateien% \\ Allgemeine Dateien \\ lync Server 2013 \\ Support \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="9b6b5-107">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="9b6b5-108">**OCSUmUtil** muss von einem Benutzerkonto mit folgenden Eigenschaften ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9b6b5-108">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="9b6b5-109">Mitgliedschaft in den Gruppen RTCUniversalServerAdmins und RTCUniversalUserAdmins (mit der Berechtigung zum Lesen von Exchange Server Unified Messaging-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="9b6b5-109">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="9b6b5-110">Domänenrechte zum Erstellen von Kontaktobjekten im angegebenen OU-Container (Organizational Unit, Organisationseinheit)</span><span class="sxs-lookup"><span data-stu-id="9b6b5-110">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="9b6b5-111">Ausführliche Informationen zur Verwendung des **Get-CsExumContact** -Cmdlets finden Sie unter [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-111">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

