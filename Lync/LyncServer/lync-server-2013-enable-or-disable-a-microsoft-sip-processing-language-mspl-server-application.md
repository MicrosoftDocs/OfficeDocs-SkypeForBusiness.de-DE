---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren einer MSPL-Server Anwendung (Microsoft SIP Processing Language)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9efa0fb6e0ab1cce452ecccfdc5c63d795f3a0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Sie können lync Server-Systemsteuerung verwenden, um MSPL-Server Anwendungen (Microsoft SIP Processing Language) zu aktivieren oder zu deaktivieren, die in ihrer lync Server 2013 Umgebung ausgeführt werden. Bei diesen Anwendungen handelt es sich nur um skriptbasierte Anwendungen, die anstelle der Microsoft lync 2013 Preview-API eine Skriptsprache verwenden.

Nicht alle Skripts können aktiviert oder deaktiviert werden. Beispielsweise ist das DefaultRouting-Skript aktiviert, und diese Option kann für DefaultRouting nicht geändert werden.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>So aktivieren oder deaktivieren Sie eine MSPL-Serveranwendung

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Serveranwendung**.

4.  Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen ggf. zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf Anwendung **aktivieren** oder **Anwendung deaktivieren** (das heißt, wenn das Skript diese Option unterstützt).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Verwalten der lync Server 2013 Topologie](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

