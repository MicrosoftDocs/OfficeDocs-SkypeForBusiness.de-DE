---
title: 'Lync Server 2013: Technische Voraussetzungen für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cc8a64ee7a49971660e7435a51c816bd4367e26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Technische Voraussetzungen für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Die technischen Voraussetzungen für lync Server 2013 umfassen die folgenden:

  - Infrastrukturanforderungen.

  - Erforderliche Software, die für die Archivierung installiert werden muss.

  - Datenspeicheranforderungen für die Archivierung

  - Skalierungsanforderungen und Überlegungen für die Archivierungs Bereitstellung.

  - Leistungsanforderungen und Überlegungen für Ihre Archivierungsdatenbanken.

<div>


> [!NOTE]  
> Skalierungs-und Leistungsinformationen stehen in dieser lync Server 2013-Version nicht zur Verfügung.



</div>

<div>

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen

Die Anforderungen der Archivierungsinfrastruktur für lync Server 2013 sind identisch mit der Bereitstellung von lync Server 2013. Ausführliche Informationen finden Sie unter [Ermitteln der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.

</div>

<div>

## <a name="archiving-prerequisites"></a>Archivierungs Voraussetzungen

Lync Server 2013 optimiert die Voraussetzungen für die Archivierung aus folgenden Gründen:

  - Der Archivierungsserver ist keine Serverrolle mehr. Stattdessen werden Unified Data Collection-Agents auf den Front-End-Servern in einem Pool und auf Standard Edition-Servern ausgeführt, um Daten für die Archivierung zu erfassen, sodass Sie keine separaten Systemplattformen für die Archivierung einrichten.

  - Bei der Archivierung wird der lync Server 2013-Dateispeicher zur temporären Speicherung von Besprechungsinhalts Dateien verwendet, sodass Sie keinen separaten Dateispeicher für die Archivierung einrichten.

  - In lync Server 2013 ist Message Queuing nicht erforderlich.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Datenspeicheranforderungen für die Archivierung

Darüber hinaus müssen Sie die Infrastruktur für die Archivierung von Speicher einrichten. Dazu gehören eine oder beide der folgenden Optionen:

  - **Microsoft Exchange-Speicher**. Besprechungsinhalts Dateien wie PowerPoint-Präsentationen werden als Anlagen archiviert. Wenn Sie die Microsoft Exchange-Integration verwenden möchten, damit lync-Archivdaten mit Exchange-Kompatibilitätsdaten gespeichert werden, müssen Sie Exchange 2013 für Ihre Exchange-Bereitstellung verwenden und sicherstellen, dass die maximale Speichergröße die Speicherung der Besprechungsinhalts Dateien unterstützt. Wenn Sie die Archivierung mithilfe der Microsoft Exchange-Integrations Option bereitstellen, werden lync-Archivdaten nur für die Benutzer, die auf Ihren Exchange 2013-Servern gehostet werden, mit Exchange 2013-Kompatibilitätsdaten gespeichert. Sie müssen Exchange 2013 vor der Bereitstellung und Aktivierung der Archivierung mithilfe der Microsoft Exchange-Integrations Option bereitstellen. Wenn Sie Exchange 2013-Speicher verwenden, müssen Sie keine separaten SQL Server-Datenbanken für die Archivierung bereitstellen, es sei denn, Sie verfügen über lync-Benutzer, die nicht auf Ihren Exchange 2013-Servern gehostet sind.

  - **SQL Server-Datenbankspeicher für die Archivierung**. Wenn Sie Benutzer unterstützen möchten, die nicht auf Exchange 2013-Servern gehostet werden, oder wenn Sie die Microsoft Exchange-Integrations Option nicht verwenden möchten, müssen Sie den Archivierungsspeicher mithilfe einer SQL Server-Datenbank bereitstellen. Lync Server 2013 unterstützt die folgenden 64-Bit-Versionen von SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express und Microsoft SQL Server 2012 Express werden für die Archivierung nicht unterstützt. 32-Bit-Versionen von SQL Server werden nicht unterstützt. Weitere SQL Server-Anforderungen und-Einschränkungen finden Sie unter unter <A href="lync-server-2013-database-software-support.md">Stützung von Datenbanksoftware in lync Server 2013</A> in der Planungsdokumentation oder in der Dokumentation zur Unterstützung.

    
    </div>
    
    Sie müssen die SQL Server-Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren können. Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen der Topologie erstellen. Sie können die Datenbank auch später erstellen, auch als Teil des Installationsvorgangs. Ausführliche Informationen zu SQL Server finden Sie im SQL Server TechCenter unter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).

</div>

</div>

<span> </span>

</div>

</div>

</div>

