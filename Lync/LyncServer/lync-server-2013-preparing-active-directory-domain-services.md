---
title: 'Lync Server 2013: Vorbereiten von Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4deedc7a3913a33ad6524a8eab4dd3f66ba961b3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="9e4c4-102">Vorbereiten der Active Directory-Domänendienste für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e4c4-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e4c4-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9e4c4-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9e4c4-104">Bevor Sie lync Server 2013 bereitstellen und verwenden, müssen Sie Active Directory-Domänendienste vorbereiten, indem Sie das Schema erweitern und dann Objekte erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9e4c4-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="9e4c4-105">Durch die Schemaerweiterungen werden die für Lync Server erforderlichen Active Directory-Klassen und ‑Attribute hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9e4c4-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="9e4c4-106">In den Themen in diesem Abschnitt wird beschrieben, wie Sie AD DS für die Bereitstellung von lync Server vorbereiten und wie Sie Setup-und Organisationseinheiten Berechtigungen (Organizational Unit, OU) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9e4c4-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="9e4c4-107">Ausführliche Informationen zu den für lync Server erforderlichen Schemaänderungen finden Sie unter [Active Directory Schema Extensions, Klassen und Attribute, die von lync Server 2013 verwendet werden](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="9e4c4-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e4c4-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e4c4-108">In This Section</span></span>

  - [<span data-ttu-id="9e4c4-109">Active Directory Infrastrukturanforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e4c4-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="9e4c4-110">Übersicht über die Active Directory-Domänendienste Vorbereitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e4c4-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="9e4c4-111">Vorbereiten Active Directory-Domänendienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e4c4-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="9e4c4-112">Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e4c4-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="9e4c4-113">Erteilen von Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e4c4-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

