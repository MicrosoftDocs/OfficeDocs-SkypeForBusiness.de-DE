---
title: Leistungs Szenarien für das Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, verwenden Sie das Tool für Stress und Leistung.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983850"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Leistungs Szenarien für das Skype for Business Server 2015 Stress and Performance Tool
 
Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, verwenden Sie das Tool für Stress und Leistung.
  
Damit Sie das Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) ausführen können, muss die Skype for Business Server 2015 Topologie zunächst für die für Sie relevanten Szenarien konfiguriert werden. Wenn Skype for Business Server 2015 nicht konfiguriert ist oder nicht ordnungsgemäß konfiguriert ist, kann es sein, dass die Auslastungssimulation sehr wahrscheinlich fehlschlägt. Mit dem Skype for Business Server 2015 Stress and Performance-Tool werden Beispiel-Skype for Business Server-Verwaltungsshell-Skripts und grundlegende Ressourcendateien als Teil des [Tool Downloads](https://www.microsoft.com/download/details.aspx?id=50367)bereitgestellt. Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype for Business Server-Bereitstellung verwendet werden. In diesem Artikel werden die bereitgestellten Windows PowerShell Beispiele beschrieben.
  
> [!NOTE]
> In diesem Thema wird nicht beschrieben, wie Sie Skype for Business Server 2015 im allgemeinen konfigurieren, sondern auch andere Planungs-und Bereitstellungsthemen. Ausführliche Informationen zum Arbeiten mit Windows PowerShell in Skype for Business Server 2015 finden Sie in der Dokumentation zur Skype for Business Server Management Shell unter INSERT Introduction here. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informationen zum Durchführen von Skype for Business Server-Verwaltungsshell-Skripts

Wir stellen Beispiel-PowerShell-Skripts bereit, mit denen Sie Ihre Auslastungssimulationen vorbereiten können. Da diese Skripts für die Lastsimulation vorgesehen sind, finden Sie diese einfach und frei zügig. Dies ist möglicherweise nicht für Ihre Produktionsumgebung geeignet. Wir betonen erneut, dass es sich bei diesen Skripts um Beispiele handelt, Sie müssen diese überprüfen und in vielen Fällen Änderungen vornehmen, die für Ihre Umgebung relevant sind, bevor Sie Sie praktisch nutzen können. Es wird davon ausgegangen, dass Sie das Wiederherstellungsskript für die Reaktions Dienstgruppe (RSG) mit der Topologie im Hinterkopf ändern müssen (um die Agents anzugeben, die den Agentgruppen zugewiesen sind). Sie müssen dies jedoch nicht ausführen, wenn Sie dies nicht tun müssen.
  
> [!CAUTION]
> Achten Sie darauf, diese Beispiele zu überprüfen und zu verstehen. Bei der Ausführung werden in Skripts alle vorhandenen Einstellungen in der Topologie überschrieben. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Client Versionsnamen für Stress und Leistungs Tool

Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie zuvor die Einstellungen von den Standardwerten geändert haben. Wenn Sie sich nicht sicher sind, überprüfen Sie die [Dokumentation zur Client Versionsüberprüfung](https://msdn.microsoft.com/vsto/jj923060).
  
Das Tool Stress and Performance verwendet bei der Kommunikation mit Skype for Business Server 2015 standardmäßig die folgenden Versionen des Benutzer-Agents:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/. 0.522
    
Für den Mobility-Client (UCWA) in LyncPerfTool:
  
- UCWA perf-Tool/Webkonferenz
    
- UCWA perf Tool/Mobile
    

