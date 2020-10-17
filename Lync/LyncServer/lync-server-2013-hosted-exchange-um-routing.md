---
title: 'Lync Server 2013: Hosted Exchange um Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31091da9a80dc03c798cbf674c1c46e0ea7b901c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533112"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Gehostetes Exchange um Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Die Exchange um Routing Anwendung wird im Front-End-Server für die Weiterleitung von Anrufen ausgeführt, entweder an eine lokale Exchange Server Unified Messaging (um)-Bereitstellung oder an einen gehosteten Exchange um Dienst.

<div>

## <a name="the-exum-routing-application"></a>Die ExUM-Routinganwendung

Die lync Server 2013 Exchange um Routing Anwendung verwendet Informationen aus Benutzerkontoeinstellungen und Richtlinienparametern für gehostete Voicemails, um zu bestimmen, wie Anrufe für gehostete Sprachnachrichten weitergeleitet werden, wie im folgenden Diagramm dargestellt.

**Beispiel für das Exchange UM-Routing in einer gemischten Bereitstellung**

![Lokale lync Server Exchange um-Bereitstellung](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")

Exchange um Routing kann so konfiguriert werden, dass Anrufe an Benutzer weitergeleitet werden, die für lokale Exchange um aktiviert sind, für Benutzer, die für gehostete Exchange um aktiviert sind, oder für eine Kombination aus beiden.

Nehmen wir beispielsweise an, dass das Postfach und der Exchange um Dienst von Roy in einer lokalen Exchange-Bereitstellung verwaltet werden.

  - Die Proxyadressinformationen aus dem Benutzerkonto von Roy bieten die Informationen, die die ExUM-Routing Anwendung zum Weiterleiten von Anrufen an einen lokalen Exchange um Server verwendet.

Alices Postfach und Exchange um Dienst befinden sich im Rechenzentrum eines gehosteten Exchange-Dienstanbieters. Das Routing für Ihre Exchange um Anrufe wird wie folgt konfiguriert:

  - Die im Attribut "msExchUCVoiceMailSettings" des Benutzerkontos von Alice festgelegten Werte weisen die ExUM-Routinganwendung an, eine gehostete Voicemailrichtlinie auf Routingdetails zu überprüfen.
    
    <div>
    

    > [!NOTE]  
    > Der Wert des "msexchucvoicemailsettings"-Attributs kann entweder vom Exchange-Dienstanbieter oder vom lync Server 2013 Administrator festgelegt werden. In dem im obigen Diagramm gezeigten Beispiel wurde der Wert (CsHostedVoiceMail = 1) vom lync Server 2013 Administrator festgelegt, um für Alice gehostete Voicemail zu aktivieren. Ausführliche Informationen zu diesem Attribut finden Sie unter <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange User Management in lync Server 2013</A>.

    
    </div>

  - Die dem Benutzerkonto von Alice zugewiesene gehostete Voicemailrichtlinie umfasst Routingdetails:
    
      - Destination ist der gehostete Exchange um Dienstanbieter (LS). ExUm. \<hostedExchangeServer\> . com in diesem Beispiel).
    
      - Organisationen werden durch die Mandanten-IDs identifiziert, die die Routing-FQDNs für SIP-Nachrichten für Exchange Server Mandanten sind, die sich auf LS befinden. ExUm. \<hostedExchangeServer\> . com (Corp.contoso.com und Corp.litwareinc.com in diesem Beispiel).
        
        <div>
        

        > [!NOTE]  
        > Der FQDN (Fully Qualified Domain Name, vollqualifizierter Domänenname) für Exchange Online lautet exap.um.outlook.com.

        
        </div>
        
        Ausführliche Informationen finden Sie unter [Hosted Voice Mail Policies in lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Wenn sowohl das Attribut "msExchUCVoiceMailSettings" als auch die UM-Proxyadresseinstellungen in einem Benutzerkonto vorhanden sind, hat das Attribut "msExchUCVoiceMailSettings" Vorrang.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

