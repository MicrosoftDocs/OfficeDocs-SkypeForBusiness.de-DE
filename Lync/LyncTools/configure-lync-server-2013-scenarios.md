---
title: Konfigurieren von lync Server 2013-Szenarien
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
ms.openlocfilehash: 789c3ee8c18b5fb0e92ef9a520152644bebbdde1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>Konfigurieren von lync Server 2013-Szenarien

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-12-28_

Zum Ausführen des lync Server 2013-Stress-und-Leistungstools (LyncPerfTool) muss die lync Server 2013-Topologie zunächst für die Szenarios konfiguriert werden, die ausgeführt werden. Wenn lync Server 2013 nicht konfiguriert ist oder falsch konfiguriert ist, schlägt die Auslastungssimulation in den meisten Fällen fehl. Mit dem lync Server 2013-Stress-und-Leistungs Tool haben wir Beispielskripts zur lync Server-Verwaltungsshell und grundlegende Ressourcendateien bereitgestellt, die als Ausgangspunkt für die Konfiguration von lync Server 2013 verwendet werden können. In diesem Thema werden die bereitgestellten Windows PowerShell-Beispiele beschrieben. Beachten Sie, dass es nicht das Ziel dieses Themas ist, die Konfiguration von lync Server 2013 im Allgemeinen zu beschreiben. Details zum Arbeiten mit Windows PowerShell in lync Server 2013 finden Sie in der Dokumentation zur lync Server-Verwaltungsshell <https://technet.microsoft.com/en-us/library/gg398474.aspx>unter.

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Informationen zum Ausführen von lync Server-Verwaltungsshell-Skripts

Wir haben Beispielskripts für die lync Server-Verwaltungsshell bereitgestellt, die möglicherweise zur Vorbereitung der Auslastungssimulation verwendet werden. Da die Skripts für die Auslastungssimulation vorgesehen sind, sind Sie einfach und frei zügig und daher möglicherweise nicht für die Produktion geeignet. Alle Skripts sind Beispiele und müssen überprüft und in einigen Fällen geändert werden, um Ihre Topologie wiederzugeben. Wir gehen davon aus, dass das Szenario des Reaktionsgruppendiensts (RGS) mindestens geändert werden muss, um die Agents anzugeben, die den Agentengruppen zugewiesen sind. Sie haben jedoch die Möglichkeit, diese Last nicht zu simulieren.

<div>


> [!WARNING]  
> Achten Sie darauf, die bereitgestellten Beispiele zu überprüfen und zu verstehen. In Skripts werden alle vorhandenen Einstellungen in der Topologie überschrieben.



</div>

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Windows PowerShell und der lync Server-Verwaltungsshell finden Sie im Windows PowerShell-Blog zu <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>lync Server 2013 unter.



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Client Version-Moniker für Spannungs-und Leistungs Tool

Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie die Einstellungen von den Standardwerten geändert haben. Ausführliche Informationen finden Sie unter "Konfigurieren unterstützter Clientversionen <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>" unter. Das Stress-und Leistungs Tool von lync Server 2013 verwendet die folgenden Benutzer-Agent-Versionen standardmäßig bei der Kommunikation mit lync Server 2013:

  - LSPT/15.0.0.0 (lync Server 2013 Stress and Performance Tool)

  - OCPHONE/. 0.522

Diese sind für den Mobilitäts Client (UCWA) in LyncPerfTool:

  - Ucwa-perf-Tool/Webkonferenz

  - Ucwa perf Tool/Mobil

</div>

</div>

<span> </span>

</div>

</div>

</div>

