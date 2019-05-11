---
title: Roles-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Die Roles-Tabelle ist eine statische Tabelle, die die Liste der möglichen Konferenzrollen wie Teilnehmer und Referent gespeichert.
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930304"
---
# <a name="roles-table"></a><span data-ttu-id="2d0af-103">Roles-Tabelle</span><span class="sxs-lookup"><span data-stu-id="2d0af-103">Roles table</span></span>
 
<span data-ttu-id="2d0af-104">Die Roles-Tabelle ist eine statische Tabelle, die die Liste der möglichen Konferenzrollen wie Teilnehmer und Referent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d0af-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="2d0af-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2d0af-105">**Column**</span></span>|<span data-ttu-id="2d0af-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="2d0af-106">**Data Type**</span></span>|<span data-ttu-id="2d0af-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="2d0af-107">**Key/Index**</span></span>|<span data-ttu-id="2d0af-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="2d0af-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d0af-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="2d0af-109">**RoleId**</span></span> <br/> |<span data-ttu-id="2d0af-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d0af-110">tinyint</span></span>  <br/> |<span data-ttu-id="2d0af-111">Primary</span><span class="sxs-lookup"><span data-stu-id="2d0af-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="2d0af-112">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="2d0af-112">**Role**</span></span> <br/> |<span data-ttu-id="2d0af-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2d0af-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2d0af-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="2d0af-114">Allowed values:</span></span> <br/>  <span data-ttu-id="2d0af-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="2d0af-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="2d0af-116">1 – Referent</span><span class="sxs-lookup"><span data-stu-id="2d0af-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="2d0af-117">2 - Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="2d0af-117">2 - Attendee</span></span> <br/> |
   

