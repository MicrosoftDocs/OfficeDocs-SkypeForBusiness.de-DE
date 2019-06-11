---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Server Anwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7ff3379f0e32166ceb263e1dbda46117b6984a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Serveranwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Sie können die lync Server-Systemsteuerung verwenden, um MSPL-Serveranwendungen (Microsoft SIP Processing Language) zu aktivieren oder zu deaktivieren, die in ihrer lync Server 2013-Umgebung ausgeführt werden. Bei diesen Anwendungen handelt es sich um nur-Skript-Anwendungen, die eine Skriptsprache anstelle der Microsoft lync 2013 Preview-API verwenden.

Nicht alle Skripts können aktiviert oder deaktiviert werden. Beispielsweise ist das DefaultRouting-Skript aktiviert, und diese Option kann für DefaultRouting nicht geändert werden.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>So aktivieren oder deaktivieren Sie eine MSPL-Serveranwendung

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Server Anwendung**.

4.  Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf Anwendung **aktivieren** oder **Anwendung deaktivieren** (das heißt, wenn das Skript diese Option unterstützt).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

