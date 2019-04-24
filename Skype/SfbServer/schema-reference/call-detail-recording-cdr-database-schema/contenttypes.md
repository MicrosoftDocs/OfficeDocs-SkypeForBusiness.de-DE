---
title: ContentTypes-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213249"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="39ec5-104">ContentTypes-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="39ec5-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="39ec5-105">Die ContentTypes-Tabelle ist eine unterstützende Tabelle, die eine Liste der Inhaltstypen in Peer-zu-Peer-Sitzungen und konferenzsitzungen verwendeten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="39ec5-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="39ec5-106">Jeder Datensatz in der Tabelle steht für einen Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="39ec5-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="39ec5-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="39ec5-107">**Column**</span></span>|<span data-ttu-id="39ec5-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="39ec5-108">**Data Type**</span></span>|<span data-ttu-id="39ec5-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="39ec5-109">**Key/Index**</span></span>|<span data-ttu-id="39ec5-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="39ec5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39ec5-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="39ec5-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="39ec5-112">int</span><span class="sxs-lookup"><span data-stu-id="39ec5-112">int</span></span>  <br/> |<span data-ttu-id="39ec5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="39ec5-113">Primary</span></span>  <br/> |<span data-ttu-id="39ec5-114">Eindeutige Zahl, die den Inhaltstyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="39ec5-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="39ec5-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="39ec5-115">**ContentType**</span></span> <br/> |<span data-ttu-id="39ec5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="39ec5-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="39ec5-117">Name des Inhaltstyps.</span><span class="sxs-lookup"><span data-stu-id="39ec5-117">Content type name.</span></span>  <br/> |
   

