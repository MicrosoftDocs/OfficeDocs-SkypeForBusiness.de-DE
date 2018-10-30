---
title: 'Lync Server 2013: Definieren der Edgetopologie'
TOCTitle: Definieren der Edgetopologie
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398591(v=OCS.15)
ms:contentKeyID: 49294471
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Edgetopologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Sie müssen den Topologie-Generator zum Erstellen der Topologie verwenden und mindestens einen internen Front-End-Pool oder Standard Edition-Server einrichten, bevor Sie den Edgeserver bereitstellen können. Verwenden Sie das folgende Verfahren, um Ihre Edgetopologie für einen einzelnen Edgeserver zu definieren, und anschließend die Verfahren in [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-your-topology.md) und [Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md), um die Topologie zu veröffentlichen und dem Edgeserver zur Verfügung zu stellen.


> [!NOTE]
> Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.



Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen **RTCUniversalServerAdmins** und **Domänen-Admins** angemeldet sein. Es ist auch möglich, die erforderlichen Administratorrechte und -berechtigungen für das Hinzufügen von Serverrollen einem Benutzerkonto zu erteilen. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Bereitstellungsdokumentation für Standard Edition-Server oder Enterprise Edition-Server. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe **RTCUniversalServerAdmins** sein.

Wenn Sie die Edgetopologie beim Definieren und Veröffentlichen der internen Topologie definiert haben und an der zuvor definierten Edgetopologie keine Änderungen erforderlich sind, müssen Sie die Topologie nicht erneut definieren und veröffentlichen. Führen Sie das folgende Verfahren nur aus, wenn Sie die Edgetopologie ändern müssen. Sie müssen die zuvor definierte und veröffentlichte Topologie jedoch den Edgeservern zur Verfügung stellen. Zu diesem Zweck führen Sie das Verfahren unter [Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) aus.


> [!IMPORTANT]
> Der Topologie-Generator kann nicht auf einem Edgeserver ausgeführt werden. Er muss entweder auf dem Front-End-Server oder auf Standard Edition-Servern ausgeführt werden.



Die Definition der Edgeservertopologie wird im Topologie-Generator vorgenommen. Die drei primären Edgeserver-Topologietypen, die Sie planen und konfigurieren, werden nachfolgend aufgelistet:

  - So definieren Sie die Topologie für einen einzelnen Edgeserver

  - So definieren Sie die Topologie für einen Edgeserverpool mit Lastenausgleich

  - So definieren Sie die Topologie für einen Edgeserverpool mit Hardwarelastenausgleich

## So definieren Sie die Topologie für einen einzelnen Edgeserver

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Standort, an dem ein Edgeserver bereitgestellt werden soll.

3.  Klicken Sie mit der rechten Maustaste auf **Edgepools** , und klicken Sie dann auf **Neuer Edgepool** .

4.  Klicken Sie in **Neuen Edgepool definieren** auf **Weiter** .

5.  Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:
    
      - Geben Sie im Feld **Pool-FQDN** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Schnittstelle für den Edgeserver ein.
        

        > [!IMPORTANT]
        > Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet FQDNs und keine Kurznamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Verwenden Sie beim Zuweisen von FQDNs der Server mit Lync&nbsp;Server, Edgeserver und Pools nur Standardzeichen (also A-Z, a-z, 0-9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt. Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013</A>.

    
      - Klicken Sie auf **Pool mit einem Computer** und dann auf **Weiter** .

6.  Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:
    
      - Wenn ein einziger FQDN und eine einzige IP-Adresse für den SIP-Zugriffsdienst, den Lync Server 2013-Webkonferenzdienst und den A/V-Edgedienst verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Einen FQDN und eine IP-Adresse verwenden** .
    
      - Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** .
        

        > [!NOTE]
        > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzer öffentlicher Chatdienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

    
      - Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)** .

7.  Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:
    
      - **IPv4 in der internen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die interne Schnittstelle des Edgeservers oder Edgepools eine IPv4-Adresse anwenden möchten.
    
      - **IPv6 in der internen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die interne Schnittstelle des Edgeservers oder Edgepools eine IPv6-Adresse anwenden möchten.
    
      - **IPv4 in der externen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die externe Schnittstelle des Edgeservers oder Edgepools eine IPv4-Adresse anwenden möchten.
    
      - **IPv6 in der externen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die externe Schnittstelle des Edgeservers oder Edgepools eine IPv6-Adresse anwenden möchten.
    
    Sie können den Edgeserver oder Edgepool auch so konfigurieren, dass eine NAT-Adresse (Network Address Translation, Netzwerkadressenübersetzung) für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt** .

8.  Führen Sie in **Externe FQDNs** die folgenden Schritte aus:
    
      - Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** den externen FQDN ein.
        

        > [!NOTE]
        > Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061&nbsp;für den Zugriffs-Edgedienst, 444&nbsp;für den Webkonferenz-Edgedienst und 443&nbsp;für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z.&nbsp;B.&nbsp;443) für alle drei Dienste verwenden.

    
      - Wenn Sie in **Funktionen auswählen** nicht festgelegt haben, dass ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie die externen FQDNs für **SIP-Zugriff** , **Webkonferenzen** und **Audio/Video** ein. Behalten Sie dabei die Standardports bei.

9.  Klicken Sie auf **Weiter** .

10. Geben Sie unter **Interne IP-Adresse definieren** in **Interne IPv4-Adresse** bzw. **Interne IPv6-Adresse** die IP-Adresse Ihres Edgeservers ein, und klicken Sie anschließend auf **Weiter** .

11. Führen Sie in **Externe IP-Adresse definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv4-Adresse des Edgeservers ein, und klicken Sie dann auf **Weiter** .
    
      - Wenn Sie IPv6-Adressen verwenden möchten, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein, und klicken Sie dann auf **Weiter** .
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** , **Webkonferenzen** und **A/V-Konferenzen** die externen IPv4-Adressen der Edgeserver ein, und klicken Sie dann auf **Weiter** .
    
      - Wenn Sie IPv6-Adressen nutzen möchten und nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** , **Webkonferenzen** und **A/V-Konferenzen** die externen IPv6-Adressen der Edgeserver ein. Klicken Sie anschließend auf **Weiter** .
        

        > [!NOTE]
        > Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.



12. Wenn Sie die Verwendung der Netzwerkadressenübersetzung festgelegt haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IPv4-Adresse des A/V-Edgediensts** die öffentliche IPv4-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter** .
    

    > [!NOTE]
    > Dies muss die externe IP-Adresse des A/V-Edgediensts sein.



13. Wenn Sie sich für die Verwendung der Netzwerkadressenübersetzung und IPv6-Adressen entschieden haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IPv6-Adresse des A/V-Edgediensts** die öffentliche IPv6-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter** .
    

    > [!NOTE]
    > Dies muss die externe IP-Adresse des A/V-Edgediensts sein.



14. Wählen Sie in **Nächsten Hop definieren** unter **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Alternativ können Sie, wenn Ihre Bereitstellung einen Director umfasst, den Namen des Directors auswählen. Klicken Sie anschließend auf **Weiter** .

15. Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.
    

    > [!NOTE]
    > Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.



16. Klicken Sie auf **Fertig stellen** .

17. Veröffentlichen Sie die Topologie.

## So definieren Sie die Topologie für einen Edgeserverpool mit DNS-Lastenausgleich

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Standort, an dem Edgeserver bereitgestellt werden sollen.

3.  Klicken Sie mit der rechten Maustaste auf **Edgepools** , und klicken Sie dann auf **Neuer Edgepool** .

4.  Klicken Sie in **Neuen Edgepool definieren** auf **Weiter** .

5.  Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:
    
      - Geben Sie im Feld **Pool-FQDN** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die interne Verbindung des Edgepools an.
        

        > [!IMPORTANT]
        > Der Name, den Sie für den Pool angeben, muss der interne Name des Edgepools sein. Dieser muss als vollqualifizierter Domänenname (FQDN) definert sein. In Topologie-Generator werden FQDNs und keine Kurznamen verwendet. Verwenden Sie bei der Zuweisung von FQDNs an Computer mit Lync Server, Edgeserver und Pools nur Standardzeichen (A-Z, a-z, 0-9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.

    
      - Klicken Sie auf **Pool mit mehreren Computern** und dann auf **Weiter** .

6.  Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:
    
      - Wenn ein einziger FQDN und eine einzige IP-Adresse für den SIP-Zugriff, den Lync Server 2013-Webkonferenzdienst und A/V-Edgedienste verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Einen FQDN und eine IP-Adresse verwenden** .
    
      - Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund aktivieren (Port 5061)** . Klicken Sie auf **Weiter** .
        

        > [!NOTE]
        > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

    
      - Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)** .

7.  Klicken Sie auf **Weiter** .

8.  Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:
    
      - **IPv4 in der internen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die interne Schnittstelle des Edgeservers oder Edgepools eine IPv4-Adresse anwenden möchten.
    
      - **IPv6 in der internen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die interne Schnittstelle des Edgeservers oder Edgepools eine IPv6-Adresse anwenden möchten.
    
      - **IPv4 in der externen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die externe Schnittstelle des Edgeservers oder Edgepools eine IPv4-Adresse anwenden möchten.
    
      - **IPv6 in der externen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die externe Schnittstelle des Edgeservers oder Edgepools eine IPv6-Adresse anwenden möchten.
    
    Sie können den Edgeserver oder Edgepool auch so konfigurieren, dass eine NAT-Adresse (Network Address Translation, Netzwerkadressenübersetzung) für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt** .

9.  Führen Sie in **Externe FQDNs** die folgenden Schritte aus:
    
      - Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** den externen FQDN ein.
        

        > [!NOTE]
        > Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061&nbsp;für den Zugriffs-Edgedienst, 444&nbsp;für den Webkonferenz-Edgedienst und 443&nbsp;für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z.&nbsp;B.&nbsp;443) für alle drei Dienste verwenden.

    
      - Wenn Sie unter **Funktionen auswählen** nicht festgelegt haben, dass nur ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie den FQDN für die öffentliche Seite des Edgepools in **SIP-Zugriff** ein. Geben Sie in **Webkonferenzen** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **Audio/Video** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Verwenden Sie die Standardports.

10. Klicken Sie auf **Weiter** .

11. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen** .

12. Führen Sie in **Interner FQDN und interne IP-Adresse** die folgenden Schritte aus:
    
      - Geben Sie entsprechend Ihren Anforderungen in **Interne IPv4-Adresse** die IPv4-Adresse bzw. in **Interne IPv6-Adresse** die IPv6-Adresse des ersten Edgeservers ein, der in diesem Pool erstellt werden soll.
    
      - Geben Sie in **Interner FQDN** den FQDN des ersten Edgeservers ein, der in diesem Pool erstellt werden soll.
        

        > [!NOTE]
        > Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet FQDNs und keine Kurznamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Verwenden Sie beim Zuweisen von FQDNs der Server mit Lync&nbsp;Server, Edgeserver, Pools und Arrays nur Standardzeichen (A-Z, a-z, 0-9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS-Einträgen und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt. Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013</A>.



13. Klicken Sie auf **Weiter** .

14. Führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IP-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IP-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.

15. Klicken Sie auf **Weiter** .

16. Wenn Sie IPv6-Adressen aktivieren möchten, führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IPv6-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.
    

    > [!NOTE]
    > Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.



17. Klicken Sie auf **Fertig stellen** .
    

    > [!NOTE]
    > Der erste Edgeserver, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.



18. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen** , und wiederholen Sie die Schritte 11 bis 14 für den zweiten Edgeserver, der zum Edgepool hinzugefügt werden soll.

19. Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Weiter** .
    

    > [!NOTE]
    > Die beiden Edgeserver werden nun in Ihrem Pool angezeigt.



20. Wenn Sie die Verwendung der Netzwerkadressenübersetzung festgelegt haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IP-Adresse** die öffentliche IPv4- bzw. IPv6-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter** .
    

    > [!NOTE]
    > Dies muss die externe IP-Adresse des A/V-Edgeservers sein.



21. Wählen Sie in **Nächsten Hop definieren** in der Liste **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Oder, wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors. Klicken Sie anschließend auf **Weiter** .

22. Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.
    

    > [!NOTE]
    > Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.



23. Klicken Sie auf **Fertig stellen** .

24. Veröffentlichen Sie die Topologie.

## So definieren Sie die Topologie für einen Edgeserverpool mit Hardwaregerät zum Lastenausgleich

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Standort, an dem Edgeserver bereitgestellt werden sollen.

3.  Klicken Sie mit der rechten Maustaste auf **Edgepools** , und wählen Sie **Neuer Edgepool** .

4.  Klicken Sie in **Neuen Edgepool definieren** auf **Weiter** .

5.  Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:
    
      - Geben Sie in **FQDN** den vollqualifizierten Domänennamen ein, den Sie für die interne Seite des Edgepools ausgewählt haben.
        

        > [!IMPORTANT]
        > Der Name, den Sie für den Pool angeben, muss der interne Name des Edgepools sein. Dieser muss als vollqualifizierter Domänenname (FQDN) definert sein. In Topologie-Generator werden FQDNs und keine Kurznamen verwendet. Verwenden Sie bei der Zuweisung von FQDNs an Computer mit Lync Server, Edgeserver und Pools nur Standardzeichen (A-Z, a-z, 0-9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.

    
    <!-- end list -->
    
      - Klicken Sie auf **Pool mit mehreren Computern** und dann auf **Weiter** .

6.  Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:
    
      - Wenn ein einziger FQDN und eine einzige IP-Adresse für den SIP-Zugriffsdienst, den Lync Server-Webkonferenzdienst und den A/V-Edgedienst verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Einen FQDN und eine IP-Adresse verwenden** .
    
      - Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund aktivieren (Port 5061)** .
        

        > [!NOTE]
        > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

    
      - Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)** .

7.  Klicken Sie auf **Weiter** .

8.  Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:
    
      - **IPv4 in der internen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die interne Schnittstelle des Edgeservers oder Edgepools eine IPv4-Adresse anwenden möchten.
    
      - **IPv6 in der internen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die interne Schnittstelle des Edgeservers oder Edgepools eine IPv6-Adresse anwenden möchten.
    
      - **IPv4 in der externen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die externe Schnittstelle des Edgeservers oder Edgepools eine IPv4-Adresse anwenden möchten.
    
      - **IPv6 in der externen Schnittstelle aktivieren** : Aktivieren Sie das Kontrollkästchen, wenn Sie auf die externe Schnittstelle des Edgeservers oder Edgepools eine IPv6-Adresse anwenden möchten.
    

    > [!IMPORTANT]
    > Aktivieren Sie <STRONG>nicht</STRONG> das Kontrollkästchen <STRONG>Die externe IP-Adresse des Edgepools wird von der Netzwerkadressenübersetzung übersetzt</STRONG> . Die Netzwerkadressenübersetzung wird bei Verwendung eines Hardwaregeräts zum Lastenausgleich nicht unterstützt.



9.  Führen Sie in **Externe FQDNs** die folgenden Schritte aus:
    
      - Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** den externen FQDN ein.
        

        > [!NOTE]
        > Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061&nbsp;für den Zugriffs-Edgedienst, 444&nbsp;für den Webkonferenz-Edgedienst und 443&nbsp;für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z.&nbsp;B.&nbsp;443) für alle drei Dienste verwenden.

    
      - Wenn Sie unter **Funktionen auswählen** nicht festgelegt haben, dass nur ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie den FQDN für die öffentliche Seite des Edgepools in **SIP-Zugriff** ein. Geben Sie in **Webkonferenzen** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **Audio/Video** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Verwenden Sie die Standardports.
        

        > [!NOTE]
        > Dabei handelt es sich um die FQDNs der virtuellen IP-Adressen (VIP) für die öffentliche Seite des Pools.



10. Klicken Sie auf **Weiter** .

11. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen** .

12. Führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den **SIP-Zugriff** , den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv4-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IP-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.

13. Klicken Sie auf **Weiter** .

14. Wenn Sie IPv6-Adressen aktivieren möchten, führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IPv6-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.
    

    > [!NOTE]
    > Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.



15. Klicken Sie auf **Fertig stellen** .
    

    > [!NOTE]
    > Der erste Edgeserver, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.



16. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen** , und wiederholen Sie die Schritte 11 bis 14 für den zweiten Edgeserver, der zum Edgepool hinzugefügt werden soll.

17. Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Weiter** .
    

    > [!NOTE]
    > Die beiden Edgeserver werden nun in Ihrem Pool angezeigt.



18. Wählen Sie in **Nächsten Hop definieren** in der Liste **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Oder, wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors. Klicken Sie anschließend auf **Weiter** .

19. Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.
    

    > [!NOTE]
    > Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.



20. Klicken Sie auf **Fertig stellen** .

21. Veröffentlichen Sie die Topologie.

