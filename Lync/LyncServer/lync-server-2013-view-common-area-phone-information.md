---
title: 'Lync Server 2013: Anzeigen von Telefon Informationen für allgemeine Bereiche'
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
ms.openlocfilehash: 5b3fbf748569e12e0801f727ecfc0ad6372f4af2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Anzeigen von Informationen zu Telefonen in öffentlichen Bereichen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Mithilfe des Cmdlets **Get-CsCommonAreaPhone** können Sie Informationen zu den Telefonen für öffentliche Bereiche anzeigen, die für die Verwendung in Ihrer Organisation konfiguriert sind. Dieses Cmdlet wird ohne Parameter verwendet und gibt Informationen zu allen Telefonen in öffentlichen Bereichen zurück. Optionale Parameter bieten unterschiedliche Möglichkeiten zum Filtern von Informationen. Sie können beispielsweise alle Telefone für gemeinsame Bereiche, die Kontaktobjekte enthalten, in einer bestimmten Organisationseinheit oder in allen Contacts-Objekten zurückgeben, die sich in einem bestimmten Gebäude befinden. Ausführliche Informationen zu den **Get-CsCommonAreaPhone** -Parametern finden Sie unter [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).

Führen **Sie Get-CsCommonAreaPhone** entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell aus.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>Anzeigen von Informationen zu allen Telefonen in öffentlichen Bereichen

  - Wenn Sie Informationen zu allen Telefonen in öffentlichen Bereichen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsCommonAreaPhone
    
    Sie erhalten ähnliche Informationen wie die folgenden:
    
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

