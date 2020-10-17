---
title: 'Lync Server 2013: tblComplianceParticipant'
description: 'Lync Server 2013: tblComplianceParticipant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569071"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="51532-103">tblComplianceParticipant in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51532-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51532-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="51532-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="51532-105">tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.</span><span class="sxs-lookup"><span data-stu-id="51532-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="51532-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="51532-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51532-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="51532-107">Column</span></span></th>
<th><span data-ttu-id="51532-108">Typ</span><span class="sxs-lookup"><span data-stu-id="51532-108">Type</span></span></th>
<th><span data-ttu-id="51532-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51532-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51532-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="51532-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="51532-111">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="51532-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="51532-112">Kanal-URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="51532-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51532-113">userId</span><span class="sxs-lookup"><span data-stu-id="51532-113">userId</span></span></p></td>
<td><p><span data-ttu-id="51532-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="51532-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="51532-115">Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="51532-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51532-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="51532-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="51532-117">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="51532-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="51532-118">Zeitstempel des Ereignisses des Beitritts.</span><span class="sxs-lookup"><span data-stu-id="51532-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51532-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="51532-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="51532-120">bigint</span><span class="sxs-lookup"><span data-stu-id="51532-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="51532-p101">NULL, wenn der Teilnehmer noch immer teilnimmt. Der Zeitstempel des Ereignisses des Verlassens des Kanals, sofern nicht NULL.</span><span class="sxs-lookup"><span data-stu-id="51532-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="51532-123">Diese Einträge werden schließlich entfernt, wenn das Ereignis von allen Konvertern verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="51532-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51532-124">userUri</span><span class="sxs-lookup"><span data-stu-id="51532-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="51532-125">nvarchar(255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="51532-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="51532-126">Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="51532-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51532-127">ServerID</span><span class="sxs-lookup"><span data-stu-id="51532-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="51532-128">int</span><span class="sxs-lookup"><span data-stu-id="51532-128">int</span></span></p></td>
<td><p><span data-ttu-id="51532-129">Serveridentität (wie in tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="51532-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51532-130">SessionID</span><span class="sxs-lookup"><span data-stu-id="51532-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="51532-131">bigint</span><span class="sxs-lookup"><span data-stu-id="51532-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="51532-p102">Serversitzung. Zufallszahl, die nach jedem Starten eines Chatdiensts generiert wird. Wird zur Unterscheidung von Sitzungen verwendet, mit dem Zweck, verwaiste Teilnehmer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="51532-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="51532-135">Key</span><span class="sxs-lookup"><span data-stu-id="51532-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51532-136">Spalte</span><span class="sxs-lookup"><span data-stu-id="51532-136">Column</span></span></th>
<th><span data-ttu-id="51532-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51532-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51532-138">&lt;channelUri, UserID, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="51532-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="51532-139">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="51532-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

