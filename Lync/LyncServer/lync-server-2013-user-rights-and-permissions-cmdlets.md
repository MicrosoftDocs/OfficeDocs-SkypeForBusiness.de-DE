---
title: 'Lync Server 2013: Cmdlets für Benutzerrechte und Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User rights and permissions cmdlets
ms:assetid: b53aae4c-651f-4cbc-a762-ba818d63897e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415672(v=OCS.15)
ms:contentKeyID: 48185178
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab95364abf7bdd0a256f2cd8272d14ec1bc86968
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-rights-and-permissions-cmdlets-in-lync-server-2013"></a><span data-ttu-id="030de-102">Cmdlets für Benutzerrechte und Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="030de-102">User rights and permissions cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="030de-103">_**Letztes Änderungsdatum des Themas:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="030de-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="030de-104">Die Cmdlets für Benutzerberechtigungen werden in erster Linie zum Verwalten der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC), der neuen Technologie zum Delegieren der administrativen Steuerung von Microsoft lync Server 2013, verwendet.</span><span class="sxs-lookup"><span data-stu-id="030de-104">The user permission cmdlets are primarily used to manage role-based access control (RBAC), the new technology for delegating administrative control of Microsoft Lync Server 2013.</span></span>

<div>

## <a name="user-permission-cmdlets"></a><span data-ttu-id="030de-105">Cmdlets für Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="030de-105">User Permission Cmdlets</span></span>

<span data-ttu-id="030de-106">Die folgende Liste enthält Cmdlets, die sich direkt auf die Verwaltung von Benutzerberechtigungen beziehen:</span><span class="sxs-lookup"><span data-stu-id="030de-106">The following is a list of cmdlets that relate directly to managing user permissions:</span></span>

<span data-ttu-id="030de-107">**Benutzerberechtigungen**</span><span class="sxs-lookup"><span data-stu-id="030de-107">**User Permissions**</span></span>

  - <span></span>  
    <span data-ttu-id="030de-108">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-108">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-109">[Neu – CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-109">[New-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-110">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-110">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-111">[Satz-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-111">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-112">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-112">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="030de-113">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-113">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="030de-114">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-114">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-115">[REVOKE-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-115">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-116">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-116">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="030de-117">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-117">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-118">[REVOKE-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-118">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="030de-119">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="030de-119">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="030de-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="030de-120">See Also</span></span>


[<span data-ttu-id="030de-121">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="030de-121">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

