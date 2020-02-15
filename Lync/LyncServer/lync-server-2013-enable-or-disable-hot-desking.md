---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Hot deskings'
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
ms.openlocfilehash: 42da4f35c78e182ac988b1185bf797e3cb88ddd5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="016dd-102">Aktivieren oder Deaktivieren des Hot deskings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="016dd-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="016dd-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="016dd-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="016dd-104">Sie können Telefone für gemeinsame Bereiche als Telefon *Apparate*einrichten.</span><span class="sxs-lookup"><span data-stu-id="016dd-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="016dd-105">Bei Hot-Desk-Telefonen können sich Benutzer bei Ihrem eigenen Benutzerkonto anmelden und nach der Anmeldung lync Server Funktionen und ihre eigenen Benutzerprofileinstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="016dd-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="016dd-106">Das Hot Desking wird mithilfe von Clientrichtlinien verwaltet: zum Aktivieren oder Deaktivieren des Hot deskings müssen Sie die Clientrichtlinien ändern, die von ihren Telefonen in öffentlichen Bereichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="016dd-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="016dd-107">Ausführliche Informationen zum Bestimmen der Konferenzrichtlinien, die ihren Telefonen für gemeinsame Bereiche zugewiesen wurden, finden Sie unter [Anzeigen von Telefon Informationen zu öffentlichen Bereichen in lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="016dd-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="016dd-108">Verwenden Sie den EnableHotdesking-Parameter des **New-CSClientPolicy-** Cmdlets oder das Cmdlet " **setCSClientPolicy** ", um das Hot Desking auf einem Telefon wie folgt zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="016dd-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="016dd-109">Führen Sie diese Cmdlets entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="016dd-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="016dd-110">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="016dd-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="016dd-111">Aktivieren von Hot Desking</span><span class="sxs-lookup"><span data-stu-id="016dd-111">Enabling hot desking</span></span>

  - <span data-ttu-id="016dd-112">Um das Hot Desking für ein Telefon im öffentlichen Bereich zu aktivieren, müssen Sie die Clientrichtlinie ändern, die diesem Telefon (oder einer Sammlung von Telefonen) zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="016dd-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="016dd-113">Nachdem Sie die Richtlinie identifiziert haben, die geändert werden muss, müssen Sie im nächsten Schritt das Cmdlet "CsClientPolicy" verwenden, um den EnableHotdesking **-** Parameter auf "true" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="016dd-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="016dd-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="016dd-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="016dd-115">Alternativ können Sie das Cmdlet **New-CsClientPolicy** verwenden, um eine neue Clientrichtlinie zu erstellen, die das Hot Desking ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="016dd-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="016dd-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="016dd-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="016dd-117">Nachdem diese Richtlinie erstellt wurde, müssen Sie Sie den entsprechenden Telefonen im öffentlichen Bereich zuweisen.</span><span class="sxs-lookup"><span data-stu-id="016dd-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="016dd-118">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich</A>.</span><span class="sxs-lookup"><span data-stu-id="016dd-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="016dd-119">Deaktivieren von Hot Desking</span><span class="sxs-lookup"><span data-stu-id="016dd-119">Disabling hot desking</span></span>

  - <span data-ttu-id="016dd-120">Wenn Sie das Hot Desking für ein Telefon in einem öffentlichen Bereich deaktivieren möchten, setzen Sie den Parameter EnableHotdesking des Cmdlets **setCsClientPolicy** auf den Standardwert false zurück.</span><span class="sxs-lookup"><span data-stu-id="016dd-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="016dd-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="016dd-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="016dd-122">Ausführliche Informationen finden Sie in den Hilfethemen für das [New-CsClientPolicy-](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet und das Cmdlet "Set [-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) ".</span><span class="sxs-lookup"><span data-stu-id="016dd-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

