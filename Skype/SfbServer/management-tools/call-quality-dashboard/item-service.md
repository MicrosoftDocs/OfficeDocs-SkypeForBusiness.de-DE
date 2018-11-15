---
title: Dienst für Anruf Qualitätsdashboard (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Zusammenfassung: Informationen Sie zu den Element-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 5e5198afd95d6c9e1de517054053b724a54b1105
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532598"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="bb3ee-104">Dienst für Anruf Qualitätsdashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="bb3ee-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="bb3ee-105">**Zusammenfassung:** Informationen Sie zu den Element-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="bb3ee-106">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bb3ee-107">Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="bb3ee-108">Element-Dienst</span><span class="sxs-lookup"><span data-stu-id="bb3ee-108">Item Service</span></span>

<span data-ttu-id="bb3ee-109">Repository-API bietet eine einfache Content Management Service, bekannt als Element-Dienst, der zum Speichern von anwendungsdefinierte Inhalt für Benutzer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="bb3ee-110">Den Inhalt des sind Besitz des Systembenutzers und von allen Benutzern mit Lesezugriff gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="bb3ee-111">Dedizierten Benutzer Inhalt Besitz regulären Benutzer und nur die Besitzer ändern oder löschen können, aber alle Benutzer weiterhin schreibgeschützten Zugriff auf die Dokumente haben.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb3ee-112">Diese API-Dokumentation behandelt schreibgeschützten Vorgängen der Repository-API.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="bb3ee-113">Rufen Sie Elemente in der Repositorydatenbank Qualitätsdashboard speichert Berichte und Abfragen.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="bb3ee-114">Ein Element kann optionale untergeordnete Elemente aufweisen, und Aufrufen Qualitätsdashboard organisiert Berichte und Abfragen in einer hierarchischen Struktur Unterelemente-Feature verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="bb3ee-115">Element Service umfasst die folgenden Konzepte:</span><span class="sxs-lookup"><span data-stu-id="bb3ee-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="bb3ee-116">**Element** - das grundlegende Element des Repositorys.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="bb3ee-117">Jedes Element gehört genau einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="bb3ee-118">**Unterelement** - die grundlegende Organisationseinheit Funktionsweise des Repositorys.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="bb3ee-119">Element kann 0 (null) aufweisen, eine oder mehrere untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="bb3ee-120">**Element Vorgänger** - die Liste der Elemente, die das oberste Element die Standardeinstellung Element des Benutzers, was zu einem bestimmten Element ab.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="bb3ee-121">**Elementinhalts** - die anwendungsspezifischen Inhalt in Elemente gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="bb3ee-122">Anruf Qualitätsdashboard JSON Darstellungen von Berichten und Abfragen im Inhalt gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="bb3ee-123">In der folgenden Tabelle sind die REST-Vorgänge enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="bb3ee-124">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="bb3ee-124">**Operation**</span></span>|<span data-ttu-id="bb3ee-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bb3ee-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="bb3ee-126">Abrufen von Elementen</span><span class="sxs-lookup"><span data-stu-id="bb3ee-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="bb3ee-127">Rufen Sie Elemente gibt alle Elemente im Repository.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="bb3ee-128">Element abrufen</span><span class="sxs-lookup"><span data-stu-id="bb3ee-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="bb3ee-129">Möchten Sie gibt ein bestimmtes Element erhalten.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="bb3ee-130">Untergeordnete Elemente abrufen</span><span class="sxs-lookup"><span data-stu-id="bb3ee-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="bb3ee-131">Rufen Sie ein bestimmtes Element Unterelemente Unterelemente gibt.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="bb3ee-132">Abrufen der Vorgänger des Elements</span><span class="sxs-lookup"><span data-stu-id="bb3ee-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="bb3ee-133">Get-Element Vorgänger gibt ein bestimmtes Element Vorgänger zurück.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="bb3ee-134">Update-Element</span><span class="sxs-lookup"><span data-stu-id="bb3ee-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="bb3ee-135">Aktualisieren Sie ein bestimmtes Element im Repository.</span><span class="sxs-lookup"><span data-stu-id="bb3ee-135">Update a specific item in the repository.</span></span>  <br/> |
   

