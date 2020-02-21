---
title: 'Lync Server 2013: Vorbereiten einer gesperrten Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e57d982983bdd5ca0f85235cd44bc2fba5b1bf7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="e5ddf-102">Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5ddf-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5ddf-103">_**Letztes Änderungsstand des Themas:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="e5ddf-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="e5ddf-104">Unternehmen sperren häufig Active Directory-Domänendienste, um Sicherheitsrisiken zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="e5ddf-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="e5ddf-105">Eine gesperrte Active Directory Umgebung kann jedoch die Berechtigungen einschränken, die lync Server 2013 erfordert.</span><span class="sxs-lookup"><span data-stu-id="e5ddf-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="e5ddf-106">Das ordnungsgemäße Vorbereiten einer gesperrten Active Directory Umgebung für lync Server 2013 umfasst einige zusätzliche Überlegungen und Schritte.</span><span class="sxs-lookup"><span data-stu-id="e5ddf-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="e5ddf-107">Zwei Möglichkeiten, wie Berechtigungen in einer gesperrten Active Directory-Umgebung beschränkt sein können, sind:</span><span class="sxs-lookup"><span data-stu-id="e5ddf-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="e5ddf-108">Zugriffssteuerungseinträge (Access Control Entries, ACEs) authentifizierter Benutzer wurden aus den Containern entfernt.</span><span class="sxs-lookup"><span data-stu-id="e5ddf-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="e5ddf-109">Die Vererbung von Berechtigungen wurde für Container mit Benutzer-, Kontakt-, InetOrgPerson- oder Computerobjekten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e5ddf-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e5ddf-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e5ddf-110">In This Section</span></span>

  - [<span data-ttu-id="e5ddf-111">Berechtigungen für authentifizierte Benutzer werden in lync Server 2013 entfernt.</span><span class="sxs-lookup"><span data-stu-id="e5ddf-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="e5ddf-112">Die Vererbung von Berechtigungen ist für Computer-, Benutzer-oder inetOrgPerson-Container in lync Server 2013 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e5ddf-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

