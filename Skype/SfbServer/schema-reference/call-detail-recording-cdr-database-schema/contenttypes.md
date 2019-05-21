---
title: Tabelle "ContentTypes" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Die ContentTypes-Tabelle ist eine unterstützende Tabelle, in der eine Liste der Inhaltstypen gespeichert wird, die sowohl in Peer-to-Peer-Sitzungen als auch in Konferenzsitzungen verwendet werden. Jeder Datensatz in der Tabelle stellt einen Inhaltstyp dar.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296371"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="12ab3-104">Tabelle "ContentTypes" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="12ab3-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="12ab3-105">Die ContentTypes-Tabelle ist eine unterstützende Tabelle, in der eine Liste der Inhaltstypen gespeichert wird, die sowohl in Peer-to-Peer-Sitzungen als auch in Konferenzsitzungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12ab3-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="12ab3-106">Jeder Datensatz in der Tabelle stellt einen Inhaltstyp dar.</span><span class="sxs-lookup"><span data-stu-id="12ab3-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="12ab3-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="12ab3-107">**Column**</span></span>|<span data-ttu-id="12ab3-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="12ab3-108">**Data Type**</span></span>|<span data-ttu-id="12ab3-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="12ab3-109">**Key/Index**</span></span>|<span data-ttu-id="12ab3-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="12ab3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12ab3-111">**ContentTypeID**</span><span class="sxs-lookup"><span data-stu-id="12ab3-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="12ab3-112">int</span><span class="sxs-lookup"><span data-stu-id="12ab3-112">int</span></span>  <br/> |<span data-ttu-id="12ab3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="12ab3-113">Primary</span></span>  <br/> |<span data-ttu-id="12ab3-114">Eindeutige Zahl, die den Inhaltstyp kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="12ab3-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="12ab3-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="12ab3-115">**ContentType**</span></span> <br/> |<span data-ttu-id="12ab3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="12ab3-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="12ab3-117">Name des Inhaltstyps.</span><span class="sxs-lookup"><span data-stu-id="12ab3-117">Content type name.</span></span>  <br/> |
   

