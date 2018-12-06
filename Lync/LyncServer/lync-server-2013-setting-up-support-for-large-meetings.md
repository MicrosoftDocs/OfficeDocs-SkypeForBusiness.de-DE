---
title: Einrichten der Unterstützung für große Besprechungen
TOCTitle: Einrichten der Unterstützung für große Besprechungen
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205074(v=OCS.15)
ms:contentKeyID: 49294708
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten der Unterstützung für große Besprechungen

 

_**Letztes Änderungsdatum des Themas:** 2014-05-12_

Wenn Besprechungen mit mehr als 1000 Benutzern unterstützt werden sollen, ist es erforderlich, eine entsprechende Topologie zu erstellen, die Anforderungen an Hardware und Software zu erfüllen und die Umgebung entsprechend zu konfigurieren.

## Anforderungen im Hinblick auf die Topologie

Bei einer einzigen großen Besprechung sind mindestens ein Front-End-Server und ein Back-End-Server erforderlich. Damit jedoch eine hohe Verfügbarkeit geboten werden kann, wird ein Front-End-Server-Pool mit gespiegeltem Back-End-Server empfohlen.

Die Benutzerkonten der Benutzer, die große Besprechungen durchführen, müssen in diesem Pool gehostet werden. Es wird jedoch nicht empfohlen, dass andere Benutzerkonten in diesem Pool gehostet werden. Er sollte nur für diese großen Besprechungen verwendet werden. In diesem Pool sollte ein spezielles Benutzerkonto erstellt werden, das nur zur Durchführung großer Besprechungen verwendet wird. Da die Einstellung für große Besprechungen auf Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme nach sich ziehen. So kann es beispielsweise nicht möglich sein, eine P2P-Sitzung zu einer Besprechung heraufzustufen, wenn ein PSTN-Endpunkt beteiligt ist.

Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Wenn Sie zusätzlich optional eine Sicherung zur Notfallwiederherstellung und ein Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie ihn auch gemeinsam mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum verwenden. Ausführliche Informationen finden Sie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Poolkonfiguration für große Besprechungen](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Poolkonfiguration für große Besprechungen")

Zusätzliche Notizen zur Topologie:

  - Zum Speichern von Besprechungsinhalten und, wenn Archivierungsserver bereitgestellt und aktiviert wurde, zum Speichern der Archivierungsdateien ist eine Dateifreigabe erforderlich. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Weitere Details zum Konfigurieren der Dateifreigabe finden Sie unter [Konfigurieren des Dateispeichers für Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Zur Aktivierung der PowerPoint-Präsentationsfunktion in großen Besprechungen ist ein Office Web Apps-Server erforderlich. Der Office Web Apps-Server kann einem großen Besprechungspool zugeordnet werden, oder es kann auch derselbe Office Web Apps-Server sein, der von anderen Pools an diesem Standort verwendet wurde, an dem der dedizierte Pool bereitgestellt wurde.

  - Bei einem Lastenausgleich für Front-End-Server ist ein Hardwaregerät zum Lastenausgleich für den HTTP-Datenverkehr (z. B. beim Herunterladen von Besprechungsinhalten) erforderlich. DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Ausführliche Informationen finden Sie unter [Anforderungen an den Lastenausgleich für Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Wenn Sie den Monitoring-Server für den dedizierten großen Besprechungspool verwenden möchten, wird empfohlen, den Monitoring-Server und seine Datenbank zu verwenden, die in allen Front-End-Server-Pools in Ihrer Lync Server-Bereitstellung freigegeben werden.

## Hardware- und Softwareanforderungen

Die Hardwareanforderungen für Server in einem dedizierten großen Besprechungspool sind mit denen für Lync Server 2013-Server identisch. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Server in einem dedizierten großen Besprechungspool müssen alle Softwareanforderungen für Lync Server 2013 erfüllen. Ausführliche Informationen zu den Softwareanforderungen finden Sie in den folgenden Dokumentationen:

  - [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Unterstützte Datenbanksoftware in Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Zusätzlich müssen sowohl der Lync Server 2013 und alle Lync Server 2013-Clients über die neuesten Updates verfügen.

## Konfigurationsanforderungen

Es wird empfohlen, eine neue Konferenzrichtlinie speziell für große Besprechungen zu erstellen und diese anschließend den Benutzern zuzuweisen, die auf den dedizierten großen Besprechungspools gehostet werden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:

  - Legen Sie die Option **MaxMeetingSize** auf **1000** fest. (Der Standardwert ist **250**.)

  - Legen Sie die Option **AllowLargeMeetings** auf **True** fest.

  - Legen Sie die Option **EnableAppDesktopSharing** auf **None** fest.

  - Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.

  - Legen Sie die Option **AllowSharedNotes** auf **False** fest.

  - Legen Sie die Option **AllowAnnotations** auf **False** fest.

  - Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.

  - Legen Sie die Option **AllowMultiview** auf **False** fest.

  - Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.


> [!NOTE]
> Damit große Besprechungen mit 1000 Benutzern in Lync Server 2013 untertstützt werden können, ist es erforderlich, dass die Einstellung <STRONG>AllowLargeMeetings</STRONG> in der Konferenzrichtlinie für den Besprechungsplaner auf "True" gesetzt wird. Wenn diese Einstellung auf "True" gesetzt ist, werden die Möglichkeiten von Lync für sehr große Besprechungen optimiert, wenn die Benutzer einer solchen Besprechung beitreten. In einer großen Besprechung wird die initiale vollständige Liste mit Besprechungsteilnehmern von Lync nicht angezeigt oder aktualisiert. Diese Liste stellt einen Leistungsengpass für den Client sowie für Lync Server 2013 dar. In Lync werden dafür nur Informationen zum Benutzer und die Liste mit den Referenten der Besprechung angezeigt. In Lync wird dennoch ordnungsgemäß die Gesamtanzahl der für die großen Besprechungen verfügbaren Teilnehmer angezeigt.



Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen zu deaktivieren, die für große Besprechungen nicht erforderlich sind.

Zusätzlich muss der dedizierte große Besprechungspool konfiguriert werden, sodass jeder Lync Server 2013-Benutzer, der auf dem Pool gehostet wird und für die Verwaltung des Besprechungszeitplans verantwortlich ist, über die erforderlichen Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:

  - Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.

  - Stellen Sie sicher, dass das Kontrollkästchen **Konferenztyp standardmäßig zugewiesen** deaktiviert ist. Mit dieser Einstellung wird gesteuert, ob das Onlinebesprechungs-Add-In für Lync 2013 die Konferenzen immer mithilfe der zugewiesenen Konferenz des Organisators plant. Das bedeutet, dass die geplanten Besprechungen über dieselbe Verbindungs-URL und dieselben Audioinformationen verfügen. In Szenarien der Zusammenarbeit von kleinen Gruppen funktioniert dieser zugewiesene Konferenztyp sehr gut, da jeder Teilnehmer über seine eigene ihm persönlich zugewiesene Konferenz verfügt. Mit einer festen Verbindungs-URL und konstanten Audioinformationen ist eine schnellere Teilnahme an Besprechungen möglich. In Szenarien mit großen Besprechungen planen viele Mitarbeiter vom Support in diesem Bereich die großen Besprechungen mithilfe eines einzigen Satzes von Anmeldeinformationen. Anschließend werden den Antragstellern der Besprechung die Verbindungs-URLs und Audioinformationen zur Verfügung gestellt. In diesem Fall ist es besser, wenn für jede Besprechung eine andere URL verwendet wird.

  - Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Wenn keine zugewiesene Konferenz verwendet wird, beeinflusst diese Einstellung den Standardtyp für den Besprechungszugriff, der von Onlinebesprechungs-Add-In für Lync 2013 geplant worden ist. Die geeignete Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.

