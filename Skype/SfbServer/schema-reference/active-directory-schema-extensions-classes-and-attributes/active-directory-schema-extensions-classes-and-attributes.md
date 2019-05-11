---
title: Active Directory-Schemaerweiterungen, -Klassen und -Attribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Dieser Abschnitt enthält die folgenden Informationen:'
ms.openlocfilehash: dc2d147791317134ee9abd3de723f1c53f8f625b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907101"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="e4b6c-103">Active Directory-Schemaerweiterungen, -Klassen und -Attribute</span><span class="sxs-lookup"><span data-stu-id="e4b6c-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="e4b6c-104">Dieser Abschnitt enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e4b6c-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="e4b6c-105">Active Directory-Erweiterungen, die neue geänderte für Skype für Business Server oder</span><span class="sxs-lookup"><span data-stu-id="e4b6c-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="e4b6c-106">Active Directory-Schema enthält formale Definitionen für alle Objektklassen, die in einer Active Directory-Gesamtstruktur erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="e4b6c-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="e4b6c-107">Das Schema enthält auch formale Definitionen für alle Attribute, die für Active Directory-Objekt vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="e4b6c-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="e4b6c-108">Der globale Katalog von Active Directory enthält Replikate aller Objekte für die Gesamtstruktur sowie eine Teilmenge der Attribute für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="e4b6c-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="e4b6c-109">Dieser Abschnitt beschreibt die Klassen und Attribute, die neue oder geänderte in Skype für Business Server sind.</span><span class="sxs-lookup"><span data-stu-id="e4b6c-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="e4b6c-110">Alle Klassen, die von Skype für Business Server mit einer Beschreibung der einzelnen verwendet</span><span class="sxs-lookup"><span data-stu-id="e4b6c-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="e4b6c-111">Alle von Skype für Business-Server mit einer Beschreibung der einzelnen verwendeten Attribute</span><span class="sxs-lookup"><span data-stu-id="e4b6c-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="e4b6c-112">Eine Liste mit den Klassen, die mit den Attributen von Skype für Business Server kann enthalten.</span><span class="sxs-lookup"><span data-stu-id="e4b6c-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="e4b6c-113">Globale Einstellungen und Objekte sowie die universellen Dienst- und Administrationsgruppen, die während der Vorbereitung der Gesamtstruktur erstellt werden</span><span class="sxs-lookup"><span data-stu-id="e4b6c-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="e4b6c-114">Zugriffssteuerungseinträge (ACEs), die auf den Domänenstamm und in integrierten Containern, während der domänenvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="e4b6c-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="e4b6c-115">Änderungen, die durch das Grant_CsSetupPermission-Cmdlet für eine Active Directory-Organisationseinheit (OU) vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e4b6c-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="e4b6c-116">Änderungen, die in einer Active Directory-Organisationseinheit durch das Grant_CsOUPermission-Cmdlet vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e4b6c-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="e4b6c-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e4b6c-117">In This Section</span></span>

- [<span data-ttu-id="e4b6c-118">Schemaänderungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="e4b6c-119">Schemaklassen und Beschreibungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="e4b6c-120">Schemaattribute und Beschreibungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="e4b6c-121">Schemaattribute nach Klasse in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="e4b6c-122">Änderungen, die durch die Vorbereitung der Gesamtstruktur in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="e4b6c-123">Änderungen, die durch domänenvorbereitung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="e4b6c-124">Änderungen, die durch Grant-CsSetupPermission in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="e4b6c-125">Änderungen, die durch Grant-CsOUPermission in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="e4b6c-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

