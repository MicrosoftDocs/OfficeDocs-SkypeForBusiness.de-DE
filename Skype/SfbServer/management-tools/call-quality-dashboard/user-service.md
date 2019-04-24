---
title: Benutzerdienst für CQD
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Zusammenfassung: Erfahren Sie mehr über den Benutzer-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 4ee4594e86b14655c94472b516b9e04da674e3f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217642"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="16a51-104">Benutzerdienst für CQD</span><span class="sxs-lookup"><span data-stu-id="16a51-104">User Service for CQD</span></span>
 
<span data-ttu-id="16a51-105">**Zusammenfassung:** Informationen Sie zu den Benutzer-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="16a51-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="16a51-106">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="16a51-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="16a51-107">Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="16a51-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="16a51-108">Benutzerdienst</span><span class="sxs-lookup"><span data-stu-id="16a51-108">User Service</span></span>

<span data-ttu-id="16a51-109">Repository-API bietet eine vereinfachte Verwaltung Benutzermodell, in dem Benutzer, die Bereitstellung (Erstellen neuer Benutzerkonten) automatische und implizite ist.</span><span class="sxs-lookup"><span data-stu-id="16a51-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="16a51-110">Wenn ein Benutzer eine Anforderung für Repository-API zum ersten Mal, erstellt das Repository einen neuen Benutzerdatensatz.</span><span class="sxs-lookup"><span data-stu-id="16a51-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="16a51-111">Anruf, dass Qualitätsdashboard auch automatisch ein Benutzer erstellt dediziert Elemente für den neuen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="16a51-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="16a51-112">Der neue dedizierte Benutzerelemente sind vollständige Auslösung von Elementen des Systembenutzers.</span><span class="sxs-lookup"><span data-stu-id="16a51-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="16a51-113">Auf diese Weise Benutzer mit ihren eigenen Kopien von Berichten und Abfragen, die sie anpassen sofort starten können beginnen.</span><span class="sxs-lookup"><span data-stu-id="16a51-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="16a51-114">Rufen Sie Qualitätsdashboard verwenden, können Benutzer ihre dedizierten Elemente zurückgesetzt jederzeit.</span><span class="sxs-lookup"><span data-stu-id="16a51-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="16a51-115">**Spezielle Benutzer-IDs**</span><span class="sxs-lookup"><span data-stu-id="16a51-115">**Special User IDs**</span></span>
  
<span data-ttu-id="16a51-116">Repository-API enthält REST-API-URIs, die einen ganzzahligen Wert an einen bestimmten Benutzer erwartet.</span><span class="sxs-lookup"><span data-stu-id="16a51-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="16a51-117">Beispiel: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="16a51-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="16a51-118">Hier sollte {Benutzer-ID} ersetzt werden, eine ganze Zahl wie 0, 1, usw..</span><span class="sxs-lookup"><span data-stu-id="16a51-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="16a51-119">Darüber hinaus akzeptiert Repository API zwei spezielle Benutzer-IDs auf {Benutzer-ID} in URIs.</span><span class="sxs-lookup"><span data-stu-id="16a51-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="16a51-120">*Standard* - steht für den Benutzer, die mit der API interagiert.</span><span class="sxs-lookup"><span data-stu-id="16a51-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="16a51-121">Dies ist die Anwendung den Zugriff auf Inhalt des aktuellen Benutzers ohne Verfolgen von der aktuelle Benutzer-ID-Wert.</span><span class="sxs-lookup"><span data-stu-id="16a51-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="16a51-122">Beispiel: ` https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="16a51-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="16a51-123">*System* - stellt den Systembenutzer dar.</span><span class="sxs-lookup"><span data-stu-id="16a51-123">*system*  - represents the system user.</span></span> <span data-ttu-id="16a51-124">Dies ist die Anwendung auf dem des Systembenutzers Inhalt zugreifen, ohne den tatsächlichen Benutzer-ID-Wert.</span><span class="sxs-lookup"><span data-stu-id="16a51-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="16a51-125">Beispiel: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="16a51-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="16a51-126">Sofern nicht anders angegeben, kann die spezielle Benutzer-IDs am {Benutzer-ID} in URIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16a51-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="16a51-127">In der folgenden Tabelle sind die REST-Vorgänge enthalten.</span><span class="sxs-lookup"><span data-stu-id="16a51-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="16a51-128">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="16a51-128">**Operation**</span></span>|<span data-ttu-id="16a51-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="16a51-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="16a51-130">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="16a51-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="16a51-131">Gibt eine Liste der Benutzer im Repository.</span><span class="sxs-lookup"><span data-stu-id="16a51-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="16a51-132">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="16a51-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="16a51-133">Gibt einen Benutzerdatensatz zurück.</span><span class="sxs-lookup"><span data-stu-id="16a51-133">Returns a user record.</span></span>  <br/> |
   

