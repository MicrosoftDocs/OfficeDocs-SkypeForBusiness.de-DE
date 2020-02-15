---
title: 'Lync Server 2013: Erstellen oder Ändern eines Kontaktobjekts eines Konferenz Geräts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bd3cfa6099d45cbad2d15ed164652756f50f5e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="921e8-102">Erstellen oder Ändern eines Kontaktobjekts für ein Konferenzgerät in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="921e8-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="921e8-103">_**Letztes Änderungsstand des Themas:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="921e8-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="921e8-104">Erstellen Sie zum Erstellen eines Konferenzraum Objekts zunächst ein Active Directory Benutzerkonto zum Darstellen des Geräts.</span><span class="sxs-lookup"><span data-stu-id="921e8-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="921e8-105">Verwenden Sie dann das Cmdlet **enable-csmeetingroom "** , um zu ermöglichen, dass dieses Konto als Konferenzgerät fungiert.</span><span class="sxs-lookup"><span data-stu-id="921e8-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="921e8-106">Wenn Sie die Eigenschaften eines vorhandenen Konferenz Geräts ändern müssen, verwenden Sie das Cmdlet " **Sets-csmeetingroom"** ".</span><span class="sxs-lookup"><span data-stu-id="921e8-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="921e8-107">Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="921e8-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="921e8-108">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="921e8-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="921e8-109">Erstellen eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="921e8-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="921e8-110">Nachdem Sie das Active Directory-Benutzerkonto erstellt haben, das das neue Konferenzgerät darstellt, aktivieren Sie es mithilfe des Cmdlets **enable-csmeetingroom "** .</span><span class="sxs-lookup"><span data-stu-id="921e8-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="921e8-111">Achten Sie darauf, eine) die Identität des Konferenz Geräts, b) den registrierungsstellenpool, in dem das Raum Konto verwaltet wird, und c) die SIP-Adresse, die diesem Konto zugewiesen werden soll, einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="921e8-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="921e8-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="921e8-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="921e8-113">Ändern eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="921e8-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="921e8-114">Verwenden Sie das Cmdlet " **csmeetingroom"** ", um die Eigenschaftswerte eines vorhandenen Konferenz Geräts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="921e8-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="921e8-115">Mit dem folgenden Befehl wird beispielsweise die Telefonnummer (LineUri) aktualisiert, die einem Konferenzgerät zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="921e8-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="921e8-116">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-csmeetingroom "](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und im Cmdlet [csmeetingroom"](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="921e8-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

