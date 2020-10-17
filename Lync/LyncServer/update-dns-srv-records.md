---
title: Aktualisieren von DNS SRV-Einträgen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d45abd1599666079705f3e77b74ac2ba81d9df71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503512"
---
# <a name="update-dns-srv-records"></a>Aktualisieren von DNS SRV-Einträgen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.

In diesem Thema wird beschrieben, wie Sie die Domain Name System (DNS) Datensätze nach der Migration zu lync Server 2013 aktualisieren. Nachdem alle Benutzer in lync Server 2013 verschoben wurden, aber bevor der Legacy lync Server 2010-Pool oder-Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren. Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.

**So konfigurieren Sie einen DNS-SRV-Eintrag**

1.  Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der lync Server 2013 installiert ist, und navigieren Sie zur ** \_ TCP** -Einstellung.

3.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf ** \_ sipinternaltls** , und wählen Sie **Eigenschaften**aus.

4.  Aktualisieren Sie unter Host, der **diesen Dienst anbietet**den Host-FQDN so, dass er auf den lync Server 2013 Pool zeigt.

5.  Klicken Sie auf **OK**.

**So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann**

1.  Melden Sie sich bei einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen**.

3.  Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK**.

4.  Geben Sie an der Eingabeaufforderung **nslookup** \<FQDN of the Front End pool\> oder \<FQDN of the Standard Edition server\> ein, und drücken Sie dann die EINGABETASTE.

5.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

</div>

<span> </span>

</div>

</div>

</div>

