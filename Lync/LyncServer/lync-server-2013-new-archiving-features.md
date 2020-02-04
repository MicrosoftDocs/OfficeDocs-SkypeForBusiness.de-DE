---
title: 'Lync Server 2013: Neue Funktionen für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1509a0857b54673ab20783f69b34b59c6d2afde8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Neue Funktionen für die Archivierung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Bei der Archivierung in lync Server 2013 können die folgenden Arten von Inhalten archiviert werden:

  - Peer-zu-Peer-Chatnachrichten

  - Konferenzen (Besprechungen), die mehr Parteien-Sofortnachrichten sind

  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)

Darüber hinaus bietet die Archivierung in lync Server 2013 neue Funktionen, die die Bereitstellung und die Effizienz des Betriebs verbessern. Diese neuen Features bestehen aus:

  - **Übersetzung der Archivierung auf Front-End-Servern.**    Lync Server 2013 verfügt nicht über eine separate Archivierungs Server Rolle. Die Archivierung ist ein optionales Feature, das auf allen Front-End-Servern in einer Enterprise Edition-Bereitstellung und auf Standard Edition-Servern zur Verfügung steht, die für einen Pool oder eine Website konfiguriert werden können.

  - **Integration von Microsoft Exchange.**    Wenn Sie die Archivierung bereitstellen, können Sie Datenspeicher für die Archivierung mit Ihrem vorhandenen Exchange 2013-Speicher für alle Benutzer integrieren, die sich in Exchange 2013 befinden und deren Postfächer in-situ-Speicher abgelegt werden, damit Sie keine separaten SQL Server-Datenbanken zum Archivieren von lync-Daten bereitstellen müssen. Wenn Sie keine Exchange 2013-Bereitstellung haben, oder wenn Sie es vorziehen, Sie nicht zu integrieren, oder wenn Sie lync 2013-Benutzer haben, die nicht in Exchange 2013 mit ihren Postfächern in-situ-Speicher abgelegt sind, können Sie separate Archivierungsdatenbanken bereitstellen, indem Sie SQL Server zum Speichern verwenden e archivierte Daten aus lync Communications. Sie können sowohl die Microsoft Exchange-Integration als auch die lync Server 2013-Archivierungsdatenbanken verwenden, wenn Sie die Microsoft Exchange-Integration für einige, aber nicht für alle Benutzer in Ihrer Bereitstellung verwenden möchten. Details zum in-situ-Speicher finden Sie unter "in-situ-Speicher [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)" unter.

  - **SQL Store-Spiegelung.**    Wenn Sie die Archivierung bereitstellen, können Sie die SQL Server-Datenbankspiegelung für Ihre Archivierungsdatenbank aktivieren.

  - **Archivierung von Whiteboards und Umfragen.**    Archivierte Konferenzinhalte enthalten nun Whiteboards und Umfragen, die während der Besprechung freigegeben werden.

Die folgenden Inhaltstypen werden nicht archiviert:

  - Peer-to-Peer-Dateiübertragungen

  - Audio-/Videoinhalte für Peer-zu-Peer-Chatnachrichten und -konferenzen

  - Anwendungsfreigabe für Peer-to-Peer-Sofortnachrichten und-Konferenzen

<div>

## <a name="see-also"></a>Siehe auch


[Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

