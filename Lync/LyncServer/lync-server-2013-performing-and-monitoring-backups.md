---
title: 'Lync Server 2013: durchführen und Überwachen von Sicherungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b79fdbaceff06155389d101570b23d6143b9bbcc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536748"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Durchführen und Überwachen von Sicherungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-15_

Ihre geschäftlichen Prioritäten sollten die Spezifikation der Sicherungs-und Wiederherstellungsanforderungen für Ihre Organisation vorantreiben. Das Durchführen von Sicherungen der Server und Daten ist die erste Verteidigungslinie bei der Planung eines Notfalls.

Computer, auf denen lync Server 2013 Dienste oder Server Rollen ausgeführt werden, müssen über eine Kopie der aktuellen Topologie, der aktuellen Konfigurationseinstellungen und der aktuellen Richtlinien verfügen, bevor Sie in ihrer benannten Rolle funktionieren können. Lync Server ist dafür verantwortlich, sicherzustellen, dass diese Informationen an jeden Computer weitergeleitet werden, der ihn benötigt.

Die Cmdlets **Export-CsConfiguration** und **Import-CsConfiguration** werden verwendet, um die lync Server Topologie, die Konfigurationseinstellungen und Richtlinien während eines Upgrades des zentralen Verwaltungsspeichers zu sichern und wiederherzustellen. Mit den Cmdlets **Export-CsConfiguration** können Sie Daten in a exportieren. ZIP-Datei. Anschließend können Sie das Cmdlet **Import-CsConfiguration** verwenden, um dies zu lesen. ZIP-Datei, und stellen Sie die Topologie, die Konfigurationseinstellungen und Richtlinien im zentralen Verwaltungsspeicher wieder her. Anschließend repliziert die Replikationsdienste von lync Server die wiederhergestellten Informationen auf andere Computer, auf denen lync Server Dienste installiert werden.

Die Möglichkeit zum Exportieren und Importieren von Konfigurationsdaten wird auch während der anfänglichen Konfiguration von Computern verwendet, die sich in Ihrem Umkreisnetzwerk befinden (beispielsweise Edgeserver). Wenn Sie einen Computer im Umkreisnetzwerk konfigurieren, müssen Sie zunächst eine manuelle Replikation mit den CsConfiguration-Cmdlets ausführen: Sie müssen die Konfigurationsdaten mithilfe von **Export-CsConfiguration** exportieren und dann kopieren. ZIP-Datei auf dem Computer im Umkreisnetzwerk. Anschließend können Sie die Daten mit dem Cmdlet **Import-CsConfiguration** und dem Parameter "LocalStore" importieren. Sie müssen dies nur einmal tun. Danach erfolgt die Replikation automatisch.

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet **Export-CsConfiguration** lokal ausführen: RTCUniversalServerAdmins. Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der Windows PowerShell Aufforderung aus:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Alle SQL 2012-Back-End-Datenbanken sollten gemäß [bewährter SQL-Methoden](https://go.microsoft.com/fwlink/p/?linkid=290716)gesichert werden.

Regelmäßige Tests des Notfallwiederherstellungsplans für Ihre lync Server 2013 Infrastruktur sollten in einer Laborumgebung durchgeführt werden, die die Produktionsumgebung so genau wie möglich imitiert. Weitere Informationen zum Testen der Notfallwiederherstellung erhalten Sie in den monatlichen Aufgaben.

Beachten Sie, dass die Sicherungshäufigkeit basierend auf Ihrem Wiederherstellungs-und Wiederherstellungspunkte-Ziel angepasst werden kann. Als bewährte Methode sollten Sie regelmäßige, periodische Momentaufnahmen im Laufe des Tages durchführen. Im Allgemeinen sollten Sie alle 24 Stunden vollständige Sicherungen durchführen.

<div>

## <a name="see-also"></a>Siehe auch


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Bewährte Methoden für SQL](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

