---
title: 'Lync Server 2013: Konfigurieren von DNS-Hosteinträgen'
TOCTitle: Konfigurieren von DNS-Hosteinträgen
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398593(v=OCS.15)
ms:contentKeyID: 49294473
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von DNS-Hosteinträgen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

## So konfigurieren Sie DNS-Hosteinträge (A)

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start** , klicken Sie auf **Verwaltung** und anschließend auf **DNS** .

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen** , und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der Lync Server 2013 installiert wird.

3.  Klicken Sie auf **Neuer Host (A oder AAAA)** .

4.  Klicken Sie auf **Name** , und geben Sie den Hostnamen für den Pool ein (der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Klicken Sie auf **IP-Adresse** , und geben Sie die virtuelle IP-Adresse (VIP) des Lastenausgleichssystems für den Front-End-Pool ein.
    

    > [!IMPORTANT]
    > In Bereitstellungen, die einen Director-Pool verwenden, sollten die Hosteinträge (A) für die einfachen URLs auf die VIP des Director-Lastenausgleichssystems zeigen.

    

    > [!NOTE]
    > Wenn Sie nur einen Enterprise Edition-Server oder Director bereitstellen, der ohne ein Lastenausgleichssystem mit der Topologie verbunden ist, oder wenn Sie einen Standard Edition-Server bereitstellen, geben Sie die IP-Adresse des Enterprise Edition-Servers, Standard Edition-Servers oder Directors ein. Ein Lastenausgleichssystem ist erforderlich, wenn sich mehrere Enterprise Edition-Server oder Directors in einem Pool befinden. Bei Standard Edition-Servern werden keine Lastenausgleichssysteme verwendet.



6.  Klicken Sie auf **Host hinzufügen** und dann auf **OK** .

7.  Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 4 und 5.

8.  Wenn Sie alle erforderlichen A-Einträge erstellt haben, klicken Sie auf **Fertig** .

