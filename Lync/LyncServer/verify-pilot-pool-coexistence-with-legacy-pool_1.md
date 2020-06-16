---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73f8d25237d7d056282cc7c88685802eb50f16
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Überprüfen des Pools im Verwaltungstool von Office Communications Server 2007 R2

1.  Öffnen Sie das Office Communications Server 2007 R2 Verwaltungstool.

2.  Erweitern Sie den Knoten **Gesamtstruktur**, den Knoten **Standard Edition-Server** oder **Enterprise-Pools** und dann den Pool- oder Servernamen.

3.  Stellen Sie sicher, dass die Office Communications Server 2007 R2 Dienste im Pool aktiv sind.
    
    ![Office Communications Server 2007 R2-Verwaltungskonsole](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Überprüfen des Pilot Pools in lync Server 2013 Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der CsAdministrator-Rolle ist, am lync Server 2013 Front-End-Server an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Topologie**.

4.  Überprüfen Sie, ob die bereitgestellten Server im Pilotpool vorhanden sind.
    
    ![Seite "lync Server-Systemsteuerung Topologie"](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Seite "lync Server-Systemsteuerung Topologie"")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Überprüfen, ob lync Server 2013 Dienste gestartet wurden

1.  Öffnen Sie im lync Server 2013 Front-End-Server das Applet **Dienste** in der Gruppe **Verwaltung** .

2.  Überprüfen Sie, ob die aufgeführten Dienste mit der Liste in der nachfolgenden Abbildung übereinstimmen.
    
    ![Dienstseite mit gestarteten lync-Diensten](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Dienstseite mit gestarteten lync-Diensten")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

