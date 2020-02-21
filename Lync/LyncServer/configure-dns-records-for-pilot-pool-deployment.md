---
title: Konfigurieren von DNS-Einträgen für die Bereitstellungeines pilotpools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89481d26c964d7b436e45f708e5fa9f4a6afc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Konfigurieren von DNS-Einträgen für die Bereitstellungeines pilotpools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Vor dem Bereitstellen des lync Server 2013-pilotpools müssen Sie den DNS-Host A-Einträge für den Pilot Pool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.

**So konfigurieren Sie DNS-Hosteinträge (A)**

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert werden soll.

3.  Klicken Sie auf **Neuer Host (A oder AAAA)**.

4.  Klicken Sie auf **Name**, geben Sie den Hostnamen für den lync Server 2013 Pool ein (der Domänen Name wird von der Zone angenommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Klicken Sie auf **IP-Adresse**, geben Sie die IP-Adresse für die Front-End-Pool ein.

6.  Klicken Sie auf **Host hinzufügen** und dann auf **OK**.

7.  Klicken Sie abschließend auf **Fertig**.

</div>

<span> </span>

</div>

</div>

</div>

