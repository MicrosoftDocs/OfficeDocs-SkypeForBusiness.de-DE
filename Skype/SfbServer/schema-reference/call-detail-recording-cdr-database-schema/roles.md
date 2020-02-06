---
title: Roles-Tabelle
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Die Tabelle "Rollen" ist eine statische Tabelle, in der die Liste möglicher Konferenz Rollen wie Teilnehmer und Referenten gespeichert ist.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814933"
---
# <a name="roles-table"></a><span data-ttu-id="a5989-103">Roles-Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5989-103">Roles table</span></span>
 
<span data-ttu-id="a5989-104">Die Tabelle "Rollen" ist eine statische Tabelle, in der die Liste möglicher Konferenz Rollen wie Teilnehmer und Referenten gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="a5989-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="a5989-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a5989-105">**Column**</span></span>|<span data-ttu-id="a5989-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a5989-106">**Data Type**</span></span>|<span data-ttu-id="a5989-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="a5989-107">**Key/Index**</span></span>|<span data-ttu-id="a5989-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="a5989-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5989-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="a5989-109">**RoleId**</span></span> <br/> |<span data-ttu-id="a5989-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5989-110">tinyint</span></span>  <br/> |<span data-ttu-id="a5989-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a5989-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="a5989-112">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="a5989-112">**Role**</span></span> <br/> |<span data-ttu-id="a5989-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a5989-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a5989-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="a5989-114">Allowed values:</span></span> <br/>  <span data-ttu-id="a5989-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="a5989-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="a5989-116">1-Referent</span><span class="sxs-lookup"><span data-stu-id="a5989-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="a5989-117">2 – Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="a5989-117">2 - Attendee</span></span> <br/> |
   

