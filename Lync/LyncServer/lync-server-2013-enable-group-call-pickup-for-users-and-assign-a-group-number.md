---
title: 'Lync Server 2013: Aktivieren der Gruppenanruf Abholung für Benutzer und Zuweisen einer Gruppennummer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9523a76eb9cd23dd4c8ee531520341aaf82f508
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Nachdem Sie die Nummern für die Anruf Abholung in die Umlaufbahn Tabelle des Anruf Parks hinzugefügt haben, weisen Sie den Benutzern die Gruppennummern zu, und aktivieren Sie die Gruppenanruf Abholung. Verwenden Sie das Resource Kit-Tool für die sekundäre Erweiterungsfeature-Aktivierung (SEFAUtil), um Gruppennummern zuzuweisen und Gruppenanruf-Pickups zu aktivieren.

<div>


> [!NOTE]  
> Weisen Sie in einer hybridbereitstellung Benutzern, die Online sind, keine Gruppenanruf-Abhol Gruppe zu. Benutzer, die Online sind, können nicht an der Gruppenanruf Abholung teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>So weisen Sie eine Gruppennummer zu und aktivieren die Gruppenanruf Abholung für einen Benutzer

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

