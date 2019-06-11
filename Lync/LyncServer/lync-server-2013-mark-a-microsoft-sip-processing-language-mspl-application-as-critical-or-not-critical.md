---
title: 'Lync Server 2013: Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

MSPL-Serveranwendungen (Microsoft SIP Processing Language) sind reine Skriptanwendungen, die die MSPL-Skriptsprache anstelle der Microsoft lync 2010-API verwenden. Einige MSPL-Serveranwendungen werden als kritisch angegeben. Wenn ein Skript kritisch ist, muss das Skript beim Systemstart gestartet werden, damit lync Server 2013 gestartet werden kann. Wenn das Skript fehlschlägt, während lync Server ausgeführt wird, wird der Server nicht heruntergefahren, aber er beendet das Senden von Datenverkehr an das Skript und schreibt Fehler im Ereignisprotokoll.

Mit der lync Server-Systemsteuerung können Sie MSPL-Serveranwendungen (Microsoft SIP Processing Language) als kritisch kennzeichnen oder die Markierung aufheben.

Diese Option wird nicht von allen Skripts unterstützt. Das DefaultRouting-Skript wird beispielsweise als kritisch markiert, und diese Option kann für DefaultRouting nicht geändert werden.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Markieren oder Aufheben der Markierung einer MSPL-Serveranwendung als kritisch

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Server Anwendung**.

4.  Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **als kritisch kennzeichnen** oder **als kritisch aufheben** (das heißt, wenn das Skript diese Option unterstützt).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Serveranwendung in lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

