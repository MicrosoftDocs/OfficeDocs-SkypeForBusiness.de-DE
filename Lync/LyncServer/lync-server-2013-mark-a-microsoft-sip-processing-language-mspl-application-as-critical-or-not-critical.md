---
title: 'Lync Server 2013: Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch'
description: 'Lync Server 2013: Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f59fb6614416c1b0e4f49a766a1373483f509d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556551"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

MSPL-Serveranwendungen (Microsoft SIP Processing Language) sind nur Skriptanwendungen, die die MSPL-Skriptsprache anstelle der Microsoft lync 2010 API verwenden. Einige MSPL-Serveranwendungen werden als kritisch eingestuft. Wenn ein Skript kritisch ist, muss das Skript beim Systemstart gestartet werden, damit lync Server 2013 gestartet werden kann. Wenn das Skript fehlschlägt, während lync Server ausgeführt wird, wird der Server nicht heruntergefahren, aber das Senden des Datenverkehrs an das Skript wird beendet, und es werden Fehler im Ereignisprotokoll geschrieben.

Sie können lync Server-Systemsteuerung verwenden, um MSPL-Server Anwendungen (Microsoft SIP Processing Language) als kritisch zu kennzeichnen oder Sie zu markieren.

Nicht alle Skripts unterstützen diese Option. Beispielsweise ist das DefaultRouting-Skript als kritisch markiert, und diese Option kann für "DefaultRouting" nicht geändert werden.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>So markieren Sie eine MSPL-Serveranwendung als kritisch oder heben die Markierung auf

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Serveranwendung**.

4.  Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen ggf. zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **Als kritisch markieren** oder **Markierung aufheben** (sofern das Skript diese Option unterstützt).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) in lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Verwalten der lync Server 2013 Topologie](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

