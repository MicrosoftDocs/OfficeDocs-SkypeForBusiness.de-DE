---
title: 'Lync Server 2013: Migrieren von Benutzern zu einem einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09897effe252f49eda73fea567d9b54bdc8ad52a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Migrieren von Benutzern zu einem einheitlichen Kontaktspeicher in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-15_

Die Kontakte eines Benutzers werden in den folgenden Fällen automatisch zum Exchange 2013-Server migriert:

  - Dem Benutzer muss eine Benutzerdiensterichtlinie zugewiesen worden sein, für die die Option "UcsAllowed" auf "True" gesetzt ist.

  - Wurde mit einem Exchange 2013 Postfachs und mindestens einmal im Postfach angemeldet.

  - Meldet sich mit einem lync 2013 Rich-Client an.

Wenn sich der Benutzer mit einem lync 2010 oder einem früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013 Server verbunden ist, wird die Benutzer Dienste-Richtlinie ignoriert, und die Kontakte des Benutzers bleiben in lync Server.

Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden:

  - Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:
    
    HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync\\\<SIP URL\>\\UCS
    
    Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel den Wert InUCSMode mit dem Wert 2165.

  - Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus. Geben Sie an der lync Server-Verwaltungsshell Befehlszeile Folgendes ein:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Ist **Test-CsUnifiedContactStore** erfolgreich, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.

</div>

<span> </span>

</div>

</div>

</div>

