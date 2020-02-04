---
title: 'Lync Server 2013: Deaktivieren der Gruppenanruf Abholung für Benutzer'
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
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Deaktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Gehen Sie wie folgt vor, um die Gruppenanruf Abholung für einen Benutzer zu deaktivieren.

<div>


> [!NOTE]  
> Wenn Sie die Gruppenanruf Abholung für einen Benutzer deaktivieren, wird die dem Benutzer zugewiesene Anrufgruppen Nummer nicht gespeichert. Wenn Sie anschließend die Gruppenanruf Abholung für diesen Benutzer wieder aktivieren möchten, müssen Sie die Nummer für die Anruf-Abhol Gruppe mit dem/enablegrouppickup-Parameter erneut zuweisen.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>So deaktivieren Sie die Gruppenanruf Abholung für einen Benutzer

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

