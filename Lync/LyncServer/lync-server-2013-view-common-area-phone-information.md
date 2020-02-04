---
title: 'Lync Server 2013: Anzeigen von Informationen zum allgemeinen Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38614b2993ddd9ad3fe3a662a334440a1d1287b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="91831-102">Anzeigen von allgemeinen Telefon Informationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91831-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91831-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="91831-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="91831-104">Mithilfe des Cmdlets " **Get-CsCommonAreaPhone** " können Sie Informationen zu den für die Verwendung in Ihrer Organisation konfigurierten Telefonen im öffentlichen Bereich anzeigen.</span><span class="sxs-lookup"><span data-stu-id="91831-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="91831-105">Dieses Cmdlet, das ohne Parameter verwendet wird, gibt Informationen zu allen Telefonen des öffentlichen Bereichs zurück.</span><span class="sxs-lookup"><span data-stu-id="91831-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="91831-106">Optionale Parameter bieten verschiedene Möglichkeiten zum Filtern von Informationen.</span><span class="sxs-lookup"><span data-stu-id="91831-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="91831-107">So können Sie beispielsweise alle Telefone im öffentlichen Bereich zurückgeben, die Kontaktobjekte in einer bestimmten Organisationseinheit (Organizational Unit, OU) haben, oder alle Kontaktobjekte, die sich in einem bestimmten Gebäude befinden.</span><span class="sxs-lookup"><span data-stu-id="91831-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="91831-108">Ausführliche Informationen zu den **Get-CsCommonAreaPhone** -Parametern finden Sie unter [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="91831-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="91831-109">Führen **Sie Get-CsCommonAreaPhone** entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="91831-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="91831-110">Anzeigen von Informationen zu allen Telefonen im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="91831-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="91831-111">Wenn Sie Informationen zu allen Telefonen im öffentlichen Bereich anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="91831-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="91831-112">Sie erhalten ähnliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="91831-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="91831-113">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="91831-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

