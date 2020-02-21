---
title: 'Lync Server 2013: Aktivieren der gruppenanrufannahme für Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5842a22d1899398b282e7305e4dd921fea86ea39
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Verwenden Sie das SEFAUtil Resource Kit-Tool, um die gruppenanrufannahme für Benutzer zu aktivieren. Benutzern muss eine Gruppennummer mit dem Typ GroupPickup in der Orbit-Tabelle für das Parken von Anrufen zugewiesen sein, damit die gruppenanrufannahme aktiviert ist. Sie weisen eine Gruppennummer für die Anrufannahme zu und aktivieren die gruppenanrufannahme gleichzeitig mithilfe des Parameters/enablegrouppickup, wenn Sie SEFAUtil. exe ausführen.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>So aktivieren Sie die gruppenanrufannahme für einen Benutzer

1.  Melden Sie sich an dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.

2.  Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Deaktivieren der gruppenanrufannahme für Benutzer in lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

