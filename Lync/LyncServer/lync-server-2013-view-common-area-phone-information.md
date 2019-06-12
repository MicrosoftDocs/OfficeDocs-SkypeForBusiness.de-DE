---
title: 'Lync Server 2013: Anzeigen von Informationen zum allgemeinen Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900beb4f96fd71e0e6a4ded40d776f1e7d356529
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Anzeigen von allgemeinen Telefon Informationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Mithilfe des Cmdlets " **Get-CsCommonAreaPhone** " können Sie Informationen zu den für die Verwendung in Ihrer Organisation konfigurierten Telefonen im öffentlichen Bereich anzeigen. Dieses Cmdlet, das ohne Parameter verwendet wird, gibt Informationen zu allen Telefonen des öffentlichen Bereichs zurück. Optionale Parameter bieten verschiedene Möglichkeiten zum Filtern von Informationen. So können Sie beispielsweise alle Telefone im öffentlichen Bereich zurückgeben, die Kontaktobjekte in einer bestimmten Organisationseinheit (Organizational Unit, OU) haben, oder alle Kontaktobjekte, die sich in einem bestimmten Gebäude befinden. Ausführliche Informationen zu den **Get-CsCommonAreaPhone** -Parametern finden Sie unter [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).

Führen **Sie Get-CsCommonAreaPhone** entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>Anzeigen von Informationen zu allen Telefonen im öffentlichen Bereich

  - Wenn Sie Informationen zu allen Telefonen im öffentlichen Bereich anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsCommonAreaPhone
    
    Sie erhalten ähnliche Informationen:
    
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

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

