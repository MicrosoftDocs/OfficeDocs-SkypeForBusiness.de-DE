---
title: Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7815f78dfa5f2b4aab3f09102a9948498c20cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="cc2a8-102">Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden</span><span class="sxs-lookup"><span data-stu-id="cc2a8-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc2a8-103">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="cc2a8-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="cc2a8-104">Verwenden Sie entweder das **OCSUmUtil** -Tool oder das Cmdlet **Get-CsExumContact** , um sicherzustellen, dass Exchange um Kontaktobjekte aus dem Legacy Office Communications Server 2007 R2-Pool entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc2a8-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="cc2a8-105">**OCSUmUtil** ist im folgenden Ordner gespeichert:</span><span class="sxs-lookup"><span data-stu-id="cc2a8-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="cc2a8-106">% Programmdateien%\\allgemeine Dateien\\lync Server 2013\\unter\\stützen OCSUMUtil. exe</span><span class="sxs-lookup"><span data-stu-id="cc2a8-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="cc2a8-107">**OCSUmUtil** muss von einem Benutzerkonto mit folgenden Eigenschaften ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="cc2a8-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="cc2a8-108">Mitgliedschaft in den Gruppen RTCUniversalServerAdmins und RTCUniversalUserAdmins (mit der Berechtigung zum Lesen von Exchange Server Unified Messaging-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="cc2a8-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="cc2a8-109">Domänenrechte zum Erstellen von Kontaktobjekten im angegebenen OU-Container (Organizational Unit, Organisationseinheit)</span><span class="sxs-lookup"><span data-stu-id="cc2a8-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="cc2a8-110">Ausführliche Informationen zur Verwendung des **Get-CsExumContact** -Cmdlets finden Sie unter [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="cc2a8-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

