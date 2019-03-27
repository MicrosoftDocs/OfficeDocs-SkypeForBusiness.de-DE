---
title: Roles-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Die Roles-Tabelle ist eine statische Tabelle, die die Liste der möglichen Konferenzrollen wie Teilnehmer und Referent gespeichert.
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891713"
---
# <a name="roles-table"></a><span data-ttu-id="ba1c1-103">Roles-Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba1c1-103">Roles table</span></span>
 
<span data-ttu-id="ba1c1-104">Die Roles-Tabelle ist eine statische Tabelle, die die Liste der möglichen Konferenzrollen wie Teilnehmer und Referent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ba1c1-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="ba1c1-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ba1c1-105">**Column**</span></span>|<span data-ttu-id="ba1c1-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ba1c1-106">**Data Type**</span></span>|<span data-ttu-id="ba1c1-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ba1c1-107">**Key/Index**</span></span>|<span data-ttu-id="ba1c1-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="ba1c1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba1c1-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="ba1c1-109">**RoleId**</span></span> <br/> |<span data-ttu-id="ba1c1-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba1c1-110">tinyint</span></span>  <br/> |<span data-ttu-id="ba1c1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ba1c1-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ba1c1-112">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="ba1c1-112">**Role**</span></span> <br/> |<span data-ttu-id="ba1c1-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba1c1-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ba1c1-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="ba1c1-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ba1c1-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="ba1c1-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="ba1c1-116">1 – Referent</span><span class="sxs-lookup"><span data-stu-id="ba1c1-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="ba1c1-117">2 - Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="ba1c1-117">2 - Attendee</span></span> <br/> |
   

