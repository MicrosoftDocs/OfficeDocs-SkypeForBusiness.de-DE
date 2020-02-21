---
title: 'Lync Server 2013: Einrichten von Benutzerrichtlinien für die Archivierung in lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e032dd276ee41a711ded56d33a065d515b182ab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Einrichten von Benutzerrichtlinien für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-10_

Das Aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer, die in lync Server 2013 verwaltet werden, erfordert das Erstellen und Konfigurieren einer oder mehrerer Benutzerrichtlinien und das anschließende Anwenden der entsprechenden Richtlinie auf bestimmte Benutzer oder Benutzergruppen. Benutzerrichtlinien setzen Standort-und globale Richtlinien außer Kraft, jedoch nur für Benutzer, die in lync Server 2013 verwaltet werden.

Benutzer werden immer in lync Server verwaltet. Wenn Microsoft Exchange Integration aktiviert ist, müssen Benutzer, deren Postfächer sich in Microsoft Exchange Server 2013 befinden, ihre Archivierungsrichtlinien nicht in lync Server verwaltet haben. Diese Benutzer mit der Archivierung werden von Exchange in-situ-Speicher verwaltet.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden. Die Archivierung für diese Benutzer erfordert, dass für ihre Postfächer das Compliance-Archiv festgelegt wird. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.<BR>Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Anwenden einer lync Server Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

