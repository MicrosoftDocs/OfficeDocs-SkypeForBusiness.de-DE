---
title: 'Lync Server 2013: Active Directory-Unterstützung'
TOCTitle: Active Directory-Unterstützung
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425756(v=OCS.15)
ms:contentKeyID: 49293494
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Active Directory-Unterstützung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Folgende lokale Topologien für Active Directory-Domänendienste werden von Lync Server 2013 unterstützt:

  - Einzelne Gesamtstruktur mit einzelner Domäne

  - Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

  - Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

  - Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

  - Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur


> [!NOTE]
> Lync Server 2013 unterstützt keine Domänen mit einfacher Bezeichnung. Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne namens <STRONG>contoso.local</STRONG> unterstützt, eine Stammdomäne mit einfacher Bezeichnung namens <STRONG>local</STRONG> hingegen nicht. Ausführliche Informationen finden Sie im Microsoft&nbsp;Knowledge Base-Artikel&nbsp;300684 "Informationen zur Konfiguration von Active Directory-Domänen mit DNS-Namen mit einfacher Bezeichnung" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=143752">http://go.microsoft.com/fwlink/?linkid=143752</A>.




> [!NOTE]
> Lync Server 2013 unterstützt die Umbenennung von Domänen nicht. Wenn Sie eine Domäne umbenennen müssen, in der Lync Server bereitgestellt ist, müssen Sie zuerst Lync Server deinstallieren, die Domäne umbenennen und Lync Server dann wieder installieren.



Ausführliche Informationen zu unterstützten Topologien und Anforderungen für lokale Bereitstellungen finden Sie unter [Anforderungen, Unterstützung und Topologien der Active Directory-Domänendienste in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in der Planungsdokumentation.

