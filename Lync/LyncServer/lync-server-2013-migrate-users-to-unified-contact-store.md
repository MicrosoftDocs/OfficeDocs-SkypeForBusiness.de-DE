---
title: 'Lync Server 2013: Migrieren von Benutzern zu einem einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ab00e89c41b075e47d7764ce1c9c4cd3c471b8c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513632"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="a19c6-102">Migrieren von Benutzern zu einem einheitlichen Kontaktspeicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a19c6-102">Migrate users to unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a19c6-103">_**Letztes Änderungsstand des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a19c6-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a19c6-104">Die Kontakte eines Benutzers werden in den folgenden Fällen automatisch zum Exchange 2013-Server migriert:</span><span class="sxs-lookup"><span data-stu-id="a19c6-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="a19c6-105">Dem Benutzer muss eine Benutzerdiensterichtlinie zugewiesen worden sein, für die die Option "UcsAllowed" auf "True" gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a19c6-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="a19c6-106">Wurde mit einem Exchange 2013 Postfachs und mindestens einmal im Postfach angemeldet.</span><span class="sxs-lookup"><span data-stu-id="a19c6-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="a19c6-107">Meldet sich mit einem lync 2013 Rich-Client an.</span><span class="sxs-lookup"><span data-stu-id="a19c6-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="a19c6-108">Wenn sich der Benutzer mit einem lync 2010 oder einem früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013 Server verbunden ist, wird die Benutzer Dienste-Richtlinie ignoriert, und die Kontakte des Benutzers bleiben in lync Server.</span><span class="sxs-lookup"><span data-stu-id="a19c6-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="a19c6-109">Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden:</span><span class="sxs-lookup"><span data-stu-id="a19c6-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="a19c6-110">Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:</span><span class="sxs-lookup"><span data-stu-id="a19c6-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="a19c6-111">HKEY \_ aktuelle \_ Benutzer \\ Software \\ Microsoft \\ Office \\ 15,0 \\ lync \\ \<SIP URL\> \\ UCS</span><span class="sxs-lookup"><span data-stu-id="a19c6-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="a19c6-112">Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel den Wert InUCSMode mit dem Wert 2165.</span><span class="sxs-lookup"><span data-stu-id="a19c6-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="a19c6-113">Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus.</span><span class="sxs-lookup"><span data-stu-id="a19c6-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="a19c6-114">Geben Sie an der lync Server-Verwaltungsshell Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a19c6-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="a19c6-115">Ist **Test-CsUnifiedContactStore** erfolgreich, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.</span><span class="sxs-lookup"><span data-stu-id="a19c6-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

