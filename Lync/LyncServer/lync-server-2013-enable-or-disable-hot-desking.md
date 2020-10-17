---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Hot deskings'
description: 'Lync Server 2013: Aktivieren oder deaktivieren Sie das Hot Desking.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd22c9bf51078324cfe5e215bd154503c2d9b57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552431"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="e56ac-103">Aktivieren oder Deaktivieren des Hot deskings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e56ac-103">Enable or disable hot desking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e56ac-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e56ac-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e56ac-105">Sie können Telefone für gemeinsame Bereiche als Telefon *Apparate*einrichten.</span><span class="sxs-lookup"><span data-stu-id="e56ac-105">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="e56ac-106">Bei Hot-Desk-Telefonen können sich Benutzer bei Ihrem eigenen Benutzerkonto anmelden und nach der Anmeldung lync Server Funktionen und ihre eigenen Benutzerprofileinstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e56ac-106">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="e56ac-107">Das Hot Desking wird mithilfe von Clientrichtlinien verwaltet: zum Aktivieren oder Deaktivieren des Hot deskings müssen Sie die Clientrichtlinien ändern, die von ihren Telefonen in öffentlichen Bereichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e56ac-107">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="e56ac-108">Ausführliche Informationen zum Bestimmen der Konferenzrichtlinien, die ihren Telefonen für gemeinsame Bereiche zugewiesen wurden, finden Sie unter [Anzeigen von Telefon Informationen zu öffentlichen Bereichen in lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="e56ac-108">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="e56ac-109">Verwenden Sie den EnableHotdesking-Parameter des **New-CSClientPolicy-** Cmdlets oder das Cmdlet " **setCSClientPolicy** ", um das Hot Desking auf einem Telefon wie folgt zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e56ac-109">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="e56ac-110">Führen Sie diese Cmdlets entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="e56ac-110">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e56ac-111">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="e56ac-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="e56ac-112">Aktivieren von Hot Desking</span><span class="sxs-lookup"><span data-stu-id="e56ac-112">Enabling hot desking</span></span>

  - <span data-ttu-id="e56ac-113">Um das Hot Desking für ein Telefon im öffentlichen Bereich zu aktivieren, müssen Sie die Clientrichtlinie ändern, die diesem Telefon (oder einer Sammlung von Telefonen) zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="e56ac-113">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="e56ac-114">Nachdem Sie die Richtlinie identifiziert haben, die geändert werden muss, müssen Sie im nächsten Schritt das Cmdlet "CsClientPolicy" verwenden, um den EnableHotdesking **-** Parameter auf "true" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e56ac-114">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="e56ac-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56ac-115">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="e56ac-116">Alternativ können Sie das Cmdlet **New-CsClientPolicy** verwenden, um eine neue Clientrichtlinie zu erstellen, die das Hot Desking ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e56ac-116">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="e56ac-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56ac-117">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e56ac-118">Nachdem diese Richtlinie erstellt wurde, müssen Sie Sie den entsprechenden Telefonen im öffentlichen Bereich zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e56ac-118">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="e56ac-119">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich</A>.</span><span class="sxs-lookup"><span data-stu-id="e56ac-119">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="e56ac-120">Deaktivieren von Hot Desking</span><span class="sxs-lookup"><span data-stu-id="e56ac-120">Disabling hot desking</span></span>

  - <span data-ttu-id="e56ac-121">Wenn Sie das Hot Desking für ein Telefon in einem öffentlichen Bereich deaktivieren möchten, setzen Sie den Parameter EnableHotdesking des Cmdlets **setCsClientPolicy** auf den Standardwert false zurück.</span><span class="sxs-lookup"><span data-stu-id="e56ac-121">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="e56ac-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56ac-122">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="e56ac-123">Ausführliche Informationen finden Sie in den Hilfethemen für das [New-CsClientPolicy-](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet und das Cmdlet "Set [-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) ".</span><span class="sxs-lookup"><span data-stu-id="e56ac-123">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

