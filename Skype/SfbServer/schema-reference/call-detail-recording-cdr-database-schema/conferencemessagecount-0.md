---
title: ConferenceMessageCount-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Die ConferenceMessageCount-Ansicht speichert Informationen über wie viele Nachrichten von einem Benutzer an einer Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: f0206145217f63e4530d2eac39c7c6533dcf154e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="58a8a-104">ConferenceMessageCount-Ansicht</span><span class="sxs-lookup"><span data-stu-id="58a8a-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="58a8a-105">Die ConferenceMessageCount-Ansicht speichert Informationen über wie viele Nachrichten von einem Benutzer an einer Konferenz gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="58a8a-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="58a8a-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="58a8a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58a8a-107">Die ConferenceMessageCount-Ansicht enthält alle Spalten in der [ConferenceSessionDetails-Ansicht](conferencesessiondetails.md) außerdem die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="58a8a-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="58a8a-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="58a8a-108">**Column**</span></span>|<span data-ttu-id="58a8a-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="58a8a-109">**Data Type**</span></span>|<span data-ttu-id="58a8a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="58a8a-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58a8a-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="58a8a-111">**UserUri**</span></span> <br/> |<span data-ttu-id="58a8a-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="58a8a-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="58a8a-113">Der URI des Benutzers, der die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="58a8a-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="58a8a-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="58a8a-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="58a8a-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="58a8a-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="58a8a-116">Typ der URI des Benutzers, der die Nachrichten gesendet.</span><span class="sxs-lookup"><span data-stu-id="58a8a-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="58a8a-117">Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="58a8a-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="58a8a-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="58a8a-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="58a8a-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="58a8a-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="58a8a-120">Mandant des Benutzers, die die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="58a8a-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="58a8a-121">Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="58a8a-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="58a8a-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="58a8a-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="58a8a-123">smallint</span><span class="sxs-lookup"><span data-stu-id="58a8a-123">smallint</span></span>  <br/> |<span data-ttu-id="58a8a-124">Anzahl der vom Benutzer während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="58a8a-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

