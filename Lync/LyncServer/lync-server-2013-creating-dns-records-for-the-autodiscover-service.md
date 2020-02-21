---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für den AutoErmittlungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 921db63f02be50866e6d26cb33007ac8ddbb32eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-20_

Ihre mobilen lync-Benutzer müssen AutoDiscovery aktivieren, und ein Teil davon umfasst das Erstellen einiger Domain Name System (DNS)er Datensätze. Je nach Ihren Anforderungen benötigen Sie Folgendes:

  - Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die im Netzwerk Ihrer Organisation eine Verbindung herstellen.

  - Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen

Warum beides? Sie müssen sowohl einen internen DNS-Eintrag als auch einen externen DNS-Eintrag für jede SIP-Domäne erstellen.

Bei den von Ihnen erstellten DNS-Einträgen kann es sich entweder um einen (Host-) Eintrag oder um CNAME-Einträge handeln. Um Ihnen zu helfen, erfahren Sie, wie Sie diese internen und externen DNS-Einträge unten erstellen. Wenn Sie weitere Informationen zu den DNS-Anforderungen für mobile Benutzer benötigen, können Sie die [technischen Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)lesen.

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1.  Um einen internen DNS-Eintrag zu erstellen, müssen Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto anmelden, das entweder Mitglied der Gruppe "Domänen-Admins" oder ein Mitglied der Gruppe "DnsAdmins" ist.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.

3.  Erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory Domäne, in der Ihre lync Server 2013 Directorpool und Front-End-Pool installiert sind. (beispielsweise "contoso. local").

4.  Prüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Directorpool für einen internen DNS-Eintrag vorhanden ist, sollte ein Host-a-Eintrag für den internen Webdienste vollqualifizierten Domänennamen (FQDN) für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local). Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Directorpool, und Sie müssen den FQDN für Ihren Front-End-Pool oder sogar einen einzelnen Server-FQDN verwenden, falls dies Ihr Setup ist.

5.  Achten Sie darauf, dass ein Host-a-Eintrag (AAAA für IPv6) für die Front-End-Pool eines internen DNS-Eintrags vorhanden ist, dass ein Host-a-Eintrag (oder AAAA) für den internen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein muss (beispielsweise , lyncwebpool01. contoso. local). Wenn dies nicht der Fall ist, müssen Sie den FQDN für den Front-End-Server oder Standard Edition-Server notieren.

6.  Wenn Sie wissen, welche Host-a-(oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).

7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Alias (CNAME)**.

8.  Geben Sie unter **Aliasname**"lyncdiscoverinternal" als Hostnamen für die interne AutoErmittlungsdienst-URL ein.

9.  Geben Sie im **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Zielhost**den internen Webdienste FQDN für den Directorpool ein (beispielsweise lyncwebdir01. contoso. local), oder klicken Sie auf **OK**.

10. Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013 Umgebung unterstützen.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1.  Zum Erstellen eines externen DNS-CNAME-Eintrags müssen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter herstellen und dann unsere Schritte ausführen. Wir können nicht genau beschreiben, wo Sie in die Umgebung Ihres DNS-Anbieters wechseln, da es unterschiedliche Möglichkeiten zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.

2.  Melden Sie sich bei Ihrem externen DNS-Anbieter mit einem Konto an, das DNS-Einträge in dieser Umgebung erstellen kann.

3.  Sie sollten bereits eine SIP-Domäne für diese Umgebung erstellt haben. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder wählen Sie Sie auf andere Weise je nach verwendeter externer DNS-Schnittstelle aus.

4.  Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihre Directorpool (beispielsweise lyncwebexdir01.contoso.com) sehen, also bestätigen Sie, dass dieser vorhanden ist. Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keine Directorpool. Wenn dies der Fall ist, müssen Sie den FQDN des Front-End-Pools verwenden, oder wenn Sie dies für einen einzelnen Server, für den Front-End-Server oder Standard Edition-Server tun.

5.  Sie müssen außerdem sicherstellen, dass ein Host-a-Eintrag (AAAA für IPv6) für Ihren externen Webdienste vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Ihre Front-End-Pool (beispielsweise lyncwebextpool01.contoso.com) oder ein FQDN für Ihren Einzelserver-FQDN vorhanden ist, wenn Sie über keine Front-End-Pool verfügen. Wie im vorherigen Schritt erwähnt, benötigen Sie diese weiter unten, wenn Sie keine Directorpool haben.

6.  Wählen Sie nun im entsprechenden Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Alias (CNAME)** (Dies kann eine Menüoption oder ein Link sein, je nach Format des DNS-Anbieters).

7.  Es sollte eine Form von **Alias Namen** -Textfeld geben wie beim internen DNS sollten Sie lyncdiscover als Hostnamen für die externe AutoErmittlungsdienst-URL eingeben.

8.  Es sollte auch eine Form eines **vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) für das Textfeld Zielhost** geben, hier geben Sie den externen Webdienste-FQDN für Ihre Directorpool ein (beispielsweise lyncwebexdir01.contoso.com), und klicken Sie dann auf OK, oder nehmen Sie alle Aktionen im externen DNS vor, um die Erstellung dieses Eintrags zu akzeptieren. Wie in Schritt 4 oben erwähnt, müssen Sie, wenn Sie nicht über ein Directorpool verfügen, den Front-End-Pool-FQDN oder den FQDN des Einzelservers verwenden, den Sie eingerichtet haben, je nach Bedarf.

9.  Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013 Umgebung unterstützt wird.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Erstellen eines internen DNS-A-Eintrags

1.  Um einen internen DNS-Eintrag zu erstellen, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto an, das Mitglied der Gruppe "Domänen-Admins" oder ein Mitglied der Gruppe "DnsAdmins" ist.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.

3.  Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory Domäne (beispielsweise "contoso. local"), in der Ihre lync Server 2013 Directorpool und Front-End-Pool installiert sind.

4.  Prüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Directorpool für einen internen DNS-Eintrag vorhanden ist, sollte ein Host-a-Eintrag für den internen Webdienste vollqualifizierten Domänennamen (FQDN) für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local). Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keine Directorpool, und Sie müssen die IP-Adresse für Ihre Front-End-Pool oder sogar eine IP-Adresse für einen einzelnen Server verwenden, falls dies Ihr Setup ist.

5.  Achten Sie darauf, dass ein Host-a-Eintrag (AAAA für IPv6) für die Front-End-Pool eines internen DNS-Eintrags vorhanden ist, dass ein Host-a-Eintrag (oder AAAA) für den internen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein muss (beispielsweise , lyncwebpool01. contoso. local). Wenn dies nicht der Fall ist, müssen Sie die IP-Adresse für die Front-End-Server oder Standard Edition-Server notieren.

6.  Wenn Sie wissen, welche Host-a-(oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).

7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Host (A oder AAAA)**.

8.  Geben Sie unter **Name**den Namen "lyncdiscoverinternal" als Hostnamen für die interne URL des AutoErmittlungsdiensts ein.

9.  Geben Sie unter **IP-Adresse**die interne Webdienste-IP-Adresse des Directors ein (oder geben Sie bei Verwendung eines Lastenausgleichs die virtuelle IP (VIP) des Director-Lastenausgleichs) ein. Wie in Schritt 4 oben erwähnt, müssen Sie möglicherweise die IP-Adresse des Front-End-Server oder Standard Edition-Server eingeben oder, wenn Sie einen Lastenausgleichsmodul verwenden, den VIP des Front-End-Pool Lastenausgleichs eingeben.

10. Klicken Sie auf **Host hinzufügen** und dann auf **OK**.

11. Wenn Sie einen zusätzlichen a-oder AAAA-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10, und beachten Sie dabei, dass Sie in der Forward-Lookupzone jeder SIP-Domäne, die in ihrer lync Server 2013 Umgebung unterstützt wird, neue a-oder AAAA-Einträge für die AutoErmittlung erstellen müssen.

12. Klicken Sie auf **Fertig**, wenn Sie das Erstellen von A-Einträgen (für IPv6, AAAA) abgeschlossen haben.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Erstellen eines externen DNS-A-Eintrags

1.  Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter her, und führen Sie dann die folgenden Schritte aus. Wir können nicht genau beschreiben, wo Sie in die Umgebung Ihres DNS-Anbieters wechseln, da es unterschiedliche Möglichkeiten zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.

2.  Sie müssen als Konto angemeldet sein, das DNS-Einträge in dieser Umgebung erstellen kann.

3.  Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com"). Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

4.  Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihre Directorpool (beispielsweise lyncwebexdir01.contoso.com) sehen, also bestätigen Sie, dass er vorhanden ist und was die IP-Adresse ist. Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keine Directorpool. Wenn dies der Fall ist, müssen Sie die IP-Adresse des Front-End-Pools verwenden, oder wenn Sie dies für einen einzelnen Server, für den Front-End-Server oder Standard Edition-Server tun. Beachten Sie, dass sich Ihre Server möglicherweise auch hinter einem Lastenausgleichsmodul oder einem Reverseproxy befinden. Notieren Sie sich die IP-Adressen, und führen Sie die folgenden Schritte aus.

5.  Sie müssen außerdem sicherstellen, dass ein Host-a-Eintrag (AAAA für IPv6) für Ihren externen Webdienste vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Ihre Front-End-Pool (beispielsweise lyncwebextpool01.contoso.com) oder eine IP-Adresse für die Einzelserver-lync-Installation vorhanden ist, wenn Sie keine Front-End-Pool. Wie im vorherigen Schritt erwähnt, benötigen Sie diese weiter unten, wenn Sie keine Directorpool haben.

6.  Wählen Sie nun im entsprechenden Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Hosts a oder AAAA** (Dies kann eine Menüoption oder ein Link sein, je nach Format des DNS-Anbieters).

7.  Es sollte einen Ort geben, um einen **Namen**einzugeben, geben Sie lyncdiscover als Hostnamen für die externe AutoErmittlungsdienst-URL ein.

8.  Es sollte auch ein **IP-Adress** Textfeld vorhanden sein, in dem Sie die IP-Adresse für Ihre Directorpool eingeben (beispielsweise lyncwebexdir01.contoso.com) oder möglicherweise die IP-Adresse des Lastenausgleichs Ihres Pools (oder eine Reverse-Proxy-IP, die dazu führt) und dann auf OK klicken oder eine beliebige Aktion im externen DNS durchführen, um die Erstellung dieses Eintrags zu akzeptieren. Wie in Schritt 4 oben erwähnt, müssen Sie, wenn Sie nicht über ein Directorpool verfügen, die Front-End-Pool-IP-Adresse oder die IP-Adresse eines einzelnen Servers verwenden, die Sie eingerichtet haben, je nach Bedarf.

9.  Sie müssen einen neuen Auto Ermittlungs Eintrag a oder AAAA in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013 Umgebung unterstützt wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

