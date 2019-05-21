---
title: Element Dienst für das Anruf Qualitäts Dashboard (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Zusammenfassung: erfahren Sie mehr über den Element Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274611"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="c0d95-104">Element Dienst für das Anruf Qualitäts Dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="c0d95-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="c0d95-105">**Zusammenfassung:** Erfahren Sie mehr über den Element Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist.</span><span class="sxs-lookup"><span data-stu-id="c0d95-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c0d95-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0d95-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c0d95-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="c0d95-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="c0d95-108">Elementdienst</span><span class="sxs-lookup"><span data-stu-id="c0d95-108">Item Service</span></span>

<span data-ttu-id="c0d95-109">Die Repository-API bietet einen einfachen Content Management-Dienst, den so genannten Element Dienst, der zum Speichern von anwendungsdefinierten Inhalten für Benutzer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0d95-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="c0d95-110">Der Systeminhalt ist Eigentum des Systembenutzers und wird von allen Benutzern mit schreibgeschütztem Zugriff freigegeben.</span><span class="sxs-lookup"><span data-stu-id="c0d95-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="c0d95-111">Dedizierte Benutzer Inhalte gehören normalen Benutzern, und nur die Besitzer können Sie ändern oder löschen, doch alle Benutzer verfügen weiterhin über schreibgeschützten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="c0d95-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0d95-112">Diese API-Dokumentation umfasst schreibgeschützte Vorgänge der Repository-API.</span><span class="sxs-lookup"><span data-stu-id="c0d95-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="c0d95-113">Das Dashboard für die Anrufqualität speichert Berichte und Abfragen als Elemente in der Repository-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c0d95-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="c0d95-114">Ein Element kann über optionale untergeordnete Elemente verfügen, und das Dashboard für die Anrufqualität organisiert Berichte und Abfragen in einer hierarchischen Struktur mithilfe von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="c0d95-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="c0d95-115">Der Element Dienst umfasst die folgenden Konzepte:</span><span class="sxs-lookup"><span data-stu-id="c0d95-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="c0d95-116">**Element** – das grundlegende Element des Repositorys.</span><span class="sxs-lookup"><span data-stu-id="c0d95-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="c0d95-117">Jedes Element gehört genau einem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c0d95-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="c0d95-118">**Unterelement** – die grundlegenden organisatorischen Mechanismen des Repositorys.</span><span class="sxs-lookup"><span data-stu-id="c0d95-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="c0d95-119">Das Element kann 0 (null), ein oder mehrere untergeordnete Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0d95-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="c0d95-120">**Item Ancestors** -die Liste der Elemente, beginnend mit dem obersten Element, das das Standardelement des Benutzers ist und zu einem bestimmten Element führt.</span><span class="sxs-lookup"><span data-stu-id="c0d95-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="c0d95-121">**Elementinhalt** – der anwendungsspezifische Inhalt, der in Elementen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="c0d95-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="c0d95-122">Das Dashboard für die Anrufqualität speichert JSON-Darstellungen von Berichten und Abfragen in Inhalten.</span><span class="sxs-lookup"><span data-stu-id="c0d95-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="c0d95-123">Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0d95-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="c0d95-124">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="c0d95-124">**Operation**</span></span>|<span data-ttu-id="c0d95-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c0d95-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c0d95-126">Abrufen von Elementen</span><span class="sxs-lookup"><span data-stu-id="c0d95-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="c0d95-127">Elemente abrufen gibt alle Elemente im Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="c0d95-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="c0d95-128">Abrufen eines Elements</span><span class="sxs-lookup"><span data-stu-id="c0d95-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="c0d95-129">Element abrufen gibt ein bestimmtes Element zurück.</span><span class="sxs-lookup"><span data-stu-id="c0d95-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="c0d95-130">Abrufen von untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="c0d95-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="c0d95-131">Abrufen untergeordneter Elemente gibt die untergeordneten Elemente eines bestimmten Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="c0d95-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="c0d95-132">Abrufen von übergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="c0d95-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="c0d95-133">Get Item Ancestors gibt die Vorfahren eines bestimmten Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="c0d95-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="c0d95-134">Aktualisieren von Elementen</span><span class="sxs-lookup"><span data-stu-id="c0d95-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="c0d95-135">Aktualisieren eines bestimmten Elements im Repository</span><span class="sxs-lookup"><span data-stu-id="c0d95-135">Update a specific item in the repository.</span></span>  <br/> |
   

