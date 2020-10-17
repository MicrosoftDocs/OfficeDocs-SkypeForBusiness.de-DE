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
ms.openlocfilehash: 0f0d1b609f7e053823de68363059d7c8b35c0659
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533932"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Technische Anforderungen für die Archivierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Lync Server 2013 technische Anforderungen umfassen Folgendes:

  - Infrastrukturanforderungen.

  - Erforderliche Software, die für die Archivierung installiert werden muss.

  - Datenspeicheranforderungen für die Archivierung.

  - Skalierungsanforderungen und Überlegungen für die Archivierungs Bereitstellung.

  - Leistungsanforderungen und Überlegungen für Ihre Archivierungsdatenbanken.

<div>


> [!NOTE]  
> Skalierungs-und Leistungsinformationen stehen in dieser lync Server 2013 Version nicht zur Verfügung.



</div>

<div>

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen

Lync Server 2013 Anforderungen an die Archivierungsinfrastruktur entsprechen denen für die Bereitstellung von lync Server 2013. Ausführliche Informationen finden Sie unter [bestimmen der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.

</div>

<div>

## <a name="archiving-prerequisites"></a>Voraussetzungen für die Archivierung

Lync Server 2013 rationalisiert die Voraussetzungen für die Archivierung aus folgenden Gründen:

  - Archivierungsserver ist keine Server Rolle mehr. Stattdessen werden einheitliche Datenerfassungs-Agents auf den Front-End-Servern in einem Pool-und Standard Edition-Server ausgeführt, um Daten für die Archivierung aufzuzeichnen, sodass Sie keine separaten Systemplattformen für die Archivierung einrichten.

  - Bei der Archivierung wird der lync Server 2013 Dateispeicher für die temporäre Speicherung von Besprechungsinhalts Dateien verwendet, sodass Sie keinen separaten Dateispeicher für die Archivierung einrichten.

  - In lync Server 2013 ist Message Queuing nicht erforderlich.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Datenspeicheranforderungen für die Archivierung

Darüber hinaus müssen Sie die Infrastruktur für die Archivierung von Speicher einrichten. Dies umfasst eine oder beide der folgenden:

  - **Microsoft Exchange Speicher**. Besprechungsinhalts Dateien wie PowerPoint-Präsentationen werden als Anlagen archiviert. Wenn Sie Microsoft Exchange Integration verwenden möchten, damit lync-Archivdaten mit Exchange-Konformitätsdaten gespeichert werden, müssen Sie Exchange 2013 für Ihre Exchange-Bereitstellung verwenden und sicherstellen, dass die maximale Speichergröße die Speicherung der Besprechungsinhalts Dateien unterstützt. Wenn Sie die Archivierung mithilfe der Option "Microsoft Exchange Integration" bereitstellen, werden lync-Archivdaten nur für die Benutzer, die auf Ihren Exchange 2013 Servern verwaltet werden, mit Exchange 2013 Compliance-Daten gespeichert. Sie müssen Exchange 2013 bereitstellen, bevor Sie die Archivierung mithilfe der Option "Microsoft Exchange Integration" bereitstellen und aktivieren. Wenn Sie Exchange 2013 Speicher verwenden möchten, müssen Sie keine separaten SQL Server Datenbanken für die Archivierung bereitstellen, es sei denn, Sie verfügen über lync-Benutzer, die nicht auf Ihren Exchange 2013 Servern verwaltet werden.

  - **SQL Server Datenbankspeicher für die Archivierung**. Zur Unterstützung von Benutzern, die nicht auf Exchange 2013 Servern verwaltet werden, oder wenn Sie die Option Microsoft Exchange Integration nicht verwenden möchten, müssen Sie den Archivierungsspeicher mithilfe einer SQL Server Datenbank bereitstellen. Lync Server 2013 unterstützt die folgenden 64-Bit-Versionen von SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express und Microsoft SQL Server 2012 Express werden für die Archivierung nicht unterstützt. 32-Bit-Versionen von SQL Server werden nicht unterstützt. Weitere SQL Server Anforderungen und-Einschränkungen finden Sie unter <A href="lync-server-2013-database-software-support.md">Database Software Support in lync Server 2013</A> in der Planungsdokumentation oder in der Unterstützungsdokumentation.

    
    </div>
    
    Sie müssen die SQL Server Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren. Wenn das zum Veröffentlichen der Topologie verwendete Konto über die entsprechenden Administratorrechte und-Berechtigungen verfügt, können Sie beim Veröffentlichen Ihrer Topologie die Archivierungsdatenbank (LcsLog) erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs. Ausführliche Informationen zu SQL Server finden Sie im SQL Server TechCenter unter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

