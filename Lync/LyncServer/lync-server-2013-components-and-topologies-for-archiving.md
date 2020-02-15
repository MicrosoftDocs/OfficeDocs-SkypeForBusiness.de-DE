---
title: 'Lync Server 2013: Komponenten und Topologien für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a762219ef6cbecab47dcaeda313ff49dba51ed0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Komponenten und Topologien für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Wenn Sie lync Server 2013 Chat-und Konferenzinhalte archivieren möchten, können Sie die Archivierung in lync Server implementieren.

<div>

## <a name="archiving-components"></a>Archivierungskomponenten

Die Archivierungsfunktion beinhaltet folgende Komponenten:

  - **Archivierungs-Agents**. Archivierungs-Agents (die auch als einheitliche Datenerfassungs-Agents bezeichnet werden) werden automatisch in jedem Front-End-Pool und auf jedem Standard Edition-Server installiert und aktiviert. Auch wenn die Archivierungs-Agents automatisch aktiviert werden, werden erst dann Nachrichten erfasst, sobald die Archivierung aktiviert und entsprechend konfiguriert wurde.

  - **Datenspeicher für die Archivierung**. Der Datenspeicher für lync Server 2013 kann einer der folgenden Werte sein:
    
      - Exchange 2013 Speicher. Wenn Sie die Option für die Microsoft Exchange Integration aktivieren, verwenden Benutzerpostfächer, die auf dem Exchange 2013-Server verwaltet werden, Exchange 2013 Speicher für archivierte Daten, jedoch nur, wenn die Postfächer im Compliance-Archiv platziert wurden.
    
      - SQL Server Speicher. Wenn Sie über Benutzer in Ihrer Bereitstellung verfügen, die in lync Server 2013 verwaltet werden, können Sie Archivierungsdatenbanken einrichten, die eine unterstützte Version von SQL Server ausführen, um die Archivierung für diese Benutzer zu aktivieren.

Die Archivierung erfordert auch Dateispeicher. Es wird jedoch der gleiche Dateispeicher wie für Front-End- und Standard Edition-Server verwendet.

Eine Liste der Hardware-und Softwareanforderungen für die Archivierung finden Sie unter [Supported Hardware for lync Server 2013](lync-server-2013-supported-hardware.md) and [Server Software and Infrastructure Support in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Unterstützungsdokumentation.

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

Die Archivierung wird in allen Pools bereitgestellt, deren Benutzer die entsprechende Funktion benötigen. Die Archivierung wird auf Front-End-Servern in Enterprise Edition-Pools und auf Standard Edition-Servern ausgeführt. Folgende Datenspeicher können für die Archivierung verwendet werden:

  - Integriert in Exchange 2013 Speicher

  - Bereitstellung mithilfe separater SQL Server-Datenbanken

Wenn Ihre Exchange 2013-Bereitstellung nicht alle Benutzer in ihrer lync Server-Bereitstellung enthält, müssen Sie Microsoft Exchange Integration für die Benutzer verwenden, deren Postfächer auf Exchange 2013 Servern gespeichert sind, und Sie müssen separate SQL Server-Datenbanken für alle anderen bereitstellen. Lync-Benutzer, die für die Archivierung verwendet werden sollen.

</div>

<div>

## <a name="supported-collocation"></a>Unterstützte Zusammenstellungen

Lync Server 2013 unterstützt eine Vielzahl von Zusammenstellungs Szenarien, die Ihnen die Möglichkeit bieten, Hardwarekosten zu sparen, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie eine kleine Organisation haben) oder einzelne Komponenten auf unterschiedlichen Servern ausführen (wenn Sie über einen größeren Organisation, die Skalierbarkeit und Leistung benötigt). Skalierbarkeits Faktoren sollten sicherlich berücksichtigt werden, bevor Sie entscheiden, ob Sie Komponenten collocate.

Die Archivierung wird auf den Front-End-Servern eines Pools oder Standard Edition-Servers bereitgestellt. Ausführliche Informationen zu den Komponenten, die dort zusammengefasst werden können, finden Sie unter [unterstützte Server](lync-server-2013-supported-server-collocation.md) Zusammenstellungen in lync Server 2013 in der Unterstützungsdokumentation.

Wenn Sie separate SQL Server-Datenbanken für die Archivierung verwenden, können Sie anstelle von oder zusätzlich zur Integration von Speicher in Exchange 2013 Speicher die Archivierungsdatenbank mit einer der folgenden collocate:

  - Überwachungsdatenbank

  - Back-End-Datenbank eines Enterprise Edition-Front-End-Pools

<div>


> [!NOTE]  
> Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden.



</div>

Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, der Back-End-Datenbank oder mit beiden verbinden, können Sie eine einzelne SQL-Instanz für eine oder für alle Datenbanken verwenden. Sie können auch eine separate SQL-Instanz für jede Datenbank verwenden. Dabei gelten jedoch folgende Einschränkungen:

  - Jede SQL-Instanz darf nur jeweils eine einzelne Back-End-Datenbank, eine einzelne Überwachungsdatenbank und eine einzelne Archivierungsdatenbank enthalten.

Ausführliche Informationen zur gemeinsamen Nutzung aller Serverrollen und Datenbanken finden Sie unter [Supported Server Colocation in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

