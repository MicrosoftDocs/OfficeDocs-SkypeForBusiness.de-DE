---
title: Active Directory-Erweiterungen, Klassen und Attribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Dieser Abschnitt enthält die folgenden Informationen:'
ms.openlocfilehash: f185a11bdc5d3700839be2f1306e266d9ab6af26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="86821-103">Active Directory-Erweiterungen, Klassen und Attribute</span><span class="sxs-lookup"><span data-stu-id="86821-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="86821-104">Dieser Abschnitt enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="86821-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="86821-105">Active Directory-Erweiterungen, die neue geänderte für Skype für Business Server oder</span><span class="sxs-lookup"><span data-stu-id="86821-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="86821-106">Active Directory-Schema enthält formale Definitionen für alle Objektklassen, die in einer Active Directory-Gesamtstruktur erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="86821-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="86821-107">Das Schema enthält auch formale Definitionen für alle Attribute, die für Active Directory-Objekt vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="86821-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="86821-108">Der globale Katalog von Active Directory enthält Replikate aller Objekte für die Gesamtstruktur sowie eine Teilmenge der Attribute für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="86821-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="86821-109">Dieser Abschnitt beschreibt die Klassen und Attribute, die neue oder geänderte in Skype für Business Server sind.</span><span class="sxs-lookup"><span data-stu-id="86821-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="86821-110">Alle Klassen, die von Skype für Business Server mit einer Beschreibung der einzelnen verwendet</span><span class="sxs-lookup"><span data-stu-id="86821-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="86821-111">Alle von Skype für Business-Server mit einer Beschreibung der einzelnen verwendeten Attribute</span><span class="sxs-lookup"><span data-stu-id="86821-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="86821-112">Eine Liste mit den Klassen, die mit den Attributen von Skype für Business Server kann enthalten.</span><span class="sxs-lookup"><span data-stu-id="86821-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="86821-113">Globale Einstellungen und Objekte sowie die universellen Dienst- und Administrationsgruppen, die während der Vorbereitung der Gesamtstruktur erstellt werden</span><span class="sxs-lookup"><span data-stu-id="86821-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="86821-114">Zugriffssteuerungseinträge (ACEs), die auf den Domänenstamm und in integrierten Containern, während der domänenvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="86821-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="86821-115">Änderungen, die durch das Grant_CsSetupPermission-Cmdlet für eine Active Directory-Organisationseinheit (OU) vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="86821-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="86821-116">Änderungen, die in einer Active Directory-Organisationseinheit durch das Grant_CsOUPermission-Cmdlet vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="86821-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="86821-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="86821-117">In This Section</span></span>

- [<span data-ttu-id="86821-118">Schemaänderungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="86821-119">Schemaklassen und Beschreibungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="86821-120">Schemaattribute und Beschreibungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="86821-121">Schemaattribute nach Klasse in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="86821-122">Änderungen, die durch die Vorbereitung der Gesamtstruktur in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="86821-123">Änderungen, die durch domänenvorbereitung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="86821-124">Änderungen, die durch Grant-CsSetupPermission in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="86821-125">Änderungen, die durch Grant-CsOUPermission in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86821-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

