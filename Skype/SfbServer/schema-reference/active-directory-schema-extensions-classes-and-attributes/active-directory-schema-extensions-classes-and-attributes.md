---
title: Active Directory-Schemaerweiterungen, -Klassen und -Attribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Dieser Referenzabschnitt enthält die folgenden Informationen:'
ms.openlocfilehash: 98ce04f38d9ee6c572f517441a370823ab7647d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815553"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="cc8b8-103">Active Directory-Schemaerweiterungen, -Klassen und -Attribute</span><span class="sxs-lookup"><span data-stu-id="cc8b8-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="cc8b8-104">Dieser Referenzabschnitt enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="cc8b8-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="cc8b8-105">Active Directory-Schemaerweiterungen, die neu sind oder für Skype for Business Server geändert wurden</span><span class="sxs-lookup"><span data-stu-id="cc8b8-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="cc8b8-106">Das Active Directory-Schema enthält formale Definitionen jeder Objektklasse, die in einer Active Directory-Gesamtstruktur erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="cc8b8-107">Das Schema enthält auch formale Definitionen für alle Attribute, die für ein Active Directory-Objekt vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="cc8b8-108">Der globale Active Directory-Katalog enthält Replikate aller Objekte für die Gesamtstruktur sowie eine Teilmenge der Attribute für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="cc8b8-109">In diesem Abschnitt werden die Klassen und Attribute beschrieben, die neu sind oder in Skype for Business Server geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="cc8b8-110">Alle von Skype for Business Server verwendeten Kurse mit einer Beschreibung der einzelnen Klassen</span><span class="sxs-lookup"><span data-stu-id="cc8b8-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="cc8b8-111">Alle von Skype for Business Server verwendeten Attribute mit einer Beschreibung der einzelnen</span><span class="sxs-lookup"><span data-stu-id="cc8b8-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="cc8b8-112">Eine Liste der von Skype for Business Server verwendeten Klassen mit den Attributen, die jeweils enthalten können</span><span class="sxs-lookup"><span data-stu-id="cc8b8-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="cc8b8-113">Globale Einstellungen und Objekte, zusätzlich zu den universellen Dienst-und Verwaltungsgruppen, die während der Gesamtstrukturvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="cc8b8-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="cc8b8-114">Zugriffssteuerungseinträge (ACEs), die im Domänenstamm und in den integrierten Containern während der Domänenvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="cc8b8-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="cc8b8-115">Änderungen, die an einer Active Directory-Organisationseinheit (OU) durch das Grant_CsSetupPermission-Cmdlet vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="cc8b8-116">Änderungen, die an einer Active Directory-OU durch das Grant_CsOUPermission-Cmdlet vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="cc8b8-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cc8b8-117">In This Section</span></span>

- [<span data-ttu-id="cc8b8-118">Schema Änderungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc8b8-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="cc8b8-119">Schema Klassen und Beschreibungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc8b8-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="cc8b8-120">Schema Attribute und Beschreibungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc8b8-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="cc8b8-121">Schema Attribute nach Klasse in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc8b8-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="cc8b8-122">Änderungen, die von der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden</span><span class="sxs-lookup"><span data-stu-id="cc8b8-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="cc8b8-123">Von der Domänenvorbereitung in Skype for Business Server vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="cc8b8-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="cc8b8-124">Von Grant-CsSetupPermission in Skype for Business Server vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="cc8b8-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="cc8b8-125">Von Grant-CsOUPermission in Skype for Business Server vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="cc8b8-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

