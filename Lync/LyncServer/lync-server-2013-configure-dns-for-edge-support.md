---
title: 'Lync Server 2013: Konfigurieren von DNS für die Edgeunterstützung'
TOCTitle: Konfigurieren von DNS für die Edgeunterstützung
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398756(v=OCS.15)
ms:contentKeyID: 49294793
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-15_

Sie müssen DNS-Einträge (Domain Name System) für interne und externe Edgeschnittstellen konfigurieren, sowohl für Edgeserver- als auch für Reverseproxyschnittstellen. Edgeserver sind standardmäßig nicht Mitglied einer Domäne und haben keinen vollqualifizierten Domänennamen. Der Edgeserver wird nur durch den kurzen Computernamen bezeichnet und nicht durch einen vollqualifizierten Domänennamen. Der Topologie-Generator verwendet jedoch FQDNs und keine Kurznamen. Der Name des Edgeservers muss mit dem vom Topologie-Generator verwendeten FQDN übereinstimmen. Hierzu definieren Sie ein DNS-Suffix, das, wenn es mit dem Computernamen kombiniert wird, den erwarteten FQDN ergibt. Nutzen Sie das unter "So fügen Sie das DNS-Suffix zum Computernamen eines Edgeservers hinzu, der nicht Mitglied einer Domäne ist" beschriebene Verfahren, um das DNS-Suffix zum Computernamen hinzuzufügen.


> [!NOTE]
> Standardmäßig verwendet DNS einen Roundrobin-Algorithmus für die Rotation von Ressourceneintragsdaten, die in Abfrageantworten zurückgegeben werden, wenn für einen abgefragten DNS-Domänennamen mehrere Ressourceneinträge desselben Typs vorhanden sind. Der DNS-Lastenausgleich in Lync Server 2013 stützt sich auf DNS Round Robin als Teil des DNS-Lastenausgleichsmechanismus. Stellen Sie sicher, dass die Round Robin-Einstellung nicht deaktiviert ist. Stellen Sie bei Verwendung eines DNS-Servers ohne Windows-Betriebssystem außerdem sicher, dass die Round Robin-Verteilungsreihenfolge für Ressourceneinträge aktiviert ist.



Erstellen und überprüfen Sie einen DNS-SRV-Eintrag entsprechend dem Verfahren **So erstellen Sie einen DNS-SRV-Eintrag** . Definieren Sie die für den Zugriff externer Benutzer erforderlichen DNS-A-Einträge nach dem unter **So erstellen Sie einen DNS-A-Eintrag** beschriebenen Verfahren. Unter **So überprüfen Sie einen DNS-Eintrag** erfahren Sie in diesem Thema, wie Sie prüfen können, ob die Einträge richtig konfiguriert sind und funktionieren. Ausführliche Informationen zu jedem erforderlichen Eintrag für den externen Benutzerzugriff finden Sie unter [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

## So fügen Sie das DNS-Suffix zum Computernamen auf einem Edgeserver hinzu, der nicht Mitglied einer Domäne ist

1.  Klicken Sie auf dem Computer auf **Start** , klicken Sie mit der rechten Maustaste auf **Arbeitsplatz** , und klicken Sie dann auf **Eigenschaften** .

2.  Klicken Sie unter **Einstellungen für Computernamen, Domäne und Arbeitsgruppe** auf **Einstellungen ändern** .

3.  Klicken Sie auf der Registerkarte **Computername** auf **Ändern** .

4.  Klicken Sie in **Ändern des Computernamens bzw. der Domäne** auf **Mehr** .

5.  Geben Sie in **DNS-Suffix und NetBIOS-Computername** unter **Primäres DNS-Suffix des Computers** den Namen Ihrer internen Domäne (z. B. corp.contoso.com) ein, und klicken Sie dann dreimal auf **OK** .

6.  Starten Sie den Computer neu.

## So erstellen Sie einen DNS-SRV-Eintrag

1.  Klicken Sie auf dem geeigneten DNS-Server nacheinander auf **Start** , **Systemsteuerung** , **Verwaltung** und dann auf **DNS** .
    

    > [!IMPORTANT]
    > Sie müssen DNS so konfigurieren, dass Folgendes vorhanden ist: 1.) externe DNS-Einträge für externe DNS-Lookups durch Remotebenutzer und Verbundpartner; 2.) Einträge für DNS-Lookups zur Verwendung durch die Edgeserver im Umkreisnetzwerk (auch als überwachtes Subnetz bezeichnet), einschließlich A-Einträge für die internen Server mit Lync Server 2013; und 3.) interne DNS-Einträge für Lookups durch die internen Clients und Server mit Lync Server 2013.



2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen** , und klicken Sie mit der rechten Maustaste auf die Domäne, in der Lync Server 2013 installiert ist.

3.  Klicken Sie auf **Neue Datensätze** .

4.  Klicken Sie unter **Wählen Sie einen Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** und dann auf **Eintrag erstellen** .

5.  Stellen Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag bereit.

## So erstellen Sie einen DNS-A-Eintrag

1.  Klicken Sie auf dem DNS-Server nacheinander auf **Start** , **Systemsteuerung** , **Verwaltung** und dann auf **DNS** .

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen** , und klicken Sie mit der rechten Maustaste auf die Domäne, in der Lync Server 2013 installiert ist.

3.  Klicken Sie auf **Neuer Host (A)** .

4.  Stellen Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag bereit.

## So überprüfen Sie einen DNS-Eintrag

1.  Melden Sie sich an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen** .

3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:
    
        nslookup <FQDN edge interface>

4.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

## Siehe auch

#### Aufgaben

[Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  

#### Konzepte

[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

