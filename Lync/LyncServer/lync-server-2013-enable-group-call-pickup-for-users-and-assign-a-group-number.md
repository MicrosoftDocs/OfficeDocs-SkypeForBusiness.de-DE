---
title: 'Lync Server 2013: Aktivieren der gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer'
description: 'Lync Server 2013: Aktivieren der gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03fcb20bfd88842dc8b29100b9ece595bf76254
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559641"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="c1ac0-103">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</span><span class="sxs-lookup"><span data-stu-id="c1ac0-103">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1ac0-104">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="c1ac0-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="c1ac0-105">Nachdem Sie die Rufnummern für die Anrufannahme Gruppe der Tabelle "Parken im Orbit" hinzugefügt haben, weisen Sie die Gruppennummern den Benutzern zu und aktivieren die gruppenanrufannahme für diese.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-105">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="c1ac0-106">Verwenden Sie das Resource Kit-Tool für die sekundäre Erweiterung Feature Activation (SEFAUtil), um Gruppennummern zuzuweisen und gruppenanrufannahme zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-106">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1ac0-107">Weisen Sie in einer hybridbereitstellung keine Gruppenanruf-pickupgruppe den Benutzern zu, die Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="c1ac0-108">Benutzer, die Online verwaltet werden, können nicht an der gruppenanrufannahme teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="c1ac0-109">Das bedeutet, dass Ihre Anrufe nicht von anderen Benutzern beantwortet werden können und Anrufe an andere Benutzer nicht beantwortet werden können.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="c1ac0-110">So weisen Sie eine Gruppennummer zu und aktivieren die gruppenanrufannahme für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="c1ac0-110">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="c1ac0-111">Melden Sie sich an dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="c1ac0-112">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c1ac0-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="c1ac0-113">Beispielsweise, um einem Benutzer die Gruppennummer 199 zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="c1ac0-113">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1ac0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1ac0-114">See Also</span></span>


[<span data-ttu-id="c1ac0-115">Deaktivieren der gruppenanrufannahme für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1ac0-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

