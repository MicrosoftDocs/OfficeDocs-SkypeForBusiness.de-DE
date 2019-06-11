---
title: 'Lync Server 2013: Aktivieren der Gruppenanruf Abholung für Benutzer und Zuweisen einer Gruppennummer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9523a76eb9cd23dd4c8ee531520341aaf82f508
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="28e08-102">Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</span><span class="sxs-lookup"><span data-stu-id="28e08-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28e08-103">_**Letztes Änderungsdatum des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="28e08-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="28e08-104">Nachdem Sie die Nummern für die Anruf Abholung in die Umlaufbahn Tabelle des Anruf Parks hinzugefügt haben, weisen Sie den Benutzern die Gruppennummern zu, und aktivieren Sie die Gruppenanruf Abholung.</span><span class="sxs-lookup"><span data-stu-id="28e08-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="28e08-105">Verwenden Sie das Resource Kit-Tool für die sekundäre Erweiterungsfeature-Aktivierung (SEFAUtil), um Gruppennummern zuzuweisen und Gruppenanruf-Pickups zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="28e08-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28e08-106">Weisen Sie in einer hybridbereitstellung Benutzern, die Online sind, keine Gruppenanruf-Abhol Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="28e08-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="28e08-107">Benutzer, die Online sind, können nicht an der Gruppenanruf Abholung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="28e08-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="28e08-108">Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.</span><span class="sxs-lookup"><span data-stu-id="28e08-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="28e08-109">So weisen Sie eine Gruppennummer zu und aktivieren die Gruppenanruf Abholung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="28e08-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="28e08-110">Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.</span><span class="sxs-lookup"><span data-stu-id="28e08-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="28e08-111">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="28e08-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="28e08-112">Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:</span><span class="sxs-lookup"><span data-stu-id="28e08-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28e08-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28e08-113">See Also</span></span>


[<span data-ttu-id="28e08-114">Deaktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28e08-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

