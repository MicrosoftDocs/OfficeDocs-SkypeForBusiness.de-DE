---
title: Leistungsszenarien für das Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 mit dem Stress and Performance Tool für Leistungs- und Auslastungstests zu konfigurieren.
ms.openlocfilehash: 0a04d94bc0c43b9de2043b9ee601a294b7945a45
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841107"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Leistungsszenarien für das Skype for Business Server 2015 Stress and Performance Tool
 
Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 mit dem Stress and Performance Tool für Leistungs- und Auslastungstests zu konfigurieren.
  
Um das Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) auszuführen, muss die topologie Skype for Business Server 2015 zunächst für szenarien konfiguriert werden, die für Sie relevant sind. Wenn Skype for Business Server 2015 nicht konfiguriert oder falsch konfiguriert ist, tritt bei der Ladesimulation mit großer Wahrscheinlichkeit ein Fehler auf. Mit dem Skype for Business Server 2015 Stress and Performance Tool stellen wir Beispiel Skype for Business Server Management Shell-Skripts und grundlegende Ressourcendateien als Teil des [Tooldownloads bereit.](https://www.microsoft.com/download/details.aspx?id=50367) Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype for Business Server-Bereitstellung verwendet werden. In diesem Artikel werden die Windows PowerShell bereitgestellten Beispiele beschrieben.
  
> [!NOTE]
> In diesem Thema erfahren Sie nicht, wie Sie Skype for Business Server 2015 im Allgemeinen konfigurieren, dafür gibt es weitere Planungs- und Bereitstellungsthemen. Ausführliche Informationen zum Arbeiten mit Windows PowerShell in Skype for Business Server 2015 finden Sie in der Dokumentation zur Skype for Business Server Verwaltungsshell unter "Einführung einfügen" HIER. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informationen zum Ausführen Skype for Business Server-Verwaltungsshell-Skripts

Wir stellen Beispiel-PowerShell-Skripts bereit, mit denen Sie sich auf Ihre Ladesimulationen vorbereiten können. Da diese Skripts für die Lastsimulation vorgesehen sind, werden Sie feststellen, dass sie einfach und eingeschränkt sind. Dies ist möglicherweise nicht für Ihre Produktionsumgebung geeignet. Wir weisen erneut darauf hin, dass es sich bei diesen Skripts um Beispiele handelt. Sie müssen sie überprüfen und in vielen Fällen änderungen vornehmen, die für Ihre Umgebung relevant sind, bevor Sie sie in der Praxis nutzen können. Wir gehen davon aus, dass Sie mindestens das RSG-Skript (Response Service Group) unter Berücksichtigung Ihrer Topologie ändern müssen (um die Agents anzugeben, die den Agentgruppen zugewiesen sind). Sie müssen dies jedoch nicht ausführen, wenn Sie dies nicht tun müssen.
  
> [!CAUTION]
> Bitte achten Sie darauf, diese Beispiele zu überprüfen und zu verstehen. Skripts überschreiben bei der Ausführung alle vorhandenen Einstellungen in der Topologie. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Stress and Performance Tool– Clientversionsnamen

Möglicherweise müssen Sie die Clientversionsprüfungsrichtlinie konfigurieren, wenn Sie die Einstellungen zuvor von den Standardwerten geändert haben. Wenn Sie sich darüber nicht sicher sind, lesen Sie die Dokumentation zur [Clientversionsprüfung.](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)
  
Das Stress and Performance Tool verwendet bei der Kommunikation mit Skype for Business Server 2015 standardmäßig die folgenden Benutzer-Agent-Versionen:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Für den Mobilitätsclient (UCWA) in LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
