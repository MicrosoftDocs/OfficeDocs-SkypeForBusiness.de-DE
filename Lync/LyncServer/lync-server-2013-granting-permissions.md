---
title: 'Lync Server 2013: Gewähren von Berechtigungen'
description: 'Lync Server 2013: Gewähren von Berechtigungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bdb2b1ef39b85caa89c7597f455e6e4fc08e44e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554501"
---
# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="a2904-103">Erteilen von Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2904-103">Granting permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2904-104">_**Letztes Änderungsstand des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a2904-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a2904-105">Für das Setup können Sie der universellen Gruppe RTCUniversalServerAdmins Berechtigungen für eine bestimmte Active Directory Organisationseinheit (Organizational Unit, OU) erteilen, sodass Mitglieder der Gruppe RTCUniversalServerAdmins in dieser Organisationseinheit lync Server 2013 in der angegebenen Domäne installieren können.</span><span class="sxs-lookup"><span data-stu-id="a2904-105">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="a2904-106">Wenn Sie Berechtigungen für eine Organisationseinheit erteilen, werden die folgenden Berechtigungen erteilt:</span><span class="sxs-lookup"><span data-stu-id="a2904-106">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="a2904-107">Lesen</span><span class="sxs-lookup"><span data-stu-id="a2904-107">Read</span></span>

  - <span data-ttu-id="a2904-108">Schreiben</span><span class="sxs-lookup"><span data-stu-id="a2904-108">Write</span></span>

  - <span data-ttu-id="a2904-109">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="a2904-109">ReadSPN</span></span>

  - <span data-ttu-id="a2904-110">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="a2904-110">WriteSPN</span></span>

<span data-ttu-id="a2904-111">Zur Verwaltung können Sie bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf die Organisationseinheit zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="a2904-111">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="a2904-112">Bei den Berechtigungen, die Sie zur angegebenen Organisationseinheit hinzufügen, handelt es sich um die gleichen Berechtigungen, die das Cmdlet **Enable-CsAdDomain** den OU-Containern für Computer und Benutzer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="a2904-112">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2904-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2904-113">In This Section</span></span>

  - [<span data-ttu-id="a2904-114">Erteilen von Setup Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2904-114">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="a2904-115">Erteilen von Berechtigungen für Organisationseinheiten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2904-115">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

