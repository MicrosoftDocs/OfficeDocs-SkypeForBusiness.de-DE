---
title: 'Lync Server 2013: Einrichten der Unterstützung für große Besprechungen'
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
ms.openlocfilehash: 8970d616d78cbfdafa591b58f123918cd20e0040
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Einrichten der Unterstützung für große Besprechungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-12_

Wenn Besprechungen mit mehr als 1000 Benutzern unterstützt werden sollen, ist es erforderlich, eine entsprechende Topologie zu erstellen, die Anforderungen an Hardware und Software zu erfüllen und die Umgebung entsprechend zu konfigurieren.

<div>

## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Eine einzelne große Besprechung erfordert mindestens eine Front-End-Server und einen Back-End-Server. Um eine hohe Verfügbarkeit zu gewährleisten, wird jedoch ein zwei Front-End-Server Pool mit gespiegelten Back-End-Servern empfohlen.

Die Benutzerkonten der Benutzer, die große Besprechungen durchführen, müssen in diesem Pool gehostet werden. Es wird jedoch nicht empfohlen, dass andere Benutzerkonten in diesem Pool gehostet werden. Er sollte nur für diese großen Besprechungen verwendet werden. In diesem Pool sollte ein spezielles Benutzerkonto erstellt werden, das nur zur Durchführung großer Besprechungen verwendet wird. Da die Einstellung für große Besprechungen für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme verursachen, beispielsweise die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung zu heraufstufen, wenn ein PSTN-Endpunkt beteiligt ist.

Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Wenn Sie optional Notfall Wiederherstellungs Sicherungen und Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie diese mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum koppeln. Ausführliche Informationen finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Konfiguration für umfangreiche Besprechungs Pools](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Konfiguration für umfangreiche Besprechungs Pools")

Zusätzliche Notizen zur Topologie:

  - Eine Dateifreigabe ist zum Speichern der Archivierungsdateien erforderlich, wenn der Besprechungsinhalt gespeichert wird und wenn Archivierungsserver bereitgestellt und aktiviert ist. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Ausführliche Informationen zum Konfigurieren der Dateifreigabe finden Sie unter [configure File Storage for lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Für die Aktivierung der PowerPoint-Präsentationsfunktion in großen Besprechungen ist ein Office-webapps-Server erforderlich. Der Office Web Apps-Server kann für den großen Besprechungs Pool reserviert werden, oder es kann sich um denselben Office Web Apps-Server handeln, der von anderen Pools an dem Standort verwendet wird, an dem der dedizierte Pool bereitgestellt wird.

  - Für den Lastenausgleich der Front-End-Server ist ein Hardwarelastenausgleich für den HTTP-Datenverkehr erforderlich (beispielsweise das Herunterladen von Besprechungsinhalten). DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Ausführliche Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Wenn Sie Monitoring Server für den dedizierten großen Besprechungs Pool verwenden möchten, empfehlen wir die Verwendung der Monitoring Server und der zugehörigen Datenbank, die für alle Front-End-Server Pools in ihrer lync Server-Bereitstellung freigegeben sind.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Voraussetzungen für Hardware und Software

Die Hardwareanforderungen für Server in einem dedizierten großen Besprechungs Pool entsprechen denen für andere lync Server 2013 Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter "[Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Server in einem dedizierten großen Besprechungs Pool müssen alle lync Server 2013 Softwareanforderungen erfüllen. Ausführliche Informationen zu den Softwareanforderungen finden Sie in den folgenden Dokumentationen:

  - [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Unterstützung der Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md)

  - [Zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md)

Darüber hinaus müssen sowohl lync Server 2013 als auch alle lync Server 2013-Clients über die neuesten Updates verfügen.

</div>

<div>

## <a name="configuration-requirements"></a>Konfigurationsanforderungen

Es wird empfohlen, eine neue Konferenzrichtlinie speziell für große Besprechungen zu erstellen und diese anschließend den Benutzern zuzuweisen, die auf den dedizierten großen Besprechungspools gehostet werden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:

  - Legen Sie die Option **MaxMeetingSize** auf **1000** fest. (Der Standardwert ist **250**.)

  - Legen Sie die Option **AllowLargeMeetings** auf **True** fest.

  - Legen Sie die Option **EnableAppDesktopSharing** auf **Keine** fest.

  - Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.

  - Legen Sie die Option **AllowSharedNotes** auf **False** fest.

  - Legen Sie die Option **AllowAnnotations** auf **False** fest.

  - Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.

  - Legen Sie die Option **AllowMultiview** auf **False** fest.

  - Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.

<div>


> [!NOTE]  
> Die Unterstützung für 1000 Benutzer große Besprechungen in lync Server 2013 erfordert, dass die <STRONG>AllowLargeMeetings</STRONG> -Einstellung in der konferenzrichtlinie für den Besprechungsplaner auf true festgelegt ist. Wenn diese Einstellung auf "true" festgelegt ist, wird die lync-Umgebung für extra große Besprechungen optimiert, wenn Benutzer einer solchen Besprechung beitreten. In einer großen Besprechung wird in lync nicht die anfängliche oder aktualisierte Liste der vollständigen Besprechungsteilnehmer angezeigt, die sowohl für den Client als auch für den lync Server 2013 einen Leistungsengpass darstellt. Stattdessen werden in lync nur Informationen über den Benutzer und die Liste der Referenten der Besprechung angezeigt. In lync wird weiterhin die Gesamtzahl der Teilnehmer angezeigt, die in den großen Besprechungen verfügbar sind.



</div>

Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen zu deaktivieren, die für große Besprechungen nicht erforderlich sind.

Darüber hinaus müssen Sie den dedizierten großen Besprechungs Pool so konfigurieren, dass jeder lync Server 2013 Benutzer, der im Pool verwaltet wird und für die Verwaltung des Besprechungs Zeitplans zuständig ist, über die entsprechenden Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:

  - Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.

  - Stellen Sie sicher, dass das Kontrollkästchen **zugewiesener Konferenztyp Standard** mäßig nicht aktiviert ist. Mit dieser Einstellung wird gesteuert, ob das Online Besprechungs-Add-in für lync 2013 Konferenzen immer mit der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Besprechungen über dieselbe Join-URL und Audioinformationen verfügen. In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert der zugewiesene Konferenztyp gut, da jeder über eine eigene zugewiesene Konferenz verfügt, und die URL und die Audioinformationen für den konstanten Beitritt helfen, eine schnellere Besprechungsteilnahme zu ermöglichen. Im Szenario mit großen Besprechungen werden die großen Besprechungen jedoch mithilfe eines einzigen Satzes von Benutzeranmeldeinformationen geplant, und dann werden den Besprechungs anfordernden Join-URLs und Audioinformationen zur Verfügung gestellt. In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.

  - Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Diese Einstellung wirkt sich auf den standardmäßigen Besprechungs Zugriffstyp aus, der vom Online Besprechungs-Add-in für lync 2013 geplant wird, wenn keine zugewiesene Konferenz verwendet wird. Die geeignete Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

