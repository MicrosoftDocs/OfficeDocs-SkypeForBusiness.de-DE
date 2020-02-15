---
title: 'Lync Server 2013: neue Archivierungs Features'
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
ms.openlocfilehash: bf8c632fa5858eaf35464e9885e65343bc699e54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Neue Archivierungs Features in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Die Archivierung in lync Server 2013 kann die folgenden Inhaltstypen archivieren:

  - Peer-zu-Peer-Chatnachrichten

  - Konferenzen (Besprechungen), bei denen es sich um Chatnachrichten mit mehreren Teilnehmern handelt

  - Konferenzinhalt, einschließlich hochgeladenem Inhalt (z. B. Handzettel) und ereignisbezogenem Inhalt (z. B. Beitritt, Verlassen, Hochladen, Freigabe und Änderungen in der Sichtbarkeit)

Darüber hinaus bietet die Archivierung in lync Server 2013 neue Features, die die Bereitstellung und die Effizienz des Betriebs verbessern. Diese neuen Features umfassen Folgendes:

  - **Nebeneinander der Archivierung auf Front-End-Servern.**    Lync Server 2013 verfügt nicht über eine separate Archivierungsserver Rolle. Die Archivierung ist ein optionales Feature, das auf allen Front-End-Servern in einer Enterprise Edition-Bereitstellung, und auf Standard Edition-Servern, die für einen Pool oder einen Standort implementiert und konfiguriert werden können, verfügbar ist.

  - **Microsoft Exchange Integration.**    Wenn Sie die Archivierung bereitstellen, können Sie den Datenspeicher für die Archivierung mit dem vorhandenen Exchange 2013 Speicher für alle Benutzer integrieren, die in Exchange 2013 verwaltet werden und deren Postfächer in einem Compliance-Archiv abgelegt werden, sodass Sie keine separaten SQL Server Datenbanken zur Archivierung von lync-Daten bereitstellen müssen. Wenn Sie nicht über eine Exchange 2013-Bereitstellung verfügen oder keine Integration in die Datenbank wünschen oder wenn Sie lync 2013 Benutzer haben, die nicht in Exchange 2013 mit ihren Postfächern in-situ-Speicher verwaltet werden, können Sie separate Archivierungsdatenbanken bereitstellen, indem Sie SQL Server zum Speichern verwenden. e archivierte Daten aus lync Communications. Sie können sowohl Microsoft Exchange Integration als auch lync Server 2013 Archivierungsdatenbanken verwenden, wenn Sie Microsoft Exchange Integration für einige, jedoch nicht für alle Benutzer in Ihrer Bereitstellung verwenden möchten. Ausführliche Informationen zum in-situ-Speicher finden Sie unter "in-situ- [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)Speicher" unter "in-situ-Aufbewahrung".

  - **SQL-Speicherspiegelung.**    Wenn Sie die Archivierung bereitstellen, können Sie SQL Server Datenbankspiegelung für Ihre Archivierungsdatenbank aktivieren.

  - **Archivierung von Whiteboards und Umfragen.**    Archivierte Konferenzinhalte enthalten jetzt Whiteboards und Umfragen, die während der Besprechung freigegeben werden.

Die folgenden Arten von Inhalt können nicht archiviert werden:

  - Peer-zu-Peer-Dateiübertragungen

  - Audio/Video für Peer-zu-Peer-Chatnachrichten und -Konferenzen

  - Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -Konferenzen

<div>

## <a name="see-also"></a>Siehe auch


[Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

