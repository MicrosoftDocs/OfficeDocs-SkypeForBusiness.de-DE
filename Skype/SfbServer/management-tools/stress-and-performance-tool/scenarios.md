---
title: Leistungsszenarien für das Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs- und Auslastungstests mithilfe des Stress- und Leistungstools zu konfigurieren.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105371"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Leistungsszenarien für das Skype for Business Server 2015 Stress and Performance Tool
 
Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs- und Auslastungstests mithilfe des Stress- und Leistungstools zu konfigurieren.
  
Zum Ausführen des Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) muss die Skype for Business Server 2015-Topologie zunächst für Szenarien konfiguriert werden, die für Sie relevant sind. Wenn Skype for Business Server 2015 nicht oder falsch konfiguriert ist, wird ihre Lastsimulation sehr wahrscheinlich fehlschlagen. Mit dem Skype for Business Server 2015 Stress and Performance Tool bieten wir Beispielskripts für die Skype for Business Server-Verwaltungsshell und grundlegende Ressourcendateien als Teil des [Tooldownloads an.](https://www.microsoft.com/download/details.aspx?id=50367) Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype for Business Server-Bereitstellung verwendet werden. In diesem Artikel werden die Windows PowerShell beschrieben.
  
> [!NOTE]
> Dieses Thema hilft Ihnen nicht zu beschreiben, wie Sie Skype for Business Server 2015 im Allgemeinen konfigurieren, dafür gibt es weitere Planungs- und Bereitstellungsthemen. Ausführliche Informationen zum Arbeiten mit Windows PowerShell in Skype for Business Server 2015 finden Sie in der Dokumentation zur Skype for Business Server Management Shell unter Einführung einfügen HIER. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informationen zum Ausführen von Skype for Business Server-Verwaltungsshellskripts

Wir stellen PowerShell-Beispielskripts bereit, die Sie für die Vorbereitung ihrer Ladesimulationen verwenden können. Da diese Skripts für die Ladesimulation vorgesehen sind, sind sie einfach und nachlässig. Dies ist möglicherweise nicht für Ihre Produktionsumgebung geeignet. Wir betonen erneut, dass es sich bei diesen Skripts um Beispiele handelt. Sie müssen sie überprüfen und in vielen Fällen Änderungen vornehmen, die für Ihre Umgebung relevant sind, bevor Sie sie praktisch nutzen können. Wir gehen zumindest davon aus, dass Sie das Skript für die Reaktionsdienstgruppe (Response Service Group, RSG) im Sinne Ihrer Topologie ändern müssen (um die Agents anzugeben, die den Agentgruppen zugewiesen sind). Sie müssen dies jedoch nicht ausführen, wenn Sie dies nicht müssen.
  
> [!CAUTION]
> Bitte achten Sie darauf, diese Beispiele zu überprüfen und zu verstehen. Skripts überschreiben alle vorhandenen Einstellungen in der Topologie bei der Ausführung. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Clientversionsnamen des Stress and Performance Tools

Möglicherweise müssen Sie die Clientversionsprüfungsrichtlinie konfigurieren, wenn Sie die Einstellungen zuvor von den Standardwerten geändert haben. Wenn Sie sich nicht sicher sind, lesen Sie die [Dokumentation zur Clientversionsprüfung](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).
  
Das Stress and Performance Tool verwendet bei der Kommunikation mit Skype for Business Server 2015 standardmäßig die folgenden User Agent-Versionen:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Für den Mobility (UCWA)-Client in LyncPerfTool:
  
- UCWA-Perf-Tool/Webkonferenz
    
- UCWA Perf Tool/Mobile
