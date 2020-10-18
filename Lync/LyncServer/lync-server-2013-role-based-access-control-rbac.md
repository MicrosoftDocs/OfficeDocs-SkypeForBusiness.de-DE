---
title: 'Lync Server 2013: rollenbasierte Zugriffssteuerung (RBAC)'
description: 'Lync Server 2013: rollenbasierte Zugriffssteuerung (RBAC).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6586517083ff6cd2c4e20d83e9b8f861edf800c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576581"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="1b2bd-103">Rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b2bd-103">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b2bd-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="1b2bd-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="1b2bd-105">Microsoft lync Server 2013 enthält Role-Based Zugriffssteuerungsgruppen, mit denen Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards aufrecht erhalten können.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-105">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="1b2bd-106">Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-106">These groups are created during forest preparation.</span></span> <span data-ttu-id="1b2bd-107">Ausführliche Informationen zur Gesamtstrukturvorbereitung finden Sie unter [Active Directory-Domänendienste für lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="1b2bd-107">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="1b2bd-108">Ausführliche Informationen zu den von der Gesamtstrukturvorbereitung erstellten Gruppen finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-108">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="1b2bd-109">Mit RBAC werden Administratorrechte erteilt, indem Benutzer vordefinierten Administratorrollen zugewiesen werden, einschließlich der 11 vordefinierten Rollen, die viele häufige administrative Aufgaben abdecken.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-109">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="1b2bd-110">Jede Rolle ist einer bestimmten Liste von lync Server-Verwaltungsshell-Cmdlets zugeordnet, die Benutzer in dieser Rolle ausführen dürfen.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-110">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="1b2bd-111">Sie können RBAC verwenden, um das Prinzip der "geringsten Rechte" zu befolgen, in dem Benutzer nur die administrativen Fähigkeiten erhalten, die Ihre Aufträge benötigen.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-111">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="1b2bd-112">Ausführliche Informationen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-112">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

