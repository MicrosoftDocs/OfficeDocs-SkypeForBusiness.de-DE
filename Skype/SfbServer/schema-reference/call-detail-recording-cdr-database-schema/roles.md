---
title: Roles-Tabelle
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
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a><span data-ttu-id="d8ae5-103">Roles-Tabelle</span><span class="sxs-lookup"><span data-stu-id="d8ae5-103">Roles table</span></span>
 
<span data-ttu-id="d8ae5-104">Die Roles-Tabelle ist eine statische Tabelle, die die Liste der möglichen Konferenzrollen wie Teilnehmer und Referent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d8ae5-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="d8ae5-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d8ae5-105">**Column**</span></span>|<span data-ttu-id="d8ae5-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d8ae5-106">**Data Type**</span></span>|<span data-ttu-id="d8ae5-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="d8ae5-107">**Key/Index**</span></span>|<span data-ttu-id="d8ae5-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="d8ae5-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d8ae5-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="d8ae5-109">**RoleId**</span></span> <br/> |<span data-ttu-id="d8ae5-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8ae5-110">tinyint</span></span>  <br/> |<span data-ttu-id="d8ae5-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d8ae5-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="d8ae5-112">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="d8ae5-112">**Role**</span></span> <br/> |<span data-ttu-id="d8ae5-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d8ae5-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d8ae5-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="d8ae5-114">Allowed values:</span></span> <br/>  <span data-ttu-id="d8ae5-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="d8ae5-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="d8ae5-116">1 – Referent</span><span class="sxs-lookup"><span data-stu-id="d8ae5-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="d8ae5-117">2 - Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="d8ae5-117">2 - Attendee</span></span> <br/> |
   

