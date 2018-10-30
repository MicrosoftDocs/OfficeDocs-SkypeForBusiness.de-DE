---
title: 'Lync Server 2013: Vorbereiten der Infrastruktur und Systeme'
TOCTitle: Vorbereiten der Infrastruktur und Systeme
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398205(v=OCS.15)
ms:contentKeyID: 49293234
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten der Infrastruktur und Systeme für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Bereitstellung von Lync Server 2013 erfordert die Verwendung des Topologie-Generators zum Definieren und Veröffentlichen des Topologieentwurfs. Zur Identifizierung der für Ihre Topologie erforderlichen Komponenten verwenden Sie den Topologie-Generator, um einen Topologieentwurf zu erstellen und zu speichern. Vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator führen Sie folgende Aufgaben aus:

  - Erwerben und installieren Sie die Hardware für jede Komponente im Topologieentwurf, den Sie unter Verwendung des Topologie-Generators s erstellt und gespeichert haben. Dies umfasst alle erforderlichen Computer (Server mit Lync Server 2013, Datenbankserver, Server mit Internet Information Services (IIS) und ggf. Reverseproxyserver), Netzwerkadapter, Hardwaregeräte zum Lastenausgleich und Speichergeräte (z. B. Dateiserver). Ausführliche Informationen zum Definieren einer Topologie, welche die für Ihre Bereitstellung benötigten Komponenten angibt, finden Sie unter [Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Ausführliche Informationen zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.

  - Stellen Sie sicher, dass die Netzwerkinfrastruktur Ihren Anforderungen entspricht. Ausführliche Informationen finden Sie unter [Anforderungen an die Netzwerkinfrastruktur](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.

  - Richten Sie Active Directory-Domänendiensteein. Zum Veröffentlichen und Aktivieren der Topologie müssen die internen Server durch Computerkonten in AD DS repräsentiert werden. Dies wird erreicht, indem die Computer in die Active Directory-Domänendienste aufgenommen werden. Ausführliche Informationen zur Vorbereitung von AD DS finden Sie unter [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Erstellen Sie eine Dateifreigabe. Standard Edition-Server können die Dateifreigabe für die erforderliche Datei hosten, während in einer Enterprise-Bereitstellung die Dateifreigabe nicht auf dem Front-End-Server gehostet werden kann. Die Berechtigungen und Gruppenmitgliedschaften, die zur Bereitstellung und Festlegung der Zugriffssteuerungsliste für den Ordner und die Freigabe erforderlich sind, müssen für den Topologie-Generator ordnungsgemäß festgelegt werden, damit er erfolgreich abgeschlossen werden kann. Stellen Sie sicher, dass die Person, die den Topologie-Generator ausführt, über folgende Berechtigungen und Gruppenmitgliedschaften verfügt:
    
      - Mitglied der lokalen Administratorgruppe
    
      - Mitglied der Domänenbenutzergruppe
    
      - Vollzugriff auf Freigabe und Ordner des Dateispeichers

  - Installieren Sie SQL Server für Enterprise Edition. Zur erfolgreichen SQL Server-Einrichtung muss der SQL Server-basierte Server online sein, und der Benutzer, der die Topologie veröffentlicht, muss auf der SQL Server-Instanz ein Mitglied der SQL Server-Gruppe "sysadmin" sein.

Nachdem Sie alle Vorbereitungsaufgaben wie in diesem Thema beschrieben abgeschlossen haben, müssen Sie vor dem Veröffentlichen der Topologie außerdem die übrigen Vorbereitungsaufgaben durchführen. Hierzu gehören die Installation der Windows-Betriebssysteme und anderer erforderlicher Software, die Einrichtung von IIS und die Konfiguration von DNS. Ausführliche Informationen zu diesen Aufgaben finden Sie unter [Systemanforderungen für Server mit Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Konfigurieren von IIS für Lync Server 2013](lync-server-2013-configure-iis.md) und [Vorbereiten der Infrastruktur und Systeme für Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Zusätzlich sollten Sie sich mit den Clients und den Clientanforderungen vertraut machen. Ausführliche Informationen finden Sie unter [Bereitstellen von Clients und Geräten in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

## In diesem Abschnitt

  - [Hardwaresetup für Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Softwaresetup für Lync Server 2013](lync-server-2013-software-setup.md)

  - [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Konfigurieren von SQL Server für Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Konfigurieren der DNS-Einträge in Lync Server 2013 für einen Front-End-Pool oder Standard Edition-Server](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)

