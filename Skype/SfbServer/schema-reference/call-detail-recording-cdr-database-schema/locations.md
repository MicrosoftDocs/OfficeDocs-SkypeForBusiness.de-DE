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
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Jeder Datensatz steht in einem Notruf wie ein E9-1-1-Anruf für einen standortbezug.
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296119"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c20a2-103">Tabelle "Speicherorte" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c20a2-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c20a2-104">Jeder Datensatz steht in einem Notruf wie ein E9-1-1-Anruf für einen standortbezug.</span><span class="sxs-lookup"><span data-stu-id="c20a2-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="c20a2-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c20a2-105">**Column**</span></span>|<span data-ttu-id="c20a2-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c20a2-106">**Data Type**</span></span>|<span data-ttu-id="c20a2-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="c20a2-107">**Key/Index**</span></span>|<span data-ttu-id="c20a2-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="c20a2-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c20a2-109">**SessionID**</span><span class="sxs-lookup"><span data-stu-id="c20a2-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="c20a2-110">datetime</span><span class="sxs-lookup"><span data-stu-id="c20a2-110">datetime</span></span>  <br/> |<span data-ttu-id="c20a2-111">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="c20a2-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c20a2-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="c20a2-112">Time of session request.</span></span> <span data-ttu-id="c20a2-113">Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c20a2-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="c20a2-114">Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="c20a2-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c20a2-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="c20a2-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="c20a2-116">int</span><span class="sxs-lookup"><span data-stu-id="c20a2-116">int</span></span>  <br/> |<span data-ttu-id="c20a2-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="c20a2-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c20a2-118">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c20a2-118">ID number to identify the session.</span></span> <span data-ttu-id="c20a2-119">Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c20a2-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="c20a2-120">Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="c20a2-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c20a2-121">**Standort**</span><span class="sxs-lookup"><span data-stu-id="c20a2-121">**Location**</span></span> <br/> |<span data-ttu-id="c20a2-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="c20a2-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="c20a2-123">Ort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="c20a2-123">Location of emergency call.</span></span>  <br/> |
   

