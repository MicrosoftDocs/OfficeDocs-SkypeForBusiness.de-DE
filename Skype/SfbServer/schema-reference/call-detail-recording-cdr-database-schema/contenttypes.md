---
title: ContentTypes-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Die ContentTypes-Tabelle ist eine unterstützende Tabelle, die eine Liste der Inhaltstypen in Peer-zu-Peer-Sitzungen und konferenzsitzungen verwendeten gespeichert. Jeder Datensatz in der Tabelle steht für einen Inhaltstyp.
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1cda7-104">ContentTypes-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1cda7-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1cda7-105">Die ContentTypes-Tabelle ist eine unterstützende Tabelle, die eine Liste der Inhaltstypen in Peer-zu-Peer-Sitzungen und konferenzsitzungen verwendeten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1cda7-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="1cda7-106">Jeder Datensatz in der Tabelle steht für einen Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="1cda7-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="1cda7-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1cda7-107">**Column**</span></span>|<span data-ttu-id="1cda7-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="1cda7-108">**Data Type**</span></span>|<span data-ttu-id="1cda7-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="1cda7-109">**Key/Index**</span></span>|<span data-ttu-id="1cda7-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="1cda7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cda7-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="1cda7-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="1cda7-112">int</span><span class="sxs-lookup"><span data-stu-id="1cda7-112">int</span></span>  <br/> |<span data-ttu-id="1cda7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1cda7-113">Primary</span></span>  <br/> |<span data-ttu-id="1cda7-114">Eindeutige Zahl, die den Inhaltstyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1cda7-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="1cda7-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="1cda7-115">**ContentType**</span></span> <br/> |<span data-ttu-id="1cda7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1cda7-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="1cda7-117">Name des Inhaltstyps.</span><span class="sxs-lookup"><span data-stu-id="1cda7-117">Content type name.</span></span>  <br/> |
   

