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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212831"
---
# <a name="roles-table"></a><span data-ttu-id="0cdb8-103">Roles-Tabelle</span><span class="sxs-lookup"><span data-stu-id="0cdb8-103">Roles table</span></span>
 
<span data-ttu-id="0cdb8-104">Die Roles-Tabelle ist eine statische Tabelle, die die Liste der möglichen Konferenzrollen wie Teilnehmer und Referent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0cdb8-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="0cdb8-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="0cdb8-105">**Column**</span></span>|<span data-ttu-id="0cdb8-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="0cdb8-106">**Data Type**</span></span>|<span data-ttu-id="0cdb8-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="0cdb8-107">**Key/Index**</span></span>|<span data-ttu-id="0cdb8-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="0cdb8-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cdb8-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="0cdb8-109">**RoleId**</span></span> <br/> |<span data-ttu-id="0cdb8-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="0cdb8-110">tinyint</span></span>  <br/> |<span data-ttu-id="0cdb8-111">Primary</span><span class="sxs-lookup"><span data-stu-id="0cdb8-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="0cdb8-112">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="0cdb8-112">**Role**</span></span> <br/> |<span data-ttu-id="0cdb8-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cdb8-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="0cdb8-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="0cdb8-114">Allowed values:</span></span> <br/>  <span data-ttu-id="0cdb8-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="0cdb8-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="0cdb8-116">1 – Referent</span><span class="sxs-lookup"><span data-stu-id="0cdb8-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="0cdb8-117">2 - Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="0cdb8-117">2 - Attendee</span></span> <br/> |
   

