---
title: 'Lync Server 2013: Vorabanforderung von Zertifikaten (optional)'
TOCTitle: Vorabanforderung von Zertifikaten (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412733(v=OCS.15)
ms:contentKeyID: 49294901
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorabanforderung von Zertifikaten (optional) für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Zertifikate sind für alle internen Server erforderlich, auf denen Lync Server 2013 ausgeführt wird. Dies gilt auch für jeden Enterprise Edition- Front-End-Server, - Standard Edition-Server, - Director, - Edgeserver und alle eigenständigen Vermittlungsserver. Wenngleich für interne Server die Verwendung einer internen Unternehmenszertifizierungsstelle empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden. Ausführliche Informationen zu Zertifikatanforderungen und zur Verwendung einer öffentlichen Zertifizierungsstelle finden Sie unter [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

Lync Server 2013-Setup umfasst den Zertifikat-Assistenten, der die Aufgaben zum Anfordern, Zuweisen und Installieren von Zertifikaten während der Bereitstellung vereinfacht. Wenn Sie vor der Installation von Servern Zertifikate anfordern möchten (um beispielsweise während der eigentlichen Serverbereitstellung Zeit zu sparen), können Sie hierzu einen Computer verwenden, auf dem die Lync Server 2013-Verwaltungstools installiert sind, oder ein in Ihrer Organisation definiertes Verfahren zur Zertifikatanforderung einsetzen, sofern Sie sicherstellen, dass die Zertifikate exportiert werden können und alle erforderlichen alternativen Antragstellernamen enthalten. Die vorzeitige Anforderung von Zertifikaten ist optional; wenn Sie sie nicht im Voraus anfordern, müssen Sie dies im Rahmen des Setups für jeden Server nachholen, für den ein Zertifikat erforderlich ist.

Diese Bereitstellungsdokumentation enthält Verfahren zur Verwendung des Zertifikat-Assistenten zum Anfordern von Zertifikaten im Rahmen des Setup-Prozesses. Beschreibungen hierzu finden Sie in den Abschnitten [Konfigurieren von Zertifikaten für Server in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Konfigurieren von Zertifikaten für den Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) und [Installieren der Dateien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in dieser Bereitstellungsdokumentation. Wenn Sie Zertifikate im Voraus anfordern, müssen Sie die Verfahren zur Zertifikatbereitstellung in den betreffenden Abschnitten entsprechend ändern, da die Zertifikate nicht zum Bereitstellungszeitpunkt angefordert, sondern importiert und zugewiesen werden müssen.


> [!NOTE]
> Lync Server 2013 umfasst die Unterstützung für SHA-256-Zertifikate für Verbindungen von Clients, auf denen die Betriebssysteme Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2 und Windows 7 sowie Lync Phone Edition ausgeführt werden. Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.


