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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: In der ConferenceMessageCount-Ansicht werden Informationen darüber gespeichert, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815383"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="b8f69-104">ConferenceMessageCount-Ansicht</span><span class="sxs-lookup"><span data-stu-id="b8f69-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="b8f69-105">In der ConferenceMessageCount-Ansicht werden Informationen darüber gespeichert, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="b8f69-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="b8f69-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b8f69-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8f69-107">Die ConferenceMessageCount-Ansicht enthält alle Spalten in der [ConferenceSessionDetails-Ansicht](conferencesessiondetails.md) sowie die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="b8f69-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="b8f69-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b8f69-108">**Column**</span></span>|<span data-ttu-id="b8f69-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b8f69-109">**Data Type**</span></span>|<span data-ttu-id="b8f69-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b8f69-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8f69-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="b8f69-111">**UserUri**</span></span> <br/> |<span data-ttu-id="b8f69-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b8f69-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b8f69-113">Der URI des Benutzers, der die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="b8f69-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="b8f69-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="b8f69-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="b8f69-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b8f69-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b8f69-116">Der Typ des URIs des Benutzers, der die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="b8f69-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="b8f69-117">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="b8f69-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b8f69-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="b8f69-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="b8f69-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b8f69-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="b8f69-120">Der Mandant des Benutzers, der die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="b8f69-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="b8f69-121">Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="b8f69-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b8f69-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="b8f69-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="b8f69-123">smallint</span><span class="sxs-lookup"><span data-stu-id="b8f69-123">smallint</span></span>  <br/> |<span data-ttu-id="b8f69-124">Die Anzahl der Nachrichten, die der Benutzer während der Konferenzsitzung gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="b8f69-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

