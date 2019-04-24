---
title: ConferenceMessageCount-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Sofortnachrichtenkonferenz und enthält die Anzahl der Nachrichten, die von diesem Benutzer gesendet. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. einen Eintrag für jeden Benutzer.
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213277"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e4f7c-104">ConferenceMessageCount-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e4f7c-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e4f7c-105">Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Sofortnachrichtenkonferenz und enthält die Anzahl der Nachrichten, die von diesem Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="e4f7c-106">Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. einen Eintrag für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="e4f7c-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-107">**Column**</span></span>|<span data-ttu-id="e4f7c-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-108">**Data Type**</span></span>|<span data-ttu-id="e4f7c-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-109">**Key/Index**</span></span>|<span data-ttu-id="e4f7c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4f7c-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="e4f7c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e4f7c-112">datetime</span></span>  <br/> |<span data-ttu-id="e4f7c-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e4f7c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e4f7c-114">Zeitpunkt des Konferenz-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-114">Time of conference instance.</span></span> <span data-ttu-id="e4f7c-115">Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Konferenz-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="e4f7c-116">[Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e4f7c-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="e4f7c-118">int</span><span class="sxs-lookup"><span data-stu-id="e4f7c-118">int</span></span>  <br/> |<span data-ttu-id="e4f7c-119">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e4f7c-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e4f7c-120">ID-Nummer zum Identifizieren der Konferenz-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="e4f7c-121">In Verbindung mit **SessionIdTime** verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="e4f7c-122">[Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e4f7c-123">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-123">**UserId**</span></span> <br/> |<span data-ttu-id="e4f7c-124">int</span><span class="sxs-lookup"><span data-stu-id="e4f7c-124">int</span></span>  <br/> |<span data-ttu-id="e4f7c-125">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="e4f7c-125">Foreign</span></span>  <br/> |<span data-ttu-id="e4f7c-126">Eindeutige Zahl, die diesen Benutzer wird aus der [Tabelle Benutzer](users.md)identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="e4f7c-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="e4f7c-128">smallint</span><span class="sxs-lookup"><span data-stu-id="e4f7c-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="e4f7c-129">Die Anzahl der während dieser Konferenz von diesem Benutzer gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

