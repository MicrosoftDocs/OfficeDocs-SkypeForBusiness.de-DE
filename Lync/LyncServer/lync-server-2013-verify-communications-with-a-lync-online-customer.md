---
title: Überprüfen der Kommunikation mithilfe eines Lync Online-Kunden
TOCTitle: Überprüfen der Kommunikation mithilfe eines Lync Online-Kunden
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202189(v=OCS.15)
ms:contentKeyID: 49295377
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Kommunikation mithilfe eines Lync Online-Kunden

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Führen Sie die folgenden Schritte aus, um den Lync-Benutzern in Ihrer Organisation die Kommunikation mit Benutzern eines Microsoft Lync Online 2010-Kunden zu ermöglichen:

  - Erfüllen aller Voraussetzungen. Dies umfasst die Bereitstellung Ihrer internen Server und Edgeserver, Aktivierung der Unterstützung für den Partnerverbund für Ihre Organisation und das Einrichten von Benutzerkonten. Weitere Informationen finden Sie unter [Voraussetzungen für den Partnerverbund mit einem Lync Online-Kunden](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Konfigurieren der Unterstützung des Domänenzugriffs für Ihre interne Datenbank. Dies umfasst das Erstellen eines Eintrags für einen Hostinganbieter und das Konfigurieren Ihrer Bereitstellung für den Zugriff von der Domäne des Lync Online-Kunden. Weitere Informationen finden Sie unter [Konfigurieren der Unterstützung des Partnerverbunds für eine Lync Online-Domäne](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Konfigurieren Ihres Benutzerkontos für die Unterstützung für den Partnerverbund. Weitere Informationen finden Sie unter [Konfigurieren des Benutzerzugriffs für den Partnerverbund mit einem Lync Online-Kunden](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Wenn Sie alle diese Schritte ausgeführt haben und der Administrator des Lync Online 2010-Kunden die gesamte Konfiguration des Onlinedienstes zur Unterstützung für den Partnerverbund mit Ihrer Organisation durchgeführt hat, überprüfen Sie die Kommunikation zwischen einem internen Benutzer Ihrer Organisation und einem Benutzer des Lync Online-Kunden. Falls die Kommunikation nicht erfolgreich ist, verwenden Sie das Protokollierungstool Ihres Edgeservers, um Protokoll- und Verlaufsdateien aufzuzeichnen, die Sie für die Problembehandlung verwenden können. Weitere Informationen zur Verwendung des Protokollierungstools finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation. Ausführliche Informationen zum Protokollierungstool finden Sie in der Dokumentation zum Lync Server 2010-Protokollierungstool in der TechNet-Bibliothek unter [http://go.microsoft.com/fwlink/?linkid=199265\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=199265%26clcid=0x407).

