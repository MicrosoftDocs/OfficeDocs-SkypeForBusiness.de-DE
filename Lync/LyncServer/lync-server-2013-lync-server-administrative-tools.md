---
title: 'Lync Server 2013: Lync Server-Verwaltungstools'
TOCTitle: Lync Server-Verwaltungstools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg195756(v=OCS.15)
ms:contentKeyID: 49294870
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013-Verwaltungstools

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Abschnitt werden die Verwaltungstools für Lync Server 2013 beschrieben.

Die Verwaltungstools werden standardmäßig auf jedem Lync Server-Server installiert. Sie können die Verwaltungstools auch auf anderen Computern wie etwa dedizierten Verwaltungskonsolen installieren. Verfahren zum Installieren der Verwaltungstools finden Sie unter [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md). Verfahren zum Öffnen der Tools, um Verwaltungsaufgaben durchzuführen, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

Vor der Installation oder Verwendung der Verwaltungstools von Lync Server müssen Sie die Anforderungen bezüglich Infrastruktur, Betriebssystem, Software und Administratorrechten überprüfen. Ausführliche Informationen zu den Anforderungen der Infrastruktur finden Sie unter [Infrastrukturanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Details zu den Anforderungen bezüglich Betriebssystem und Software für die Installation der Verwaltungstools von Lync Server finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md) sowie unter [Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Die für die Installation und Verwendung der Tools erforderlichen Benutzerrechte und Berechtigungen finden Sie unter [Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Zu den Verwaltungstools gehören:

  - **Lync Server-Bereitstellungs-Assistent**   Zum Bereitstellen von Lync Server und Installieren aller Verwaltungstools.

  - **Lync ServerTopologie-Generator**   Zum Festlegen der Komponenten Ihrer Bereitstellung.

  - **Lync Server-Systemsteuerung**   Zur kontinuierlichen Verwaltung Ihrer Bereitstellung über eine webbasierte Schnittstelle.

  - **Lync Server-Verwaltungsshell**   Zur kontinuierlichen Verwaltung Ihrer Bereitstellung über die Eingabeaufforderung.

  - **Lync Server-Protokollierungstool**   Zur Fehlersuche in Ihrer Bereitstellung.

  - **Zentraler Protokollierungsdienst**   Zur Erfassung von Protokollen und Nachverfolgung von Dateien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene. Wählen und definieren Sie Szenarien, die Anbieter, Flags und Ablaufverfolgungsebenen enthalten. Die Protokolle werden erfasst, aggregiert und mit beliebigen textbasierten Tools oder Snooper.exe angezeigt.

Zur Verwaltung Ihrer Bereitstellung verwenden Sie hauptsächlich Topologie-Generator und Lync Server-Systemsteuerung.

## Bereitstellungs-Assistent

Sie müssen den Lync Server-Bereitstellungs-Assistent auf dem Installationsmedium verwenden, um alle Verwaltungstools auf einem Computer zu installieren, auf dem Sie nicht bereits Lync Server installiert haben. Während der Installation der Verwaltungstools wird der Lync Server-Bereitstellungs-Assistent zusammen mit weiteren Tools lokal installiert. Sie können ihn später verwenden, um Dateien für zusätzliche Komponenten zu installieren oder Dateien für Komponenten zu entfernen, die Sie auf dem jeweiligen Computer nicht benötigen.

Ausführliche Informationen zum erstmaligen Ausführen des Lync Server-Bereitstellungs-Assistents vom Lync Server-Installationsmedium finden Sie unter [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md).

## Topologie-Generator

Ausführliche Informationen zu Bereitstellungsaufgaben, die Sie mit dem Topologie-Generator durchführen können, finden Sie in der Bereitstellungsdokumentation für die jeweilige Serverrolle.

## Lync Server-Systemsteuerung

Sie können für die meisten administrativen Aufgaben zur Verwaltung und Wartung von Lync Server 2013 die Systemsteuerung für Lync Server 2013 benutzen. Die Lync Server-Systemsteuerung bietet eine grafische Benutzeroberfläche zur Verwaltung der Konfiguration der Server mit Lync Server sowie der Benutzer, Clients und Geräte in Ihrer Organisation. Die Lync Server-Verwaltungsshell verwendet die Lync Server-Systemsteuerung als zugrunde liegenden Mechanismus für die Lync Server-Konfiguration.

Die Lync Server-Systemsteuerung wird automatisch auf jedem Front-End-Server oder Standard Edition-Server von Lync Server installiert. In dieser Version werden Edgeserver remote verwaltet. Sie können die Lync Server-Systemsteuerung auch auf einem anderen Computer installieren, z. B. einer Verwaltungskonsole, von der aus Sie Lync Server zentral verwalten können. Ausführliche Informationen finden Sie unter [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md).


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Zur Konfiguration von Einstellungen mit der Lync Server-Systemsteuerung müssen Sie sich über ein Konto anmelden, das der CsAdministrator-Rolle zugewiesen ist. Informationen zu den verfügbaren vordefinierten Administratorrollen in Lync Server&nbsp;2013 finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</A>.</P>
> <LI>
> <P>Für die Konfiguration von Einstellungen über die Lync Server-Systemsteuerung benötigen Sie einen Computer mit einer Bildschirmauflösung von mindestens 1024 x 768.</P></LI></UL>



## Lync Server-Verwaltungsshell

In Lync Server bietet die Lync Server-Verwaltungsshell eine neue Methode für die Ausführung von Verwaltungsaufgaben. Die Lync Server-Verwaltungsshell ist eine leistungsfähige Verwaltungsoberfläche, die auf der Windows PowerShell-Befehlszeilenschnittstelle aufbaut und einen umfangreichen Satz an Cmdlets speziell für Lync Server bereithält. Die Lync Server-Verwaltungsshell ermöglicht eine einfachere Steuerung der Systemverwaltung und -automatisierung. Der Topologie-Generator und die Lync Server-Systemsteuerung implementieren beide Teilmengen dieser Cmdlets, um die Verwaltung von Lync Server zu unterstützen. Die Lync Server-Verwaltungsshell enthält Cmdlets für alle Lync Server-Verwaltungsaufgaben und ermöglicht Ihnen einen individuellen Einsatz der Cmdlets zur Verwaltung Ihrer Bereitstellung. Weitere Informationen finden Sie unter [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) oder in der Befehlszeilenhilfe für jedes Cmdlet.

## Protokollierungstool

Das Lync Server-Protokollierungstool vereinfacht die Fehlersuche durch das Aufzeichnen von Protokollierungs- und Verlaufsinformationen während der Ausführung des Produkts. Sie können das Tool verwenden, um Debugsitzungen für jede Lync Server-Serverrolle auszuführen. Ausführliche Informationen zum Protokollierungstool finden Sie in der Dokumentation zum Lync Server 2010-Protokollierungstool in der TechNet-Bibliothek unter [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).


> [!IMPORTANT]
> Der Zentraler Protokollierungsdienst wird unter allen Umständen für die gesamte Protokollerfassung anstatt dem Lync Server-Protokollierungstool empfohlen. Das Lync Server-Protokollierungstool funktioniert zwar noch, wird aber beeinträchtigt oder so gut wie ineffektiv, wenn der Zentraler Protokollierungsdienst bereits ausgeführt wird. Sie sollten entweder nur den Zentraler Protokollierungsdienst oder nur das Lync Server-Protokollierungstool verwenden, aber nie beides gleichzeitig. Weitere Informationen zum Zentraler Protokollierungsdienst und dazu, warum er ausschließlich verwendet werden sollte, finden Sie unter <A href="lync-server-2013-using-the-centralized-logging-service.md">Verwenden des zentralisierten Protokollierungsdiensts</A>.



## In diesem Abschnitt

  - [Infrastrukturanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Softwareanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Anforderungen an das Veröffentlichen einer Topologie in Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Problembehandlung für die Lync Server 2013-Systemsteuerung](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Verwenden des zentralisierten Protokollierungsdiensts](lync-server-2013-using-the-centralized-logging-service.md)

## Siehe auch

#### Weitere Ressourcen

[Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md)

