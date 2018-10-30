---
title: 'Lync Server 2013: Anfordern von Zertifikaten für Edgekomponenten'
TOCTitle: Anfordern von Zertifikaten für Edgekomponenten
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398708(v=OCS.15)
ms:contentKeyID: 49294691
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anfordern von Zertifikaten für Edgekomponenten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Die erforderlichen Zertifikate für die Unterstützung des Zugriffs durch externe Benutzer umfassen Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden, sowie Zertifikate, die von einer internen Unternehmenszertifizierungsstelle ausgestellt wurden:

  - Die für die externe Schnittstelle von Edgeserver und den Reverseproxy erforderlichen Zertifikate müssen von einer öffentlichen Zertifizierungsstelle ausgestellt werden.

  - Die für die interne Schnittstelle benötigten Zertifikate können entweder von einer öffentlichen oder von einer internen Unternehmenszertifizierungsstelle ausgestellt werden. Zum Reduzieren der Kosten bei der Verwendung öffentlicher Zertifikate wird zur Erstellung dieser Zertifikate die Verwendung einer internen Windows Server 2008-, Windows Server 2008 R2-, Windows Server 2012- oder Windows Server 2012 R2- Zertifizierungsstelle empfohlen.


> [!IMPORTANT]
> Da die Verarbeitung von Zertifikatanforderungen (insbesondere bei Anforderungen an öffentliche Zertifizierungsstellen) mit einem gewissen Zeitaufwand verbunden sein kann, sollten Sie die Zertifikate für Ihre Edgeserver frühzeitig anfordern, um ihre Verfügbarkeit sicherzustellen, wenn Sie mit der Bereitstellung Ihrer Edgeserver-Komponenten beginnen. Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013</A>.



Wenngleich Sie eine öffentliche Zertifizierungsstelle für das interne Edgezertifikat verwenden können, wird die Verwendung einer internen Unternehmenszertifizierungsstelle für diese anderen Zertifikate empfohlen, um die Kosten für Zertifikate zu minimieren. Eine Zusammenfassung der Anforderungen für Zertifikate für Edgeserver finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).


> [!NOTE]
> Bei der Installation eines Edgeserver umfasst Setup einen Zertifikats-Assistenten, der die Aufgaben zum Anfordern, Zuweisen und Installieren von Zertifikaten vereinfacht (eine Beschreibung finden Sie im Abschnitt <A href="lync-server-2013-set-up-edge-certificates.md">Einrichten von Edgezertifikaten für Lync Server 2013</A>). Wenn Sie die Zertifikate vor der Installation eines Edgeserver anfordern möchten (um bei der eigentlichen Bereitstellung der Edgeserver-Komponenten Zeit zu sparen), können Sie zu diesem Zweck interne Server verwenden. Sie müssen lediglich sicherstellen, dass die Zertifikate exportierbar sind und alle erforderlichen alternativen Antragstellernamen enthalten. Die Verfahren zur Verwendung interner Server zum Anfordern von Zertifikaten sind in dieser Dokumentation nicht beschrieben.



## Anfordern von Zertifikaten von einer öffentlichen Zertifizierungsstelle

Für die Bereitstellung Ihres Edgeserver ist ein einzelnes öffentliches Zertifikat für die externen Schnittstellen der Edgeserver erforderlich, das für den Zugriffs-Edgedienst-, den Webkonferenz-Edgedienst-Dienst und den A/V-Authentifizierungsdienst verwendet wird. Dieses Zertifikat muss einen exportierbaren privaten Schlüssel enthalten, damit sichergestellt ist, dass der A/V-Authentifizierungsdienst auf allen Edgeserver in einem Pool die gleichen Schlüssel verwendet. Für den Reverseproxy, der mit Microsoft Internet Security and Acceleration Server (ISA) 2006 oder Microsoft Forefront Threat Management Gateway 2010 eingesetzt wird, ist ebenfalls ein öffentliches Zertifikat erforderlich.

## Anfordern von Zertifikaten von einer internen Unternehmenszertifizierungsstelle

Die für die interne Edgeschnittstelle benötigten Zertifikate können entweder von einer öffentlichen oder von einer internen Zertifizierungsstelle ausgestellt werden. Mithilfe einer internen Unternehmenszertifizierungsstelle können Sie die Kosten für Zertifikate minimieren. Wenn in Ihrer Organisation eine interne Zertifizierungsstelle bereitgestellt wurde, sollten die Zertifikate für die interne Edgeschnittstelle durch die interne Zertifizierungsstelle ausgegeben werden. Das Verwenden einer internen Unternehmenszertifizierungsstelle für interne Zertifikate kann zu einer erheblichen Senkung der Kosten für Zertifikate beitragen.

Eine Zusammenfassung der Zertifikatanforderungen für Edgekomponenten finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Ausführliche Informationen zum Verwenden einer öffentlichen Zertifizierungsstelle für das Abrufen von Zertifikaten finden Sie unter [Anfordern von Zertifikaten für Edgekomponenten in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Ausführliche Informationen zum Anfordern, Installieren und Zuweisen von Zertifikaten finden Sie unter [Einrichten von Edgezertifikaten für Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

