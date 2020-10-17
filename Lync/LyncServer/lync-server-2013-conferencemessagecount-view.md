---
title: 'Lync Server 2013: ConferenceMessageCount-Ansicht'
description: 'Lync Server 2013: ConferenceMessageCount-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561611"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="acd54-103">ConferenceMessageCount-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acd54-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acd54-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="acd54-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="acd54-105">In der ConferenceMessageCount-Ansicht werden Informationen darüber gespeichert, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="acd54-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="acd54-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="acd54-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acd54-107">Die ConferenceMessageCount-Ansicht enthält alle Spalten in der <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails-Ansicht in lync Server 2013</A> zusätzlich zu den unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="acd54-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acd54-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="acd54-108">Column</span></span></th>
<th><span data-ttu-id="acd54-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="acd54-109">Data Type</span></span></th>
<th><span data-ttu-id="acd54-110">Details</span><span class="sxs-lookup"><span data-stu-id="acd54-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acd54-111"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="acd54-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="acd54-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="acd54-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="acd54-113">URI des Benutzers, der die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="acd54-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acd54-114"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="acd54-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="acd54-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="acd54-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="acd54-116">URI-Typ des Benutzers, der die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="acd54-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="acd54-117">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="acd54-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acd54-118"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="acd54-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="acd54-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="acd54-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="acd54-120">Mandant des Benutzers, der die Nachrichten gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="acd54-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="acd54-121">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="acd54-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acd54-122"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="acd54-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="acd54-123">smallint</span><span class="sxs-lookup"><span data-stu-id="acd54-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="acd54-124">Die Anzahl der Nachrichten, die der Benutzer während der Konferenzsitzung gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="acd54-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

