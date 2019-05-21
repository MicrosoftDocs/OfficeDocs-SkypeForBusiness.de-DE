---
title: ConferenceMessageCount-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: In der ConferenceMessageCount-Ansicht werden Informationen darüber gespeichert, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296490"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="18f7f-104">ConferenceMessageCount-Ansicht</span><span class="sxs-lookup"><span data-stu-id="18f7f-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="18f7f-105">In der ConferenceMessageCount-Ansicht werden Informationen darüber gespeichert, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="18f7f-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="18f7f-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="18f7f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="18f7f-107">Die ConferenceMessageCount-Ansicht enthält alle Spalten in der [ConferenceSessionDetails-Ansicht](conferencesessiondetails.md) sowie die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="18f7f-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="18f7f-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="18f7f-108">**Column**</span></span>|<span data-ttu-id="18f7f-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="18f7f-109">**Data Type**</span></span>|<span data-ttu-id="18f7f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="18f7f-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="18f7f-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="18f7f-111">**UserUri**</span></span> <br/> |<span data-ttu-id="18f7f-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="18f7f-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="18f7f-113">Der URI des Benutzers, der die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="18f7f-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="18f7f-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="18f7f-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="18f7f-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="18f7f-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="18f7f-116">Der Typ des URIs des Benutzers, der die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="18f7f-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="18f7f-117">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="18f7f-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="18f7f-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="18f7f-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="18f7f-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="18f7f-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="18f7f-120">Der Mandant des Benutzers, der die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="18f7f-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="18f7f-121">Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="18f7f-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="18f7f-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="18f7f-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="18f7f-123">smallint</span><span class="sxs-lookup"><span data-stu-id="18f7f-123">smallint</span></span>  <br/> |<span data-ttu-id="18f7f-124">Die Anzahl der Nachrichten, die der Benutzer während der Konferenzsitzung gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="18f7f-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

