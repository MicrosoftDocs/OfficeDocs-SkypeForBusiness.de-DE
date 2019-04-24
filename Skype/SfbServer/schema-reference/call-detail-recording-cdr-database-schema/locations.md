---
title: Locations-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213001"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ee0c9-103">Locations-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ee0c9-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ee0c9-104">Jeder Datensatz steht für einen Verweis auf den Speicherort in ein Notruf, wie ein Anruf E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="ee0c9-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ee0c9-105">**Column**</span></span>|<span data-ttu-id="ee0c9-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ee0c9-106">**Data Type**</span></span>|<span data-ttu-id="ee0c9-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ee0c9-107">**Key/Index**</span></span>|<span data-ttu-id="ee0c9-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="ee0c9-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee0c9-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="ee0c9-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ee0c9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ee0c9-110">datetime</span></span>  <br/> |<span data-ttu-id="ee0c9-111">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="ee0c9-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee0c9-112">Zeitpunkt der sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-112">Time of session request.</span></span> <span data-ttu-id="ee0c9-113">Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="ee0c9-114">Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ee0c9-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ee0c9-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ee0c9-116">int</span><span class="sxs-lookup"><span data-stu-id="ee0c9-116">int</span></span>  <br/> |<span data-ttu-id="ee0c9-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="ee0c9-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee0c9-118">ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-118">ID number to identify the session.</span></span> <span data-ttu-id="ee0c9-119">In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="ee0c9-120">Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ee0c9-121">**Standort**</span><span class="sxs-lookup"><span data-stu-id="ee0c9-121">**Location**</span></span> <br/> |<span data-ttu-id="ee0c9-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="ee0c9-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="ee0c9-123">Standort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="ee0c9-123">Location of emergency call.</span></span>  <br/> |
   

