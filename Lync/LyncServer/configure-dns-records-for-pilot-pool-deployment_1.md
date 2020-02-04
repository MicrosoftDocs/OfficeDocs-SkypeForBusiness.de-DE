---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612857ba1a0ec599b0011ab5779cb7fc4b5a0615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Vor der Bereitstellung des lync Server 2013-pilotpools müssen Sie den DNS-Host einen Eintrag für den Pilot Pool aktualisieren. Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie mindestens als Mitglied der Gruppe Domänen-Admins oder als Mitglied der DnsAdmins-Gruppe bei dem Server oder der Domäne angemeldet sein.

**So konfigurieren Sie DNS-Host A-Einträge**

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert wird.

3.  Klicken Sie auf **neuer Host (A oder AAAA)**.

4.  Klicken Sie auf **Name**, geben Sie den Hostnamen für den Pool ein (der Domänen Name wird aus der Zone übernommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Klicken Sie auf **IP-Adresse**, und geben Sie die IP-Adresse für den Front-End-Pool ein.

6.  Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.

7.  Wenn Sie fertig sind, klicken Sie auf **Fertig**.

</div>

<span> </span>

</div>

</div>

</div>

