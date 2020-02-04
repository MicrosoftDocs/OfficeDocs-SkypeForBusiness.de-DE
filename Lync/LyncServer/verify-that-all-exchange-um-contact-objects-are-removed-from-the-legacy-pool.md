---
title: Überprüfen, ob alle Exchange um-Kontaktobjekte aus dem Legacy Pool entfernt wurden
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
ms.openlocfilehash: 0e49aa2fdef3731a34de05e04b8195cb8aa32cd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="99be1-102">Überprüfen, ob alle Exchange um-Kontaktobjekte aus dem Legacy Pool entfernt wurden</span><span class="sxs-lookup"><span data-stu-id="99be1-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99be1-103">_**Letztes Änderungsdatum des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="99be1-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="99be1-104">Verwenden Sie entweder das **OCSUmUtil** -Tool oder das Cmdlet " **Get-CsExumContact** ", um zu überprüfen, ob Exchange um-Kontaktobjekte aus dem Legacy Office Communications Server 2007 R2-Pool entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="99be1-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="99be1-105">**OCSUmUtil** befindet sich im folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="99be1-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="99be1-106">% Programmdateien%\\allgemeine Dateien\\lync Server 2013\\unter\\stützt OCSUMUtil. exe</span><span class="sxs-lookup"><span data-stu-id="99be1-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="99be1-107">**OCSUmUtil** muss von einem Benutzerkonto ausgeführt werden, das Folgendes hat:</span><span class="sxs-lookup"><span data-stu-id="99be1-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="99be1-108">Mitgliedschaft in der Gruppe "RTCUniversalServerAdmins" und "RTCUniversalUserAdmins" (die Rechte zum Lesen von Exchange Server Unified Messaging-Einstellungen umfasst)</span><span class="sxs-lookup"><span data-stu-id="99be1-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="99be1-109">Domänenrechte zum Erstellen von Kontaktobjekten im angegebenen Organisationseinheitscontainer (OU)</span><span class="sxs-lookup"><span data-stu-id="99be1-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="99be1-110">Ausführliche Informationen zur Verwendung des Cmdlets **Get-CsExumContact** finden Sie unter [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="99be1-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

