---
title: 'Lync Server 2013: Anforderungen an das Veröffentlichen einer Topologie'
TOCTitle: Anforderungen an das Veröffentlichen einer Topologie
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg195733(v=OCS.15)
ms:contentKeyID: 49294611
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen an das Veröffentlichen einer Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Im Rahmen dieses Themas werden die Anforderungen bezüglich der Infrastruktur und der Software beschrieben, die spezifisch für die Veröffentlichung einer Topologie sind, unabhängig davon, ob der Topologie-Generator oder die Verwaltungsshell für Lync Server 2013-Befehlszeilenschnittstelle verwendet wird. Diese Anforderungen gelten zusätzlich zu den Anforderungen an das allgemeine Betriebssystem, Software und Berechtigungen, die für alle Verwaltungstools von Lync Server 2013 gelten. Stellen Sie sicher, dass alle Anforderungen an Verwaltungstools erfüllt sind, ehe Sie mit der Veröffentlichung einer Topologie beginnen.

  - Sie müssen den Topologie-Generator auf einem Computer ausführen, der derselben Domäne oder Gesamtstruktur der Lync Server 2013-Bereitstellung, die Sie erstellen, angehört. In diesem Fall sind die vorbereitenden Schritte für Active Directory-Domänendienste bereits abgeschlossen, sodass Sie die Verwaltungstools auf diesem Computer für die erfolgreiche Veröffentlichung der Topologie verwenden können.

  - Die in der Topologie definierten Computer müssen mit der Domäne (mit Ausnahme der Edgeserver) und in AD DS verbunden werden. Die Computer müssen beim Veröffentlichen der Topologie jedoch nicht online sein.

  - Die Dateifreigabe für den Pool muss erstellt worden und für Remotebenutzer verfügbar sein.

  - Für die Veröffentlichung eines Enterprise Edition- Front-End-Pools muss der SQL Server-basierte Back-End-Server mit der Domäne verbunden werden, in der Sie die Server bereitstellen. Der Server muss online und mithilfe der entsprechenden Firewallregeln konfiguriert sein, um Remotebenutzern zur Verfügung zu stehen. Ausführliche Informationen zum Festlegen von Firewallausnahmen finden Sie unter [Grundlegendes zu den Firewallanforderungen für SQL Server mit Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Weitere Details über die Konfiguration von SQL Server finden Sie unter [Konfigurieren von SQL Server für Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    

    > [!NOTE]
    > Der Standard Edition-Server verfügt über eine verbundene Datenbank, die die veröffentlichte Konfiguration übernimmt. Sie müssen zunächst den Installationsschritt <STRONG>Ersten Standard Edition-Server vorbereiten</STRONG> im Lync Server-Bereitstellungs-Assistent ausführen.



## Siehe auch

#### Aufgaben

[Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  

#### Konzepte

[Softwareanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  

#### Weitere Ressourcen

[Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

