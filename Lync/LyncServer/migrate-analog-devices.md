---
title: Migrieren analoger Geräte
description: Migrieren von analogen Geräten.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579401"
---
# <a name="migrate-analog-devices"></a>Migrieren analoger Geräte

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-16_

Lync Server bietet Unterstützung für analoge Geräte. Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in ihrer lync Server Umgebung unterstützt wird. Nachdem Sie von lync Server 2010 zu lync Server 2013 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie lync Server-Verwaltungsshell, um zunächst alle Contact-Objekte abzurufen, die den lync Server 2010 analogen Geräten zugeordnet sind, und diese Objekte dann in den lync Server 2013-Pool zu übertragen.

<div>

## <a name="to-migrate-analog-devices"></a>So migrieren Sie analoge Geräte

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie in die Befehlszeile Folgendes ein:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Stellen Sie sicher, dass alle Kontaktobjekte in den lync Server 2013 Pool verschoben wurden. Geben Sie in die Befehlszeile Folgendes ein:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Stellen Sie sicher, dass alle Contact-Objekte nun dem lync Server 2013-Pool zugeordnet sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

