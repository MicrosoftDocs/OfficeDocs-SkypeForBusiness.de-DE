---
title: Gateways-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Die Gateways-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über ein Gateway, die beteiligt ist im öffentlichen Telefonnetz (Network, PSTN) anrufen, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: 16860e924fb69f1dfe337e05c13d54fb66a8ed81
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213074"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ea050-104">Gateways-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea050-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ea050-105">Die Gateways-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ea050-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="ea050-106">Jeder Datensatz speichert Informationen über ein Gateway, die beteiligt ist im öffentlichen Telefonnetz (Network, PSTN) anrufen, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="ea050-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="ea050-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ea050-107">**Column**</span></span>|<span data-ttu-id="ea050-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ea050-108">**Data Type**</span></span>|<span data-ttu-id="ea050-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ea050-109">**Key/Index**</span></span>|<span data-ttu-id="ea050-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ea050-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea050-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="ea050-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="ea050-112">int</span><span class="sxs-lookup"><span data-stu-id="ea050-112">int</span></span>  <br/> |<span data-ttu-id="ea050-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ea050-113">Primary</span></span>  <br/> |<span data-ttu-id="ea050-114">Eindeutige Zahl, die dieses Gateway identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ea050-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="ea050-115">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="ea050-115">**Gateway**</span></span> <br/> |<span data-ttu-id="ea050-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea050-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="ea050-117">Gatewayname</span><span class="sxs-lookup"><span data-stu-id="ea050-117">Gateway name.</span></span>  <br/> |
   

