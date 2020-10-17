---
title: 'Lync Server 2013: für lync Server aktivierte Benutzerkonten'
description: 'Lync Server 2013: für lync Server aktivierte Benutzerkonten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569871"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="f0933-103">Für lync Server 2013 aktivierte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f0933-103">User accounts enabled for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0933-104">_**Letztes Änderungsstand des Themas:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="f0933-104">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="f0933-105">Die Themen in diesem Abschnitt bieten schrittweise Anleitungen zum Konfigurieren von Benutzereinstellungen, die Sie mit der lync Server 2013-Systemsteuerung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f0933-105">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f0933-106">Sie können lync Server-Systemsteuerung nicht zum Verwalten von Benutzern verwenden, die Mitglied der Gruppe "Active Directory Domänen-Admins" sind.</span><span class="sxs-lookup"><span data-stu-id="f0933-106">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="f0933-107">Für Benutzer von Domänenadministratoren können Sie lync Server-Systemsteuerung nur zum Ausführen schreibgeschützter Suchvorgänge verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0933-107">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="f0933-108">Zum Ausführen von Schreibvorgängen für Benutzer von Domänenadministratoren (zum Beispiel aktivieren oder deaktivieren für lync Server-Systemsteuerung, Ändern von Pool-oder Richtlinienzuweisungen, Telefonieeinstellungen, SIP-Adresse) müssen Sie Windows PowerShell-Cmdlets verwenden, während Sie als Domänenadministrator Benutzer angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="f0933-108">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="f0933-109">Ausführliche Informationen zur Verwendung von Windows PowerShell-Cmdlets zum Verwalten von Benutzern finden Sie unter <A href="lync-server-2013-lync-server-management-shell.md">lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="f0933-109">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="f0933-110">Wenn Sie eine lync Server 2013 administrative Aufgabe ausführen, die die Suche nach einem Benutzer oder das Filtern von Benutzersuchergebnissen umfasst, gibt es einige Benutzereigenschaften, die als Attribute in Active Directory-Domänendienste vorhanden sind, aber erst nach der Bereitstellung von Exchange Server in den globalen Katalog repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="f0933-110">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="f0933-111">Microsoft Exchange, nicht lync Server, markiert bei der Installation die folgenden Attribute für die Replikation in den globalen Katalog:</span><span class="sxs-lookup"><span data-stu-id="f0933-111">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0933-112">Benutzerinformationen</span><span class="sxs-lookup"><span data-stu-id="f0933-112">User Information</span></span></th>
<th><span data-ttu-id="f0933-113">Adresse und Telefon</span><span class="sxs-lookup"><span data-stu-id="f0933-113">Address and Phone</span></span></th>
<th><span data-ttu-id="f0933-114">Organization (Organisation)</span><span class="sxs-lookup"><span data-stu-id="f0933-114">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0933-115">Initialen</span><span class="sxs-lookup"><span data-stu-id="f0933-115">Initials</span></span></p></td>
<td><p><span data-ttu-id="f0933-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="f0933-116">Street address</span></span></p>
<p><span data-ttu-id="f0933-117">Land/Region</span><span class="sxs-lookup"><span data-stu-id="f0933-117">Country/region</span></span></p>
<p><span data-ttu-id="f0933-118">Pager</span><span class="sxs-lookup"><span data-stu-id="f0933-118">Pager</span></span></p>
<p><span data-ttu-id="f0933-119">Fax</span><span class="sxs-lookup"><span data-stu-id="f0933-119">Fax</span></span></p>
<p><span data-ttu-id="f0933-120">Mobile</span><span class="sxs-lookup"><span data-stu-id="f0933-120">Mobile</span></span></p></td>
<td><p><span data-ttu-id="f0933-121">Titel</span><span class="sxs-lookup"><span data-stu-id="f0933-121">Title</span></span></p>
<p><span data-ttu-id="f0933-122">Company</span><span class="sxs-lookup"><span data-stu-id="f0933-122">Company</span></span></p>
<p><span data-ttu-id="f0933-123">Abteilung</span><span class="sxs-lookup"><span data-stu-id="f0933-123">Department</span></span></p>
<p><span data-ttu-id="f0933-124">Büro</span><span class="sxs-lookup"><span data-stu-id="f0933-124">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="f0933-125">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f0933-125">In This Section</span></span>

  - [<span data-ttu-id="f0933-126">Anzeigen von Informationen zu Benutzerkonten, die für lync Server 2013 aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="f0933-126">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="f0933-127">Aktivieren und Deaktivieren von Benutzern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0933-127">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="f0933-128">Verwalten von Enterprise-VoIP für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0933-128">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="f0933-129">Ändern von Benutzerkontoeigenschaften in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0933-129">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="f0933-130">Verwalten von Richtlinien für den externen Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0933-130">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="f0933-131">Zuweisen von Richtlinien pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0933-131">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0933-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0933-132">See Also</span></span>


[<span data-ttu-id="f0933-133">Cmdlets für die Benutzerverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0933-133">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="f0933-134">Verwalten von Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0933-134">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

