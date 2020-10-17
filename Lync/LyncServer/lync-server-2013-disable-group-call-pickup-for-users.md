---
title: 'Lync Server 2013: Deaktivieren der gruppenanrufannahme für Benutzer'
description: 'Lync Server 2013: Deaktivieren der gruppenanrufannahme für Benutzer.'
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
ms.openlocfilehash: b3f5b4542cf7bb8ea5be524d2695701979ec2987
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568191"
---
# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="2b02f-103">Deaktivieren der gruppenanrufannahme für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b02f-103">Disable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b02f-104">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="2b02f-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2b02f-105">Verwenden Sie das folgende Verfahren, um die gruppenanrufannahme für einen Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2b02f-105">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b02f-106">Wenn Sie die gruppenanrufannahme für einen Benutzer deaktivieren, wird die Nummer der Anrufannahme Gruppe, die dem Benutzer zugewiesen wurde, nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2b02f-106">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="2b02f-107">Wenn Sie anschließend die gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie die Nummer für die Anrufannahme Gruppe mit dem Parameter/enablegrouppickup erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2b02f-107">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="2b02f-108">So deaktivieren Sie die gruppenanrufannahme für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="2b02f-108">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="2b02f-109">Melden Sie sich an dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.</span><span class="sxs-lookup"><span data-stu-id="2b02f-109">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="2b02f-110">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2b02f-110">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="2b02f-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2b02f-111">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b02f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b02f-112">See Also</span></span>


[<span data-ttu-id="2b02f-113">Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b02f-113">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="2b02f-114">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b02f-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

