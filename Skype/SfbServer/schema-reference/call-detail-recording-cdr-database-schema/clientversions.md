---
title: ClientVersions-Tabelle in Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Die ClientVersions-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Clienttypen und-Versionen gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle stellt eine Client Version dar.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815403"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5817e-104">ClientVersions-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5817e-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5817e-105">Die ClientVersions-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Clienttypen und-Versionen gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="5817e-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="5817e-106">Jeder Datensatz in der Tabelle stellt eine Client Version dar.</span><span class="sxs-lookup"><span data-stu-id="5817e-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="5817e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5817e-107">**Column**</span></span>|<span data-ttu-id="5817e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5817e-108">**Data Type**</span></span>|<span data-ttu-id="5817e-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="5817e-109">**Key/Index**</span></span>|<span data-ttu-id="5817e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="5817e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5817e-111">**VersionID**</span><span class="sxs-lookup"><span data-stu-id="5817e-111">**VersionId**</span></span> <br/> |<span data-ttu-id="5817e-112">**int**</span><span class="sxs-lookup"><span data-stu-id="5817e-112">**int**</span></span> <br/> |<span data-ttu-id="5817e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5817e-113">Primary</span></span>  <br/> |<span data-ttu-id="5817e-114">Eindeutige Nummer, die diesen Clienttyp und die Version identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5817e-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="5817e-115">**Version**</span><span class="sxs-lookup"><span data-stu-id="5817e-115">**Version**</span></span> <br/> |<span data-ttu-id="5817e-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="5817e-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="5817e-117">Versionsname.</span><span class="sxs-lookup"><span data-stu-id="5817e-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="5817e-118">**Clienttyp**</span><span class="sxs-lookup"><span data-stu-id="5817e-118">**ClientType**</span></span> <br/> |<span data-ttu-id="5817e-119">int</span><span class="sxs-lookup"><span data-stu-id="5817e-119">int</span></span>  <br/> ||<span data-ttu-id="5817e-120">Gibt den Typ des in der Sitzung verwendeten Clients an.</span><span class="sxs-lookup"><span data-stu-id="5817e-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="5817e-121">Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="5817e-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="5817e-122">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5817e-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

