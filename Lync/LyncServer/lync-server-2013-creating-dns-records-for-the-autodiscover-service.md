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
ms.openlocfilehash: d91c67620a87fdd91a1755592175e8cf2964d259
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-20_

Für Ihre lync Mobile-Benutzer müssen Sie die AutoErmittlung aktivieren, und ein Teil davon umfasst das Erstellen einiger DNS-Einträge (Domain Name System). Je nach Ihren Anforderungen benötigen Sie Folgendes:

  - Ein interner DNS-Eintrag zur Unterstützung von mobilen Benutzern, die im Netzwerk Ihrer Organisation eine Verbindung herstellen.

  - Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung von mobilen Benutzern, die eine Verbindung mit dem Internet herstellen

Warum beides? Sie müssen sowohl einen internen DNS-Eintrag als auch einen externen DNS-Eintrag für jede SIP-Domäne erstellen.

Die von Ihnen erstellten DNS-Einträge können entweder als (Host-) Datensätze oder als CNAME-Einträge angezeigt werden. Um Ihnen zu helfen, führen wir die folgenden Schritte zum Erstellen dieser internen und externen DNS-Einträge aus. Wenn Sie weitere Informationen zu den DNS-Anforderungen für mobile Benutzer benötigen, können Sie die [technischen Voraussetzungen für die Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)lesen.

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1.  Wenn Sie einen internen DNS-Eintrag erstellen möchten, müssen Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto anmelden, das entweder ein Mitglied der Gruppe der Domänenadministratoren oder ein Mitglied der DnsAdmins-Gruppe ist.

2.  Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

3.  Erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne, in der der lync Server 2013 Director-Pool und der Front-End-Pool installiert sind. (Beispiel: contoso. local).

4.  Überprüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool für einen internen DNS-Eintrag vorhanden ist, und geben Sie einen Host einen Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools (beispielsweise lyncwebdir01. contoso. local) ein. Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool, und Sie müssen den FQDN für Ihren Front-End-Pool oder sogar einen einzelnen Server-FQDN verwenden, wenn dies Ihr Setup ist.

5.  Beachten Sie Folgendes: Überprüfen Sie, ob ein Host a (AAAA für IPv6)-Eintrag für Ihren Front-End-Pool für einen internen DNS-Eintrag vorhanden ist, ein Host-a-Eintrag (oder AAAA-Eintrag) für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden sein soll (beispielsweise , lyncwebpool01. contoso. local). Wenn dies nicht der Fall ist, müssen Sie den FQDN für den Front-End-Server oder den Standard Edition-Server notieren.

6.  Sobald Sie wissen, welche Host A (oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).

7.  Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **Neuer Alias (CNAME)**.

8.  Geben Sie unter **Aliasname**den Namen lyncdiscoverinternal als Hostnamen für die interne URL des AutoErmittlungsdiensts ein.

9.  Geben Sie im **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Ziel Host**den internen Webdienst-FQDN für Ihren Director-Pool ein, oder suchen Sie nach ihm (beispielsweise lyncwebdir01. contoso. local), und klicken Sie dann auf **OK**.

10. Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013-Umgebung unterstützen.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1.  Wenn Sie einen externen DNS-CNAME-Eintrag erstellen möchten, müssen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter herstellen, und führen Sie dann die folgenden Schritte aus. Wir können nicht genau beschreiben, wohin Sie in der Umgebung Ihres DNS-Anbieters wechseln, da es verschiedene Methoden zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.

2.  Melden Sie sich bei Ihrem externen DNS-Anbieter mit einem Konto an, das DNS-Einträge in dieser Umgebung erstellen kann.

3.  Für diese Umgebung sollte bereits eine SIP-Domäne erstellt werden. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder wählen Sie Sie auf andere Weise abhängig von der verwendeten externen DNS-Schnittstelle aus.

4.  Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool (wie lyncwebexdir01.contoso.com) sehen, um sicherzustellen, dass er vorhanden ist. Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool. Wenn dies der Fall ist, müssen Sie den FQDN Ihres Front-End-Pools verwenden, oder wenn Sie dies für einen einzelnen Server, für Ihren Front-End-Server oder Standard Edition-Server tun.

5.  Außerdem müssen Sie sicherstellen, dass ein Host a (AAAA für IPv6)-Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres externen Webdiensts für Ihren Front-End-Pool (wie lyncwebextpool01.contoso.com) vorhanden ist, oder einen FQDN für den FQDN Ihres Single Servers, wenn Sie über keinen Front-End-Pool verfügen. Wie im vorherigen Schritt beschrieben, benötigen Sie diese unten, wenn Sie nicht über einen Director-Pool verfügen.

6.  Wählen Sie jetzt im geeigneten Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Alias (CNAME)** (Dies kann eine Menüoption oder ein Link sein, abhängig vom Format des DNS-Anbieters).

7.  Es sollte eine Form von **Alias Namen** -Textfeld geben wie beim internen DNS sollten Sie lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts eingeben.

8.  Es sollte auch eine Form eines **vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) für** das Textfeld "Zielhost" geben, hier können Sie den FQDN der externen Webdienste für Ihren Director-Pool eingeben (beispielsweise lyncwebexdir01.contoso.com) und dann auf OK klicken oder alle Aktionen im externen DNS ausführen, um die Erstellung dieses Eintrags zu akzeptieren. Wie in Schritt 4 oben zu sehen ist, müssen Sie, falls Sie nicht über einen Director-Pool verfügen, den FQDN des Front-End-Pools oder den von Ihnen eingerichteten Single-Server-FQDN verwenden.

9.  Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013-Umgebung unterstützt wird.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Erstellen eines internen DNS-A-Eintrags

1.  Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto an, das ein Mitglied der Gruppe "Domain Admins" oder ein Mitglied der DnsAdmins-Gruppe ist.

2.  Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

3.  Für einen internen DNS-Eintrag erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory-Domäne (beispielsweise contoso. local), in der der lync Server 2013 Director-Pool und der Front-End-Pool installiert sind.

4.  Überprüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool für einen internen DNS-Eintrag vorhanden ist, und geben Sie einen Host einen Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools (beispielsweise lyncwebdir01. contoso. local) ein. Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool, und Sie müssen die IP-Adresse für Ihren Front-End-Pool oder sogar eine einzelne Server-IP-Adresse verwenden, wenn dies Ihr Setup ist.

5.  Beachten Sie Folgendes: Überprüfen Sie, ob ein Host a (AAAA für IPv6)-Eintrag für Ihren Front-End-Pool für einen internen DNS-Eintrag vorhanden ist, ein Host-a-Eintrag (oder AAAA-Eintrag) für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden sein soll (beispielsweise , lyncwebpool01. contoso. local). Wenn dies nicht der Fall ist, müssen Sie die IP-Adresse für den Front-End-Server oder den Standard Edition-Server notieren.

6.  Sobald Sie wissen, welche Host A (oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).

7.  Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **neuer Host (A oder AAAA)**.

8.  Geben Sie unter **Name**den Namen lyncdiscoverinternal als Hostname für die interne URL des AutoErmittlungsdiensts ein.

9.  Geben Sie unter **IP-Adresse**die interne Webdienste-IP-Adresse des Directors ein (oder geben Sie bei Verwendung eines Load Balancer die virtuelle IP (VIP) des Director Load Balancer ein). Wie in Schritt 4 oben festgestellt, müssen Sie möglicherweise die IP-Adresse des Front-End-Servers oder des Standard Edition-Servers eingeben, oder wenn Sie ein Lastenausgleichsmodul verwenden, geben Sie den VIP des Load Balancer des Front-End-Pools ein.

10. Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.

11. Wenn Sie einen zusätzlichen a-oder AAAA-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10, und unter Berücksichtigung dessen, dass Sie neue Auto Ermittlungs-a-oder AAAA-Einträge in der Forward-Lookupzone jeder SIP-Domäne erstellen müssen, die in ihrer lync Server 2013-Umgebung unterstützt wird.

12. Wenn Sie mit dem Erstellen eines (für IPv6-, AAAA)-Datensatzes fertig sind, klicken Sie auf **Fertig**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Erstellen eines externen DNS-A-Eintrags

1.  Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter her, und führen Sie dann die folgenden Schritte aus. Wir können nicht genau beschreiben, wohin Sie in der Umgebung Ihres DNS-Anbieters wechseln, da es verschiedene Methoden zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.

2.  Sie müssen als Konto angemeldet sein, das DNS-Einträge in dieser Umgebung erstellen kann.

3.  Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com). Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).

4.  Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool (wie lyncwebexdir01.contoso.com) sehen, um sicherzustellen, dass er da ist und was die IP-Adresse ist. Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool. Wenn dies der Fall ist, müssen Sie die IP-Adresse des Front-End-Pools verwenden, oder wenn Sie dies für einen einzelnen Server, für Ihren Front-End-Server oder Standard Edition-Server tun. Beachten Sie, dass sich Ihre Server auch hinter einem Load-Balancer oder einem Reverse-Proxy befinden können. Notieren Sie sich die IP-Adressen, und führen Sie die folgenden Schritte aus.

5.  Darüber hinaus müssen Sie sicherstellen, dass ein Host a (AAAA für IPv6)-Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres externen Webdiensts für Ihren Front-End-Pool (wie lyncwebextpool01.contoso.com) oder eine IP-Adresse für Ihre lync-Installation mit einem Server vorhanden ist, wenn Sie keine Front-End-Pools. Wie im vorherigen Schritt beschrieben, benötigen Sie diese unten, wenn Sie nicht über einen Director-Pool verfügen.

6.  Wählen Sie jetzt im geeigneten Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Hosts a oder AAAA** (Dies kann eine Menüoption oder ein Link sein, abhängig vom Format des DNS-Anbieters).

7.  Es sollte einen Ort geben, an dem Sie einen **Namen**eingeben können, und geben Sie lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts ein.

8.  Es sollte auch ein Textfeld für die **IP-Adresse** vorhanden sein, in dem Sie die IP-Adresse für Ihr Director-Pool (beispielsweise lyncwebexdir01.contoso.com) oder möglicherweise die IP-Adresse des Load Balancer Ihres Pools (oder eine Reverse-Proxy-IP-Adresse, die zum gleichen führt) eingeben und dann auf OK klicken oder die Aktion im externen DNS durchführen, um die Erstellung dieses Eintrags Wie in Schritt 4 oben erwähnt, müssen Sie, falls Sie keinen Director-Pool besitzen, die IP-Adresse des Front-End-Pools oder die IP-Adresse des Einzelservers verwenden, die Sie eingerichtet haben.

9.  Sie müssen einen neuen Auto Ermittlungs-a-oder AAAA-Eintrag in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013-Umgebung unterstützt wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

