---
title: 'Lync Server 2013: Migrieren von Benutzern zum einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ec64192f1aa83eb9c076976c20a9e87ab9115
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="1562d-102">Migrieren von Benutzern zum einheitlichen Kontaktspeicher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1562d-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1562d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="1562d-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="1562d-104">Die Kontakte eines Benutzers werden automatisch auf den Exchange 2013-Server migriert, wenn der Benutzer:</span><span class="sxs-lookup"><span data-stu-id="1562d-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="1562d-105">Dem Benutzer muss eine Benutzerdienstrichtlinie zugewiesen worden sein, für die die Option „UcsAllowed“ auf „True“ gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="1562d-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="1562d-106">Wurde mit einem Exchange 2013-Postfach bereitgestellt und hat sich mindestens einmal beim Postfach angemeldet.</span><span class="sxs-lookup"><span data-stu-id="1562d-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="1562d-107">Meldet sich mit einem Rich-Client mit lync 2013 an.</span><span class="sxs-lookup"><span data-stu-id="1562d-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="1562d-108">Wenn sich der Benutzer mit einem lync 2010-oder früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, wird die Richtlinie für Benutzer Dienste ignoriert, und die Kontakte des Benutzers verbleiben in lync Server.</span><span class="sxs-lookup"><span data-stu-id="1562d-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="1562d-109">Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden:</span><span class="sxs-lookup"><span data-stu-id="1562d-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="1562d-110">Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:</span><span class="sxs-lookup"><span data-stu-id="1562d-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="1562d-111">HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync\\\<SIP-\>\\URL UCS</span><span class="sxs-lookup"><span data-stu-id="1562d-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="1562d-112">Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel den Wert InUCSMode mit dem Wert 2165.</span><span class="sxs-lookup"><span data-stu-id="1562d-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="1562d-113">Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus.</span><span class="sxs-lookup"><span data-stu-id="1562d-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="1562d-114">Geben Sie in der Befehlszeile der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1562d-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="1562d-115">Wenn**Test-CsUnifiedContactStore** erfolgreich ist, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.</span><span class="sxs-lookup"><span data-stu-id="1562d-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

