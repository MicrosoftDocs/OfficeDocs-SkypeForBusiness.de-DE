---
title: 'Lync Server 2013: Active Directory Schemaerweiterungen, Klassen und Attribute, die von lync Server verwendet werden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ed67522a2f47466bbf01efdd3a548c3e3637321
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="e24b6-102">Active Directory von lync Server 2013 verwendeten Schemaerweiterungen, Klassen und Attribute</span><span class="sxs-lookup"><span data-stu-id="e24b6-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e24b6-103">_**Letztes Änderungsstand des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="e24b6-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="e24b6-104">Dieser Referenzbereich enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e24b6-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="e24b6-105">Active Directory Schemaerweiterungen, die neu oder für lync Server 2013 geändert wurden</span><span class="sxs-lookup"><span data-stu-id="e24b6-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="e24b6-106">Das Active Directory-Schema enthält formale Definitionen für alle Objektklassen, die in einer Active Directory-Gesamtstruktur erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="e24b6-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="e24b6-107">Das Schema enthält darüber hinaus auch formale Definitionen für alle Attribute, die für ein Active Directory-Objekt vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="e24b6-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="e24b6-108">Der globale Katalog von Active Directory enthält Replikate aller Objekte für die Gesamtstruktur sowie eine Teilmenge der Attribute für die einzelnen Objekte.</span><span class="sxs-lookup"><span data-stu-id="e24b6-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="e24b6-109">In diesem Abschnitt werden die Klassen und Attribute beschrieben, die in lync Server 2013 neu oder geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="e24b6-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="e24b6-110">Alle von lync Server verwendeten Klassen mit einer Beschreibung jeder</span><span class="sxs-lookup"><span data-stu-id="e24b6-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="e24b6-111">Alle von lync Server verwendeten Attribute mit einer Beschreibung der einzelnen</span><span class="sxs-lookup"><span data-stu-id="e24b6-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="e24b6-112">Eine Liste der von lync Server verwendeten Klassen mit den jeweiligen Attributen enthält möglicherweise</span><span class="sxs-lookup"><span data-stu-id="e24b6-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="e24b6-113">Globale Einstellungen und Objekte, die zusätzlich zu den universellen Dienst- und Administrationsgruppen verfügbar sind, die während der Vorbereitung der Gesamtstruktur erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e24b6-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="e24b6-114">Während der Domänenvorbereitung im Domänenstamm und in integrierten Containern erstellte Zugriffssteuerungseinträge (Access Control Entries, ACEs).</span><span class="sxs-lookup"><span data-stu-id="e24b6-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="e24b6-115">Änderungen, die an einer Active Directory Organisationseinheit (Organizational Unit, OU)\_durch das Grant CsSetupPermission-Cmdlet vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e24b6-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="e24b6-116">Änderungen, die auf einer Active Directory-OU durch das Grant\_CsOUPermission-Cmdlet vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e24b6-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e24b6-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e24b6-117">In This Section</span></span>

  - [<span data-ttu-id="e24b6-118">Schema Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e24b6-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="e24b6-119">Schema Klassen und Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e24b6-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="e24b6-120">Schema Attribute und-Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e24b6-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="e24b6-121">Schema Attribute nach Klasse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e24b6-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="e24b6-122">Von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="e24b6-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="e24b6-123">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="e24b6-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="e24b6-124">Von Grant-CsSetupPermission vorgenommene Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e24b6-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="e24b6-125">Von Grant-CsOUPermission vorgenommene Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e24b6-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

