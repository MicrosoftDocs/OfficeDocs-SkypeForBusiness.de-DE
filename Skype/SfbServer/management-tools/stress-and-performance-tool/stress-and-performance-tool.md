---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Das Skype for Business Server 2015 Stress and Performance Tool wird bei der Kapazitätsplanung und Leistungsoptimierung in Nicht-Produktions- oder Testumgebungen verwendet.
---

# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Das Skype for Business Server 2015 Stress and Performance Tool wird bei der Kapazitätsplanung und Leistungsoptimierung in Nicht-Produktions- oder Testumgebungen verwendet.
  
Das Skype for Business Server 2015 Stress and Performance Tool enthält Tools, die Ihre Kapazitätsplanung für Skype for Business Server 2015 vereinfachen. Das Skype for Business Server 2015 Stress and Performance Tool hilft Ihnen dabei:
  
- Vereinfachen der Hardwareplanung für Skype for Business Server
    
- Bereitstellen von mehr Wissen und bewährten Methoden für die Leistungsoptimierung
    
- Messen der Leistung Ihrer Skype for Business Server-Bereitstellungen
    
Normalerweise verwenden Sie dieses Tool, nachdem Sie das [Skype for Business Server 2015-Planungstool](../../management-tools/planning-tool/planning-tool.md) zum Entwerfen der Topologie und zum Optimieren der Topologie mit dem [Skype for Business Server 2015 Capacity Planning Calculator verwendet haben](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Dieses Tool wird für Skype for Business Server 2019 nicht aktualisiert.
  
## <a name="tests"></a>Tests

Das Stress and Performance Tool kann diese Arten von Benutzerlast simulieren:
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Chat und Anwesenheit   |Audiokonferenz   |
|Anwendungsfreigabe   |Voice over IP (VoIP), einschließlich PtSN-Simulation (Public Switched Telephone Network)   |
|Web Access-Clientkonferenzen   |Automatische Telefonzentrale für Konferenzen   |
|Reaktionsgruppen   |Erweiterung der Verteilerliste   |
|Adressbuchdownload und Adressbuchabfrage   |Erweiterte 911(E911)-Anrufe und Standortprofil (Wählplan)   |
|Multiview   |Datenzusammenarbeit   |
|Mobilität   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Anwendungen und Dateien im Skype for Business Server 2015 Stress and Performance Tool

Diese Anwendungen sind Teil des Tools Skype for Business Server Stress and Performance:
  
|Tool|Beschreibung|
|:-----|:-----|
|UserProvisioningTool.exe   |Dieses Tool wird zum Erstellen von Benutzern und Kontakten verwendet.   |
|UserProfileGenerator.exe   |Wird verwendet, um die Merkmale der Benutzerlast zu konfigurieren, die Sie simulieren.   |
|LyncPerfTool.exe   |Das Tool, das das Laden des Benutzers simuliert.   |
|Default.tmx   |Erforderlich für die Verwendung des Skype for Business Server 2015-Protokollierungstools.   |
|Beispiele für Bereitstellungsskripts   |Wird verwendet, um die Topologie für die Ausführung von Auslastungstests basierend auf bestimmten Szenarien zu konfigurieren. Sie müssen sie wahrscheinlich ändern, um sie für Ihre bestimmte Umgebung relevant zu machen.   |
   
## <a name="topics-in-this-section"></a>Themen in diesem Abschnitt

Wenn Sie mehr wissen möchten, sollten Sie die folgenden Artikel lesen:
  
- [Voraussetzungen und Einrichtung für die Skype für das Stress- und Leistungstool von Busines](prerequisites-and-setup.md)
    
- [Leistungsszenarien für das Skype for Business Server 2015 Stress and Performance Tool](scenarios.md)
    
  - [Bereitstellen der Topologie zum Ausführen von Last in Stress- und Leistungsszenarien](provisioning-the-topology-to-run-load.md)
    
  - [Konfigurieren von Richtlinien für das Skype for Business Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [Verwenden des Tools Skype for Business Server 2015 Stress and Performance](using-the-tool.md)
    
- [Häufig gestellte Fragen zum Skype for Business Server 2015 Stress and Performance Tool](faq.md)
    

