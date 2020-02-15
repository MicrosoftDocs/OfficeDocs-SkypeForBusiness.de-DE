---
title: 'Lync Server 2013: Konfigurieren von VoIP-Routen für ausgehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5c74a11adfb3785196352f3c03772028e73ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Eine lync Server 2013 VoIP-Route ordnet Zielrufnummern ein oder mehrere PSTN-Gateways (Public Switched Telephone Network) oder SIP-Trunks sowie mindestens einen PSTN-Verwendungsdaten Satz zu.

**So zeigen Sie VoIP-Routen mithilfe von lync Server-Systemsteuerung an**

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie auf **VoIP-Routing**.

3.  Klicken Sie auf **Route**.

4.  Doppelklicken Sie auf eine VoIP-Route, um zusätzliche Eigenschaften aus der Liste der VoIP-Routen anzuzeigen, oder wählen Sie die Route aus, und klicken Sie auf **Bearbeiten**. Klicken Sie dann auf **Details anzeigen**.
    
    <div>
    

    > [!NOTE]  
    > Sie können nur jeweils für eine einzelne Route Detailinformationen anzeigen.

    
    </div>

**So zeigen Sie VoIP-Routen mithilfe von Windows PowerShell an**

  - Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**. VoIP-Routen können mit Windows PowerShell und dem Cmdlet **Get-CsVoiceRoute** angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.
    
    Wenn Sie Informationen zu allen VoIP-Routen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsVoiceRoute
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> Ausführliche Informationen finden Sie unter <A href="lync-server-2013-voice-routes.md">VoIP-Routen in lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten des VoIP-Routings in lync Server 2013](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

