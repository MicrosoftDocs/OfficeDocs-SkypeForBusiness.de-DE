---
title: 'Lync Server 2013: Einrichten der Zertifikate für den Reverseproxy'
TOCTitle: Einrichten der Zertifikate für den Reverseproxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412938(v=OCS.15)
ms:contentKeyID: 49295287
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten der Zertifikate für den Reverseproxy in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Jeder Reverseproxyserver erfordert ein Webserverzertifikat zur Verwendung durch den Überwachungsdienst. Das Webserverzertifikat muss von einer öffentlichen Zertifizierungsstelle ausgestellt werden.

Ausführliche Informationen zu diesen und anderen Voraussetzungen für Zertifikate finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

## So richten Sie ein Webdienstezertifikat für den Reverseproxy ein

  - Der Reverseproxy sollte bereits eingerichtet sein (einschließlich des Webdienstezertifikats). Wenn Sie die erforderlichen Schritte nicht ausgeführt haben, bevor Sie mit der Bereitstellung Ihrer Edgeserver begonnen haben, führen Sie die Schritte in [Einrichten von Reverseproxyservern für Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) aus, um eine Anforderung zu erstellen, das Webdienstezertifikat zu installieren und anschließend die einzelnen Webveröffentlichungsregeln zu erstellen und für die Verwendung des Zertifikats zu konfigurieren.

