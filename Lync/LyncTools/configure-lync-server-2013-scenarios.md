---
title: Konfigurieren von lync Server 2013 Szenarien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f05039aab6d09fe498ffce465554d6bbbbbebaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>Konfigurieren von lync Server 2013 Szenarien

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-28_

Zum Ausführen des lync Server 2013 Stress and Performance Tool (LyncPerfTool) muss die lync Server 2013 Topologie zunächst für die Szenarien konfiguriert werden, die ausgeführt werden. Wenn lync Server 2013 nicht konfiguriert ist oder nicht ordnungsgemäß konfiguriert ist, tritt bei der Auslastungssimulation in den meisten Fällen ein Fehler auf. Mit dem lync Server 2013 Stress and Performance-Tool haben wir Beispiel lync Server-Verwaltungsshell Skripts und grundlegende Ressourcendateien bereitgestellt, die als Ausgangspunkt für die Konfiguration von lync Server 2013 verwendet werden können. In diesem Thema werden die bereitgestellten Windows PowerShell Beispiele beschrieben. Beachten Sie, dass es nicht das Ziel dieses Themas ist, die Konfiguration von lync Server 2013 im Allgemeinen zu beschreiben. Ausführliche Informationen zum Arbeiten mit Windows PowerShell in lync Server 2013 finden Sie in der lync Server-Verwaltungsshell Dokumentation <https://technet.microsoft.com/library/gg398474.aspx>unter.

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Informationen zum Durchführen von lync Server-Verwaltungsshell Skripts

Wir haben Beispiel lync Server-Verwaltungsshell Skripts bereitgestellt, die möglicherweise zur Vorbereitung auf die Ausführung der Auslastungssimulation verwendet werden. Da die Skripts für die Lastsimulation vorgesehen sind, sind Sie einfach und frei zügig und daher möglicherweise nicht für die Produktion geeignet. Alle Skripts sind Beispiele und müssen überprüft und in einigen Fällen geändert werden, um Ihre Topologie widerzuspiegeln. Es wird davon ausgegangen, dass das Szenario für den Reaktionsgruppendienst (RGS) geändert werden muss, um die Agents anzugeben, die den Agentgruppen zugewiesen sind. Sie haben jedoch die Möglichkeit, diese Last nicht zu simulieren.

<div>


> [!WARNING]  
> Achten Sie darauf, die bereitgestellten Beispiele zu überprüfen und zu verstehen. In Skripts werden alle vorhandenen Einstellungen in der Topologie überschrieben.



</div>

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Windows PowerShell und dem lync Server-Verwaltungsshell finden Sie im lync Server 2013 Windows PowerShell- <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>Blog unter.



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Client Versions-Moniker für Spannungs-und Leistungs Tool

Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie die Einstellungen von den Standardwerten geändert haben. Ausführliche Informationen finden Sie unter "Konfigurieren unterstützter Clientversionen <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>" unter. Das Tool für die lync Server 2013 Spannung und Leistung verwendet standardmäßig die folgenden Versionen des Benutzer-Agents bei der Kommunikation mit lync Server 2013:

  - LSPT/15.0.0.0 (lync Server 2013 Stress and Performance Tool)

  - OCPHONE/. 0.522

Diese sind für den Mobility (UCWA)-Client in LyncPerfTool:

  - Ucwa perf-Tool/Webkonferenz

  - Ucwa perf Tool/Mobile

</div>

</div>

<span> </span>

</div>

</div>

</div>

