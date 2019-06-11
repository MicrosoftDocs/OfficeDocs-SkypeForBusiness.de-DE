---
title: Autorisieren der Verbindung zu Office Communications Server 2007 R2 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f81d8aaf9a01fc73516778487f8cc9a2d28a04ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorisieren der Verbindung zu Office Communications Server 2007 R2 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Für jeden lync Server 2013-Front-End-Server oder Standard Edition-Server in Ihrem Pilot Pool müssen Sie die Liste der internen Server aktualisieren, die zum Herstellen einer Verbindung mit dem Office Communications Server 2007 R2 Edge-Server autorisiert sind. Ohne diese Updates funktionieren externe Audio/visuelle (A/V)-Konferenzen für Benutzer, die mit dem Legacy-Edgeserver verbunden sind, nicht.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>So autorisieren Sie die Verbindung zu Office Communications Server 2007 R2 Edge Server

1.  Öffnen Sie auf dem Office Communications Server 2007 R2-Edgeserver in der Gruppe **Administrative Tools** das Snap-in **Computer Verwaltung** .

2.  Erweitern Sie in der Konsolenstruktur **Dienste und Anwendungen**.

3.  Klicken Sie mit der rechten Maustaste auf **Office Communications Server 2007 R2**, und klicken Sie dann auf **Eigenschaften**.

4.  Klicken Sie auf die Registerkarte **intern** .

5.  Klicken Sie unter **Server hinzufügen**auf **Hinzufügen**.

6.  Geben Sie im Dialogfeld **Office Communications Server hinzufügen** die entsprechenden Informationen ein:
    
      - Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes lync Server 2013-Front-End-Servers oder Standard Edition-Servers und lync Server 2013-Pools an.
    
      - Geben Sie den FQDN des lync Server 2013-Directors an, wenn Sie eine statische Route im Pool konfiguriert haben, die den Computer für den nächsten Hop nach dem FQDN angibt.

7.  Nachdem Sie einen Eintrag für jeden lync Server 2013, Front-End-Server, Standard Edition-Server,-Pool und-Director hinzugefügt haben, klicken Sie auf über **nehmen** , und klicken Sie dann auf **OK** , um die Seite Eigenschaften zu schließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

