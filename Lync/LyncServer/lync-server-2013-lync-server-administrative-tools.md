---
title: 'Lync Server 2013: lync Server Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ac976f2c05268b5cf864511b19db1fd251edbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525112"
---
# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 Verwaltungstools

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

In diesem Thema werden die Verwaltungstools für lync Server 2013 beschrieben.

Die Verwaltungstools werden auf jedem lync Server Server standardmäßig installiert. Sie können die Verwaltungstools auch auf anderen Computern wie etwa dedizierten Verwaltungskonsolen installieren. Verfahren zum Installieren der Verwaltungstools finden Sie unter [install lync Server 2013 Administration Tools](lync-server-2013-install-lync-server-administrative-tools.md). Verfahren zum Öffnen der Tools zum Ausführen von Verwaltungsaufgaben finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

Stellen Sie sicher, dass Sie die Anforderungen an Infrastruktur, Betriebssystem, Software und Administratorrechte überprüfen, bevor Sie die lync Server Verwaltungstools installieren oder verwenden. Ausführliche Informationen zu den Infrastrukturanforderungen finden Sie unter [Administrative Tools Infrastructure Requirements in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Ausführliche Informationen zu den Betriebssystem-und Softwareanforderungen für die Installation der lync Server Verwaltungstools finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md)sowie [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Die für die Installation und Verwendung der Tools erforderlichen Benutzerrechte und-Berechtigungen werden in den [Administrator Rechten und-Berechtigungen beschrieben, die für die Einrichtung und Verwaltung von lync Server 2013 erforderlich](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)sind.

Zu den Verwaltungstools gehören:

  - **Lync Server-Bereitstellungs-Assistent**     Wird verwendet, um lync Server bereitzustellen und alle Verwaltungstools zu installieren.

  - **Lync Server Topologie-Generator**     Verwenden Sie, um Komponenten in Ihrer Bereitstellung zu definieren.

  - **Lync Server-Systemsteuerung**     Verwenden Sie für die laufende Verwaltung Ihrer Bereitstellung über eine webbasierte Schnittstelle.

  - **Lync Server-Verwaltungsshell**     Verwenden Sie für die laufende Verwaltung Ihrer Bereitstellung über die Befehlszeile.

  - **Lync Server Protokollierungstool**     Verwenden Sie zur Behandlung von Problemen in Ihrer Bereitstellung.

  - **Zentralisierter Protokollierungsdienst**     Sammeln von Protokollen und Ablaufverfolgungsdateien von einem Computer, Pool, Standort oder Global. Auswählen und Definieren von Szenarien, die Anbieter, Kennzeichen und Ablaufverfolgungsstufen enthalten Die Protokollierung wird gesammelt, aggregiert und mit Tools wie einem textbasierten Tool oder Snooper.exe angezeigt.

Sie können Ihre Bereitstellung verwalten, indem Sie in erster Linie den Topologie-Generator und lync Server-Systemsteuerung verwenden.

<div>

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Sie müssen den auf dem Installationsdatenträger enthaltenen lync Server-Bereitstellungs-Assistenten verwenden, um alle Verwaltungstools auf einem Computer zu installieren, auf dem Sie lync Server noch nicht installiert haben. Während der Installation von Verwaltungstools wird der lync Server-Bereitstellungs-Assistent lokal zusammen mit den anderen Tools installiert, sodass Sie ihn später zum Installieren von Dateien für zusätzliche Komponenten oder zum Entfernen von Dateien für Komponenten verwenden können, die Sie auf dem Computer nicht benötigen.

Ausführliche Informationen dazu, wie Sie den lync Server-Bereitstellungs-Assistenten erstmals auf dem lync Server Installationsmedium ausführen, finden Sie unter [install lync Server 2013 Administration Tools](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Topologie-Generator

Ausführliche Informationen zu Bereitstellungsaufgaben, die Sie mithilfe des Topologie-Generators ausführen können, finden Sie in der Bereitstellungsdokumentation für jede Serverrolle.

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server-Systemsteuerung

Sie können lync Server 2013 Systemsteuerung verwenden, um die meisten administrativen Aufgaben auszuführen, die zum Verwalten und warten von lync Server 2013 erforderlich sind. Lync Server-Systemsteuerung bietet Ihnen eine grafische Benutzeroberfläche zur Verwaltung der Konfiguration der Server, auf denen lync Server läuft, zusätzlich zu den Benutzern, Clients und Geräten in Ihrer Organisation. Lync Server-Verwaltungsshell verwendet lync Server-Systemsteuerung als den zugrunde liegenden Mechanismus zum Ausführen lync Server Konfiguration.

Lync Server-Systemsteuerung wird automatisch auf jeder lync Server Front-End-Server oder Standard Edition-Server installiert. In dieser Version werden Edgeserver remote verwaltet. Sie können lync Server-Systemsteuerung auch auf einem anderen Computer installieren, beispielsweise in einer Verwaltungskonsole, von der Sie lync Server zentral verwalten möchten. Ausführliche Informationen finden Sie unter [install lync Server 2013 Administration Tools](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Zum Konfigurieren von Einstellungen mit lync Server-Systemsteuerung müssen Sie mit einem Konto angemeldet sein, das der Rolle CsAdministrator zugewiesen ist. Ausführliche Informationen zu den in lync Server 2013 verfügbaren vordefinierten Administratorrollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A>.</P>
> <LI>
> <P>Zum Konfigurieren von Einstellungen mit lync Server-Systemsteuerung müssen Sie auch einen Computer mit einer minimalen Bildschirmauflösung von 1024 x 768 verwenden.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server-Verwaltungsshell

In lync Server bietet der lync Server-Verwaltungsshell eine neue Methode für Verwaltung und Verwaltung. Lync Server-Verwaltungsshell ist eine leistungsstarke Verwaltungsschnittstelle, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert und eine umfassende Gruppe von lync Server spezifischen Cmdlets enthält. Mit lync Server-Verwaltungsshell erhalten Sie eine umfangreiche Reihe von Konfigurations-und Automatisierungs Steuerelementen. Topologie-Generator und lync Server-Systemsteuerung implementieren beide Teilmengen dieser Cmdlets, um die Verwaltung von lync Server zu unterstützen. Das lync Server-Verwaltungsshell enthält Cmdlets für alle lync Server Verwaltungsaufgaben, und Sie können die Cmdlets einzeln zum Verwalten Ihrer Bereitstellung verwenden. Ausführliche Informationen finden Sie in der Dokumentation zu [lync Server 2013 Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) oder in der Befehlszeilenhilfe für jedes Cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Protokollierungstool

Das lync Server Protokollierungs Tool erleichtert die Problembehandlung durch Erfassen von Protokollierungs-und Ablaufverfolgungsinformationen aus dem Produkt während der Ausführung des Produkts. Sie können das Tool verwenden, um Debug-Sitzungen auf jeder lync Server-Server Rolle auszuführen. Ausführliche Informationen zum Protokollierungstool finden Sie in der Dokumentation zum lync Server 2010 Protokollierungstool in der TechNet-Bibliothek unter [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .

<div>


> [!IMPORTANT]  
> Der zentralisierte Protokollierungsdienst wird für alle Protokollierungs Sammlungen über das lync Server Protokollierungs Tool unter allen Umständen empfohlen. Das lync Server-Protokollierungs Tool funktioniert zwar weiterhin, es stört oder wird jedoch meist wirkungslos, wenn der zentralisierte Protokollierungsdienst bereits aktiv ist. Sie sollten nur den zentralisierten Protokollierungsdienst oder das lync Server Protokollierungs Tool verwenden, jedoch niemals gleichzeitig. Weitere Informationen zum zentralisierten Protokollierungsdienst und warum er ausschließlich verwendet werden sollte, finden Sie unter <A href="lync-server-2013-using-the-centralized-logging-service.md">using the zentralisiert Logging Service in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Infrastrukturanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Softwareanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Für die Einrichtung und Verwaltung von lync Server 2013 erforderliche Administrator Rechte und-Berechtigungen](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Anforderungen zum Veröffentlichen einer Topologie in lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installieren von lync Server 2013 Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Öffnen lync Server 2013 Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Problembehandlung für die Lync Server 2013-Systemsteuerung](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Verwenden des zentralisierten Protokollierungsdiensts in lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server 2013 Management-Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

