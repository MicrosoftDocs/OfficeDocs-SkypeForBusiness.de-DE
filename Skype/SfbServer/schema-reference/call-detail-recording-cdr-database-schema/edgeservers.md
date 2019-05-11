---
title: EdgeServers-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über einen Edge-Server, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: a55a72f9a98dda0295256803a7f9318116ecf969
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901052"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6addf-104">EdgeServers-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6addf-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6addf-105">EdgeServers-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6addf-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="6addf-106">Jeder Datensatz speichert Informationen über einen Edge-Server, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="6addf-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="6addf-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="6addf-107">**Column**</span></span>|<span data-ttu-id="6addf-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="6addf-108">**Data Type**</span></span>|<span data-ttu-id="6addf-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="6addf-109">**Key/Index**</span></span>|<span data-ttu-id="6addf-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="6addf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6addf-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="6addf-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="6addf-112">int</span><span class="sxs-lookup"><span data-stu-id="6addf-112">int</span></span>  <br/> |<span data-ttu-id="6addf-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6addf-113">Primary</span></span>  <br/> |<span data-ttu-id="6addf-114">Eindeutige Zahl, die diesen Edgeserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6addf-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="6addf-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="6addf-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="6addf-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6addf-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="6addf-117">Name des Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="6addf-117">Edge Server name.</span></span>  <br/> |
   

