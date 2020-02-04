---
title: 'Lync Server 2013: Einrichten der Unterstützung für umfangreiche Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Einrichten der Unterstützung für umfangreiche Besprechungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-12_

Zur Unterstützung großer Besprechungen mit bis zu 1000-Benutzern müssen eine geeignete Topologie erstellt, Hardware-und Softwarevoraussetzungen erfüllt und die Umgebung entsprechend konfiguriert werden.

<div>

## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Bei einer einzigen großen Besprechung sind mindestens ein Front-End und ein Back-End-Server erforderlich. Zur Bereitstellung einer höheren Verfügbarkeit empfehlen wir jedoch einen zwei Front-End-Serverpool mit gespiegelten Back-End-Servern.

Der Benutzer, der die umfangreichen Besprechungen hostet, muss sein Benutzerkonto in diesem Pool verwaltet haben. Es wird jedoch nicht empfohlen, andere Benutzerkonten in diesem Pool zu hosten. Verwenden Sie Sie stattdessen nur für die umfangreichen Besprechungen. Die bewährte Methode besteht darin, ein spezielles Benutzerkonto in diesem Pool zu erstellen, das nur zum Hosten großer Besprechungen verwendet wird. Da die große Besprechungs Einstellung für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme haben, beispielsweise die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung zu bewerben, wenn ein PSTN-Endpunkt involviert ist.

Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Wenn Sie zusätzlich optional eine Sicherung zur Notfallwiederherstellung und ein Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie ihn auch gemeinsam mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum verwenden. Ausführliche Informationen finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Konfiguration des umfangreichen Besprechungs Pools](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Konfiguration des umfangreichen Besprechungs Pools")

Zusätzliche Notizen zur Topologie:

  - Eine Dateifreigabe ist erforderlich, um Besprechungsinhalte zu speichern und um, wenn ein Archivierungsserver bereitgestellt und aktiviert wurde, die Archivierungsdateien zu speichern. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Details zum Konfigurieren der Dateifreigabe finden Sie unter [Konfigurieren des Dateispeichers für lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Ein Office Web Apps-Server ist erforderlich, um die PowerPoint-Präsentations Funktionalität in umfangreichen Besprechungen zu aktivieren. Der Office Web Apps-Server kann für den umfangreichen Besprechungs Pool dediziert sein, oder er kann derselbe Office Web Apps-Server sein, der von anderen Pools auf der Website verwendet wird, in der der dedizierte Pool bereitgestellt wird.

  - Bei einem Lastenausgleich für die Front-End-Server ist ein Hardwaregerät zum Lastenausgleich für den HTTP-Datenverkehr (z. B. beim Herunterladen von Besprechungsinhalten) erforderlich. DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Ausführliche Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Wenn Sie den Monitoring Server für den dedizierten groß Besprechungs Pool verwenden möchten, empfehlen wir die Verwendung des Überwachungsservers und der zugehörigen Datenbank, die für alle Front-End-Server Pools in ihrer lync Server-Bereitstellung freigegeben sind.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Hardware-und Software Anforderungen

Die Hardwareanforderungen für Server in einem dedizierten groß Besprechungs Pool sind dieselben wie für Ihre anderen lync Server 2013-Server. Details zu den Hardwareanforderungen finden Sie unter "[Server-Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Server in einem dedizierten groß Besprechungs Pool müssen allen lync Server 2013-Softwareanforderungen entsprechen. Details zu den Softwareanforderungen finden Sie in der folgenden Dokumentation:

  - [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Unterstützte Datenbanksoftware in Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Darüber hinaus müssen sowohl lync Server 2013 als auch alle lync Server 2013-Clients über die neuesten Updates verfügen.

</div>

<div>

## <a name="configuration-requirements"></a>Konfigurationsanforderungen

Wir empfehlen, speziell für große Besprechungen eine neue konferenzrichtlinie zu erstellen und dann die konferenzrichtlinie den Benutzern zuzuweisen, die sich in dem dedizierten Pool für große Besprechungen befinden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:

  - Setzen Sie die Option **MaxMeetingSize** auf **1000**. (Der Standardwert ist **250**.)

  - Legen Sie die Option **AllowLargeMeetings** auf **True** fest.

  - Legen Sie die Option **EnableAppDesktopSharing** auf **None** fest.

  - Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.

  - Legen Sie die Option **AllowSharedNotes** auf **False** fest.

  - Legen Sie die Option **AllowAnnotations** auf **False** fest.

  - Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.

  - Legen Sie die Option **AllowMultiview** auf **False** fest.

  - Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.

<div>


> [!NOTE]  
> Die Unterstützung für 1000-Benutzer große Besprechungen in lync Server 2013 setzt voraus, dass die <STRONG>AllowLargeMeetings</STRONG> -Einstellung in der konferenzrichtlinie für den Besprechungsplaner auf "true" festgelegt ist. Wenn diese Einstellung auf "true" festgelegt ist, wird die lync-Benutzeroberfläche für besonders große Besprechungen optimiert, wenn Benutzer einer solchen Besprechung beitreten. In einer umfangreichen Besprechung wird in lync nicht das erste oder das Update der vollständigen Besprechungsteilnehmer Liste angezeigt, bei der es sich um einen Leistungsengpass für den Client und lync Server 2013 handelt. Stattdessen werden in lync nur Informationen über den Benutzer und die Liste der Referenten der Besprechung angezeigt. Lync zeigt weiterhin die Gesamtzahl der Teilnehmer an, die in den umfangreichen Besprechungen zur Verfügung stehen.



</div>

Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen, die für große Besprechungen nicht erforderlich sind, zu deaktivieren.

Darüber hinaus müssen Sie den dedizierten Pool für große Besprechungen so konfigurieren, dass jeder lync Server 2013-Benutzer, der im Pool verwaltet wird und für die Verwaltung des Besprechungs Zeitplans verantwortlich ist, über die entsprechenden Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:

  - Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.

  - Stellen Sie sicher, dass das Kontrollkästchen **zugewiesene Konferenztyp Standard** mäßig nicht aktiviert ist. Mit dieser Einstellung wird gesteuert, ob das Online Besprechungs-Add-in für lync 2013 Konferenzen immer mit der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Besprechungen über die gleiche URL und Audioinformationen für die Teilnahme verfügen. In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert der zugewiesene Konferenztyp gut, weil jeder eine eigene, individuell zugewiesene Konferenz hat, und die URL-und Audioinformationen für die dauerhafte Teilnahme helfen, eine schnellere Besprechung zu ermöglichen. Im Szenario mit großer Besprechung plant der große Besprechungs Support die umfangreichen Besprechungen jedoch mit einem einzigen Satz von Benutzeranmeldeinformationen und stellt dann den Besprechungs anfordernden Teilnehmer-URLs und Audioinformationen zur Verfügung. In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.

  - Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Diese Einstellung wirkt sich auf den standardmäßigen Besprechungs Zugriffstyp aus, der vom Online Besprechungs-Add-in für lync 2013 geplant wird, wenn keine zugewiesene Konferenz verwendet wird. Die geeignete Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

