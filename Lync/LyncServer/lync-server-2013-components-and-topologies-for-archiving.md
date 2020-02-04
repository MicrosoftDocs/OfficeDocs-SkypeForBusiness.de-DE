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
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Komponenten und Topologien für die Archivierung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Wenn Sie lync Server 2013-Chat-und Konferenzinhalte archivieren möchten, können Sie die Archivierung in lync Server implementieren.

<div>

## <a name="archiving-components"></a>Archivierungskomponenten

Das Archivierungsfeature umfasst die folgenden Komponenten:

  - **Archivierungs-Agents**. Archivierungs-Agents (auch bekannt als Unified Data Collection Agents) werden auf jedem Front-End-Pool und Standard Edition-Server automatisch installiert und aktiviert. Obwohl Archivierungs-Agents automatisch aktiviert werden, werden keine Nachrichten erfasst, bis die Archivierung aktiviert und entsprechend konfiguriert ist.

  - **Archivierungsdatenspeicher**. Bei der Datenspeicherung für lync Server 2013 kann es sich um eine der folgenden Optionen handeln:
    
      - Exchange 2013-Speicher. Wenn Sie die Microsoft Exchange-Integrations Option aktivieren, verwenden Benutzerpostfächer, die sich auf dem Exchange 2013-Server befinden, den Exchange 2013-Speicher für archivierte Daten, jedoch nur, wenn die Postfächer in-situ-Speicher abgelegt wurden.
    
      - SQL Server-Speicher. Wenn Sie Benutzer in Ihrer Bereitstellung haben, die sich in lync Server 2013 befinden, können Sie Archivierungsdatenbanken einrichten, die eine unterstützte Version von SQL Server ausführen, um die Archivierung für diese Benutzer zu ermöglichen.

Die Archivierung erfordert auch Dateispeicher, doch die Archivierung verwendet denselben Dateispeicher wie die Front-End-Server oder den Standard Edition-Server.

Eine Liste der Hardware-und Softwareanforderungen für die Archivierung finden Sie unter unter [stützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) und [Server Software und Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Dokumentation zur Unterstützung.

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

Sie können die Archivierung in jedem Pool mit Benutzern bereitstellen, für die Archivierungsunterstützung erforderlich ist. Die Archivierung wird auf Front-End-Servern in Enterprise Edition-Pools und auf Standard Edition-Servern ausgeführt. Archivierungsdaten Speicher können wie folgt lauten:

  - In Exchange 2013-Speicher integriert

  - Bereitstellung mithilfe separater SQL Server-Datenbanken

Wenn Ihre Exchange 2013-Bereitstellung nicht alle Benutzer in ihrer lync Server-Bereitstellung umfasst, müssen Sie die Microsoft Exchange-Integration für die Benutzer verwenden, deren Postfächer auf Exchange 2013-Servern zu Hause sind, und Sie müssen getrennte SQL Server-Datenbanken für alle anderen bereitstellen. Lync-Benutzer, die für die Archivierung verwendet werden sollen.

</div>

<div>

## <a name="supported-collocation"></a>Unterstützte Anordnung

Lync Server 2013 unterstützt eine Vielzahl von Szenarien für die Zusammenfassung, wodurch Sie Flexibilität beim Speichern von Hardwarekosten haben, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie über eine kleine Organisation verfügen) oder einzelne Komponenten auf verschiedenen Servern ausführen (wenn Sie über eine größere Organisation, die Skalierbarkeit und Leistung benötigt). Skalierbarkeits Faktoren sollten sicherlich berücksichtigt werden, bevor Sie entscheiden, ob Sie Komponenten collocate.

Die Archivierung wird auf den Front-End-Servern eines Pools oder von Standard Edition-Servern bereitgestellt. Details zu den Komponenten, die sich dort befinden können, finden Sie unter [unterstützte Server Zusammenstellung in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.

Wenn Sie separate SQL Server-Datenbanken für die Archivierung verwenden, können Sie die Archivierungsdatenbank mit einer der folgenden collocate, anstatt Sie mit dem Exchange 2013-Speicher zu integrieren.

  - Überwachungsdatenbank

  - Back-End-Datenbank eines Enterprise Edition-Front-End-Pools

<div>


> [!NOTE]  
> Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden.



</div>

Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, der Back-End-Datenbank oder beider Datenbanken collocate, können Sie entweder eine einzelne SQL-Instanz für eine oder alle Datenbanken verwenden, oder Sie können für jede Datenbank eine separate SQL-Instanz verwenden, mit den folgenden Einschränkung

  - Jede SQL-Instanz kann nur eine einzige Back-End-Datenbank, eine einzige Überwachungsdatenbank und eine einzelne Archivierungsdatenbank enthalten.

Ausführliche Informationen zur Anordnung aller Serverrollen und Datenbanken finden Sie unter [unterstützte Server in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.

</div>

</div>

<span> </span>

</div>

</div>

</div>

