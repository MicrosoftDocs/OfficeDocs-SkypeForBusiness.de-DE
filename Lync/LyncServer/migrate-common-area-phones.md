---
title: Migireren von Telefonen für gemeinsame Bereiche
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af08e6de9b832289e898fd27003b896dd40fa81c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503572"
---
# <a name="migrate-common-area-phones"></a>Migireren von Telefonen für gemeinsame Bereiche

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Telefone in öffentlichen Bereichen sind IP-Telefone, die sich am häufigsten in einem gemeinsamen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, wie beispielsweise eine Lobby, eine Küche oder ein Factory Floor. Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden sein, um lync Server UC-Funktionalität bereitzustellen. Nachdem Sie eine lync Server 2010-Bereitstellung in lync Server 2013 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die dem Legacy-Telefon für gemeinsame Bereiche zugeordnet sind. Mit lync Server-Verwaltungsshell werden zunächst alle Contact-Objekte abgerufen, lync Server 2010 die mit den Telefonen für gemeinsame Bereiche verbunden sind, und diese Objekte dann in den lync Server 2013-Pool zu übertragen.

**Migrieren von Telefonen für gemeinsame Bereiche**

1.  Öffnen Sie auf dem lync Server 2013-Front-End-Server lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Um zu überprüfen, ob alle Kontaktobjekte in den lync Server 2013 Pool verschoben wurden, geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Überprüfen Sie, ob jetzt alle Contact-Objekte dem lync Server 2013-Pool zugeordnet sind.

</div>

<span> </span>

</div>

</div>

</div>

