---
title: 'Lync Server 2013: Testen des Directors'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad5c885e032800e4233aaa58c5238c066a87a1df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Testen des Directors in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Zu diesem Zeitpunkt haben Sie einen Director oder einen Directorpool konfiguriert, Ihre DNS-SRV-Einträge (Domain Name System) verweisen Clients jedoch noch immer an die Anmeldung über einen Pool- oder einen Standard Edition-Server. Bevor Sie den DNS-Eintrag so ändern, dass lync 2013 Clients sich automatisch mit dem Director anmelden, testen Sie einen Client, indem Sie ihn manuell an den Director richten.

<div>

## <a name="to-test-the-deployment"></a>So testen Sie die Bereitstellung

1.  Melden Sie sich an dem Computer an, auf dem Sie die lync Server-Systemsteuerung mit einem Domänenkonto installiert haben, das Teil der **CSAdministrator** -Gruppe ist.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie im Navigationsbereich auf **Topologie**, und vergewissern Sie sich in der Spalte **Status** , dass ein grüner Server mit einem Pfeil ( ![Serversymbol mit grünem Pfeil](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server Symbol mit grünem Pfeil")) für Ihren Director oder Directorpool vorhanden ist.

4.  Verbinden Sie zwei Clientcomputer, auf denen der lync Server 2013-Client installiert ist, und melden Sie sich mit einem anderen Benutzerkonto an, das für lync Server 2013 für jeden Computer aktiviert ist.

5.  Klicken Sie auf einem der Clientcomputer auf das Menü **Optionen**, wählen Sie die Einstellungsgruppe **Persönlich** aus, klicken Sie auf **Erweitert**, dann auf **Manuelle Konfiguration**, und legen Sie dann die Option **Interner Servername oder IP-Adresse** auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Directors oder Directorpools ein.

6.  Melden Sie sich bei beiden Clients an, und stellen Sie sicher, dass die Anmeldung auf dem Client, der sich über den Director anmeldet, erfolgreich verläuft. Beachten Sie den Anwesenheitsstatus des anderen Benutzers, und prüfen Sie, ob beide Sofortnachrichten austauschen können.

</div>

</div>

<span> </span>

</div>

</div>

</div>

