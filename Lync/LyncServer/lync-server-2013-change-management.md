---
title: 'Lync Server 2013: Änderungsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13eb521ea6b4be5f8d701885df65a3e1672b2eaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Änderungsverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-18_

Änderungen an der IT-Umgebung sind unvermeidlich. Zu den Änderungen gehören neue Technologien, Systeme, Anwendungen, Hardware, Tools, Prozesse und Änderungen an Rollen und Zuständigkeiten. Mit einem effektiven Änderungsverwaltungssystem können Sie Änderungen an der IT-Umgebung schnell und mit minimaler Dienstunterbrechung einführen. Ein Change Management System führt die Teams zusammen, die an der Änderung eines Systems beteiligt sind. Beispielsweise die Entscheidung, die Vorteile der Office Web Apps zu nutzen. Hierbei handelt es sich um eine integrierte lync-Dienstanwendung, mit der Benutzer Dokumente in einem Browser lesen und bearbeiten können. Die Implementierung dieses Diensts erfordert, nachdem Sie die Produktion durchlaufen haben, die Einbindung mehrerer Teams:

  - **Testteam**   dieses Team lädt-testet die Office Web Apps auf einem Testserver im Prozess, in dem Informationen zu den voraussichtlichen Verwendungsmustern und der erwarteten Leistung der Produktionsserver bereitgestellt werden.

  - **Lync-Administratoren**   dieses Team ermittelt die Bereitstellungsstrategie und erstellt Skripts für die Installation, sofern dies möglich war. Das Team ist dafür verantwortlich, sicherzustellen, dass die Änderung in der Produktionsumgebung bereitgestellt wird, und ist danach für die Verwaltung verantwortlich. Das Team muss die Auswirkungen der Änderungen verstehen und in Verfahren einbeziehen, bevor die Änderungen in die Produktion übernommen werden.

  - **Netzwerkteam**   dieses Team ist für Änderungen an Firewallregeln verantwortlich, die den Zugriff aus dem Internet auf die internen lync-Pool Server zulassen. Das Team ist auch für die Zusammenarbeit mit den lync-Administratoren verantwortlich, um sicherzustellen, dass die verfügbare Bandbreite die zusätzliche Last unterstützenkann.

  - **Sicherheitsteam**   dieses Team bewertet die Sicherheit und minimiert Risiken. Das Sicherheitsteam muss bekannte Sicherheitsanfälligkeiten überprüfen und sicherstellen, dass Sicherheitsrisiken minimiert werden.

  - **Benutzerakzeptanzteam**   dieses Team besteht aus Benutzern, die bereit sind, das System zu testen und Feedback zu Verbesserungen anzubieten.

Der Change Management-Prozess definiert die Zuständigkeiten der einzelnen Teams und plant die auszuführende Arbeit, wobei die erforderlichen Prüfungen und Tests integriert werden. Die Steuerelemente für Änderungen variieren abhängig von der Komplexität und dem erwarteten Effekt einer Änderung. Sie können von der automatischen Genehmigung für geringfügige Änderungen, über Änderungs Überprüfungs Besprechungen bis hin zu vollständigen Bewertungen auf Projektebene variieren. Um dies besser zu erklären, werden die Gruppen von Änderungen in diesem Abschnitt erläutert.

  - **Wichtige Änderungen**   größere Änderungen haben eine globale Auswirkung auf das System und erfordern möglicherweise Eingaben von verschiedenen Teams. Ein Beispiel hierfür ist das Upgrade auf lync Server 2013. Wichtige Änderungen betreffen viele Teams und möglicherweise andere Systeme. Der Change Management-Prozess umfasst wahrscheinlich eine oder mehrere Änderungs Überprüfungs Besprechungen, um die Teams zu informieren, die an der Änderung beteiligt sind oder von der Änderung betroffen sein werden.

  - **Signifikante Änderungen**   wesentliche Änderungen erfordern erhebliche Ressourcen, um zu planen, zu erstellen und zu implementieren. Es sollten geeignete Änderungs Steuerelemente eingeführt werden, um sicherzustellen, dass die Auswirkungen der Änderung verstanden werden, Bereitstellungsverfahren getestet und die Rollback-und Notfallpläne bereit sind. Ein Beispiel für eine wesentliche Änderung ist die Bereitstellungeines neuen kumulativen Updates.

  - **Geringfügige Änderungen**   geringfügige Änderungen haben keine nennenswerten Auswirkungen auf die IT-Umgebung, beispielsweise das Ändern bestimmter lync-Richtlinien über die Microsoft lync Server 2013-Systemsteuerung.

  - ****   Standardänderungen Standardänderungen werden regelmäßig durchgeführt und sind gut verstanden und dokumentiert. Der Change Management-Prozess sollte alle Änderungen an den Prozeduren überprüfen. Es sollte nicht für Routineänderungen wie das Erstellen einer Inhaltsdatenbank oder das Hinzufügen eines Benutzers benötigt werden.

Im folgenden Beispiel für die Änderungsverwaltung wird untersucht, wie verschiedene Teams interagieren und welche Aktionen ausgeführt werden, wenn ein neues Service Pack bereitgestellt wird. Diese Aktionen werden vom Change Management-Prozess organisiert und verwaltet.

  - **Auslösen einer Änderungsanforderung**   das Sicherheitsteam hat das neueste Service Pack bewertet und bestätigt, dass es eine mögliche Sicherheitsanfälligkeit im Produktionssystem behebt. Das Team löst eine Änderungsanforderung aus, damit das neue kumulative Update auf alle Server angewendet wird, auf denen lync Server ausgeführt wird.

  - **Informationen zu Service Pack-Versions**   hinweisen das lync-Administrator Team überprüft die Versionshinweise des Service Packs, um die Auswirkungen auf das System zu ermitteln.

  - **Eine Reihe von Lab-Tests wird durchgeführt**   das lync-Administrator Team muss Test Updates auf einem Server in einer Testumgebung durchführen, um zu entscheiden, ob das Service Pack erfolgreich angewendet werden kann, ohne dass dies Auswirkungen auf installierte Anwendungen und Server hat. Systeme. Wenn es sich um von Drittanbietern oder intern erstellte Anwendungen handelt, die eine Schnittstelle zu lync Server in einer Produktionsumgebung aufweisen, sollten diese ebenfalls getestet werden. Diese Tests können auch verwendet werden, um die Zeit zu schätzen, die für die Ausführung der Upgrades erforderlich ist.

  - **Die Benutzer werden über den Ausfall**   informiert, den das lync-Administrator Team, das Kommunikationsteam oder der Benutzer-Helpdesk alle betroffenen Benutzer über den geplanten Wartungszyklus informiert und wie lange der Dienst nicht verfügbar ist.

  - **Eine vollständige Sicherung von lync wird vor dem Upgrade**   durchgeführt, das vom lync-Administrator Team überprüft werden muss, ob eine gültige Sicherung vorhanden ist, die zum Wiederherstellen des ursprünglichen Systemzustands verwendet werden kann, wenn die Service Pack-Installation fehlschlägt. Wir empfehlen, dass die Sicherung auf einem Standbyserver wiederhergestellt wird, damit dieses System bei Problemen problemlos zur Verfügung steht.

  - **Das kumulative Update wird bereitgestellt**   , wenn das lync-Administrator Team die Installation während des geplanten Wartungszyklus durchführt.

<div>

## <a name="managing-the-timing-of-changes"></a>Verwalten der Anzeigedauer von Änderungen

Wir empfehlen, dass Sie eine Vorgehensweise zum Planen von Änderungen implementieren, um Unterbrechungen in überlappenden Abschnitten ihrer Arbeit zu vermeiden. So können beispielsweise zwei Teams eine geringfügige Änderung an einem System planen. Ein Team kann ein kumulatives Update in einem Pool anwenden, während ein anderes Team ältere Benutzer in diesen Pool migriert. Keines der Teams ist von den Änderungen betroffen, die das andere Team plant, und jedes Team weiß möglicherweise nicht unbedingt, welche Änderungen das andere Team plant. Wenn beide Änderungen gleichzeitig aufgetreten sind, gibt es möglicherweise Probleme beim Implementieren der Änderungen. Wenn nach dem Anwenden der Änderungen Probleme auftreten, beispielsweise wenn die Benutzermigration fehlschlägt, ist es möglicherweise schwierig, zu entscheiden, welche Änderung zurückgesetzt werden soll. Es sollten regelmäßige Wartungszeiten zwischen IT und Verwaltung eingerichtet werden, um die Änderungen zu testen und zu akzeptieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

