---
title: IPAddress-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920033"
---
# <a name="ipaddress-table"></a><span data-ttu-id="3fabb-104">IPAddress-Tabelle</span><span class="sxs-lookup"><span data-stu-id="3fabb-104">IPAddress table</span></span>
 
<span data-ttu-id="3fabb-105">IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fabb-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3fabb-106">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3fabb-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3fabb-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3fabb-107">**Column**</span></span>|<span data-ttu-id="3fabb-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="3fabb-108">**Data Type**</span></span>|<span data-ttu-id="3fabb-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="3fabb-109">**Key/Index**</span></span>|<span data-ttu-id="3fabb-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="3fabb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3fabb-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3fabb-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3fabb-112">int</span><span class="sxs-lookup"><span data-stu-id="3fabb-112">int</span></span>  <br/> |<span data-ttu-id="3fabb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3fabb-113">Primary</span></span>  <br/> |<span data-ttu-id="3fabb-114">Eindeutiger Bezeichner für die angegebene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="3fabb-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="3fabb-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="3fabb-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="3fabb-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="3fabb-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="3fabb-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="3fabb-117">Unique</span></span>  <br/> |<span data-ttu-id="3fabb-118">Eindeutige IP-Adresse (beispielsweise 189.168.1.1), der die IpAddressKey zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3fabb-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="3fabb-119">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="3fabb-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

