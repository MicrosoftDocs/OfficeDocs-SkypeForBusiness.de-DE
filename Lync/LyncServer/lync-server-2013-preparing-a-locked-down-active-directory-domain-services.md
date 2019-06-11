---
title: 'Lync Server 2013: Vorbereiten gesperrter Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 482c5a59c6dc53fc712db7e77430367dd9c37af5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="cd445-102">Vorbereiten gesperrter Active Directory-Domänendienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd445-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd445-103">_**Letztes Änderungsdatum des Themas:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="cd445-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="cd445-104">Organisationen Sperren häufig Active Directory-Domänendienste, um Sicherheitsrisiken zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="cd445-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="cd445-105">Eine gesperrte Active Directory-Umgebung kann jedoch die von lync Server 2013 erforderlichen Berechtigungen einschränken.</span><span class="sxs-lookup"><span data-stu-id="cd445-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="cd445-106">Das ordnungsgemäße Vorbereiten einer gesperrten Active Directory-Umgebung für lync Server 2013 umfasst einige zusätzliche Überlegungen und Schritte.</span><span class="sxs-lookup"><span data-stu-id="cd445-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="cd445-107">Es gibt zwei gängige Methoden, mit denen Berechtigungen in einer gesperrten Active Directory-Umgebung eingeschränkt sind:</span><span class="sxs-lookup"><span data-stu-id="cd445-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="cd445-108">Zugriffssteuerungseinträge (ACEs) für authentifizierte Benutzer werden aus Containern entfernt.</span><span class="sxs-lookup"><span data-stu-id="cd445-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="cd445-109">Die Vererbung von Berechtigungen ist für Container von Benutzer-, Kontakt-, InetOrgPerson-oder Computer Objekten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd445-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cd445-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cd445-110">In This Section</span></span>

  - [<span data-ttu-id="cd445-111">Entfernte Berechtigungen für authentifizierte Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd445-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="cd445-112">Vererbung von Berechtigungen ist für Computer-, Benutzer- oder InetOrgPerson-Container deaktiviert in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd445-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

