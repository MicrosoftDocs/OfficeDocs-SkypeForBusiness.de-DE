---
title: 'Lync Server 2013: Gewähren von Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="91a27-102">Gewähren von Berechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91a27-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91a27-103">_**Letztes Änderungsdatum des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="91a27-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="91a27-104">Für Setup können Sie der universellen RTCUniversalServerAdmins-Gruppe für eine bestimmte Active Directory-Organisationseinheit Berechtigungen erteilen, sodass Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU lync Server 2013 in der angegebenen Domäne installieren können.</span><span class="sxs-lookup"><span data-stu-id="91a27-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="91a27-105">Wenn Sie Berechtigungen für eine OU erteilen, werden die folgenden Berechtigungen gewährt:</span><span class="sxs-lookup"><span data-stu-id="91a27-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="91a27-106">Lesen</span><span class="sxs-lookup"><span data-stu-id="91a27-106">Read</span></span>

  - <span data-ttu-id="91a27-107">Schreiben</span><span class="sxs-lookup"><span data-stu-id="91a27-107">Write</span></span>

  - <span data-ttu-id="91a27-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="91a27-108">ReadSPN</span></span>

  - <span data-ttu-id="91a27-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="91a27-109">WriteSPN</span></span>

<span data-ttu-id="91a27-110">Für die Verwaltung können Sie den angegebenen OUs Berechtigungen hinzufügen, sodass Mitglieder der universellen RTC-Gruppen, die von der Gesamtstrukturvorbereitung erstellt wurden, auf die OUs zugreifen können, ohne dass Sie Mitglieder der Gruppe der Domänenadministratoren sein müssen.</span><span class="sxs-lookup"><span data-stu-id="91a27-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="91a27-111">Die der angegebenen Organisationseinheit hinzugefügten Berechtigungen sind dieselben Berechtigungen, die das Cmdlet **enable-CsAdDomain** den OU-Containern Computer und Benutzer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="91a27-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="91a27-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="91a27-112">In This Section</span></span>

  - [<span data-ttu-id="91a27-113">Gewähren von Setupberechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91a27-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="91a27-114">Gewähren von Berechtigungen für die Organisationseinheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91a27-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

