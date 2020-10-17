---
title: 'Lync Server 2013: Hinzufügen eines Administrators für beständigen Chat'
description: 'Lync Server 2013: Hinzufügen eines Administrators für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a Persistent Chat administrator
ms:assetid: c107eb20-4e58-4463-b4f9-63fb5b1d9534
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205230(v=OCS.15)
ms:contentKeyID: 48185300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d98ef6420ce976cd983b287a0f7c63b514d083d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572401"
---
# <a name="adding-a-persistent-chat-administrator-in-lync-server-2013"></a><span data-ttu-id="e250f-103">Hinzufügen eines Administrators für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e250f-103">Adding a Persistent Chat administrator in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e250f-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e250f-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e250f-105">In lync Server 2013 müssen Benutzer, die bestimmte Aufgaben ausführen, als Mitglieder einer oder mehrerer bestimmter Gruppen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e250f-105">In Lync Server 2013, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="e250f-106">Die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) kann auch verwendet werden, um Berechtigungen zu gewähren, indem Benutzer vordefinierten lync Server 2013 Administratorrollen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e250f-106">Role-based access control (RBAC) can also be used to grant privileges by assigning users to predefined Lync Server 2013 administrative roles.</span></span>

<span data-ttu-id="e250f-107">Bevor Sie den Server für beständigen Chat Konfigurieren und verwalten, müssen Sie sicherstellen, dass die entsprechenden Benutzerrechte und-Berechtigungen vorhanden sind und dass alle Benutzer, die als Administratoren für beständigen Chat klassifiziert werden sollen, der "cspersistentchatadministrator"-Sicherheitsgruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e250f-107">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users to be classified as Persistent Chat administrators are added to the CsPersistentChatAdministrator security group.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

