---
title: IPAddress-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Die IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294922"
---
# <a name="ipaddress-table"></a><span data-ttu-id="928f1-104">IPAddress-Tabelle</span><span class="sxs-lookup"><span data-stu-id="928f1-104">IPAddress table</span></span>
 
<span data-ttu-id="928f1-105">Die IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="928f1-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="928f1-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="928f1-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="928f1-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="928f1-107">**Column**</span></span>|<span data-ttu-id="928f1-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="928f1-108">**Data Type**</span></span>|<span data-ttu-id="928f1-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="928f1-109">**Key/Index**</span></span>|<span data-ttu-id="928f1-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="928f1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="928f1-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="928f1-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="928f1-112">int</span><span class="sxs-lookup"><span data-stu-id="928f1-112">int</span></span>  <br/> |<span data-ttu-id="928f1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="928f1-113">Primary</span></span>  <br/> |<span data-ttu-id="928f1-114">Eindeutiger Bezeichner für die angegebene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="928f1-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="928f1-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="928f1-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="928f1-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="928f1-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="928f1-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="928f1-117">Unique</span></span>  <br/> |<span data-ttu-id="928f1-118">Eindeutige IP-Adresse (beispielsweise 189.168.1.1), die dem IpAddressKey zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="928f1-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="928f1-119">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="928f1-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

