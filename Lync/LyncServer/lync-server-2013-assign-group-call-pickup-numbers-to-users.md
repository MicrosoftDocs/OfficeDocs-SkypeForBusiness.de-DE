---
title: 'Lync Server 2013: Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b437b9da1abaa62d34a177c0188396c30bf7a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="c9c75-102">Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c75-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c75-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="c9c75-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="c9c75-104">Nachdem Sie Gruppennummern für die Anrufannahme Gruppe zur Parken-Umlaufbahn-Tabelle hinzugefügt haben, können Sie die Gruppen Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9c75-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="c9c75-105">Verwenden Sie das Resource Kit-Tool für die sekundäre Erweiterung Feature Activation (SEFAUtil), um Benutzern Anrufannahme Gruppen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9c75-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9c75-106">Weisen Sie in einer hybridbereitstellung keine Gruppenanruf-pickupgruppe den Benutzern zu, die Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c9c75-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="c9c75-107">Benutzer, die Online verwaltet werden, können nicht an der gruppenanrufannahme teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="c9c75-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="c9c75-108">Das bedeutet, dass Ihre Anrufe nicht von anderen Benutzern beantwortet werden können und Anrufe an andere Benutzer nicht beantwortet werden können.</span><span class="sxs-lookup"><span data-stu-id="c9c75-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="c9c75-109">So weisen Sie einem Benutzer eine Gruppenanruf-Abhol Gruppe zu</span><span class="sxs-lookup"><span data-stu-id="c9c75-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="c9c75-110">Melden Sie sich an dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c9c75-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="c9c75-111">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c9c75-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="c9c75-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9c75-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9c75-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9c75-113">See Also</span></span>


[<span data-ttu-id="c9c75-114">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c75-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="c9c75-115">Deaktivieren der gruppenanrufannahme für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c75-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

