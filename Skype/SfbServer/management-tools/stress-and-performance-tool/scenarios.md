---
title: Leistungs Szenarien für das Stress-und Leistungs Tool von Skype for Business Server 2015
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
description: Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, indem Sie das Tool Stress und Leistung verwenden.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803875"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Leistungs Szenarien für das Stress-und Leistungs Tool von Skype for Business Server 2015
 
Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, indem Sie das Tool Stress und Leistung verwenden.
  
Zum Ausführen des Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) muss die Skype for Business Server 2015-Topologie zunächst für für Sie relevante Szenarien konfiguriert werden. Wenn Skype for Business Server 2015 nicht konfiguriert ist oder falsch konfiguriert ist, schlägt die Auslastungssimulation höchstwahrscheinlich fehl. Mit dem Stress-und Leistungstool für Skype for Business Server 2015 stellen wir Beispiele für Skype for Business Server-Verwaltungsshell-Skripts und grundlegende Ressourcendateien als Teil des [Tool Downloads](https://www.microsoft.com/download/details.aspx?id=50367)zur Verfügung. Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype for Business Server-Bereitstellung verwendet werden. In diesem Artikel werden die bereitgestellten Windows PowerShell-Beispiele beschrieben.
  
> [!NOTE]
> In diesem Thema wird Ihnen nicht geholfen, die Konfiguration von Skype for Business Server 2015 im Allgemeinen zu beschreiben. Details zum Arbeiten mit Windows PowerShell in Skype for Business Server 2015 finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell unter Einfügen-Einführung hier. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informationen zum Ausführen von Skripts für die Verwaltung von Skype for Business Server-Verwaltungsshell

Wir stellen Beispiel-PowerShell-Skripts bereit, mit denen Sie Ihre Auslastungssimulationen vorbereiten können. Da diese Skripts für die Auslastungssimulation vorgesehen sind, finden Sie Sie einfach und frei zügig. , Die möglicherweise nicht für Ihre Produktionsumgebung geeignet sind. Wir betonen erneut, dass es sich bei diesen Skripts um Beispiele handelt, Sie müssen Sie überprüfen und in vielen Fällen Änderungen vornehmen, die für Ihre Umgebung relevant sind, bevor Sie Sie praktisch nutzen können. Wir gehen davon aus, dass Sie mindestens das Wiederherstellungsskript der Antwortdienst Gruppe (RSG) mit Ihrer Topologie ändern müssten (um die Agents anzugeben, die den Agentengruppen zugewiesen sind). Sie müssen dies aber nicht ausführen, wenn Sie dies nicht benötigen.
  
> [!CAUTION]
> Achten Sie bitte darauf, diese Beispiele zu überprüfen und zu verstehen. Skripts überschreiben alle vorhandenen Einstellungen in der Topologie, wenn Sie ausgeführt werden. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Versionsnamen für Spannungs-und Leistungs Tool-Client

Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie die Einstellungen zuvor von den Standardwerten geändert haben. Wenn Sie sich nicht sicher sind, sehen Sie in der [Dokumentation zur Client Version](https://msdn.microsoft.com/en-us/vsto/jj923060)nach.
  
Das Tool "Spannung und Leistung" verwendet standardmäßig die folgenden Benutzer-Agent-Versionen, wenn Sie mit Skype for Business Server 2015 kommunizieren:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress-und Leistungs Tool)
    
- OCPHONE/. 0.522
    
Für den Mobilitäts Client (UCWA) in LyncPerfTool:
  
- UCWA-perf-Tool/Webkonferenz
    
- UCWA perf Tool/Mobil
    

