---
title: 'Lync Server 2013: Anzeigen von Telefon Informationen für allgemeine Bereiche'
description: 'Lync Server 2013: anzeigen allgemeiner Bereichs Telefon Informationen.'
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
ms.openlocfilehash: e4debe9a76118ac0bf1ca711426ce5487009a053
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572471"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="a5c3a-103">Anzeigen von Informationen zu Telefonen in öffentlichen Bereichen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5c3a-103">View common area phone information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5c3a-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a5c3a-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a5c3a-105">Mithilfe des Cmdlets **Get-CsCommonAreaPhone** können Sie Informationen zu den Telefonen für öffentliche Bereiche anzeigen, die für die Verwendung in Ihrer Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-105">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="a5c3a-106">Dieses Cmdlet wird ohne Parameter verwendet und gibt Informationen zu allen Telefonen in öffentlichen Bereichen zurück.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-106">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="a5c3a-107">Optionale Parameter bieten unterschiedliche Möglichkeiten zum Filtern von Informationen.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-107">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="a5c3a-108">Sie können beispielsweise alle Telefone für gemeinsame Bereiche, die Kontaktobjekte enthalten, in einer bestimmten Organisationseinheit oder in allen Contacts-Objekten zurückgeben, die sich in einem bestimmten Gebäude befinden.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-108">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="a5c3a-109">Ausführliche Informationen zu den **Get-CsCommonAreaPhone** -Parametern finden Sie unter [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="a5c3a-109">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="a5c3a-110">Führen **Sie Get-CsCommonAreaPhone** entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-110">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="a5c3a-111">Anzeigen von Informationen zu allen Telefonen in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="a5c3a-111">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="a5c3a-112">Wenn Sie Informationen zu allen Telefonen in öffentlichen Bereichen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a5c3a-112">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="a5c3a-113">Sie erhalten ähnliche Informationen wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="a5c3a-113">You’ll get information similar to this:</span></span>
    
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

<span data-ttu-id="a5c3a-114">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="a5c3a-114">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

