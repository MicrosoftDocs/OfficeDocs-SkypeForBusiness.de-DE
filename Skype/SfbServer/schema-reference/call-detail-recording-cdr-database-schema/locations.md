---
title: Locations-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Jeder Datensatz steht für einen Verweis auf den Speicherort in ein Notruf, wie ein Anruf E9-1-1.
ms.openlocfilehash: b15e7f0b7930871b97dc3341a47153965529810e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d832f-103">Locations-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d832f-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d832f-104">Jeder Datensatz steht für einen Verweis auf den Speicherort in ein Notruf, wie ein Anruf E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d832f-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="d832f-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d832f-105">**Column**</span></span>|<span data-ttu-id="d832f-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d832f-106">**Data Type**</span></span>|<span data-ttu-id="d832f-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="d832f-107">**Key/Index**</span></span>|<span data-ttu-id="d832f-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="d832f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d832f-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="d832f-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="d832f-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d832f-110">datetime</span></span>  <br/> |<span data-ttu-id="d832f-111">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="d832f-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d832f-112">Zeitpunkt der sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="d832f-112">Time of session request.</span></span> <span data-ttu-id="d832f-113">Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d832f-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="d832f-114">Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d832f-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d832f-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="d832f-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="d832f-116">int</span><span class="sxs-lookup"><span data-stu-id="d832f-116">int</span></span>  <br/> |<span data-ttu-id="d832f-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="d832f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d832f-118">ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d832f-118">ID number to identify the session.</span></span> <span data-ttu-id="d832f-119">In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d832f-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="d832f-120">Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d832f-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d832f-121">**Standort**</span><span class="sxs-lookup"><span data-stu-id="d832f-121">**Location**</span></span> <br/> |<span data-ttu-id="d832f-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="d832f-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="d832f-123">Standort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="d832f-123">Location of emergency call.</span></span>  <br/> |
   

