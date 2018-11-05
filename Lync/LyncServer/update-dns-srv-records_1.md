---
title: Aktualisieren von DNS-SRV-Einträgen
TOCTitle: Aktualisieren von DNS-SRV-Einträgen
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49890872
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktualisieren von DNS-SRV-Einträgen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** bei dem Server oder der Domäne angemeldet sein.

In diesem Thema wird das Aktualisieren von DNS-Einträgen (Domain Name System) nach der Migration zu Lync Server 2013 beschrieben. Nachdem alle Benutzer nach Lync Server 2013 verschoben wurden und bevor der ursprüngliche Office Communications Server 2007 R2-Pool oder -Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für alle SIP-Domänen aktualisieren. Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.

**So konfigurieren Sie einen DNS-SRV-Eintrag**

1.  Klicken Sie auf dem DNS-Server auf **Start** , klicken Sie auf **Verwaltung** und anschließend auf **DNS** .

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Eintrag **Forward-Lookupzonen** , erweitern Sie die SIP-Domäne, in der Lync Server 2013 installiert ist, und navigieren Sie zur **\_tcp**-Einstellung.

3.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf **\_sipinternaltls**, und wählen Sie **Eigenschaften** aus.

4.  Aktualisieren Sie unter **Host, der diesen Dienst anbietet** den FQDN des Hosts, sodass er auf den Lync Server 2013-Pool verweist.

5.  Klicken Sie auf **OK** .

**So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann**

1.  Melden Sie sich an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen** .

3.  Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK** .

4.  Geben Sie an der Eingabeaufforderung **nslookup** *\<FQDN des Front-End-Pools\>* oder *\<FQDN des Standard Edition-Servers\>* ein, und drücken Sie anschließend die EINGABETASTE.

5.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

