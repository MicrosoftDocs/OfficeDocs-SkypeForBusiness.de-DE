---
title: 'Lync Server 2013: rollenbasierte Zugriffssteuerung (RBAC)'
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
ms.openlocfilehash: 46f0fd496c8aa42a1dc498df00288c807a7556cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="70a6a-102">Rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70a6a-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70a6a-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="70a6a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="70a6a-104">Microsoft lync Server 2013 umfasst Rollenbasierte Zugriffssteuerungsgruppen, mit denen Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards aufrecht erhalten können.</span><span class="sxs-lookup"><span data-stu-id="70a6a-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="70a6a-105">Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt.</span><span class="sxs-lookup"><span data-stu-id="70a6a-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="70a6a-106">Ausführliche Informationen zur Gesamtstrukturvorbereitung finden Sie unter [Active Directory-Domänendienste für lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="70a6a-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="70a6a-107">Ausführliche Informationen zu den von der Gesamtstrukturvorbereitung erstellten Gruppen finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="70a6a-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="70a6a-108">Mit RBAC werden Administratorrechte erteilt, indem Benutzer vordefinierten Administratorrollen zugewiesen werden, einschließlich der 11 vordefinierten Rollen, die viele häufige administrative Aufgaben abdecken.</span><span class="sxs-lookup"><span data-stu-id="70a6a-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="70a6a-109">Jede Rolle ist einer bestimmten Liste von lync Server-Verwaltungsshell-Cmdlets zugeordnet, die Benutzer in dieser Rolle ausführen dürfen.</span><span class="sxs-lookup"><span data-stu-id="70a6a-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="70a6a-110">Sie können RBAC verwenden, um das Prinzip der "geringsten Rechte" zu befolgen, in dem Benutzer nur die administrativen Fähigkeiten erhalten, die Ihre Aufträge benötigen.</span><span class="sxs-lookup"><span data-stu-id="70a6a-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="70a6a-111">Ausführliche Informationen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="70a6a-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

