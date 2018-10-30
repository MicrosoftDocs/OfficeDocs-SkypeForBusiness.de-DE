---
title: 'Lync Server 2013: Komponenten und Topologien für die Archivierung'
TOCTitle: Komponenten und Topologien für die Archivierung
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204916(v=OCS.15)
ms:contentKeyID: 49294075
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten und Topologien für die Archivierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Wenn Sie Sofortnachrichten- und Konferenzinhalte von Lync Server 2013 archivieren möchten, können Sie die Archivierung in Lync Server implementieren.

## Archivierungskomponenten

Die Archivierungsfunktion beinhaltet folgende Komponenten:

  - **Archivierungs-Agents**. Archivierungs-Agents (die auch als einheitliche Datenerfassungs-Agents bezeichnet werden) werden automatisch in jedem Front-End-Pool und auf jedem Standard Edition-Server installiert und aktiviert. Auch wenn die Archivierungs-Agents automatisch aktiviert werden, werden erst dann Nachrichten erfasst, sobald die Archivierung aktiviert und entsprechend konfiguriert wurde.

  - **Datenspeicher für die Archivierung**. Sie können folgende Datenspeicher für Lync Server 2013 verwenden:
    
      - Exchange 2013-Speicher. Wenn Sie die Microsoft Exchange-Integrationsoption aktivieren, wird der Exchange 2013-Speicher für archivierte Daten der Postfächer von Benutzern verwendet, die auf dem Exchange 2013-Server verwaltet werden. Dies gilt jedoch nur, wenn sich die Postfächer im Compliance-Archiv befinden.
    
      - SQL Server-Speicher. Wenn Ihre Bereitstellung Benutzer aufweist, die in Lync Server 2013 verwaltet werden, können Sie Archivierungsdatenbanken einrichten, die eine unterstützte Version von SQL Server ausführen, um die Archivierung für diese Benutzer zu ermöglichen.

Die Archivierung erfordert auch Dateispeicher. Es wird jedoch der gleiche Dateispeicher wie für Front-End- und Standard Edition-Server verwendet.

Eine Liste der Hardware- und Softwareanforderungen finden in der Unterstützungsdokumentation unter [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) und unter [Serversoftware- und Infrastrukturunterstützung in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

## Unterstützte Topologien

Die Archivierung wird in allen Pools bereitgestellt, deren Benutzer die entsprechende Funktion benötigen. Die Archivierung wird auf Front-End-Server in Enterprise Edition-Pools und auf Standard Edition-Server ausgeführt. Folgende Datenspeicher können für die Archivierung verwendet werden:

  - Datenspeicher, die in Exchange 2013-Speicher integriert sind

  - Datenspeicher, der mit separaten SQL Server-Datenbanken bereitgestellt wird

Wenn Ihre Bereitstellung von Exchange 2013 nicht alle Benutzer in Ihrer Bereitstellung von Lync Server umfasst, müssen Sie die Microsoft Exchange-Integration für die Benutzer verwenden, deren Postfächer auf Exchange 2013-Servern verwaltet werden. Darüber hinaus müssen Sie separate SQL Server-Datenbanken für alle anderen Lync-Benutzer zur Archivierung bereitstellen.

## Unterstützte Kollokation

Lync Server 2013 unterstützt eine Vielzahl von Szenarien für das Verbinden, sodass Sie Ihr System flexibel bereitstellen und dabei Hardwarekosten einsparen können: Wenn Sie über eine kleine Organisation verfügen, können Sie mehrere Komponenten auf einem Server ausführen. Wenn Ihre Organisation größer ist und mehr Skalierbarkeit und Leistung erfordert, können Sie separate Komponenten auf verschiedenen Servern ausführen. Der Faktor Skalierbarkeit sollte auf jeden Fall bedacht werden, bevor Sie entscheiden, ob Sie verschiedene Komponenten verbinden möchten.

Die Archivierung wird auf den Front-End-Server eines Pools oder auf Standard Edition-Server bereitgestellt. Nähere Informationen zu den Komponenten, die verbunden werden können, finden Sie in der Unterstützungsdokumentation unter [Unterstützte Serverzusammenstellungen in Lync Server 2013](lync-server-2013-supported-server-collocation.md).

Wenn Sie separate SQL Server-Datenbanken für die Archivierung verwenden, können Sie die Archivierungsdatenbank anstelle der oder zusätzlich zur Integration des Speichers in Exchange 2013 mit folgenden Komponenten verbinden:

  - Überwachungsdatenbank

  - Back-End-Datenbank eines Enterprise Edition-Front-End-Pools


> [!NOTE]
> Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden.



Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, der Back-End-Datenbank oder mit beiden verbinden, können Sie eine einzelne SQL-Instanz für eine oder für alle Datenbanken verwenden. Sie können auch eine separate SQL-Instanz für jede Datenbank verwenden. Dabei gelten jedoch folgende Einschränkungen:

  - Jede SQL-Instanz darf nur jeweils eine einzelne Back-End-Datenbank, eine einzelne Überwachungsdatenbank und eine einzelne Archivierungsdatenbank enthalten.

Nähere Informationen zum gemeinsamen Betrieb aller Serverrollen und Datenbanken finden Sie unter [Unterstützte Serverzusammenstellungen in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.

