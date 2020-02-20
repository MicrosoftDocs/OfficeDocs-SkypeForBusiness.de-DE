---
title: 'Lync Server 2013: Deaktivieren der gruppenanrufannahme für Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3e015fd7fc3be36439fb240e2f3f50ed7bc8ec1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Deaktivieren der gruppenanrufannahme für Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Verwenden Sie das folgende Verfahren, um die gruppenanrufannahme für einen Benutzer zu deaktivieren.

<div>


> [!NOTE]  
> Wenn Sie die gruppenanrufannahme für einen Benutzer deaktivieren, wird die Nummer der Anrufannahme Gruppe, die dem Benutzer zugewiesen wurde, nicht beibehalten. Wenn Sie anschließend die gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie die Nummer für die Anrufannahme Gruppe mit dem Parameter/enablegrouppickup erneut zuweisen.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>So deaktivieren Sie die gruppenanrufannahme für einen Benutzer

1.  Melden Sie sich an dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.

2.  Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

