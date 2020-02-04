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
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Durchführen und Überwachen von Sicherungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-15_

Ihre geschäftlichen Prioritäten sollten die Spezifikation von Sicherungs-und Wiederherstellungsanforderungen für Ihre Organisation steuern. Das Durchführen von Sicherungen der Server und Daten ist die erste Verteidigungslinie bei der Planung eines Notfalls.

Computer, auf denen lync Server 2013-Dienste oder Serverrollen ausgeführt werden, müssen über eine Kopie der aktuellen Topologie, der aktuellen Konfigurationseinstellungen und der aktuellen Richtlinien verfügen, bevor Sie in ihrer benannten Rolle funktionieren können. Lync Server ist dafür verantwortlich, sicherzustellen, dass diese Informationen an jeden Computer weitergeleitet werden, der Sie benötigt.

Die Cmdlets **Export-CsConfiguration** und **Import-CsConfiguration** werden verwendet, um die lync Server-Topologie, die Konfigurationseinstellungen und Richtlinien während eines Upgrades des zentralen Verwaltungsspeichers zu sichern und wiederherzustellen. Mit den Cmdlets **Export-CsConfiguration** können Sie Daten in eine exportieren. ZIP-Datei. Anschließend können Sie das Cmdlet **Import-CsConfiguration** verwenden, um dies zu lesen. ZIP-Datei aus, und stellen Sie die Topologie, die Konfigurationseinstellungen und Richtlinien im zentralen Verwaltungsspeicher wieder her. Anschließend werden die wiederhergestellten Informationen von den Replikationsdiensten von lync Server auf andere Computer repliziert, auf denen lync Server-Dienste ausgeführt werden.

Die Möglichkeit zum Exportieren und Importieren von Konfigurationsdaten wird auch bei der Erstkonfiguration von Computern verwendet, die sich in Ihrem Umkreisnetzwerk befinden (beispielsweise Edgeserver). Wenn Sie einen Computer im Umkreisnetzwerk konfigurieren, müssen Sie zuerst eine manuelle Replikation mithilfe der CsConfiguration-Cmdlets durchführen: Sie müssen die Konfigurationsdaten mithilfe von **Export-CsConfiguration** exportieren und dann das Kopieren. ZIP-Datei auf dem Computer im Umkreisnetzwerk. Anschließend können Sie **Import-CsConfiguration** und den localstore-Parameter verwenden, um die Daten zu importieren. Sie müssen dies nur einmal tun. Anschließend erfolgt die Replikation automatisch.

Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das **Export-CsConfiguration-** Cmdlet lokal auszuführen: RTCUniversalServerAdmins. Führen Sie den folgenden Befehl aus der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugeordnet ist (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Alle SQL 2012-Back-End-Datenbanken sollten gemäß den [bewährten SQL-Methoden](http://go.microsoft.com/fwlink/p/?linkid=290716)gesichert werden.

Regelmäßige Tests des Disaster Recovery-Plans für Ihre lync Server 2013-Infrastruktur sollten in einer Lab-Umgebung durchgeführt werden, die die Produktionsumgebung so genau wie möglich imitiert. Weitere Informationen zu Disaster Recovery-Tests finden Sie in den monatlichen Aufgaben.

Beachten Sie, dass die Sicherungshäufigkeit basierend auf den Wiederherstellungspunkt-und Wiederherstellungspunkt Zielen angepasst werden kann. Als bewährte Methode können Sie regelmäßige, periodische Schnappschüsse über den ganzen Tag hinweg erstellen. Im Allgemeinen sollten Sie alle 24 Stunden vollständige Sicherungen durchführen.

<div>

## <a name="see-also"></a>Siehe auch


[Importieren-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Bewährte Methoden für SQL](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

