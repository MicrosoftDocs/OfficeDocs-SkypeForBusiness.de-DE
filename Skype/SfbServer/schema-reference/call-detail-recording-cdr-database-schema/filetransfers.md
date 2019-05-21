---
title: Dateiübertragungen (Ansicht)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Die Filetransfer-Ansicht speichert Informationen zu Peer-to-Peer-Dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296238"
---
# <a name="filetransfers-view"></a><span data-ttu-id="b429f-104">Dateiübertragungen (Ansicht)</span><span class="sxs-lookup"><span data-stu-id="b429f-104">FileTransfers view</span></span>
 
<span data-ttu-id="b429f-105">Die Filetransfer-Ansicht speichert Informationen zu Peer-to-Peer-Dateiübertragungssitzungen.</span><span class="sxs-lookup"><span data-stu-id="b429f-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="b429f-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b429f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b429f-107">Die Dateiübertragungen-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) sowie die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="b429f-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="b429f-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b429f-108">**Column**</span></span>|<span data-ttu-id="b429f-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b429f-109">**Data Type**</span></span>|<span data-ttu-id="b429f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b429f-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b429f-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="b429f-111">**FileName**</span></span> <br/> |<span data-ttu-id="b429f-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b429f-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b429f-113">Der Name der übertragenen Datei.</span><span class="sxs-lookup"><span data-stu-id="b429f-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="b429f-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="b429f-114">**Cookie**</span></span> <br/> |<span data-ttu-id="b429f-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b429f-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="b429f-116">Wird verwendet, um jede nach Verfolgungs Nachricht als zugeordnet zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="b429f-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="b429f-117">**Fileidentity**</span><span class="sxs-lookup"><span data-stu-id="b429f-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="b429f-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b429f-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="b429f-119">Eindeutiger Bezeichner zur Unterscheidung Zwischendatei Übertragungen mit demselben Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="b429f-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="b429f-120">**Annehmen**</span><span class="sxs-lookup"><span data-stu-id="b429f-120">**Accept**</span></span> <br/> |<span data-ttu-id="b429f-121">bit</span><span class="sxs-lookup"><span data-stu-id="b429f-121">bit</span></span>  <br/> |<span data-ttu-id="b429f-122">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="b429f-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="b429f-123">Ist "true", ist "ablehnen" und "Abbrechen" NULL.</span><span class="sxs-lookup"><span data-stu-id="b429f-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="b429f-124">**Ablehnen**</span><span class="sxs-lookup"><span data-stu-id="b429f-124">**Reject**</span></span> <br/> |<span data-ttu-id="b429f-125">bit</span><span class="sxs-lookup"><span data-stu-id="b429f-125">bit</span></span>  <br/> |<span data-ttu-id="b429f-126">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="b429f-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="b429f-127">Ist "true", ist "akzeptieren" und "Abbrechen" NULL.</span><span class="sxs-lookup"><span data-stu-id="b429f-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="b429f-128">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="b429f-128">**Cancel**</span></span> <br/> |<span data-ttu-id="b429f-129">bit</span><span class="sxs-lookup"><span data-stu-id="b429f-129">bit</span></span>  <br/> |<span data-ttu-id="b429f-130">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="b429f-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="b429f-131">Ist "true", ist "annehmen und ablehnen" NULL.</span><span class="sxs-lookup"><span data-stu-id="b429f-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

