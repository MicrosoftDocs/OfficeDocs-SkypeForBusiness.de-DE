---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afde57a9ed64dbff537395ccef908ae44b86177d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Vor der Bereitstellung des lync Server 2013-pilotpools müssen Sie den DNS-Host einen Eintrag für den Pilot Pool aktualisieren. Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.

**So konfigurieren Sie DNS-Host A-Einträge**

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert wird.

3.  Klicken Sie auf **neuer Host (A oder AAAA)**.

4.  Klicken Sie auf **Name**, geben Sie den Hostnamen für den lync Server 2013-Pool ein (der Domänen Name wird aus der Zone übernommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Klicken Sie auf **IP-Adresse**, und geben Sie die IP-Adresse für den Front-End-Pool ein.

6.  Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.

7.  Wenn Sie fertig sind, klicken Sie auf **Fertig**.

</div>

<span> </span>

</div>

</div>

</div>

