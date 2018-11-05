---
title: 'Lync Server 2013: Routing zwischen Trunks'
TOCTitle: Routing zwischen Trunks
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49891022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routing zwischen Trunks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-08_

Lync Server 2013 bietet eine einfache Sitzungsverwaltung mittels Unterstützung des Routings zwischen Trunks. Dank dieser neuen Funktion können in Lync Server Anrufsteuerungsfunktionen in Downstreamtelefoniesystemen bereitgestellt werden. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz weitergeleitet und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. Entsprechend kann Lync Server zwei oder mehr IP-Nebenstellenanlagensysteme miteinander verbinden, sodass Anrufe zwischen Festnetztelefonen aus den verschiedenen IP-Nebenstellenanlagen ausgeführt und angenommen werden können.

Die folgende Abbildung veranschaulicht, wie Lync Server 2013 die Zusammenschaltung eines PSTN-Gateways und einer IP-Nebenstellenanlage ermöglicht.

![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)")

In der nächsten Abbildung wird gezeigt, wie Lync Server 2013 zwei IP-Nebenstellenanlagensysteme miteinander verbindet.

![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)")

