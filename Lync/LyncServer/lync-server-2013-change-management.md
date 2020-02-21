---
title: 'Lync Server 2013: Change Management'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39488d423457c01102d6af3c4d5bbfaf6962e2c3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Änderungsverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-18_

Änderungen an der IT-Umgebung sind unvermeidlich. Zu den Änderungen gehören neue Technologien, Systeme, Anwendungen, Hardware, Tools, Prozesse und Änderungen in Rollen und Verantwortlichkeiten. Mithilfe eines effektiven Änderungsverwaltungssystems können Sie Änderungen an der IT-Umgebung schnell und mit minimaler Dienstunterbrechung einleiten. Ein Change Management System bringt die Teams zusammen, die an der Änderung eines Systems beteiligt sind. Beispielsweise die Entscheidung, die Vorteile der Office-Webanwendungen zu nutzen. Hierbei handelt es sich um eine integrierte lync-Dienstanwendung, mit der Benutzer Dokumente in einem Browser lesen und bearbeiten können. Die Implementierung dieses Diensts erfordert, nachdem Sie die Produktion durchlaufen haben, eine Beteiligung von mehreren Teams:

  - **Testteam**   dieses Team lädt die Office-Webanwendungen auf einem Testserver, wobei Informationen zu den erwarteten Verwendungsmustern und der erwarteten Leistung der Produktionsserver bereitgestellt werden.

  - **Lync-Administratoren**   dieses Team bestimmt die Bereitstellungsstrategie und legt die Installation so fest, wie es möglich war. Das Team ist dafür verantwortlich, sicherzustellen, dass die Änderung in der Produktionsumgebung bereitgestellt wird und danach für die Verwaltung zuständig ist. Das Team muss die Auswirkungen der Änderungen verstehen und in Prozeduren einbinden, bevor die Änderungen in die Produktion übernommen werden.

  - **Netzwerkteam**   dieses Team ist für Änderungen an Firewallregeln verantwortlich, die den Zugriff über das Internet auf die internen lync-Pool Server ermöglichen. Das Team ist außerdem für die Zusammenarbeit mit den lync-Administratoren verantwortlich, um sicherzustellen, dass die verfügbare Bandbreite die zusätzliche Last unterstützenkann.

  - **Sicherheitsteam**   dieses Team bewertet die Sicherheit und minimiert Risiken. Das Sicherheitsteam muss bekannte Sicherheitsanfälligkeiten überprüfen und sicherstellen, dass Sicherheitsrisiken minimiert werden.

  - **Benutzerakzeptanzteam**   dieses Team besteht aus Benutzern, die bereit sind, das System zu testen und Feedback für Verbesserungen anzubieten.

Der Change Management-Prozess definiert die Zuständigkeiten jedes Teams und plant die auszuführende Arbeit, wobei die erforderlichen Prüfungen und Tests durchgeführt werden. Änderungs Steuerelemente hängen von der Komplexität und dem erwarteten Effekt einer Änderung ab. Sie können von der automatischen Genehmigung für geringfügige Änderungen, über Änderungs Überprüfungs Besprechungen bis hin zu vollständigen Reviews auf Projektebene variieren. Um dies besser zu erklären, werden die Gruppen von Änderungen in diesem Abschnitt erläutert.

  - **Wesentliche Änderungen**   wichtige Änderungen haben eine globale Auswirkung auf das System und erfordern möglicherweise Eingaben von verschiedenen Teams. Ein Beispiel hierfür ist ein Upgrade auf lync Server 2013. Wesentliche Änderungen betreffen viele Teams und möglicherweise unterschiedliche Systeme. Der Änderungsverwaltungsprozess umfasst möglicherweise eine oder mehrere Änderungs Überprüfungs Besprechungen, um die Teams zu informieren, die an der Änderung beteiligt sind oder von der Änderung betroffen sind.

  - **Wesentliche Änderungen**   wesentliche Änderungen erfordern erhebliche Ressourcen für die Planung, Erstellung und Implementierung. Es sollten geeignete Änderungs Steuerelemente eingeführt werden, um sicherzustellen, dass die Auswirkungen der Änderung verstanden werden, Bereitstellungsverfahren getestet werden und die Rollback-und Notfallpläne bereit sind. Ein Beispiel für eine wesentliche Änderung ist die Bereitstellungeines neuen kumulativen Updates.

  - **Geringfügige**   Änderungen geringfügige Änderungen wirken sich nicht wesentlich auf die IT-Umgebung aus, beispielsweisedurch Ändern bestimmter lync-Richtlinien über die Microsoft lync Server 2013-Systemsteuerung.

  - **Standardänderungen**   Standardänderungen werden regelmäßig durchgeführt und sind gut verstanden und dokumentiert. Der Änderungsverwaltungsprozess sollte alle Änderungen an den Verfahren überprüfen. Es sollte nicht für Routineänderungen wie das Erstellen einer Inhaltsdatenbank oder das Hinzufügen eines Benutzers benötigt werden.

Im folgenden Beispiel für die Änderungsverwaltung wird untersucht, wie unterschiedliche Teams interagieren und welche Aktionen ausgeführt werden, wenn ein neues Service Pack bereitgestellt wird. Diese Aktionen werden vom Änderungsverwaltungsprozess organisiert und verwaltet.

  - **Auslösen einer Änderungsanforderung**   das Sicherheitsteam hat das neueste Service Pack bewertet und bestätigt, dass es eine mögliche Sicherheitsanfälligkeit im Produktionssystem behebt. Das Team löst eine Änderungsanforderung aus, damit das neue kumulative Update auf alle Server angewendet wird, auf denen lync Server ausgeführt wird.

  - **Service Pack-Versionshinweise überprüfen**   das lync-Administrator Team überprüft die Service Pack-Versionshinweise, um die Auswirkungen auf das System zu identifizieren.

  - **Eine Reihe von Labortests wird durchgeführt**   das lync-Administrator Team muss Testaktualisierungen auf einem Server in einer Testumgebung durchführen, um zu entscheiden, ob das Service Pack erfolgreich angewendet werden kann, ohne dass sich dies auf installierte Anwendungen und Server Systeme auswirkt. Wenn Drittanbieter-oder intern erstellte Anwendungen vorhanden sind, die mit lync Server in einer Produktionsumgebung Schnittstellen, sollten diese ebenfalls getestet werden. Diese Tests können auch verwendet werden, um die Zeit zu schätzen, die zum Durchführen der Upgrades erforderlich ist.

  - **Benutzer werden über den Ausfall**   informiert das lync-Administrator Team, das Kommunikationsteam oder das Benutzer-Helpdesk informiert alle betroffenen Benutzer über den geplanten Wartungszyklus und darüber, wie lange der Dienst nicht verfügbar ist.

  - **Eine vollständige Sicherung von lync wird vor dem Upgrade**   durchgeführt. das lync-Administrator Team muss überprüfen, ob eine gültige Sicherung vorhanden ist, die zum Wiederherstellen des ursprünglichen Systemstatus verwendet werden kann, wenn die Installation des Service Packs fehlschlägt. Es wird empfohlen, dass die Sicherung auf einem Standbyserver wiederhergestellt wird, damit dieses System leicht verfügbar ist, wenn Probleme vorliegen.

  - **Das kumulative Update wird bereitgestellt**   das lync-Administrator Team führt die Installation während des geplanten Wartungszyklus durch.

<div>

## <a name="managing-the-timing-of-changes"></a>Verwalten des Zeitpunkts von Änderungen

Es wird empfohlen, eine Prozedur für die Planung von Änderungen zu implementieren, um Unterbrechungen in überlappenden Abschnitten ihrer Arbeit zu vermeiden. Beispielsweise können zwei Teams beide eine geringfügige Änderung an einem System planen. Ein Team kann ein kumulatives Update in einem Pool anwenden, während ein anderes Team ältere Benutzer in diesen Pool migriert. Keines der Teams ist von den Änderungen betroffen, die das andere Team plant, und jedes Team kennt möglicherweise nicht unbedingt Änderungen, die das andere Team plant. Wenn beide Änderungen gleichzeitig aufgetreten sind, gibt es möglicherweise Probleme beim Implementieren der Änderungen. Wenn nach der Anwendung der Änderungen Probleme auftreten, beispielsweise wenn die Benutzermigration fehlschlägt, kann es schwierig sein zu entscheiden, für welche Änderung ein Rollback ausgeführt werden soll. Es sollten regelmäßige Wartungszeiträume zwischen IT und Management eingerichtet werden, um die Änderungen zu testen und zu akzeptieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

