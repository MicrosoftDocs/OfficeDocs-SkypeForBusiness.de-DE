---
title: 'Lync Server 2013: Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste'
TOCTitle: Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh500728(v=OCS.15)
ms:contentKeyID: 49294714
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Thema wird beschrieben, wie der DNS-SRV-Eintrag konfiguriert wird, der erforderlich ist, damit ein Lync Server 2013  Edgeserver eine Weiterleitung an einen gehosteten Exchange-Dienst durchführen kann, z. B. Microsoft Exchange Online.

## So erstellen Sie einen externen DNS-SRV-Eintrag für den gehosteten Exchange-Dienst

1.  Melden Sie sich am externen DNS-Server als Mitglied der Gruppe "DnsAdmins" an.

2.  Klicken Sie auf **Start** , auf **Verwaltung** und anschließend auf **DNS** .

3.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen** , und wählen Sie die SIP-Domäne aus, in der Lync Server 2013 installiert wird.
    

    > [!IMPORTANT]
    > Sie müssen den DNS-SRV-Eintrag in der SIP-Domäne erstellen, in der Lync Server installiert ist oder wird. Wenn Sie den SRV-Eintrag erstellen, muss für das Feld "Host, der diesen Dienst anbietet" der externe FQDN des Edgepools verwendet werden. Wenn beispielsweise der externe FQDN des Edgepools "edge01.contoso.net" ist, geben Sie diesen Wert in das Feld ein. Der FQDN muss sich auch in derselben Domäne wie der DNS-A-Eintrag (Hosts) befinden.



4.  Klicken Sie mit der rechten Maustaste auf die ausgewählte Domäne, und klicken Sie dann auf **Andere neue Einträge** .

5.  Klicken Sie In **Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** , und klicken Sie dann auf **Eintrag erstellen** .

6.  Klicken Sie in **Neuen Eintrag erstellen** auf **Dienst** , und geben Sie dann **\_sipfederationtls** ein.

7.  Klicken Sie auf **Protokoll** und geben Sie **\_tcp** ein.

8.  Klicken Sie auf **Portnummer** und geben Sie **5061** ein.

9.  Klicken Sie auf **Host, der diesen Dienst anbietet:** , und geben Sie dann den vollqualifizierten Domänennamen (FQDN) des Lync Server 2013  Edgepools ein, der Zugriff auf das Lync Server 2013-System für vertrauenswürdige externe Clients bietet.
    

    > [!NOTE]
    > Die Domäne muss auch als autorisierende akzeptierte Domäne in den Exchange Online-Einstellungen eingerichtet werden. Ausführliche Informationen finden Sie im Thema zum Erstellen von akzeptierten Domänen unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=229762">http://go.microsoft.com/fwlink/?linkid=229762</A>.



10. Klicken Sie auf **OK** und dann auf **Fertig** .

## So stellen Sie sicher, dass der DNS-SRV-Eintrag erfolgreich erstellt wurde

1.  Melden Sie sich an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen** .

3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:
    
        nslookup <FQDN Lync Edge Pool>

4.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

## Siehe auch

#### Konzepte

[Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

