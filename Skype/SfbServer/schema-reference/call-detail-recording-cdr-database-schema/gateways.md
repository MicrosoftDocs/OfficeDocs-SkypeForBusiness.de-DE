---
title: Tabelle "Gateways" in Skype for Business Server 2015
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Die Tabelle Gateways ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gateway, das an PSTN-anrufen (Public Switched Telephone Network) beteiligt ist, die Datensätze in der Datenbank aufweisen.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815163"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="88f1d-104">Tabelle "Gateways" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="88f1d-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="88f1d-105">Die Tabelle Gateways ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="88f1d-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="88f1d-106">Jeder Datensatz speichert Informationen zu einem Gateway, das an PSTN-anrufen (Public Switched Telephone Network) beteiligt ist, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="88f1d-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="88f1d-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="88f1d-107">**Column**</span></span>|<span data-ttu-id="88f1d-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="88f1d-108">**Data Type**</span></span>|<span data-ttu-id="88f1d-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="88f1d-109">**Key/Index**</span></span>|<span data-ttu-id="88f1d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="88f1d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="88f1d-111">**Gatewayserver**</span><span class="sxs-lookup"><span data-stu-id="88f1d-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="88f1d-112">int</span><span class="sxs-lookup"><span data-stu-id="88f1d-112">int</span></span>  <br/> |<span data-ttu-id="88f1d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="88f1d-113">Primary</span></span>  <br/> |<span data-ttu-id="88f1d-114">Eindeutige Nummer, die dieses Gateway kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="88f1d-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="88f1d-115">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="88f1d-115">**Gateway**</span></span> <br/> |<span data-ttu-id="88f1d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="88f1d-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="88f1d-117">Gateway-Name.</span><span class="sxs-lookup"><span data-stu-id="88f1d-117">Gateway name.</span></span>  <br/> |
   

