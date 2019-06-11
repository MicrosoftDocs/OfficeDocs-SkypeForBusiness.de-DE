---
title: 'Lync Server 2013: Einrichten von Archivierungsrichtlinien für Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55a56ff5c44d10d112762bb06662e9266dbc270b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>Einrichten von Archivierungsrichtlinien für Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Sie können die Archivierung für bestimmte Benutzer aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie für Benutzer erstellen und konfigurieren und dann die Richtlinie auf bestimmte Benutzer oder Benutzergruppen anwenden. Benutzerrichtlinien überschreiben alle globalen Richtlinien oder Website Richtlinien. Archivierungsrichtlinien gelten nur, wenn Sie die Microsoft Exchange-Integration nicht verwenden, oder wenn Sie die Microsoft Exchange-Integration verwenden, aber einige Benutzer haben, die nicht in Exchange 2013 sind und deren Postfächer in-situ-Speicher abgelegt werden.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in der lync Server 2013](lync-server-2013-how-archiving-works.md) -Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Konfigurieren Sie in der Archivierungskonfiguration erst alle erforderlichen Optionen, bevor Sie in den Archivierungsrichtlinien die Archivierung der internen oder externen Kommunikation aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Einrichten von Benutzerrichtlinien für die Archivierung in lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

