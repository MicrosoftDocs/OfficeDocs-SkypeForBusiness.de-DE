---
title: 'Lync Server 2013: Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers'
TOCTitle: Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398280(v=OCS.15)
ms:contentKeyID: 49293385
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

Führen Sie das vorliegende Verfahren am zentralen Standort aus, wenn Sie die Survivable Branch Appliance oder den Survivable Branch Server nicht beim Hinzufügen zu Ihrer Topologie definiert haben.

## So definieren Sie eine Survivable Branch-Anwendung oder einen Survivable Branch-Server

1.  Klicken Sie auf **Start** , **Alle Programme** , **Microsoft Lync Server 2013** und dann auf **Lync ServerTopologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den zentralen Standort, erweitern Sie **Zweigstellenstandorte** , und erweitern Sie anschließend den Namen des Zweigstellenstandorts, in dem Sie die Survivable Branch-Anwendung oder den Survivable Branch-Server bereitstellen möchten.

3.  Klicken Sie mit der rechten Maustaste auf **Survivable Branch-Anwendungen** und klicken Sie dann auf **Neu Survivable Branch-Anwendung**.
    

    > [!IMPORTANT]
    > Unter <STRONG>Survivable Branch-Anwendungen</STRONG> definieren Sie die Survivable Branch-Server und Survivable Branch-Anwendungen.



4.  Klicken Sie im Dialogfeld **Survivable Branch-Anwendung definieren** auf **FQDN** , geben Sie den FQDN der Survivable Branch-Anwendung oder des Survivable Branch-Servers ein, die bzw. den Sie an diesem Zweigstellenstandort bereitstellen, und klicken Sie dann auf **Weiter** .
    

    > [!IMPORTANT]
    > Wenn Sie eine Survivable Branch-Anwendung definieren, muss der in <STRONG>FQDN</STRONG> eingegebene Name mit dem Survivable Branch-Anwendung-FQDN übereinstimmen, den Sie im Attribut <STRONG>servicePrincipalName</STRONG> zugewiesen haben. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013</A>.



5.  Klicken Sie auf **Front-End-Pool** , klicken Sie auf den Front-End-Server (Benutzerdienstepool) am zentralen Standort, mit dem diese Survivable Branch-Anwendung oder der Survivable Branch-Server eine Verbindung herstellen, und klicken Sie dann auf **Weiter** .

6.  Klicken Sie auf **Edgeserver** und auf den Edgepool, mit dem diese Survivable Branch-Anwendung oder der Survivable Branch-Server eine Verbindung herstellt, um für Remotebenutzer des Zweigstellenstandorts eine PSTN-Anbindung zu gewährleisten, und klicken Sie dann auf **Weiter** .

7.  Klicken Sie auf **Gateway-FQDN oder IP-Adresse** , und geben Sie den FQDN oder die IP-Adresse des Gatewaypeers ein, dem die Survivable Branch-Anwendung oder der Survivable Branch-Server für das Routing eingehender oder ausgehender PSTN-Anrufe zugeordnet ist.
    

    > [!IMPORTANT]
    > Beim Definieren einer Survivable Branch-Anwendung ist dies das Gateway, mit dem sich der Vermittlungsserver in der Survivable Branch-Anwendung zur Bereitstellung einer PSTN-Anbindung verbindet.



8.  Klicken Sie auf **Überwachungsport für das IP/PSTN-Gateway** , und akzeptieren Sie den Standardport.

9.  Klicken Sie unter **SIP-Transportprotokoll** auf das für die Survivable Branch-Anwendung oder den Survivable Branch-Server zu verwendende Transportprotokoll, und klicken Sie dann auf **Fertig stellen** .
    

    > [!NOTE]
    > Aus Sicherheitsgründen wird der Einsatz von TLS (Transport Layer Security) ausdrücklich empfohlen. Wenn Sie eine Survivable Branch-Anwendung definieren, überprüfen Sie anhand der Herstellerdokumentation für die Survivable Branch-Anwendung, ob Ihre Survivable Branch-Anwendung das TLS-Protokoll unterstützt.



10. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch Appliance oder den Survivable Branch Server, klicken Sie auf **Topologie** und anschließend auf **Veröffentlichen** .

**Nächster Schritt**: [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am Zweigstellenstandort](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

