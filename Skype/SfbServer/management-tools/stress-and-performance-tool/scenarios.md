---
title: Leistung Szenarien für die Skype für Business Server 2015 Stress and Performance-Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Aufgaben, die Sie Schritte zum Konfigurieren von Skype für Business Server 2015 erforderlichen zu Leistung und Auslastungstests, führen Sie den Stress and Performance-Tool verwenden.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194618"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Leistung Szenarien für die Skype für Business Server 2015 Stress and Performance-Tool
 
Aufgaben, die Sie Schritte zum Konfigurieren von Skype für Business Server 2015 erforderlichen zu Leistung und Auslastungstests, führen Sie den Stress and Performance-Tool verwenden.
  
Um die Skype für Business Server 2015 Stress and Performance-Tool (LyncPerfTool) ausgeführt werden soll, muss die Skype für Business Server 2015 Topologie zunächst für Szenarien, die für Sie relevant konfiguriert werden. Skype für Business Server 2015 ist nicht konfiguriert oder falsch konfiguriert ist, ist die Load Simulation sehr wahrscheinlich ein Fehler auftritt. Mit der Skype für Business Server 2015 Stress and Performance-Tool sind wir Beispiel Skype als Teil der [herunterladen Tools](https://www.microsoft.com/download/details.aspx?id=50367)für Business Server-Verwaltungsshell-Skripts und grundlegende Ressourcendateien bereit. Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype für Business Server-Bereitstellung verwendet werden. In diesem Artikel werden die Windows PowerShell-Beispiele zur Verfügung gestellt.
  
> [!NOTE]
> In diesem Thema kann damit nicht im Allgemeinen Skype für Business Server 2015 konfigurieren beschrieben, haben wir für die anderen Themen Planning and Deployment. Ausführliche Informationen zum Arbeiten mit Windows PowerShell in Skype für Business Server 2015 finden Sie unter der Skype für Business Server Management Shell-Dokumentation unter Einführung hier einfügen. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Zum Ausführen von Skype für Business Server Management Shell-Skripts

Wir sind PowerShell-Skriptbeispiele bereit, die Sie zur Vorbereitung Ihrer Load Simulationen verwenden können. Da diese Skripts für Load Simulation vorgesehen sind, finden Sie diese einfach und permissive sein. Die kann nicht für die produktionsumgebung geeignet sein. Belasten es erneut, dass diese Skripts sind Beispiele können, müssen Sie zu prüfen, und in vielen Fällen zu ändern, damit Sie die von ihnen praktische nutzen für Ihre Umgebung relevant. Mindestens würden wir erwarten, dass Sie das Skript Antwort Service Group (RSG) mit Ihrer Topologie berücksichtigen (an die Agents, agentgruppen zugewiesen) ändern müssen. Sie müssen aber nicht ausgeführt, die bei Bedarf nicht.
  
> [!CAUTION]
> Bitte achten Sie in die Überprüfung und Grundlegendes zu in diesen Beispielen. Skripts überschreibt eine vorhandene Einstellung in der Topologie, die beim Ausführen. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Stress and Performance-Tool-Client-Version-Namen

Sie müssen möglicherweise die Clientversionsüberprüfung Richtlinie zu konfigurieren, sollten Sie zuvor die Einstellungen die Standardwerte geändert haben. Wenn Sie dies nicht sicher sind, überprüfen Sie die [Dokumentation Clientversionsüberprüfung](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
Die Stress and Performance-Tool verwendet die folgenden Benutzer-Agent-Versionen werden standardmäßig bei der Kommunikation mit Skype für Business Server 2015:
  
- LSPT/15.0.0.0 (Skype für Business Server 2015 Stress and Performance-Tool)
    
- OCPHONE/.0.522
    
Für die Mobilität (UCWA)-Client in LyncPerfTool:
  
- UCWA Perf Tool/Webkonferenz
    
- UCWA Perf Tool/Mobile
    

