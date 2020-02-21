---
title: 'Lync Server 2013: Probleme mit dem Topologie-Test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3e9b587a286cdff2b7ef08ec217a420792b121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Probleme beim Topologie-Test in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Wie das Cmdlet " **Test-CsTopology** " bietet Ihnen Best Practice Analyzer die Möglichkeit, zu überprüfen, ob lync Server 2013 auf globaler Ebene ordnungsgemäß funktioniert. Standardmäßig prüft Best Practice Analyzer wie das Cmdlet die gesamte lync Server 2013 Infrastruktur, überprüft, ob die erforderlichen Dienste aktiv sind und dass die entsprechenden Benutzerrechte und-Berechtigungen für diese Dienste und für die universelle festgelegt wurden. bei der Installation von lync Server 2013 erstellte Sicherheitsgruppen.

Zusätzlich zur Überprüfung der Gültigkeit von lync Server als Ganzes überprüft **Test-CsTopology** auch die Gültigkeit eines bestimmten Diensts. Ausführliche Informationen zur Verwendung des Cmdlets zum Testen bestimmter Dienste finden Sie unter [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in der lync Server-Verwaltungsshell Dokumentation. Nutzen Sie die folgenden Informationen, um Probleme mit Ihrer Topologie zu lösen.

<div>


> [!NOTE]  
> Je nach Konfiguration Ihrer Edgeserver und den entsprechenden Einstellungen im Umkreisnetzwerk, inklusive Firewall- Einstellungen und Berechtigungen, kann Best Practices Analyzer möglicherweise nicht auf Ihre Edgeserver zugreifen, um diese zu scannen. Wenn Sie die Edgeserver scannen lassen und die Berichte anzeigen, dass ein Zugriffsproblem für die Edgeserver vorliegt, deaktivieren Sie das Kontrollkästchen <STRONG>Edgeserver</STRONG>, und führen Sie den Scanvorgang erneut aus, um zu verhindern, dass das Problem in den Berichten aufgelistet wird.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Problembehebung für Ihre Topologie

Wenn beim Topologietest Probleme mit Ihrer Topologie gefunden werden, werden diese Probleme wahrscheinlich durch Fehler verursacht, die beim Veröffentlichen oder Aktivieren Ihrer Topologie aufgetreten sind.

Wenn Sie Änderungen an Ihrer Topologie vornehmen, werden die Änderungen erst dann wirksam, wenn sie sowohl veröffentlicht als auch aktiviert wurden. Sie müssen den Topologie-Generator verwenden, um Topologie-Änderungen vorzunehmen. Nachdem Sie Änderungen vorgenommen haben, können Sie diese Änderungen dann mithilfe des Topologie-Generators veröffentlichen und aktivieren.

Wenn Sie die Änderungen veröffentlichen, werden die neuen Informationen (beispielsweise eine neue Website oder eine neue Serverrolle) in den zentralen Verwaltungsspeicher geschrieben. Diese neuen (oder neu geänderten) Objekte werden jedoch nicht unmittelbar Ihrer Topologie beitreten. Objekte werden nur dann an Ihre Topologie anschliessen, wenn Sie die aktualisierte Topologie aktivieren. Wenn Sie im Topologie-Generator die Option veröffentlichen auswählen, treten beide Schritte auf: die Änderungen werden veröffentlicht (das heißt, Sie werden in den zentralen Verwaltungsspeicher geschrieben) und dann wird die neue Topologie aktiviert.

Standardmäßig sind Mitglieder der Gruppe "RTCUniversalServerAdmins" autorisiert, die Cmdlets **Publish-CsTopology** und **Enable-CsTopology** auszuführen. Wenn die Setupberechtigungen jedoch nicht delegiert wurden, müssen Sie als Domänenadministrator angemeldet sein, um das Cmdlet **Publish-CsTopology** auszuführen. Um RTCUniversalServerAdmins das Recht zu geben, das Cmdlet " **Publish-CsTopology** " tatsächlich zu verwenden, müssen Sie das **Grant-CsSetupPermission-** Cmdlet für jeden Active Directory Container ausführen, der Computer mit lync Server Diensten enthält. Um RTCUniversalServerAdmins das Recht zu geben, das Cmdlet **enable-CsTopology** zu verwenden, müssen Sie das Cmdlet " **CsSetupPermission** " für jeden Active Directory-Domänendienste Container ausführen, der Computer mit lync Server Diensten enthält. Beachten Sie, dass dies für das Aktivieren und Veröffentlichen einer Topologie mithilfe des Topologie-Generators gilt. Wenn Sie die Berechtigungen nicht mithilfe von "CsSetupPermission" delegiert haben, kann nur ein Domänenadministrator eine Topologie mithilfe des Topologie **-** Generators aktivieren und veröffentlichen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

