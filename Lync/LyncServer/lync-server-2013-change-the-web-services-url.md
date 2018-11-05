---
title: Ändern der Webdienste-URL in Lync Server 2013
TOCTitle: Ändern der Webdienste-URL in Lync Server 2013
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520992(v=OCS.15)
ms:contentKeyID: 49293943
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern der Webdienste-URL in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-11-16_

Bei der Einrichtung von Front-End-Pools und Standard Edition-Servern können Sie einen externen Webfarm-FQDN sowie entsprechende Ports konfigurieren. Wenn Sie diese URL nicht während der Ausführung des Lync Server-Bereitstellungs-Assistenten konfiguriert haben, müssen Sie diese Einstellungen manuell festlegen. Ein Administrator muss diese Einstellungen normalerweise nicht ändern, da bereits die empfohlenen Standardports eingerichtet sind.


> [!NOTE]
> Der folgende Screenshot wurde bei der Konfiguration eines Standard Edition-Servers erstellt, deshalb ist die Option zum Außerkraftsetzen des FQDN deaktiviert. Diese Option ist aktiviert, wenn Sie einen Enterprise Edition-Server in einem Front-End-Pool konfigurieren.



![Bearbeiten von Webdienst-Pooleinstellungen](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Bearbeiten von Webdienst-Pooleinstellungen")

## So konfigurieren Sie Webdienste

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

3.  Wählen Sie im Topologie-Generator in der Konsolenstruktur unter **Front-End-Server der Standard Edition**, **Front-End-Pools der Enterprise Edition** und **Director-Pools** den Poolnamen aus. Klicken Sie mit der rechten Maustaste auf den Namen, dann auf **Eigenschaften bearbeiten** und schließlich auf **Webdienste**.

4.  Fügen Sie unter **Externer FQDN für Webdienste** den FQDN hinzu bzw. bearbeiten Sie ihn, und klicken Sie dann auf **OK**.
    

    > [!WARNING]
    > Wenn Sie über mehr als einen Front-End-Pool oder über mehr als eine Front-End-Server verfügen, muss der FQDN für externe Webdienste eindeutig sein. Angenommen, Sie definieren den FQDN für externe Webdienste einer Front-End-Server als <STRONG>pool01.contoso.com</STRONG>. In diesem Fall können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder für eine andere Front-End-Server verwenden. Wenn Sie darüber hinaus Directors bereitstellen, muss der für einen Director oder einen Directorpool definierte FQDN für externe Webdienste sowohl in Bezug auf jeden anderen Director oder jeden anderen Directorpool als auch in Bezug auf jeden Front-End-Pool und jede Front-End-Server eindeutig sein.



5.  Stellen Sie sicher, dass die Überwachungs- und veröffentlichten Ports für Ihre Umgebung korrekt konfiguriert sind.

6.  Wiederholen Sie diese Schritte für alle Standard Edition-Server, Front-End-Pools und Director-Pools in Ihrer Umgebung.

7.  Klicken Sie in der Konsolenstruktur auf **Lync Server 2013**, und klicken Sie anschließend im Bereich **Aktionen** auf **Topologie veröffentlichen**.

Bei der Konfiguration der Überwachungs- und veröffentlichten Ports sollten Sie folgende Anforderungen beachten:

  - Die angezeigten Überwachungsports entsprechen den Ports, die für die Internetinformationsdienste (Internet Information Services, IIS) auf jedem Front-End-Server konfiguriert sind.

  - Der interne und der externe Überwachungsport müssen für IIS unterschiedlich lauten. Bei den externen Überwachungsports stimmen diese in der Regel überein, da ein Port das Hardwaregerät zum Lastenausgleich für den internen Webdatenverkehr und ein Port den Reverseproxyserver für den externen Webdatenverkehr repräsentiert.

  - Sie können die internen Webdienste in einem Front-End-Pool, einer Director oder einem Directorpool überschreiben und einen eigenen FQDN definieren.
    

    > [!WARNING]
    > Wenn Sie den internen Webdienst mit einem eigenen FQDN überschreiben, muss der FQDN gegenüber jedem anderen Front-End-Pool, jedem anderen Director und jedem anderen Directorpool eindeutig sein.



  - Die veröffentlichten Ports müssen auf dem Reverseproxy oder auf dem Hardwaregerät zum Lastenausgleich als Überwachungsports konfiguriert werden.

  - Für einen Front-End-Pool (nicht im Beispiel gezeigt) muss sich der interne FQDN für den SIP-Pool von dem internen FQDN der Webdienste unterscheiden, da der Webdatenverkehr über das Hardwaregerät zum Lastenausgleich und der interne Datenverkehr des SIP-Pools über den DNS-Lastenausgleich verläuft. Diese Anforderung muss erfüllt werden.

  - Für eine Lync Server Standard Edition-Bereitstellung muss und kann ein interner Webdienste-FQDN nicht außer Kraft gesetzt werden, da für diesen Server kein Lastenausgleich verfügbar ist.

  - Wenn Sie in Ihrer Umgebung ein Hardwaregerät zum Lastenausgleich einsetzen, das sowohl für den internen SIP-Datenverkehr als auch für Webdatenverkehr genutzt wird, kann der Topologie-Generator nicht zwischen beidem unterscheiden.
    
    Webdienst-FQDNs sollten einfach voneinander unterschieden werden können, da damit sichergestellt werden kann, dass die URL-Umleitung Clients auf den geeigneten Server verweist. Wenn Sie beispielsweise zwei FQDNs haben, sollten Sie in Betracht ziehen, einen der beiden meeting.contoso.com und den anderen conferencing.contoso.com zu nennen. Potenziell können Umleitungsprobleme auftreten, wenn Sie zwei FQDNs mit ähnlicheren Namen wie meet1.contoso.com und meet2.contoso.com haben.

Die externen Webdienste funktionieren zusammen mit einem Reverseproxy im Umkreisnetzwerk. Über diese Webdienste erhalten Clients externen Zugriff auf das Programm. Die an dieser Stelle konfigurierten FQDNs werden an Clients gesendet, wenn diese sich anmelden, und sie werden bei einer Remoteverbindung zum Herstellen einer HTTPS-Verbindung zurück zum Reverseproxy eingesetzt. Der Reverseproxyserver leitet den FQDN für den externen Webdienst an ein internes Hardwaregerät zum Lastenausgleich oder direkt an den Pool weiter. Der Reverseproxy muss in der Lage sein, den externen FQDN für die Webdienste in die IP-Adresse des internen Webservers aufzulösen. Der FQDN für externe Webdienste muss im öffentlichen Internet auflösbar sein.

Wenn Ihr interner Server ein Standard Edition-Server ist, entspricht der interne FQDN dem FQDN des Standard Edition-Servers. Handelt es sich bei Ihrem internen Server um einen Front-End-Pool, entspricht der FQDN einer virtuellen IP (VIP) für das Hardwaregerät zum Lastenausgleich, das den Lastenausgleich für die internen Webfarmserver durchführt. Ein Hardwaregerät zum Lastenausgleich ist in einem Front-End-Pool mit mehreren Enterprise Edition-Servern erforderlich. Für einen Standard Edition-Server oder einen einzelnen Front-End-Server der Enterprise Edition ist kein Lastenausgleichssystem erforderlich.

