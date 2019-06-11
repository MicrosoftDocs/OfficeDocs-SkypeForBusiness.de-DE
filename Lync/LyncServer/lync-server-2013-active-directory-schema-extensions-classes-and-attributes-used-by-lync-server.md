---
title: 'Lync Server 2013: Active Directory-Schemaerweiterungen, -Klassen und -Attribute, die von Lync Server verwendet werden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc883c1c85acbe41bec6a25467e50800c036996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="172c2-102">Active Directory-Schemaerweiterungen, -Klassen und -Attribute, die von Lync Server 2013 verwendet werden</span><span class="sxs-lookup"><span data-stu-id="172c2-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="172c2-103">_**Letztes Änderungsdatum des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="172c2-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="172c2-104">Dieser Referenzabschnitt enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="172c2-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="172c2-105">Active Directory-Schemaerweiterungen, die neu sind oder für lync Server 2013 geändert wurden</span><span class="sxs-lookup"><span data-stu-id="172c2-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="172c2-106">Das Active Directory-Schema enthält formale Definitionen jeder Objektklasse, die in einer Active Directory-Gesamtstruktur erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="172c2-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="172c2-107">Das Schema enthält auch formale Definitionen für alle Attribute, die für ein Active Directory-Objekt vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="172c2-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="172c2-108">Der globale Active Directory-Katalog enthält Replikate aller Objekte für die Gesamtstruktur sowie eine Teilmenge der Attribute für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="172c2-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="172c2-109">In diesem Abschnitt werden die Klassen und Attribute beschrieben, die in lync Server 2013 neu oder geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="172c2-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="172c2-110">Alle von lync Server verwendeten Klassen mit einer Beschreibung der einzelnen Klassen</span><span class="sxs-lookup"><span data-stu-id="172c2-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="172c2-111">Alle von lync Server verwendeten Attribute mit einer Beschreibung der einzelnen Attribute</span><span class="sxs-lookup"><span data-stu-id="172c2-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="172c2-112">Eine Liste der von lync Server verwendeten Klassen mit den Attributen, die jeweils enthalten können</span><span class="sxs-lookup"><span data-stu-id="172c2-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="172c2-113">Globale Einstellungen und Objekte, zusätzlich zu den universellen Dienst-und Verwaltungsgruppen, die während der Gesamtstrukturvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="172c2-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="172c2-114">Zugriffssteuerungseinträge (ACEs), die im Domänenstamm und in den integrierten Containern während der Domänenvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="172c2-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="172c2-115">Änderungen, die an einer Active Directory-Organisationseinheit (OU) durch das Grant\_CsSetupPermission-Cmdlet vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="172c2-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="172c2-116">Änderungen, die an einer Active Directory-OU durch das Grant\_CsOUPermission-Cmdlet vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="172c2-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="172c2-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="172c2-117">In This Section</span></span>

  - [<span data-ttu-id="172c2-118">Schema Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="172c2-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="172c2-119">Schema Klassen und Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="172c2-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="172c2-120">Schema Attribute und Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="172c2-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="172c2-121">Schema Attribute nach Klasse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="172c2-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="172c2-122">Änderungen, die von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommen wurden</span><span class="sxs-lookup"><span data-stu-id="172c2-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="172c2-123">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="172c2-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="172c2-124">Von Grant-CsSetupPermission in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="172c2-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="172c2-125">Von Grant-CsOUPermission in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="172c2-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

