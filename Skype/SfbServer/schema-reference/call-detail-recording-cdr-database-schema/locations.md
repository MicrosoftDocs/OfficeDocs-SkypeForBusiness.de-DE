---
title: Tabelle "Speicherorte" in Skype for Business Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Jeder Datensatz steht in einem Notruf wie ein E9-1-1-Anruf für einen standortbezug.
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815113"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5ec71-103">Tabelle "Speicherorte" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ec71-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5ec71-104">Jeder Datensatz steht in einem Notruf wie ein E9-1-1-Anruf für einen standortbezug.</span><span class="sxs-lookup"><span data-stu-id="5ec71-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="5ec71-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5ec71-105">**Column**</span></span>|<span data-ttu-id="5ec71-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5ec71-106">**Data Type**</span></span>|<span data-ttu-id="5ec71-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="5ec71-107">**Key/Index**</span></span>|<span data-ttu-id="5ec71-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="5ec71-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ec71-109">**SessionID**</span><span class="sxs-lookup"><span data-stu-id="5ec71-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="5ec71-110">datetime</span><span class="sxs-lookup"><span data-stu-id="5ec71-110">datetime</span></span>  <br/> |<span data-ttu-id="5ec71-111">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="5ec71-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5ec71-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="5ec71-112">Time of session request.</span></span> <span data-ttu-id="5ec71-113">Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ec71-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="5ec71-114">Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="5ec71-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="5ec71-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="5ec71-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="5ec71-116">int</span><span class="sxs-lookup"><span data-stu-id="5ec71-116">int</span></span>  <br/> |<span data-ttu-id="5ec71-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="5ec71-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5ec71-118">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ec71-118">ID number to identify the session.</span></span> <span data-ttu-id="5ec71-119">Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ec71-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="5ec71-120">Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="5ec71-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="5ec71-121">**Standort**</span><span class="sxs-lookup"><span data-stu-id="5ec71-121">**Location**</span></span> <br/> |<span data-ttu-id="5ec71-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5ec71-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="5ec71-123">Ort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="5ec71-123">Location of emergency call.</span></span>  <br/> |
   

