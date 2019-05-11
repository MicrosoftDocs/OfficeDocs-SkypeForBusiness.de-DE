---
title: FileTransfers-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Die Ansicht FileTransfer speichert Informationen zu Peer-zu-Peer-dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: aa238d11a88b8259427619271171adcf6f1c3e42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901187"
---
# <a name="filetransfers-view"></a><span data-ttu-id="f60de-104">FileTransfers-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f60de-104">FileTransfers view</span></span>
 
<span data-ttu-id="f60de-105">Die Ansicht FileTransfer speichert Informationen zu Peer-zu-Peer-dateiübertragungssitzungen.</span><span class="sxs-lookup"><span data-stu-id="f60de-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="f60de-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f60de-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f60de-107">Die FileTransfers-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) außerdem die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="f60de-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="f60de-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f60de-108">**Column**</span></span>|<span data-ttu-id="f60de-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f60de-109">**Data Type**</span></span>|<span data-ttu-id="f60de-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f60de-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f60de-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="f60de-111">**FileName**</span></span> <br/> |<span data-ttu-id="f60de-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f60de-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f60de-113">Name der Datei übertragen.</span><span class="sxs-lookup"><span data-stu-id="f60de-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="f60de-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="f60de-114">**Cookie**</span></span> <br/> |<span data-ttu-id="f60de-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="f60de-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="f60de-116">Verwendet, um jede Nachricht zur nachverfolgung als wird hiermit zugeordnet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f60de-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="f60de-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="f60de-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="f60de-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f60de-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="f60de-119">Eindeutiger Bezeichner zum unterscheiden zwischen dateiübertragungen mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="f60de-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="f60de-120">**Akzeptieren**</span><span class="sxs-lookup"><span data-stu-id="f60de-120">**Accept**</span></span> <br/> |<span data-ttu-id="f60de-121">bit</span><span class="sxs-lookup"><span data-stu-id="f60de-121">bit</span></span>  <br/> |<span data-ttu-id="f60de-122">TRUE oder NULL kann sein.</span><span class="sxs-lookup"><span data-stu-id="f60de-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="f60de-123">Wenn TRUE, dann ablehnen, und Abbrechen werden NULL sein.</span><span class="sxs-lookup"><span data-stu-id="f60de-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f60de-124">**Ablehnen**</span><span class="sxs-lookup"><span data-stu-id="f60de-124">**Reject**</span></span> <br/> |<span data-ttu-id="f60de-125">bit</span><span class="sxs-lookup"><span data-stu-id="f60de-125">bit</span></span>  <br/> |<span data-ttu-id="f60de-126">TRUE oder NULL kann sein.</span><span class="sxs-lookup"><span data-stu-id="f60de-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="f60de-127">Bei TRUE wird annehmen und Abbrechen NULL sein.</span><span class="sxs-lookup"><span data-stu-id="f60de-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f60de-128">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="f60de-128">**Cancel**</span></span> <br/> |<span data-ttu-id="f60de-129">bit</span><span class="sxs-lookup"><span data-stu-id="f60de-129">bit</span></span>  <br/> |<span data-ttu-id="f60de-130">TRUE oder NULL kann sein.</span><span class="sxs-lookup"><span data-stu-id="f60de-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="f60de-131">Bei TRUE wird annehmen und Ablehnen NULL sein.</span><span class="sxs-lookup"><span data-stu-id="f60de-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

