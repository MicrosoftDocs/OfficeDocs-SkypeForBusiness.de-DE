---
title: 'Lync Server 2013: 9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver'
TOCTitle: 9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398903(v=OCS.15)
ms:contentKeyID: 49295488
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Der Vermittlungsserver verfügt über erweiterte Funktionen für die ordnungsgemäße Interaktion mit Anbietern von E9-1-1-Diensten (9-1-1 \[erweitert\]). Für den Vermittlungsserver ist keine besondere Konfiguration erforderlich. Die für E9-1-1-Interaktion benötigten SIP-Erweiterungen sind standardmäßig im SIP-Protokoll des Vermittlungsservers enthalten, damit der Server mit einem Gatewaypeer (einem PSTN-Gateway, einer IP-Nebenstellenanlage oder dem SBC eines Internettelefoniedienstanbieters, einschließlich E9-1-1-Dienstanbietern) interagieren kann.

Ob ein SIP-Trunk zu einem E9-1-1-Dienstanbieter in einem vorhandenen Vermittlungsserverpool terminiert werden kann oder eigenständige Vermittlungsserver erfordert, hängt davon ab, ob der E9-1-1-SBC mit einem Vermittlungsserverpool interagieren kann. Weitere Informationen finden Sie unter [M:N-Trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).

