---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Das Skype for Business Server 2015 Stress and Performance Tool wird während der Kapazitätsplanung und Leistungsoptimierung in Nichtproduktions- oder Testumgebungen verwendet.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814925"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Das Skype for Business Server 2015 Stress and Performance Tool wird während der Kapazitätsplanung und Leistungsoptimierung in Nichtproduktions- oder Testumgebungen verwendet.
  
Das Skype for Business Server 2015 Stress and Performance Tool umfasst Tools, die Ihre Kapazitätsplanung für Skype for Business Server 2015 vereinfachen. Das Skype for Business Server 2015 Stress and Performance Tool hilft Ihnen bei den:
  
- Vereinfachen der Hardwareplanung für Skype for Business Server
    
- Mehr Wissen und bewährte Methoden für die Leistungsoptimierung
    
- Messen der Leistung Ihrer Skype for Business Server-Bereitstellungen
    
Normalerweise verwenden Sie dieses Tool, nachdem Sie das [Skype for Business Server 2015-Planungstool](../../management-tools/planning-tool/planning-tool.md) zum Entwerfen der Topologie und Optimieren der Topologie mit dem Kapazitätsplanungsrechner für Skype for Business Server [2015](../../management-tools/capacity-planning-calculator.md)verwendet haben. 

> [!NOTE]
> Dieses Tool wird für Skype for Business Server 2019 nicht aktualisiert.
  
## <a name="tests"></a>Tests

Das Stress and Performance Tool kann diese Arten von Benutzerauslastung simulieren:
  
|||
|:-----|:-----|
|Chat und Anwesenheit  <br/> |Audiokonferenz  <br/> |
|Anwendungsfreigabe  <br/> |VoIP (Voice over IP), einschließlich PtSN(Public Switched Telephone Network)-Simulation  <br/> |
|Webzugriffsclientkonferenzen  <br/> |Automatische Konferenz attendant  <br/> |
|Reaktionsgruppen  <br/> |Verteilerlistenerweiterung  <br/> |
|Adressbuchdownload und Adressbuchabfrage  <br/> |Erweiterte 911-Anrufe (E911) und Standortprofil (Wählplan)  <br/> |
|MultiView  <br/> |Datenzusammenarbeit  <br/> |
|Mobilität  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Im Skype for Business Server 2015 Stress and Performance Tool enthaltene Anwendungen und Dateien

Diese Anwendungen sind Teil des Skype for Business Server Stress and Performance Tool:
  
|**Tool**|**Beschreibung**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Dieses Tool wird zum Erstellen von Benutzern und Kontakten verwendet.  <br/> |
|UserProfileGenerator.exe  <br/> |Wird verwendet, um die Merkmale der Benutzerlast zu konfigurieren, die Sie simulieren.  <br/> |
|LyncPerfTool.exe  <br/> |Das Tool, das die Benutzerlast simuliert.  <br/> |
|Default.tmx  <br/> |Erforderlich für die Verwendung des Skype for Business Server 2015-Protokollierungstools.  <br/> |
|Beispiele für Bereitstellungsskripts  <br/> |Wird verwendet, um die Topologie für die Ausführung von Auslastungstests basierend auf bestimmten Szenarien zu konfigurieren. Wahrscheinlich müssen Sie sie ändern, um sie für Ihre jeweilige Umgebung relevant zu machen.  <br/> |
   
## <a name="topics-in-this-section"></a>Themen in diesem Abschnitt

Wenn Sie mehr wissen müssen, sollten Sie die folgenden Artikel lesen:
  
- [Voraussetzungen und Einrichtung für das Skype for Busines Stress and Performance Tool](prerequisites-and-setup.md)
    
- [Leistungsszenarien für das Skype for Business Server 2015 Stress and Performance Tool](scenarios.md)
    
  - [Bereitstellen der Topologie zum Ausführen von Last in Stress- und Leistungsszenarien](provisioning-the-topology-to-run-load.md)
    
  - [Konfigurieren von Richtlinien für das Skype for Business Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [Verwenden des Skype for Business Server 2015 Stress and Performance Tool](using-the-tool.md)
    
- [Häufig gestellte Fragen zum Skype for Business Server 2015 Stress and Performance Tool](faq.md)
    

