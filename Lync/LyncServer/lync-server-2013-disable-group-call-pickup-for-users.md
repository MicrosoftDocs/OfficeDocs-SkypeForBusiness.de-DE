---
title: 'Lync Server 2013: Deaktivieren der Gruppenanruf Abholung für Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="d32e3-102">Deaktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d32e3-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d32e3-103">_**Letztes Änderungsdatum des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d32e3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d32e3-104">Gehen Sie wie folgt vor, um die Gruppenanruf Abholung für einen Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d32e3-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d32e3-105">Wenn Sie die Gruppenanruf Abholung für einen Benutzer deaktivieren, wird die dem Benutzer zugewiesene Anrufgruppen Nummer nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d32e3-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="d32e3-106">Wenn Sie anschließend die Gruppenanruf Abholung für diesen Benutzer wieder aktivieren möchten, müssen Sie die Nummer für die Anruf-Abhol Gruppe mit dem/enablegrouppickup-Parameter erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d32e3-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="d32e3-107">So deaktivieren Sie die Gruppenanruf Abholung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d32e3-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="d32e3-108">Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.</span><span class="sxs-lookup"><span data-stu-id="d32e3-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="d32e3-109">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d32e3-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="d32e3-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d32e3-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d32e3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d32e3-111">See Also</span></span>


[<span data-ttu-id="d32e3-112">Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d32e3-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="d32e3-113">Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d32e3-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

