---
title: 'Lync Server 2013: Lync Server-Verwaltungstools'
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
ms.openlocfilehash: a34561e9880870b53cd8f7aaad2fe13cfe33c8d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013-Verwaltungstools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In diesem Thema werden die Verwaltungstools für lync Server 2013 beschrieben.

Die Verwaltungstools werden standardmäßig auf jedem lync Server-Server installiert. Darüber hinaus können Sie die Verwaltungstools auf anderen Computern installieren, beispielsweise in dedizierten Verwaltungskonsolen. Verfahren zum Installieren der Verwaltungstools finden Sie unter [Installieren von lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md). Verfahren zum Öffnen der Tools zum Durchführen von Verwaltungsaufgaben finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

Stellen Sie sicher, dass Sie die Anforderungen für Infrastruktur, Betriebssystem, Software und Administratorrechte überprüfen, bevor Sie die lync Server-Verwaltungstools installieren oder verwenden. Details zu den Infrastrukturanforderungen finden Sie unter [Infrastrukturanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Ausführliche Informationen zu den Anforderungen des Betriebssystems und der Software zum Installieren der lync Server-Verwaltungstools finden Sie unter [Unterstützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md)und [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Die für die Installation und Verwendung der Tools erforderlichen Benutzerrechte und Berechtigungen sind unter [Administrator Rechte und-Berechtigungen für die Einrichtung und Verwaltung von lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)beschrieben.

Die Verwaltungstools bestehen aus folgenden Themen:

  - **Der lync Server-Bereitstellungs-Assistent**   verwendet zum Bereitstellen von lync Server und zum Installieren aller Verwaltungstools.

  - **Der lync Server Topology Builder**   verwendet, um Komponenten in Ihrer Bereitstellung zu definieren.

  - **Lync Server Control Panel**   verwenden Sie für die fortlaufende Verwaltung Ihrer Bereitstellung mithilfe einer webbasierten Benutzeroberfläche.

  - **Lync Server-Verwaltungsshell**   verwenden Sie die Befehlszeile für die fortlaufende Verwaltung Ihrer Bereitstellung.

  - **Das lync Server-Protokollierungstool**   verwendet, um Probleme in Ihrer Bereitstellung zu beheben.

  - **Der zentralisierte Protokollierungsdienst**   sammelt Protokolle und Ablaufverfolgungs-Dateien von einem Computer, Pool, Standort oder Global. Wählen Sie Szenarien aus, die Anbieter, Flags und Ablaufverfolgungsebenen enthalten, und definieren Sie Sie. Die Protokollierung wird gesammelt, aggregiert und mit Tools wie textbasierten Tools oder Snooper. exe angezeigt.

Sie können Ihre Bereitstellung in erster Linie mithilfe des Topologie-Generators und der lync Server-Systemsteuerung verwalten.

<div>

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Sie müssen den lync Server-Bereitstellungs-Assistenten auf dem Installationsdatenträger verwenden, um alle Verwaltungstools auf einem Computer zu installieren, auf dem Sie lync Server noch nicht installiert haben. Während des Installationsvorgangs für die Verwaltungstools wird der lync Server-Bereitstellungs-Assistent lokal zusammen mit den anderen Tools installiert, damit Sie ihn später zum Installieren von Dateien für zusätzliche Komponenten oder Entfernen von Dateien für Komponenten verwenden können, die nicht auf der Computer.

Details dazu, wie Sie den lync Server-Bereitstellungs-Assistenten zum ersten Mal auf den lync Server-Installationsmedien ausführen können, finden Sie unter [Installieren von lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Topologie-Generator

Details zu Bereitstellungsaufgaben, die Sie mithilfe des Topologie-Generators ausführen können, finden Sie in der Bereitstellungsdokumentation für jede Serverrolle.

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server-Systemsteuerung

Sie können die lync Server 2013-Systemsteuerung verwenden, um die meisten administrativen Aufgaben auszuführen, die zum Verwalten und Verwalten von lync Server 2013 erforderlich sind. Die lync Server-Systemsteuerung bietet Ihnen eine grafische Benutzeroberfläche (Graphical User Interface, GUI) zum Verwalten der Konfiguration der Server, auf denen lync Server ausgeführt wird, zusätzlich zu den Benutzern, Clients und Geräten in Ihrer Organisation. Die lync Server-Verwaltungsshell verwendet die lync Server-Systemsteuerung als den zugrunde liegenden Mechanismus zum Ausführen der lync Server-Konfiguration.

Die lync Server-Systemsteuerung wird automatisch auf jedem lync Server-Front-End-Server oder Standard Edition-Server installiert. In dieser Version verwalten Sie Edgeserver Remote. Sie können auch die lync Server-Systemsteuerung auf einem anderen Computer installieren, beispielsweise eine Verwaltungskonsole, auf der Sie lync Server zentral verwalten möchten. Ausführliche Informationen finden Sie unter [Installieren von lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Wenn Sie die Einstellungen mithilfe der lync Server-Systemsteuerung konfigurieren möchten, müssen Sie mit einem Konto angemeldet sein, das der Rolle CsAdministrator zugewiesen ist. Details zu den vordefinierten Administratorrollen, die in lync Server 2013 zur Verfügung stehen, finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A>.</P>
> <LI>
> <P>Wenn Sie die Einstellungen mithilfe der lync Server-Systemsteuerung konfigurieren möchten, müssen Sie auch einen Computer mit einer Mindestauflösung von 1024 x 768 verwenden.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server-Verwaltungsshell

In lync Server bietet die lync Server-Verwaltungsshell eine neue Methode für Verwaltung und Verwaltung. Bei der lync Server-Verwaltungsshell handelt es sich um eine leistungsfähige Verwaltungsschnittstelle, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert und einen umfassenden Satz an Cmdlets enthält, die für lync Server spezifisch sind. Mit der lync Server-Verwaltungsshell erhalten Sie einen umfangreichen Satz an Konfigurations-und Automatisierungs Steuerelementen. Der Topologie-Generator und die lync Server-Systemsteuerung implementieren beide Teilmengen dieser Cmdlets, um die Verwaltung von lync Server zu unterstützen. Die lync Server-Verwaltungsshell umfasst Cmdlets für alle lync Server-Verwaltungsaufgaben, und Sie können die Cmdlets einzeln verwenden, um Ihre Bereitstellung zu verwalten. Ausführliche Informationen finden Sie unter Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) oder in der Befehlszeilenhilfe für die einzelnen Cmdlets.

</div>

<div>

## <a name="logging-tool"></a>Protokollierungs Tool

Das lync Server-Protokollierungs Tool vereinfacht die Problembehandlung, indem Protokollierungs-und Ablaufverfolgungsinformationen vom Produkt erfasst werden, während das Produkt ausgeführt wird. Sie können das Tool verwenden, um Debug-Sitzungen für eine beliebige lync Server-Serverrolle auszuführen. Details zum Protokollierungstool finden Sie in der Dokumentation zum Protokollierungstool für lync Server 2010 in der [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)TechNet-Bibliothek unter.

<div>


> [!IMPORTANT]  
> Der zentralisierte Protokollierungsdienst wird für alle Protokollierungs Sammlung über das lync Server-Protokollierungs Tool unter allen Umständen empfohlen. Das lync Server-Protokollierungs Tool funktioniert weiterhin, aber es stört oder wird größtenteils wirkungslos, wenn der zentralisierte Protokollierungsdienst bereits ausgeführt wird. Sie sollten nur den zentralisierten Protokollierungsdienst oder das lync Server-Protokollierungs Tool verwenden, aber nie beide gleichzeitig. Weitere Informationen zum zentralen Protokollierungsdienst und dazu, warum Sie ihn ausschließlich verwenden sollten, finden Sie unter <A href="lync-server-2013-using-the-centralized-logging-service.md">Verwenden des zentralen Protokollierungsdiensts in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Infrastrukturanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Softwareanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Anforderungen an das Veröffentlichen einer Topologie in Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Öffnen der lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Problembehandlung bei der lync Server 2013-Systemsteuerung](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Verwenden des zentralisierten Protokollierungsdiensts in lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwaltungsshell für Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

