---
title: Migrieren analoger Geräte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e809db03cf098bea07f57673ddcbfc019e15f299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>Migrieren analoger Geräte

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Lync Server bietet Unterstützung für analoge Geräte. Die unterstützten analogen Geräte sind analoge Audio-Telefone und analoge Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in ihrer lync Server-Umgebung unterstützt wird. Nachdem Sie von lync Server 2010 zu lync Server 2013 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie die lync Server-Verwaltungsshell, um zuerst alle Kontaktobjekte abzurufen, die mit den analogen Geräten von lync Server 2010 verknüpft sind, und verschieben Sie diese Objekte dann in den lync Server 2013-Pool.

<div>

## <a name="to-migrate-analog-devices"></a>So migrieren Sie analoge Geräte

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Überprüfen Sie, ob alle Kontaktobjekte in den lync Server 2013-Pool verschoben wurden. Geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Überprüfen Sie, ob alle Kontaktobjekte jetzt dem lync Server 2013-Pool zugeordnet sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

