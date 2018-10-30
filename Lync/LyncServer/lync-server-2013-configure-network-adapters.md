---
title: 'Lync Server 2013: Konfigurieren von Netzwerkadaptern'
TOCTitle: Konfigurieren von Netzwerkadaptern
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429707(v=OCS.15)
ms:contentKeyID: 49294221
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Netzwerkadaptern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Sie müssen der externen Netzwerkkarte eine oder mehrere IP-Adressen und der internen Netzwerkkarte mindestens eine IP-Adresse zuweisen.

In den folgenden Verfahren hat der Server, auf dem entweder Forefront Threat Management Gateway (TMG) 2010 oder Internet Information Server mit Routing von Anwendungsanforderungen (IIS ARR) ausgeführt wird, zwei Netzwerkkarten:

  - Eine öffentliche (oder externe) Netzwerkkarte für Clients, die versuchen, eine Verbindung zu Ihrer Website herzustellen (normalerweise über das Internet).

  - Eine private (oder interne) Netzwerkkarte für interne Server mit Lync Server, auf denen Webdienste gehostet werden.


> [!IMPORTANT]
> Wie bei den Edgeservern legen Sie das Standardgateway nur auf dem externen Netzwerkadapter fest. Das Standardgateway ist die IP-Adresse des Routers oder der externen Firewall, der bzw. die Datenverkehr in das Internet weiterleitet. Für Datenverkehr, der vom Reverseproxy zum internen Netzwerkadapter verläuft, müssen Sie beständige statische Routen (wie zum Beispiel den route -Befehl in Windows Server) für alle Subnetze verwenden, in denen sich Server befinden, auf die von den Webveröffentlichungsregeln verwiesen wird. Ein Einrichten einer beständigen Route bewirkt nicht, dass der Computer ein Router wird. Wenn IP-Weiterleitung nicht aktiviert ist, agiert der Computer nur so, dass er speziellen Datenverkehr, der für ein anderes Netzwerk bestimmt ist, an die entsprechende Schnittstelle weiterleitet. Dies bedeutet im Grundsatz ein Festlegen von zwei Gateways: eines als Standardgateway, das auf die externen Netzwerke verweist, und eines für Datenverkehr, der für die interne Schnittstelle und weiter für einen Router oder ein anderes Netzwerk bestimmt ist.<BR>Wenn Ihr Router jedoch so konfiguriert ist, dass Routen zusammengefasst werden, brauchen Sie nicht für sämtliche Subnetze beständige Routen zu erstellen. Erstellen Sie eine beständige Route für das Netzwerk, in dem der Router definiert ist, und verwenden Sie den Router dann als Standardgateway. Wenn Sie nicht genau wissen, wie Ihr Netzwerk konfiguriert ist und genauere Anleitungen bezüglich der Erstellung von Routen benötigen, wenden Sie sich an die Netzwerkexperten Ihres Unternehmens.<BR>Der Reverseproxy muss in der Lage sein, die DNS-Host-(A)-Einträge für den internen Director oder Front-End-Server sowie die nächsten Hoppool-FQDNs, die in den Webveröffentlichungsregeln verwendet werden, aufzulösen. Wie bei den Edgeservern wird aus Sicherheitsgründen empfohlen, dass Sie einen Reverseproxy nicht so konfigurieren, dass er einen DNS-Server verwendet, der sich im internen Netzwerk befindet. Das bedeutet, dass Sie entweder DNS-Server im Umkreisnetzwerk oder HOSTS-Dateieinträge auf dem Reverseproxy benötigen, in denen diese FQDNs in die internen IP-Adressen der Server aufgelöst werden.



## So konfigurieren Sie die Netzwerkkarten auf dem Reverseproxycomputer

1.  Öffnen Sie auf dem Server mit Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2, der als Reverseproxy ausgeführt wird, das Fenster **Adaptereinstellungen ändern** . Klicken Sie dazu auf **Start** , zeigen Sie auf **Systemsteuerung** , klicken Sie auf **Netzwerk- und Freigabecenter** , und klicken Sie dann auf **Adaptereinstellungen ändern** .

2.  Klicken Sie mit der rechten Maustaste auf die externe Netzwerkverbindung, die Sie für die externe Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften** .

3.  Klicken Sie auf der Seite **Eigenschaften** auf die Registerkarte **Netzwerk** , klicken Sie in der Liste **Diese Verbindung verwendet folgende Elemente** auf **Internetprotokoll Version 4 (TCP/IPv4)** , und klicken Sie dann auf **Eigenschaften** .

4.  Konfigurieren Sie auf der Seite **Internetprotokolleigenschaften (TCP/IP)** die IP-Adressen entsprechend dem Netzwerksubnetz, an das die Netzwerkkarte angeschlossen ist.
    

    > [!NOTE]
    > Wenn der Reverseproxy bereits von anderen Anwendungen genutzt wird, die HTTPS/TCP/443 verwenden (z.&nbsp;B. zum Veröffentlichen von Outlook Web Access), müssen Sie entweder eine weitere IP-Adresse hinzufügen, um die Lync Server 2013-Webdienste ohne Konflikte mit den vorhandenen Regeln und Weblisteners über HTTPS/TCP/443 veröffentlichen zu können, oder Sie müssen das vorhandene Zertifikat durch ein Zertifikat ersetzen, das die neuen externen FQDNs zum alternativen Antragstellernamen hinzufügt.



5.  Klicken Sie auf **OK** und dann nochmals auf **OK** .

6.  Klicken Sie unter **Netzwerkverbindungen** mit der rechten Maustaste auf die interne Netzwerkverbindung, die Sie für die interne Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften** .

7.  Wiederholen Sie die Schritte 3 bis 5, um die interne Netzwerkverbindung zu konfigurieren.

