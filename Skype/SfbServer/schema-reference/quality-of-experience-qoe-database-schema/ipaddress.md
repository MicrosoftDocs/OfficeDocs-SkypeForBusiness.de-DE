---
title: IPAddress-Tabelle
ms.reviewer: ''
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
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212207"
---
# <a name="ipaddress-table"></a><span data-ttu-id="e4522-104">IPAddress-Tabelle</span><span class="sxs-lookup"><span data-stu-id="e4522-104">IPAddress table</span></span>
 
<span data-ttu-id="e4522-105">IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4522-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="e4522-106">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e4522-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e4522-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e4522-107">**Column**</span></span>|<span data-ttu-id="e4522-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e4522-108">**Data Type**</span></span>|<span data-ttu-id="e4522-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="e4522-109">**Key/Index**</span></span>|<span data-ttu-id="e4522-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e4522-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4522-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="e4522-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="e4522-112">int</span><span class="sxs-lookup"><span data-stu-id="e4522-112">int</span></span>  <br/> |<span data-ttu-id="e4522-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e4522-113">Primary</span></span>  <br/> |<span data-ttu-id="e4522-114">Eindeutiger Bezeichner für die angegebene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="e4522-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="e4522-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="e4522-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="e4522-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="e4522-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="e4522-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="e4522-117">Unique</span></span>  <br/> |<span data-ttu-id="e4522-118">Eindeutige IP-Adresse (beispielsweise 189.168.1.1), der die IpAddressKey zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e4522-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="e4522-119">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="e4522-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

