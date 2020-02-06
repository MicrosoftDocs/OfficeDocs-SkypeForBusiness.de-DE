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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Die IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809543"
---
# <a name="ipaddress-table"></a><span data-ttu-id="5464a-104">IPAddress-Tabelle</span><span class="sxs-lookup"><span data-stu-id="5464a-104">IPAddress table</span></span>
 
<span data-ttu-id="5464a-105">Die IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5464a-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="5464a-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5464a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5464a-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5464a-107">**Column**</span></span>|<span data-ttu-id="5464a-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5464a-108">**Data Type**</span></span>|<span data-ttu-id="5464a-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="5464a-109">**Key/Index**</span></span>|<span data-ttu-id="5464a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="5464a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5464a-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="5464a-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="5464a-112">int</span><span class="sxs-lookup"><span data-stu-id="5464a-112">int</span></span>  <br/> |<span data-ttu-id="5464a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5464a-113">Primary</span></span>  <br/> |<span data-ttu-id="5464a-114">Eindeutiger Bezeichner für die angegebene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="5464a-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="5464a-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="5464a-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="5464a-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="5464a-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="5464a-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="5464a-117">Unique</span></span>  <br/> |<span data-ttu-id="5464a-118">Eindeutige IP-Adresse (beispielsweise 189.168.1.1), die dem IpAddressKey zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5464a-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="5464a-119">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="5464a-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

