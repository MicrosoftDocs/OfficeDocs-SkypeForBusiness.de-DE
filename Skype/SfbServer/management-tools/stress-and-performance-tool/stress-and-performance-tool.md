---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Das Stress-und Leistungs Tool für Skype for Business Server 2015 wird während der Kapazitätsplanung und der Leistungsoptimierung in nicht Produktions-oder Testumgebungen verwendet.
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299516"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Das Stress-und Leistungs Tool für Skype for Business Server 2015 wird während der Kapazitätsplanung und der Leistungsoptimierung in nicht Produktions-oder Testumgebungen verwendet.
  
Das Stress-und Leistungs Tool von Skype for Business Server 2015 umfasst Tools, mit denen Sie Ihre Kapazitätsplanung für Skype for Business Server 2015 vereinfachen können. Das Stress-und Leistungs Tool von Skype for Business Server 2015 wird Ihnen dabei helfen, Folgendes zu tun:
  
- Vereinfachung ihrer Hardwareplanung für Skype for Business Server
    
- Erweitertes Wissen und bewährte Methoden für die Leistungsoptimierung
    
- Messen der Leistung Ihrer Skype for Business Server-Bereitstellungen
    
In der Regel verwenden Sie dieses Tool, nachdem Sie das [Planungstool für Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) verwendet haben, um die Topologie zu entwerfen und die Topologie mit dem [Skype for Business Server 2015-Kapazitäts planungsrechner](../../management-tools/capacity-planning-calculator.md)zu verfeinern. 

> [!NOTE]
> Dieses Tool wird für Skype for Business Server 2019 nicht aktualisiert.
  
## <a name="tests"></a>Tests

Das Tool "Spannung und Leistung" kann diese Art von Benutzerauslastung simulieren:
  
|||
|:-----|:-----|
|Instant Messaging (im) und Anwesenheitsinformationen  <br/> |Audiokonferenzen  <br/> |
|Anwendungsfreigabe  <br/> |VoIP (Voice over IP), einschließlich PTSN-Simulation (Public Switched Telephone Network)  <br/> |
|Web Access-Client Konferenzen  <br/> |Automatische Konferenzzentrale  <br/> |
|Reaktionsgruppen  <br/> |Erweiterung der Verteilerliste  <br/> |
|Adressbuch Download und Adressbuch Abfrage  <br/> |Erweiterte 911 (E911)-Anrufe und Standortprofil (Wählplan)  <br/> |
|MultiView  <br/> |Datenzusammenarbeit  <br/> |
|Mobilität  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Im Lieferumfang des Skype for Business Server 2015-Tools für Stress und Leistung enthaltene Anwendungen und Dateien

Diese Anwendungen sind Teil des Skype for Business Server Stress and Performance-Tools:
  
|**Tool**|**Beschreibung**|
|:-----|:-----|
|UserProvisioningTool. exe  <br/> |Dieses Tool dient zum Erstellen von Benutzern und Kontakten.  <br/> |
|UserProfileGenerator. exe  <br/> |Wird verwendet, um die Eigenschaften der Benutzerauslastung zu konfigurieren, die Sie simulieren.  <br/> |
|LyncPerfTool. exe  <br/> |Das Tool, das die Benutzerauslastung simuliert.  <br/> |
|Standard. TMX  <br/> |Erforderlich, um das Skype for Business Server 2015-Protokollierungs Tool zu verwenden.  <br/> |
|Beispiele für Bereitstellungsskripts  <br/> |Wird verwendet, um die Topologie für die Ausführung von Auslastungstests basierend auf bestimmten Szenarien zu konfigurieren. Sie müssen diese Änderungen wahrscheinlich ändern, damit Sie für ihre jeweilige Umgebung relevant sind.  <br/> |
   
## <a name="topics-in-this-section"></a>Themen in diesem Abschnitt

Wenn Sie weitere Informationen benötigen, sollten Sie die folgenden Artikel lesen:
  
- [Voraussetzungen und Setup für Skype for Business Stress and Performance Tool](prerequisites-and-setup.md)
    
- [Leistungs Szenarien für das Stress-und Leistungs Tool von Skype for Business Server 2015](scenarios.md)
    
  - [Bereitstellen der Topologie zum Ausführen der Auslastung in Stress-und Leistungs Szenarien](provisioning-the-topology-to-run-load.md)
    
  - [Konfigurieren von Richtlinien für das Stress-und Leistungs Tool von Skype for Business Server 2015](configuring-policies.md)
    
- [Verwenden des Skype for Business Server 2015 Stress-und Leistungstools](using-the-tool.md)
    
- [Häufig gestellte Fragen zum Skype for Business Server 2015 Stress-und Leistungs Tool](faq.md)
    

