---
title: 'Lync Server 2013: tblComplianceParticipant'
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
ms.openlocfilehash: a4d5a0024c273dbef8fee16f1fb4b3372692ab4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="7b1d5-102">tblComplianceParticipant in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b1d5-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b1d5-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7b1d5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7b1d5-104">tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.</span><span class="sxs-lookup"><span data-stu-id="7b1d5-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="7b1d5-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="7b1d5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b1d5-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="7b1d5-106">Column</span></span></th>
<th><span data-ttu-id="7b1d5-107">Typ</span><span class="sxs-lookup"><span data-stu-id="7b1d5-107">Type</span></span></th>
<th><span data-ttu-id="7b1d5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b1d5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b1d5-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="7b1d5-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-110">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7b1d5-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-111">Kanal-URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="7b1d5-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b1d5-112">userId</span><span class="sxs-lookup"><span data-stu-id="7b1d5-112">userId</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7b1d5-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-114">Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="7b1d5-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b1d5-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="7b1d5-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-116">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7b1d5-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-117">Zeitstempel des Ereignisses des Beitritts.</span><span class="sxs-lookup"><span data-stu-id="7b1d5-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b1d5-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="7b1d5-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-119">bigint</span><span class="sxs-lookup"><span data-stu-id="7b1d5-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-p101">NULL, wenn der Teilnehmer noch immer teilnimmt. Der Zeitstempel des Ereignisses des Verlassens des Kanals, sofern nicht NULL.</span><span class="sxs-lookup"><span data-stu-id="7b1d5-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="7b1d5-122">Diese Einträge werden schließlich entfernt, wenn das Ereignis von allen Konvertern verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="7b1d5-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b1d5-123">userUri</span><span class="sxs-lookup"><span data-stu-id="7b1d5-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-124">nvarchar(255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7b1d5-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-125">Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="7b1d5-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b1d5-126">ServerID</span><span class="sxs-lookup"><span data-stu-id="7b1d5-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-127">int</span><span class="sxs-lookup"><span data-stu-id="7b1d5-127">int</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-128">Serveridentität (wie in tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="7b1d5-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b1d5-129">SessionID</span><span class="sxs-lookup"><span data-stu-id="7b1d5-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-130">bigint</span><span class="sxs-lookup"><span data-stu-id="7b1d5-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-p102">Serversitzung. Zufallszahl, die nach jedem Starten eines Chatdiensts generiert wird. Wird zur Unterscheidung von Sitzungen verwendet, mit dem Zweck, verwaiste Teilnehmer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7b1d5-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7b1d5-134">Key</span><span class="sxs-lookup"><span data-stu-id="7b1d5-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b1d5-135">Spalte</span><span class="sxs-lookup"><span data-stu-id="7b1d5-135">Column</span></span></th>
<th><span data-ttu-id="7b1d5-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b1d5-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b1d5-137">&lt;channelUri, UserID, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="7b1d5-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="7b1d5-138">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="7b1d5-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

