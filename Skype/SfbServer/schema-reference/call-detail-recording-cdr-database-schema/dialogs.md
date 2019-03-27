---
title: Dialogs-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs-Tabelle ist eine unterstützende Tabelle, die Informationen über DialogIDs für Peer-zu-Peer-Sitzungen gespeichert.
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889628"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="dc6c6-103">Dialogs-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc6c6-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dc6c6-104">Dialogs-Tabelle ist eine unterstützende Tabelle, die Informationen über DialogIDs für Peer-zu-Peer-Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="dc6c6-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-105">**Column**</span></span>|<span data-ttu-id="dc6c6-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-106">**Data Type**</span></span>|<span data-ttu-id="dc6c6-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-107">**Key/Index**</span></span>|<span data-ttu-id="dc6c6-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc6c6-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="dc6c6-110">datetime</span><span class="sxs-lookup"><span data-stu-id="dc6c6-110">datetime</span></span>  <br/> |<span data-ttu-id="dc6c6-111">Primary</span><span class="sxs-lookup"><span data-stu-id="dc6c6-111">Primary</span></span>  <br/> |<span data-ttu-id="dc6c6-112">Zeitpunkt der sitzungsanforderung; zusammen mit SessionIDSeq verwendet zur eindeutigen Identifizierung eine Sitzung.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="dc6c6-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="dc6c6-114">int</span><span class="sxs-lookup"><span data-stu-id="dc6c6-114">int</span></span>  <br/> |<span data-ttu-id="dc6c6-115">Primary</span><span class="sxs-lookup"><span data-stu-id="dc6c6-115">Primary</span></span>  <br/> |<span data-ttu-id="dc6c6-116">ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-116">ID number to identify the session.</span></span> <span data-ttu-id="dc6c6-117">In Verbindung mit SessionIDTime verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="dc6c6-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="dc6c6-119">int</span><span class="sxs-lookup"><span data-stu-id="dc6c6-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="dc6c6-120">Prüfsumme der ExternalID.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="dc6c6-121">Dieses Feld wird verwendet, um die Datenbank Suchvorgänge zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="dc6c6-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="dc6c6-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="dc6c6-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="dc6c6-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="dc6c6-124">SIP-Dialog-ID als binäre gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="dc6c6-125">Das Format der Binärdatei ist:</span><span class="sxs-lookup"><span data-stu-id="dc6c6-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="dc6c6-126">Dialogfeld; aus Tag; -tag</span><span class="sxs-lookup"><span data-stu-id="dc6c6-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="dc6c6-127">Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="dc6c6-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

