---
title: Autorisieren der Verbindung mit Office Communications Server 2007 R2 Edgeserver
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db737eae5ec02a015fac3a894b5f19079743c4c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorisieren der Verbindung mit Office Communications Server 2007 R2 Edgeserver

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Für jeden lync Server 2013 Front-End-Server oder Standard Edition-Server im Pilot Pool müssen Sie die Liste der internen Server aktualisieren, die zum Herstellen einer Verbindung mit dem Office Communications Server 2007 R2 Edgeserver autorisiert sind. Ohne diese Aktualisierungen sind keine Audio/Video (A/V)-Konferenzen für Benutzer möglich, die den Edgeserver der Vorversion verwenden.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>So autorisieren Sie die Verbindung mit Office Communications Server 2007 R2 Edgeserver

1.  Öffnen Sie in der Office Communications Server 2007 R2 Edgeserver in der Gruppe **Verwaltungs Tools** das Snap-in **Computer Verwaltung** .

2.  Erweitern Sie in der Konsolenstruktur die Option **Dienste und Anwendungen**.

3.  Klicken Sie mit der rechten Maustaste auf **Office Communications Server 2007 R2** und anschließend auf **Eigenschaften**.

4.  Klicken Sie auf die Registerkarte **Intern**.

5.  Klicken Sie unter **Server hinzufügen** auf **Hinzufügen**.

6.  Geben Sie im Dialogfeld **Office Communications Server hinzufügen** die entsprechenden Informationen ein:
    
      - Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der einzelnen lync Server 2013 Front-End-Server oder Standard Edition-Server und lync Server 2013 Pool an.
    
      - Geben Sie den FQDN des lync Server 2013 Directors an, wenn Sie eine statische Route im Pool konfiguriert haben, die den Computer für den nächsten Hop nach dem FQDN angibt.

7.  Nachdem Sie einen Eintrag für jeden lync Server 2013, Front-End-Server, Standard Edition-Server, Pool und Director hinzugefügt haben, klicken Sie auf über **nehmen** und dann auf **OK** , um die Eigenschaftenseite zu schließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

