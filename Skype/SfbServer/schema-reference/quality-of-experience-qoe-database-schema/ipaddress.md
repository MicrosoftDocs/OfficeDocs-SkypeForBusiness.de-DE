---
title: IPAddress-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a><span data-ttu-id="cc90f-104">IPAddress-Tabelle</span><span class="sxs-lookup"><span data-stu-id="cc90f-104">IPAddress table</span></span>
 
<span data-ttu-id="cc90f-105">IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc90f-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="cc90f-106">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cc90f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cc90f-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cc90f-107">**Column**</span></span>|<span data-ttu-id="cc90f-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="cc90f-108">**Data Type**</span></span>|<span data-ttu-id="cc90f-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="cc90f-109">**Key/Index**</span></span>|<span data-ttu-id="cc90f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="cc90f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc90f-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="cc90f-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="cc90f-112">int</span><span class="sxs-lookup"><span data-stu-id="cc90f-112">int</span></span>  <br/> |<span data-ttu-id="cc90f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cc90f-113">Primary</span></span>  <br/> |<span data-ttu-id="cc90f-114">Eindeutiger Bezeichner für die angegebene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="cc90f-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="cc90f-115">**IP-Adresse**</span><span class="sxs-lookup"><span data-stu-id="cc90f-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="cc90f-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="cc90f-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="cc90f-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="cc90f-117">Unique</span></span>  <br/> |<span data-ttu-id="cc90f-118">Eindeutige IP-Adresse (beispielsweise 189.168.1.1), der die IpAddressKey zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="cc90f-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="cc90f-119">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="cc90f-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

