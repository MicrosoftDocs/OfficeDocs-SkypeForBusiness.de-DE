---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für den AutoErmittlungsdienst'
TOCTitle: Erstellen von DNS-Einträgen für den AutoErmittlungsdienst
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690010(v=OCS.15)
ms:contentKeyID: 49293668
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-06-20_

Sie müssen für Ihre Benutzer von Lync Mobile wahrscheinlich die Autoermittlung aktivieren. Hierzu müssen Sie u. a. einige DNS-Einträge erstellen (Domain Name System). Hierzu gehören je nach bestehenden Anforderungen die Folgenden:

  - Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen

  - Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen

Warum beide? Für jede SIP-Domäne muss ein interner DNS-Eintrag und ein externer DNS-Eintrag erstellt werden.

Bei den erstellten DNS-Einträgen kann es sich entweder um A-Einträge (Host) oder um CNAME-Einträge handeln. Wir zeigen Ihnen weiter unten, wie Sie diese internen und externen DNS-Einträge erstellen. Weitere Informationen zu DNS-Anforderungen finden Sie unter [Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

## Erstellen eines internen DNS CNAME-Eintrags

1.  Zum Erstellen eines internen DNS-Eintrags müssen Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto anmelden, das entweder zur Gruppe der Domänen-Admins oder zur Gruppe DnsAdmins gehört.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start** , auf **Verwaltung** und dann auf **DNS** .

3.  Erweitern Sie in der Konsolenstruktur des DNS-Servers den Eintrag **Forward-Lookupzonen** für die Active Directory-Domäne, in der Ihr Lync Server 2013Directorpool und Ihr Front-End-Pool installiert sind. (z. B. contoso.local).

4.  Überprüfen Sie, ob ein Host A-Eintrag (AAAA bei IPv6) für den Directorpool für einen internen DNS-Eintrag vorhanden ist. Ein Host A-Eintrag sollte für den voll qualifizierten Domänennamen (FQDN) des internen Webdiensts für Ihren Directorpool (z. B. lyncwebdir01.contoso.local) vorhanden sein. Ist er das nicht, verwenden Sie möglicherweise keinen Directorpool und müssen den FQDN für Ihren Front-End-Pool oder sogar den FQDN für einen einzelnen Server verwenden, wenn Sie mit einer solchen Konfiguration arbeiten.

5.  Berücksichtigen Sie dies und überprüfen Sie, ob ein Host A-Eintrag (AAAA bei IPv6) für den Front-End-Pool für einen internen DNS-Eintrag vorhanden ist. Ein Host A-Eintrag (oder AAAA) sollte für den voll qualifizierten Domänennamen (FQDN) des internen Webdiensts für Ihren Front-End-Pool (z. B lyncwebpool01.contoso.local) vorhanden sein. Ist er das nicht, müssen Sie sich den FQDN für den Front-End-Server oder Standard Edition-Server notieren.

6.  Wenn Sie wissen, welche Host-A-Datensätze (oder AAAA) vorhanden sind, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Alias (CNAME)** .

8.  Geben Sie unter **Aliasname** als Hostnamen für die URL des internen Autoermittlungsdiensts **lyncdiscoverinternal** ein.

9.  Geben Sie unter **Vollqualifizierter Domänenname des Zielhosts** den FQDN des internen Webdiensts für Ihren Directorpool ein (z. B. lyncwebdir01.contoso.local) oder navigieren Sie in der Verzeichnisstruktur dorthin. Klicken Sie dann auf **OK**.

10. Sie müssen einen neuen AutoErmittlung-CNAME-Eintrag in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in Ihrer Lync Server 2013-Umgebung unterstützt wird.

## Erstellen eines externen DNS CNAME-Eintrags

1.  Zum Erstellen eines externen DNS CNAME-Eintrags müssen Sie eine Verbindung zu Ihrem öffentlichen DNS-Anbieter herstellen und dann die folgenden Schritte ausführen. Leider können wir nicht beschreiben, wie Sie genau in der Umgebung Ihres DNS-Anbieters vorgehen müssen, da es unterschiedliche Methoden zur Verwaltung Ihres externen DNS gibt, wir hoffen jedoch, dass diese Anleitung hilfreich ist.

2.  Melden Sie sich bei Ihrem externen DNS-Anbieter an. Verwenden Sie ein Konto, das über die entsprechenden Berechtigungen zum Erstellen von DNS-Einträgen verfügt.

3.  Es sollte bereits eine SIP-Domäne für diese Umgebung erstellt worden sein. Erweitern Sie den Eintrag **Forward-Lookupzonen** für diese SIP-Domäne. Je nachdem, wie die Benutzeroberfläche für die externe DNS-Struktur aufgebaut ist, kann es auch sein, dass Sie den Eintrag auswählen müssen.

4.  Ihnen sollte bereits ein Host A-Eintrag (AAAA bei IPv6) für Ihren Directorpool angezeigt werden (z. B. lyncwebexdir01.contoso.com). Ist kein solcher Eintrag vorhanden, verwenden Sie möglicherweise keinen Directorpool. In diesem Fall müssen Sie den FQDN Ihres Front-End-Pools verwenden bzw. bei einem einzelnen Server den FQDN Ihres Front-End- oder Standard Edition-Servers.

5.  Darüber hinaus müssen Sie prüfen, ob ein Host A-Eintrag (AAAA bei IPv6) für den vollqualifizierten Domänennamen (FQDN) Ihres externen Webdienstes für Ihren Front-End-Pool (z. B. lyncwebextpool01.contoso.com) oder ein FQDN für einen einzelnen Server vorhanden ist, falls Sie keinen Front-End-Pool haben. Wie im vorherigen Schritt erwähnt, benötigen Sie diese Angaben für die Vorgehensweise weiter unten, falls Sie keinen Directorpool haben.

6.  Wählen Sie jetzt im jeweiligen Format Ihres DNS-Anbieters die Option zum Erstellen eines **Neuen Alias (CNAME)** aus (je nach Format des DNS-Anbieters kann es sich dabei um eine Menüoption oder einen Link handeln).

7.  In der Regel gibt es ein Eingabefeld für den **Aliasnamen**. Geben Sie dort wie beim internen DNS "lyncdiscover" als Hostname für die URL des externen Autoermittlungsdiensts ein.

8.  Außerdem sollte ein Eingabefeld für den **Vollqualifizierten Domänennamen des Zielhosts** vorhanden sein. Geben Sie hier den FQDN des externen Webdiensts für Ihren Directorpool (z. B. lyncwebexdir01.contoso.com) ein. Klicken Sie dann auf OK bzw. führen Sie die entsprechende Aktion im externen DNS aus, um das Erstellen dieses Eintrags zu bestätigen. Wie bereits in Schritt 4 oben erwähnt, müssen Sie ersatzweise den FQDN des Front-End-Pools bzw. des einzelnen Servers verwenden, wenn Sie nicht über einen Directorpool verfügen.

9.  Sie müssen einen neuen AutoErmittlungs-CNAME-Eintrag in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in Ihrer Lync 2013-Umgebung unterstützt wird.

## Erstellen eines internen DNS A-Eintrags

1.  Zum Erstellen eines internen DNS-Eintrags müssen Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto anmelden, das entweder zur Gruppe der Domänen-Admins oder der DnsAdmins gehört.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start** , auf **Verwaltung** und dann auf **DNS** .

3.  Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne (z. B. "contoso.local"), in denen Ihr Lync Server 2013Director-Pool und Front-End-Pool installiert sind.

4.  Überprüfen Sie, ob ein Host A-Eintrag (AAAA bei IPv6) für den Directorpool für einen internen DNS-Eintrag vorhanden ist. Ein Host A-Eintrag sollte für den voll qualifizierten Domänennamen (FQDN) des internen Webdiensts für Ihren Directorpool (z. B. lyncwebdir01.contoso.local) vorhanden sein. Ist er das nicht, verwenden Sie möglicherweise keinen Directorpool und müssen die IP-Adresse für Ihren Front-End-Pool oder sogar eine IP-Adresse für einen einzelnen Server verwenden, wenn Sie mit einer solchen Konfiguration arbeiten.

5.  Berücksichtigen Sie dies und überprüfen Sie, ob ein Host A-Eintrag (AAAA bei IPv6) für den Front-End-Pool für einen internen DNS-Eintrag vorhanden ist. Ein Host A-Eintrag (oder AAAA) sollte für den voll qualifizierten Domänennamen (FQDN) des internen Webdiensts für Ihren Front-End-Pool (z. B lyncwebpool01.contoso.local) vorhanden sein. Ist er das nicht, müssen Sie sich die IP-Adresse für den Front-End-Server oder Standard Edition-Server notieren.

6.  Wenn Sie wissen, welche Host-A-Datensätze (oder AAAA) vorhanden sind, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne und klicken Sie dann auf **Neuer Host (A oder AAAA)**.

8.  Geben Sie unter **Name** als Hostnamen für die URL des internen AutoErmittlungsdiensts **lyncdiscoverinternal** ein.

9.  Geben Sie unter **IP-Adresse** die IP-Adresse des internen Webdiensts des Director ein (oder, falls Sie ein Lastenausgleichsmodul verwenden, die virtuelle IP-Adresse (VIP) des Director-Lastenausgleichsmoduls). Wie in Schritt 4 erwähnt, wenn Sie einen Director verwenden, müssen Sie möglicherweise die IP-Adresse des Front-End-Server oder Standard Edition-Server eingeben bzw. falls Sie ein Lastenausgleichsmodul verwenden, geben Sie die VIP des Front-End-Pool-Lastenausgleichsmoduls ein.

10. Klicken Sie auf **Host hinzufügen** und dann auf **OK** .

11. Wiederholen Sie zum Erstellen weiterer A- oder AAAA-Einträge die Schritte 8 bis 10. Denken Sie daran, dass Sie neue AutoErmittlungs-A- oder -AAAA-Einträge in den Forwardlookup-Zonen jeder SIP-Domäne erstellen müssen, die in Ihrer Lync Server 2013-Umgebung unterstützt wird.

12. Klicken Sie auf **Fertig** , wenn Sie das Erstellen von A-Einträgen (für IPv6, AAAA) abgeschlossen haben.

## Erstellen eines externen DNS A-Eintrags

1.  Zum Erstellen eines externen DNS-Eintrags stellen Sie eine Verbindung zu Ihrem öffentlichen DNS-Anbieter her und führen Sie dann die folgenden Schritte aus. Leider können wir nicht beschreiben, wie Sie genau in der Umgebung Ihres DNS-Anbieters vorgehen müssen, da es unterschiedliche Methoden zur Verwaltung Ihres externen DNS gibt, wir hoffen jedoch, dass diese Anleitung hilfreich ist.

2.  Sie müssen sich mit einem Konto anmelden, das berechtigt ist, DNS-Einträge in dieser Umgebung zu erstellen.

3.  Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

4.  Ihnen sollte bereits ein Host A-Eintrag (AAAA bei IPv6) für Ihren Directorpool angezeigt werden (z. B. lyncwebexdir01.contoso.com). Überprüfen Sie dies und schauen Sie sich die IP-Adresse an. Ist kein solcher Eintrag vorhanden, verwenden Sie möglicherweise keinen Directorpool. In diesem Fall müssen Sie die IP-Adresse Ihres Front-End-Pools verwenden bzw. bei einem einzelnen Server den FQDN Ihres Front-End- oder Standard Edition-Servers. Denken Sie daran, dass Ihre Server möglicherweise mit einem Lastenausgleichsmodul arbeiten oder ein Reverseproxy eingesetzt wird. Notieren Sie sich auch die IP-Adressen, damit Sie die folgenden Schritte ausführen können.

5.  Darüber hinaus müssen Sie überprüfen, ob ein Host A-Eintrag (AAAA bei IPv6) für den vollqualifizierten Domänennamen (FQDN) Ihres externen Webdiensts für Ihren Front-End-Pool (z. B. lyncwebextpool01.contoso.com) bzw. eine IP-Adresse im Falle einer Lync-Installation mit einem einzelnen Server vorhanden ist, falls Sie keinen Front-End-Pool haben. Wie bereits im vorigen Schritt erwähnt, benötigen Sie diese Angaben für die Vorgehensweise weiter unten, wenn Sie keinen Directorpool haben.

6.  Wählen Sie jetzt im jeweiligen Format Ihres DNS-Anbieters die Option zum Erstellen eines **Neuen Host A oder AAAA** aus (je nach Format des DNS-Anbieters kann es sich dabei um eine Menüoption oder einen Link handeln).

7.  Es sollte ein Feld vorhanden sein, in das Sie den **Namen** eingeben können. Geben Sie "lyncdiscover" als Hostname für die URL des externen AutoErmittlungsdiensts ein.

8.  Es sollte außerdem ein Feld für die **IP-Adresse** vorhanden sein. Geben Sie hier die IP-Adresse für Ihren Directorpool ein (z. B. lyncwebexdir01.contoso.com) oder möglicherweise die IP des für den Pool verwendeten Lastenausgleichsmoduls (oder die IP eines Reverseproxys, die dorthin umleitet). Klicken Sie dann auf OK oder führen Sie eine andere Aktion im externen DNS aus, um das Erstellen des Eintrags zu bestätigen. Wie bereits in Schritt 4 erwähnt, müssen Sie ersatzweise die IP-Adresse des Front-End-Pools bzw. des einzelnen Servers verwenden, wenn Sie nicht über einen Directorpool verfügen.

9.  Sie müssen einen neuen AutoErmittlungs-A- oder -AAAA-Eintrag in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in Ihrer Lync 2013-Umgebung unterstützt wird.

