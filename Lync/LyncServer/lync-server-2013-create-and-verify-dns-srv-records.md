---
title: 'Lync Server 2013: Erstellen und Überprüfen von DNS-SRV-Einträgen'
TOCTitle: Erstellen und Überprüfen von DNS-SRV-Einträgen
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398680(v=OCS.15)
ms:contentKeyID: 49294639
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen und Überprüfen von DNS-SRV-Einträgen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.

Dieses Thema beschreibt, wie Sie DNS-Einträge (Domain Name System) konfigurieren, die einerseits für Bereitstellungen von Lync Server 2013 erstellt werden und anderseits für die automatische Clientanmeldung benötigt werden. Beim Erstellen eines Front-End-Pools erstellt das Setup Active Directory-Objekte und -Einstellungen für den Pool, darunter auch den vollständig qualifizierten Domänennamen (FQDN) des Pools. Ähnliche Objekte und Einstellungen werden auch für einen Standard Edition-Server erstellt. Damit Clients mit dem Pool oder Standard Edition-Server kommunizierern können, muss der FQDN des Pools bzw. des Standard Edition-Servers im DNS registriert werden. Sie müssen für jede SIP-Domäne DNS-SRV-Einträge im internen DNS erstellen. Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.

## So konfigurieren Sie einen DNS-SRV-Eintrag

1.  Klicken Sie auf dem DNS-Server auf **Start** , klicken Sie auf **Verwaltung** und anschließend auf **DNS** .

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen** , und klicken Sie dann mit der rechten Maustaste auf die SIP-Domäne, in der Lync Server 2013 installiert wird.

3.  Klicken Sie auf **Neue Datensätze** .

4.  Klicken Sie unter **Wählen Sie einen Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** und dann auf **Eintrag erstellen** .

5.  Klicken Sie auf **Dienst** , und geben Sie **\_sipinternaltls** ein.

6.  Klicken Sie auf **Protokoll** , und geben Sie **\_tcp** ein.

7.  Klicken Sie auf **Portnummer** , und geben Sie **5061** ein.

8.  Klicken Sie auf **Host, der diesen Dienst anbietet** , und geben Sie den FQDN des Pools oder Standard Edition-Servers ein.

9.  Klicken Sie auf **OK** und dann auf **Fertig** .

## So überprüfen Sie die Erstellung eines DNS-SRV-Eintrags

1.  Melden Sie sich mit einem Konto, das Mitglied der Gruppe der authentifizierten Benutzer ist oder über gleichwertige Berechtigungen verfügt, an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen** .

3.  Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK** .

4.  Geben Sie an der Eingabeaufforderung **nslookup** ein, und drücken Sie die EINGABETASTE.

5.  Geben Sie **set type=srv** ein, und drücken Sie dann die EINGABETASTE.

6.  Geben Sie **\_sipinternaltls.\_tcp.contoso.com** ein, und drücken Sie dann die EINGABETASTE. Die folgende Ausgabe wird für den TLS-Eintrag (Transport Layer Security) angezeigt:
    
    Server: *\<dns server\>* .contoso.com
    
    Adresse: *\<IP-Adresse des DNS-Servers\>*
    
    Nicht autorisierende Antwort:
    
    \_sipinternaltls.\_tcp.contoso.com SRV-Dienstidentifizierung:
    
    Priorität = 0
    
    Gewichtung = 0
    
    Port = 5061
    
    svr hostname = poolname.contoso.com (oder A-Eintrag des Standard Edition-Servers)
    
    poolname.contoso.com Internetadresse = *\<virtuelle IP-Adresse des Systems zum Lastenausgleich\>* oder *\<IP-Adresse eines einzelnen Enterprise Edition-Servers bei Pools mit nur einem Enterprise Edition-Server\>* oder *\<IP-Adresse des Standard Edition-Servers\>*

7.  Geben Sie abschließend an der Eingabeaufforderung **exit** ein, und drücken Sie die EINGABETASTE.

## So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann

1.  Melden Sie sich an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen** .

3.  Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK** .

4.  Geben Sie an der Eingabeaufforderung **nslookup** *\<FQDN des Front-End-Pools\>* oder *\<FQDN des Standard Edition-Servers\>* ein, und drücken Sie anschließend die EINGABETASTE.

5.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

