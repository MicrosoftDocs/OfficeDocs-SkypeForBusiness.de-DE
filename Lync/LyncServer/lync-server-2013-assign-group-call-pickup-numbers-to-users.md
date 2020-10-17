---
title: 'Lync Server 2013: Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern'
description: 'Lync Server 2013: Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern.'
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
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566131"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="66f07-103">Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f07-103">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66f07-104">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="66f07-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="66f07-105">Nachdem Sie Gruppennummern für die Anrufannahme Gruppe zur Parken-Umlaufbahn-Tabelle hinzugefügt haben, können Sie die Gruppen Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="66f07-105">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="66f07-106">Verwenden Sie das Resource Kit-Tool für die sekundäre Erweiterung Feature Activation (SEFAUtil), um Benutzern Anrufannahme Gruppen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="66f07-106">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66f07-107">Weisen Sie in einer hybridbereitstellung keine Gruppenanruf-pickupgruppe den Benutzern zu, die Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="66f07-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="66f07-108">Benutzer, die Online verwaltet werden, können nicht an der gruppenanrufannahme teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="66f07-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="66f07-109">Das bedeutet, dass Ihre Anrufe nicht von anderen Benutzern beantwortet werden können und Anrufe an andere Benutzer nicht beantwortet werden können.</span><span class="sxs-lookup"><span data-stu-id="66f07-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="66f07-110">So weisen Sie einem Benutzer eine Gruppenanruf-Abhol Gruppe zu</span><span class="sxs-lookup"><span data-stu-id="66f07-110">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="66f07-111">Melden Sie sich an dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.</span><span class="sxs-lookup"><span data-stu-id="66f07-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="66f07-112">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="66f07-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="66f07-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="66f07-113">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66f07-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66f07-114">See Also</span></span>


[<span data-ttu-id="66f07-115">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f07-115">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="66f07-116">Deaktivieren der gruppenanrufannahme für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f07-116">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

