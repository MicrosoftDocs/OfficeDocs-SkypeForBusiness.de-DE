---
title: 'Lync Server 2013: Konfigurieren einer SNMP-Anwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15a911abc614ff30c4130fb2a35886458fcb1dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Konfigurieren einer SNMP-Anwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Lync Server 2013 enthält eine standardmäßige Webdienstschnittstelle, mit der Sie den standortinformationsdienst mit SNMP-Anwendungen (Simple Network Management Protocol) verbinden können, die Mac-Adressen mit Port-und Switch-Informationen entsprechen.

Wenn eine SNMP-Anwendung installiert ist und der standortinformationsdienst keine Übereinstimmung in der Standortdatenbank findet, fragt der standortinformationsdienst die Anwendung automatisch mit der vom Client angegebenen MAC-Adresse ab. Der standortinformationsdienst verwendet dann die von der SNMP-Anwendung zurückgegebenen Port-und Switch-Informationen, um die Standortdatenbank erneut abzufragen.

Ausführliche Informationen finden Sie unter [Satz-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Mac-Adressen stehen auf Computern unter Windows 8 nicht zur Verfügung.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>So konfigurieren Sie die URL für die SNMP-Anwendung

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

