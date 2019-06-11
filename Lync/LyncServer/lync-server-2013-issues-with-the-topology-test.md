---
title: 'Lync Server 2013: Probleme mit dem Topologie-Test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d416aac6460870ab14d5296bcc6c7944ecf699e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Probleme mit dem Topologie-Test in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Wie das Cmdlet " **Test-CsTopology** " bietet Ihnen Best Practice Analyzer eine Möglichkeit, zu überprüfen, ob lync Server 2013 auf globaler Ebene ordnungsgemäß funktioniert. Standardmäßig überprüft Best Practice Analyzer wie das Cmdlet Ihre gesamte lync Server 2013-Infrastruktur, überprüft, ob die erforderlichen Dienste ausgeführt werden, und dass die entsprechenden Benutzerrechte und Berechtigungen für diese Dienste und für die universelle Anwendung festgesetzt wurden. bei der Installation von lync Server 2013 erstellte Sicherheitsgruppen

Zusätzlich zur Überprüfung der Gültigkeit von lync Server als Ganzes überprüft **Test-CsTopology** auch die Gültigkeit eines bestimmten Diensts. Details zur Verwendung des Cmdlets zum Testen bestimmter Dienste finden Sie unter [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in der Dokumentation zur lync Server-Verwaltungsshell. Verwenden Sie die folgenden Informationen, um Probleme mit Ihrer Topologie zu beheben.

<div>


> [!NOTE]  
> Je nach Konfiguration Ihrer Edgeserver und der zugehörigen Umkreisnetzwerk Einstellungen, einschließlich Firewalleinstellungen und-Berechtigungen, ist Best Practices Analyzer möglicherweise nicht in der Lage, auf Ihre Edgeserver zuzugreifen und diese zu überprüfen. Wenn Sie bei der Überprüfung Edgeserver einbeziehen und die Berichte darauf hindeuten, dass ein Problem beim Zugriff auf Edgeserver vorliegt, deaktivieren Sie das Kontrollkästchen <STRONG>Edgeserver</STRONG> , und führen Sie den Scan erneut aus, um zu verhindern, dass das Problem in Berichten angezeigt wird.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Beheben von Problemen mit Ihrer Topologie

Wenn der Topologie-Test Probleme mit Ihrer Topologie gefunden hat, sind diese Probleme wahrscheinlich auf Probleme zurückzuführen, die beim Veröffentlichen oder Aktivieren Ihrer Topologie aufgetreten sind.

Wenn Sie Änderungen an Ihrer Topologie vornehmen, werden die Änderungen erst wirksam, wenn Sie sowohl veröffentlicht als auch aktiviert wurden. Sie müssen Topologie-Generator verwenden, um Topologie-Änderungen vorzunehmen. Nachdem Sie Änderungen vorgenommen haben, können Sie diese Änderungen dann mithilfe des Topologie-Generators veröffentlichen und aktivieren.

Wenn Sie die Änderungen veröffentlichen, werden die neuen Informationen (beispielsweise eine neue Website oder eine neue Serverrolle) in den zentralen Verwaltungsspeicher geschrieben. Diese neuen (oder die neu geänderten) Objekte treten jedoch nicht unmittelbar in Ihre Topologie ein. Objekte treten nur bei der Aktivierung der aktualisierten Topologie in Ihre Topologie ein. Wenn Sie die Option "veröffentlichen" im Topologie-Generator auswählen, treten beide Schritte auf: die Änderungen werden veröffentlicht (das heißt, Sie werden in den zentralen Verwaltungsspeicher geschrieben), und dann wird die neue Topologie aktiviert.

Standardmäßig sind Mitglieder der RTCUniversalServerAdmins-Gruppe autorisiert, das Cmdlet **Publish-CsTopology** und das Cmdlet **enable-CsTopology** auszuführen. Wenn jedoch keine Setup-Berechtigungen delegiert wurden, müssen Sie als Domänenadministrator angemeldet sein, um **Publish-CsTopology**ausführen zu können. Um RTCUniversalServerAdmins das Recht zu geben, das Cmdlet **Publish-CsTopology** tatsächlich zu verwenden, müssen Sie das **Grant-CsSetupPermission-** Cmdlet auf jedem Active Directory-Container ausführen, der Computer mit lync Server-Diensten enthält. Um RTCUniversalServerAdmins das Recht zu geben, das Cmdlet **enable-CsTopology** zu verwenden, müssen Sie das Cmdlet " **Satz-CsSetupPermission** " für jeden Active Directory-Domänendienst Container ausführen, der Computer mit lync Server-Diensten enthält. Beachten Sie, dass dies für das Aktivieren und Veröffentlichen einer Topologie mithilfe des Topologie-Generators gilt. Wenn Sie die Berechtigungen nicht mithilfe von " **CsSetupPermission**" delegiert haben, kann nur ein Domänenadministrator eine Topologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

