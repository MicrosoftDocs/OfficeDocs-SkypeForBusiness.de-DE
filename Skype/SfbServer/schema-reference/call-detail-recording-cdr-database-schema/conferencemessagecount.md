---
title: ConferenceMessageCount-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Jeder Datensatz in dieser Tabelle steht für einen Benutzer in einer Chat Konferenz und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296455"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="12613-104">ConferenceMessageCount-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="12613-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="12613-105">Jeder Datensatz in dieser Tabelle steht für einen Benutzer in einer Chat Konferenz und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="12613-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="12613-106">Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="12613-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="12613-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="12613-107">**Column**</span></span>|<span data-ttu-id="12613-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="12613-108">**Data Type**</span></span>|<span data-ttu-id="12613-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="12613-109">**Key/Index**</span></span>|<span data-ttu-id="12613-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="12613-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12613-111">**SessionID**</span><span class="sxs-lookup"><span data-stu-id="12613-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="12613-112">datetime</span><span class="sxs-lookup"><span data-stu-id="12613-112">datetime</span></span>  <br/> |<span data-ttu-id="12613-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="12613-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="12613-114">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="12613-114">Time of conference instance.</span></span> <span data-ttu-id="12613-115">Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="12613-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="12613-116">Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="12613-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="12613-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="12613-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="12613-118">int</span><span class="sxs-lookup"><span data-stu-id="12613-118">int</span></span>  <br/> |<span data-ttu-id="12613-119">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="12613-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="12613-120">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="12613-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="12613-121">Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="12613-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="12613-122">Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="12613-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="12613-123">**UserID**</span><span class="sxs-lookup"><span data-stu-id="12613-123">**UserId**</span></span> <br/> |<span data-ttu-id="12613-124">int</span><span class="sxs-lookup"><span data-stu-id="12613-124">int</span></span>  <br/> |<span data-ttu-id="12613-125">Fremd</span><span class="sxs-lookup"><span data-stu-id="12613-125">Foreign</span></span>  <br/> |<span data-ttu-id="12613-126">Eindeutige Nummer, die diesen Benutzer identifiziert, auf die in der [Tabelle "Benutzer](users.md)" verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="12613-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="12613-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="12613-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="12613-128">smallint</span><span class="sxs-lookup"><span data-stu-id="12613-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="12613-129">Die Anzahl der Nachrichten, die dieser Benutzer während dieser Konferenz gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="12613-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

