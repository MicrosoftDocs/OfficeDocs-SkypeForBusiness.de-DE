---
title: ConferenceMessageCount-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Die ConferenceMessageCount-Ansicht speichert Informationen über wie viele Nachrichten von einem Benutzer an einer Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901415"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="36c8e-104">ConferenceMessageCount-Ansicht</span><span class="sxs-lookup"><span data-stu-id="36c8e-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="36c8e-105">Die ConferenceMessageCount-Ansicht speichert Informationen über wie viele Nachrichten von einem Benutzer an einer Konferenz gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="36c8e-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="36c8e-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="36c8e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36c8e-107">Die ConferenceMessageCount-Ansicht enthält alle Spalten in der [ConferenceSessionDetails-Ansicht](conferencesessiondetails.md) außerdem die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="36c8e-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="36c8e-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="36c8e-108">**Column**</span></span>|<span data-ttu-id="36c8e-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="36c8e-109">**Data Type**</span></span>|<span data-ttu-id="36c8e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="36c8e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="36c8e-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="36c8e-111">**UserUri**</span></span> <br/> |<span data-ttu-id="36c8e-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="36c8e-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="36c8e-113">Der URI des Benutzers, der die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="36c8e-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="36c8e-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="36c8e-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="36c8e-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="36c8e-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="36c8e-116">Typ der URI des Benutzers, der die Nachrichten gesendet.</span><span class="sxs-lookup"><span data-stu-id="36c8e-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="36c8e-117">Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="36c8e-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="36c8e-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="36c8e-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="36c8e-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="36c8e-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="36c8e-120">Mandant des Benutzers, die die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="36c8e-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="36c8e-121">Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="36c8e-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="36c8e-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="36c8e-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="36c8e-123">smallint</span><span class="sxs-lookup"><span data-stu-id="36c8e-123">smallint</span></span>  <br/> |<span data-ttu-id="36c8e-124">Anzahl der vom Benutzer während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="36c8e-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

