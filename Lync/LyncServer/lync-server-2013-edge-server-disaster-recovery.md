---
title: 'Lync Server 2013: Notfallwiederherstellung für Edgeserver'
TOCTitle: Notfallwiederherstellung für Edgeserver
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49890610
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Notfallwiederherstellung für Edgeserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-03-12_

Wie bei anderen Serverrollen wird die hohe Verfügbarkeit für Ihre Edgeserver am besten durch die Bereitstellung mehrerer Edgeserver in Pools an den einzelnen Standorten gewährleistet. Fällt ein Edgeserver aus, stellen die anderen Server im Pool weiterhin Edgedienste bereit.

Zur Ermöglichung von Notfallwiederherstellungsprozeduren müssen Sie separate Edgeserver an verschiedenen Standorten bereitstellen. Sie müssen Edgepools nicht wie Front-End-Pools explizit zusammenfassen. Bei mehreren Edgepools besteht jedoch die Möglichkeit, die Arbeit fortzusetzen, falls ein Edgepool ausfällt. Die folgenden Abschnitte enthalten ausführliche Informationen zur Notfallwiederherstellung der verschiedenen Funktionen von Edgeservern.

## Remotezugriff

Wenn Sie mehrere Standorte mit jeweils einem Pool mit Edgeservern besitzen und ein gesamter Edgepool ausfällt, funktionieren die Remotezugriffsdienste weiterhin ohne Aktion durch den Administrator. Wenn Sie Edgepools an verschiedenen Standorten erstellen, können Sie nicht denselben FQDN verwenden. Jeder Edgepool muss eindeutige FQDNs (intern und extern) haben. Die Edgepools verwenden keine Reverseproxy-Veröffentlichungsregeln, um mit den Front-End-Servern zu kommunizieren. Ein automatisches Failover findet statt, wenn der Client die DNS-Servicedatensätze für den Remotezugriff erneut abfragt und Remotebenutzer zu den Edgeservern an einem anderen Standort weitergeleitet werden. Der Client probiert jeden externen Edge-FQDN gemäß der Priorität der DNS-SRV-Datensätze aus.


> [!NOTE]
> Damit das Failover reibungslos funktioniert, muss die Firewall zulassen, dass die Front-End-Server von jedem Pool mit allen Edgeservern kommunizieren können.



## Partnerverbund

Für Partnerverbundbeziehungen mit anderen Organisationen mit Lync Server funktionieren eingehende Partnerverbundanforderungen weiterhin, solange Sie jeden Edgepool mit einer anderen Priorität in Ihren SRV-Einträgen konfiguriert haben. Für Partnerverbundanforderungen an einen ausgefallenen Edgepool wird ein Failback ausgeführt und anschließend eine Verbindung mit einem ausgeführten Edgepool hergestellt.

Der ausgehende Partnerverbund wird immer über einen veröffentlichten Edgepool oder Edgeserver in der Organisation eingerichtet. Fällt dieser Edgepool aus, müssen Sie mit dem Topologie-Generator die ausgehende Partnerverbundroute ändern, sodass sie einen Edgepool verwendet, der noch ausgeführt wird. Ausführliche Informationen finden Sie unter [Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

## XMPP-Partnerverbund

Beim XMPP-Partnerverbund treten beim ausgehenden und eingehenden Datenverkehr Fehler auf, wenn der als XMPP-Verbundpartner-Gateway festgelegte Edgepool ausfällt. Damit der XMPP-Partnerverbund wieder funktioniert, müssen Sie die Verwendung eines anderen Edgepools durch den XMPP-Partnerverbund festlegen. Ausführliche Informationen finden Sie unter [Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

## Ausfall des Edgepools bei weiterer Ausführung des Front-End-Pools

Falls ein Edgepool an einem Standort ausfällt, der Front-End-Pool an diesem Standort jedoch weiterhin ausgeführt wird, müssen Sie den Front-End-Pool so ändern, dass er einen anderen Edgepool an einem anderen Standort verwendet, während der erste Edgepool nicht verfügbar ist. Weitere Informationen finden Sie unter [Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

