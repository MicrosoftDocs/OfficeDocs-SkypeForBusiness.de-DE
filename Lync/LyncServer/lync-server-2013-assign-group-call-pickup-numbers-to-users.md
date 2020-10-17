---
title: 'Lync Server 2013: Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3de74542edc65de68ab5f803934aa671575cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499482"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Nachdem Sie Gruppennummern für die Anrufannahme Gruppe zur Parken-Umlaufbahn-Tabelle hinzugefügt haben, können Sie die Gruppen Benutzern zuweisen. Verwenden Sie das Resource Kit-Tool für die sekundäre Erweiterung Feature Activation (SEFAUtil), um Benutzern Anrufannahme Gruppen zuzuweisen.

<div>


> [!NOTE]  
> Weisen Sie in einer hybridbereitstellung keine Gruppenanruf-pickupgruppe den Benutzern zu, die Online verwaltet werden. Benutzer, die Online verwaltet werden, können nicht an der gruppenanrufannahme teilnehmen. Das bedeutet, dass Ihre Anrufe nicht von anderen Benutzern beantwortet werden können und Anrufe an andere Benutzer nicht beantwortet werden können.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>So weisen Sie einem Benutzer eine Gruppenanruf-Abhol Gruppe zu

1.  Melden Sie sich an dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.

2.  Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Deaktivieren der gruppenanrufannahme für Benutzer in lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

