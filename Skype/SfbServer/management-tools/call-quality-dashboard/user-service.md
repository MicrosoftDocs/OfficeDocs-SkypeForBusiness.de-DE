---
title: Benutzer Dienst für CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Zusammenfassung: erfahren Sie mehr über den Benutzer Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816654"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="149ed-104">Benutzer Dienst für CQD</span><span class="sxs-lookup"><span data-stu-id="149ed-104">User Service for CQD</span></span>
 
<span data-ttu-id="149ed-105">**Zusammenfassung:** Erfahren Sie mehr über den Benutzer Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist.</span><span class="sxs-lookup"><span data-stu-id="149ed-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="149ed-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="149ed-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="149ed-107">Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="149ed-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="149ed-108">Benutzerdienst</span><span class="sxs-lookup"><span data-stu-id="149ed-108">User Service</span></span>

<span data-ttu-id="149ed-109">Die Repository-API bietet ein vereinfachtes Benutzer Verwaltungsmodell, bei dem die Benutzerbereitstellung (Erstellen neuer Benutzerkonten) automatisch und implizit erfolgt.</span><span class="sxs-lookup"><span data-stu-id="149ed-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="149ed-110">Wenn ein Benutzer zum ersten Mal eine Anforderung an die Repository-API stellt, erstellt das Repository einen neuen Benutzerdatensatz.</span><span class="sxs-lookup"><span data-stu-id="149ed-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="149ed-111">Mit dem Dashboard für die Anrufqualität werden auch automatisch benutzerspezifische Elemente für den neuen Benutzer erstellt.</span><span class="sxs-lookup"><span data-stu-id="149ed-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="149ed-112">Die neuen benutzerspezifischen Elemente sind vollständige Klone der Elemente des Systembenutzers.</span><span class="sxs-lookup"><span data-stu-id="149ed-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="149ed-113">Auf diese Weise beginnen Benutzer mit eigenen Kopien von Berichten und Abfragen, dass Sie sofort mit dem Customizing beginnen können.</span><span class="sxs-lookup"><span data-stu-id="149ed-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="149ed-114">Mithilfe des Dashboards für die Anrufqualität können Benutzer ihre dedizierten Elemente jederzeit zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="149ed-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="149ed-115">**Spezielle Benutzer-IDs**</span><span class="sxs-lookup"><span data-stu-id="149ed-115">**Special User IDs**</span></span>
  
<span data-ttu-id="149ed-116">Die Repository-API enthält die RESTful-API-URIs, die einen ganzzahligen Wert zur Angabe eines bestimmten Benutzers erwartet.</span><span class="sxs-lookup"><span data-stu-id="149ed-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="149ed-117">Beispiel: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="149ed-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="149ed-118">Hier sollte {UserID} durch einen ganzzahligen Wert wie 0, 1 usw. ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="149ed-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="149ed-119">Darüber hinaus akzeptiert die Repository-API zwei spezielle Benutzer-IDs bei {UserID} in URIs.</span><span class="sxs-lookup"><span data-stu-id="149ed-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="149ed-120">*Standard* – stellt den Benutzer dar, der gerade mit der API interagiert.</span><span class="sxs-lookup"><span data-stu-id="149ed-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="149ed-121">Dies ermöglicht Anwendungen den Zugriff auf den Inhalt des aktuellen Benutzers, ohne den tatsächlichen Benutzer-ID-Wert zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="149ed-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="149ed-122">Beispiel: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="149ed-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="149ed-123">*System* – stellt den Systembenutzer dar.</span><span class="sxs-lookup"><span data-stu-id="149ed-123">*system*  - represents the system user.</span></span> <span data-ttu-id="149ed-124">Dies ermöglicht Anwendungen den Zugriff auf die Inhalte des Systembenutzers, ohne den tatsächlichen Benutzer-ID-Wert zu kennen.</span><span class="sxs-lookup"><span data-stu-id="149ed-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="149ed-125">Beispiel: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="149ed-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="149ed-126">Sofern nicht anders angegeben, können die speziellen Benutzer-IDs bei {UserID} in URIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="149ed-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="149ed-127">Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="149ed-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="149ed-128">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="149ed-128">**Operation**</span></span>|<span data-ttu-id="149ed-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="149ed-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="149ed-130">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="149ed-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="149ed-131">Gibt eine Liste der Benutzer im Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="149ed-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="149ed-132">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="149ed-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="149ed-133">Gibt einen Benutzerdatensatz zurück.</span><span class="sxs-lookup"><span data-stu-id="149ed-133">Returns a user record.</span></span>  <br/> |
   

