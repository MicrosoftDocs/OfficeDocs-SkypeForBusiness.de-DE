---
title: 'Lync Server 2013: Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e919b1fb4ee225eba1c5317ff1f3049791075bcc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Nachdem Sie Gruppennummern für Gruppenanruf-Pickups zur Umlauf Tabelle des Anruf Parks hinzugefügt haben, können Sie die Gruppen den Benutzern zuweisen. Verwenden Sie das Resource Kit-Tool für die sekundäre Erweiterungsfeature-Aktivierung (SEFAUtil), um Benutzern Anruf Abhol Gruppen zuzuweisen.

<div>


> [!NOTE]  
> Weisen Sie in einer hybridbereitstellung Benutzern, die Online sind, keine Gruppenanruf-Abhol Gruppe zu. Benutzer, die Online sind, können nicht an der Gruppenanruf Abholung teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>So weisen Sie einem Benutzer eine Gruppenanruf-Abhol Gruppe zu

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Deaktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

