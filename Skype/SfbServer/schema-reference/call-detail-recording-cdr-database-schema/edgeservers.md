---
title: EdgeServers-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über einen Edge-Server, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: 253190f23d130d12a1b4af701bf68922717d8da8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213137"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8add6-104">EdgeServers-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8add6-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8add6-105">EdgeServers-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8add6-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="8add6-106">Jeder Datensatz speichert Informationen über einen Edge-Server, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="8add6-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="8add6-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8add6-107">**Column**</span></span>|<span data-ttu-id="8add6-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8add6-108">**Data Type**</span></span>|<span data-ttu-id="8add6-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="8add6-109">**Key/Index**</span></span>|<span data-ttu-id="8add6-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="8add6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8add6-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="8add6-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="8add6-112">int</span><span class="sxs-lookup"><span data-stu-id="8add6-112">int</span></span>  <br/> |<span data-ttu-id="8add6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8add6-113">Primary</span></span>  <br/> |<span data-ttu-id="8add6-114">Eindeutige Zahl, die diesen Edgeserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8add6-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="8add6-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="8add6-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="8add6-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8add6-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="8add6-117">Name des Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="8add6-117">Edge Server name.</span></span>  <br/> |
   

