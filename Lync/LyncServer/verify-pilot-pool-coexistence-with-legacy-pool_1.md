---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7585970a53ffd94959653555dad8a02724ba2f03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Überprüfen des Pools im Office Communications Server 2007 R2-Verwaltungs Tool

1.  Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.

2.  Erweitern Sie den Knoten **Gesamtstruktur** , erweitern Sie den Knoten **Standard Edition-Server** oder **Enterprise-Pools** , und erweitern Sie dann den Pool-oder Servernamen.

3.  Stellen Sie sicher, dass die Office Communications Server 2007 R2-Dienste im Pool ausgeführt werden.
    
    ![Office Communications Server 2007 R2-Verwaltungskonsole](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Überprüfen des Pilot Pools in der lync Server 2013-Systemsteuerung

1.  Melden Sie sich von einem Benutzerkonto, das ein Mitglied der CsAdministrator-Rolle ist, beim lync Server 2013-Front-End-Server an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Topologie**.

4.  Überprüfen Sie, ob die von Ihnen bereitgestellten Server in Ihrem Pilot Pool vorhanden sind.
    
    ![Seite "Topologie der lync Server-Systemsteuerung"](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Seite "Topologie der lync Server-Systemsteuerung"")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Überprüfen, ob die lync Server 2013-Dienste gestartet wurden

1.  Öffnen Sie auf dem lync Server 2013-Front-End-Server das Applet **Dienste** in der Gruppe **Verwaltungs Tools** .

2.  Überprüfen Sie, ob die aufgeführten Dienste der Liste in der folgenden Abbildung entsprechen.
    
    ![Seite "Dienste" mit gestarteten lync-Diensten](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Seite "Dienste" mit gestarteten lync-Diensten")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

