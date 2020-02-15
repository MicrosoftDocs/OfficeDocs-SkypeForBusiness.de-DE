---
title: Planen des Anruf Qualitäts Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Zusammenfassung: Hier erfahren Sie, was Sie bei der Planung des Anruf Qualitäts Dashboards berücksichtigen sollten.'
ms.openlocfilehash: 25342998332a596abce9ecd02e63e153be6e6d94
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029416"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planen des Anruf Qualitäts Dashboards für Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie, was Sie bei der Planung des Anruf Qualitäts Dashboards berücksichtigen sollten.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Übersicht über das Skype for Business Server Dashboard für die Anrufqualität

Das Skype for Business Server-Anruf Qualitäts Dashboard (CQD) ist eine Berichtsebene über der Quality of Experience-Datenbank im Monitoring Server in Skype for Business Server. CQD verwendet Microsoft SQL Server Analysis Services zum Bereitstellen von aggregierten Nutzungs-und Anruf Qualitätsinformationen sowie zum Filtern und pivotieren des Datasets. Zu den CQD-Features gehören:
  
- **Archivierungsspeicher für QoE-Daten über die QoE-Archiv Komponente von CQD.** Die QoE-Archiv Komponente kann QoE-Daten für eine wesentlich längere Zeit als die Monitoring Server speichern können. Dies ermöglicht eine Trend-und Berichterstellung für bis zu sieben Monate Daten, wobei das Berichtsfenster so weit zurückgeschoben werden kann, wie Daten vorhanden sind.
- **Berichterstellung und Analyse mithilfe der Leistung und Geschwindigkeit von Microsoft SQL Server Analysis Services.** CQD verwendet Microsoft SQL Analysis Services, um schnelle Zusammenfassungs-, Filter-und pivotfunktionen bereitzustellen, um das Dashboard über einen Analyse Cube anzutreiben. Das Melden der Ausführungsgeschwindigkeit und der Möglichkeit, einen Drilldown in die Daten durchführen zu können, kann die Analysezeit drastisch reduzieren.
- **Neues Datenschema für die Berichterstellung zur Anrufqualität optimiert.** Der Cube verfügt über ein Schema, das für die sprach Qualitätsberichterstattung und-Untersuchungen entwickelt wurde. Portal Benutzer können sich auf die Berichtsaufgaben konzentrieren, anstatt herauszufinden, wie das Datenbankschema für QoE-Metriken den Ansichten zugeordnet wird, die Sie benötigen. Die Kombination aus QoE-Archiv und Cube stellt eine Abstraktion dar, die die Komplexität von Berichterstellung und Analyse über CQD reduziert. Das QoE-Archivdaten Bank Schema enthält auch Tabellen, die mit bereitstellungsspezifischen Daten aufgefüllt werden können, um den Gesamtwert der Daten zu verbessern.
- **Integrierter Berichts-Designer und Bearbeitung von in-Place-Berichten.** Die Portal Komponente enthält mehrere integrierte Berichte, die nach der Methode für die Anrufqualität modelliert wurden. Portalbenutzer können die Berichte ändern und über die Bearbeitungsfunktion des Portals neue Berichte erstellen.
- **WebAPI-Zugriff auf die Berichtsstruktur und Analyse Cubedaten.** Das Dashboard-Berichtsframework stellt nicht die einzige Möglichkeit dar, um die Daten aus dem Cube anzuzeigen. CQD bietet mehrere Beispiele für die Verwendung von HTML und JavaScript zum Abrufen von Daten aus den CQD-webapis und zum Rendern der Daten in einem benutzerdefinierten Format. Die Kombination aus dem Berichts-Editor und den CQD-webapis ermöglicht ein schnelles Prototyping von Berichten und benutzerdefiniertem Berichtslayout.

> [!NOTE]
> Ein Administrator kann nun Skype for Business Server 2019 mit [CQD Version 3](https://cqd.teams.microsoft.com) verwalten (Anmelden mit Administratoranmeldeinformationen). Dies erfordert eine Hybrid Implementierung und die Verwendung von Call Data Connector (CDC). Weitere Informationen zum Aktivieren von CDC finden Sie unter [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) . Informationen zur Dokumentation zur Version 3 von CQD finden Sie unter [aktivieren und Verwenden des Anruf Qualitäts Dashboards für Microsoft Teams und Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) Weitere Informationen zu CQD Version 3.

## <a name="cqd-design-goals"></a>CQD-Entwurfsziele

CQD ermöglicht es IT-Experten, aggregierte Daten zu verwenden, um Schwerpunkte in Ihrer Umgebung zu identifizieren, bei denen Medienqualität Probleme auftreten. Es ermöglicht einem IT-Experten, Statistiken für verschiedene Benutzergruppen zu vergleichen und Trends und Muster zu identifizieren. Sie konzentriert sich nicht auf die Lösung einzelner Anruf Probleme, sondern auf die Ermittlung von Problemen und Lösungen, die für viele Benutzer in einer bestimmten Umgebung gelten. 
  
## <a name="call-quality-dashboard-components"></a>Dashboard-Komponenten für Anrufqualität

Das Anruf Qualitäts Dashboard besteht aus mehreren Datenbanken, Microsoft SQL-Agent-Aufträgen,-Prozessen und-Webanwendungen. Die Microsoft SQL Agent-Aufträge kopieren regelmäßig Daten aus der QoE-metrikdatenbank in die QoE-Archivdatenbank und verarbeiten den Cube mit den Daten in der QoE-Archivdatenbank. In der Repositorydatenbank werden die Berichtsdefinitionen gespeichert, mit denen das Portal versorgt wird. Das Portal bietet Browser Zugriff auf die Cubedaten. 
  
Die CQD-Komponenten, einschließlich QoE-Archiv, Cube und Repository-Datenbanken, können auf dem Monitoring Server installiert, auf einem eigenen Server installiert oder auf mehreren Servern installiert werden. Die jeweilige Installationsmethode hängt von den Leistungsanforderungen von CQD ab und wirkt sich auch auf andere Prozesse auf denselben Servern aus. Weitere Informationen finden Sie im Abschnitt "Komponenten und Topologien für CQD" weiter unten in diesem Artikel.
  
### <a name="architectural-overview"></a>Übersicht über die Architektur

Zusammenfassend erfordert CQD die folgenden Elemente:
  
- Zwei Datenbanken: eine Archivdatenbank und eine Repository-Datenbank.
    
- Ein SSAS-Cube, der aggregierte Daten visualisiert 
    
- IIS hostet CQD-Webportal
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Die gleiche CQD-Architektur unterstützt lync Server 2013 und Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD und Skype for Business vs. lync 2013

 Nur in einer Skype for Business Umgebung stehen die folgenden Funktionen zur Verfügung:
  
- Wi-Fi-Berichterstellung der Signal Stärke
    
- Wi-Fi-Berichterstellung für Chipsatz-Treiber
    
- Meine Anrufdaten bewerten 
    
## <a name="information-available-through-cqd"></a>Informationen, die über CQD verfügbar sind

CQD kann Skype for Business Server Audio-, Video-und Anwendungsfreigabe Datenstrom Zählungen und die Anzahl von guten und schlechten anrufen sowie Verhältnisse von schlechten bis guten anrufen anzeigen. Die Ansichten können in verschiedenen Dimensionen geschnitten und gefiltert werden. CQD zeichnet Daten aus der Datenbank für QoE-Metriken in der Monitoring Server. Die Daten werden dann mit allen vom Kunden bereitgestellten Daten zusammengeführt, wie beispielsweise Netzwerk-Subnetze-zu-erstellen-Zuordnung, um Berichte wie "Anrufqualität pro Gebäude" zu ermöglichen. 
  
CQD abstrahiert auch viele der internen QoE-Daten Eigenheiten wie "Aufrufer" und "angerufener", sodass der Benutzer sich auf das Erstellen von Berichtsansichten um "Server" und "Client" konzentrieren kann. Im Anschluss an die Methodik für die Anrufqualität wird CQD optimiert, um die Bedingungen zu ermitteln, die in Taschen mit schlechten anrufen gemeinsam sind – einer der Grundsätze für die Verbesserung der Anrufqualität.
  
## <a name="viewing-data-in-cqd"></a>Anzeigen von Daten in CQD

Die CQD-Daten können über das CQD-Portal angezeigt und über REST-API-Aufrufe aufgerufen werden.
  
### <a name="cqd-portal"></a>CQD-Portal

Das Portal stellt die schnellste Möglichkeit dar, um die Daten im Cube anzuzeigen. Das Portal enthält mehrere integrierte Berichte, die sofort nutzbar sind. Die integrierten Berichte sind in strukturierter Weise verknüpft, um den Benutzer zu sukzessiven kleineren und kleineren Segmenten der Anrufdaten zu führen. Die integrierten Berichte heben auch die unterschiedlichen Möglichkeiten hervor, die die Daten angezeigt werden können, indem Sie eine Kombination aus Diagrammen und Tabellen mit unterschiedlichen Pivots, Filtern und Measures demonstrieren. Jeder Benutzer, der auf das Portal zugreift, kann über seine eigenen Berichte verfügen, die er ändern und freigeben kann. Weitere Informationen zur Verwendung des CQD-Webportals finden Sie unter [use Call Quality Dashboard for Skype for Business Server](use.md).
  
Unterstützte Betriebssysteme für das CQD-Portal: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 und Windows Server 2016 (nur Skype for Business Server 2019 CQD).
  
Unterstützte Browser für CQD-Portal: Internet Explorer 11, Internet Explorer 10 und Internet Explorer 9.
  
### <a name="rest-apis"></a>REST-APIs

Auf die Cubedaten kann auch über REST-API-Aufrufe zugegriffen werden. Die über die Rest-API-Aufrufe abgerufenen Daten können über HTML-Seiten gerendert werden. Benutzer können die Abfragegeschwindigkeit und das allgemeine Schema von CQD nutzen, während Sie weiterhin benutzerdefinierte Berichte erstellen, die für Ihre geschäftlichen Anforderungen geeignet sind. Weitere Informationen zur API und zu Beispielen finden Sie unter [entwickeln des Anruf Qualitäts Dashboards für Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definieren der Anforderungen Ihrer Organisation für CQD

CQD bietet QoE-Datenarchivierung und schnelle und Tiefe Analyse von Daten zur Anrufqualität. Das folgende Handbuch hilft Ihnen bei der Entscheidung, wann und warum Sie CQD bereitstellen möchten.
  
### <a name="when-to-deploy-cqd"></a>Zeitpunkt der Bereitstellung von CQD

 **CQD kann bereitgestellt werden, um eine Baseline-Anruf Qualitätsmessung einzurichten, auch wenn eine Organisation keine Probleme mit der Anrufqualität hat.** Das Einrichten einer grundlegenden Anruf Qualitätsmessung ist wichtig, da jede Organisation über eine andere Mischung aus Wi-Fi im Vergleich zu drahtgebundenen und Remote-als auch Office-Mitarbeitern verfügt. Wenn Probleme mit der Anrufqualität auftreten, können die letzten Anruf Qualitätsmessungen mit vorherigen Zeitintervallen verglichen werden. Die Trending-Funktionen von CQD ermöglichen eine einfache Erkennung von Änderungen der Anrufqualität im Laufe der Zeit.
  
 **CQD kann zur proaktiven Suche von Problembereichen bereitgestellt werden, die sich möglicherweise auf die Anrufqualität auswirken.** Selbst wenn die durchschnittliche Anrufqualität für eine Organisation die von der Organisation festgelegten Ziele erfüllen kann, gibt es möglicherweise Probleme mit der Anrufqualität, die hinter den durchschnittlichen Metriken verborgen liegen. CQD ermöglicht eine Pivot-tabellenartige Aufschlüsselung der Anruf Qualitäts Metriken nach vielen Dimensionen in der QoEMetrics-Datenbank. Das Spotting von Ausreißer in Peergruppen stellt eine schnelle Möglichkeit dar, um Probleme mit der Anrufqualität proaktiv zu ermitteln.
  
 **CQD sollte bereitgestellt werden, wenn in der Organisation Probleme mit der Anrufqualität auftreten, um die für die Problembehandlung erforderliche Zeit zu verringern.** CQD kann vorhandene Untersuchungen zur Anrufqualität vereinfachen, indem schnelle Berichtsleistung und dynamische Drilldownfunktionen angeboten werden. CQD ist für viele Arten von Workflows in Anruf Qualitätsuntersuchungen für die Validierung von Reparaturen an der Umgebung konzipiert.
  
### <a name="why-deploy-cqd"></a>Gründe für die Bereitstellung von CQD

 **CQD sollte bereitgestellt werden, wenn die QoE-Berichterstellung für mehr als 3 Monate Daten erfolgen muss.** Die QoEMetrics-Datenbank-und Monitoring Server-Berichte dienen dazu, eine kleine Gruppe von Daten beizubehalten und zu melden. Die QoE-metrikdatenbank ist für schnelle Einfügungen optimiert, sodass die Berichtsleistung durch große Anzahl von anrufen oder konkurrierende Berichts Zugriffe auf die Datenbank behindert werden kann. Die QoE-Archivdatenbank von CQD stellt eine zweite Kopie der QoE-Metrikdaten mit wesentlich längeren Aufbewahrungsfunktionen bereit. Das Portal ist außerdem für die Anzeige von bis zu 7 Monaten Daten gleichzeitig optimiert und kann bei Bedarf über alle Daten im QoE-Archiv Berichten.
  
 **CQD sollte bereitgestellt werden, wenn benutzerdefinierte QoE-Berichte benötigt werden.** Das Portal verfügt über eine Berichts-Editor-Funktion zum schnellen und einfachen Erstellen und Prototypen von Berichten. Es stellt auch Rest-APIs für den programmatischen Zugriff auf die Cubedaten zur Verfügung, sodass benutzerdefinierte Präsentationen mit HTML/JavaScript oder vielen anderen Frameworks möglich sind. Es ist nicht mehr erforderlich, neue SQL-Abfragen zum Erstellen benutzerdefinierter Datenansichten für die Berichterstellung zu erstellen.
  
 **CQD sollte bereitgestellt werden, wenn die vorhandene QoE-Berichtsfunktionalität nicht die von der Organisation benötigte Geschwindigkeit oder tiefe erfüllt.** CQD enthält zahlreiche integrierte Berichte. Die Berichte sind sofort nützlich und veranschaulichen, wie schrittweise durchbohren in den Daten zusätzliche Einblicke auf jeder Ebene möglich sind. Die Berichtshierarchie hilft auch bei der Verwaltung der zahlreichen Berichte auf logische Weise und fördert die Erstellung von vielen weiteren Berichten, die leicht zugänglich und verständlich sind. CQD bietet nicht nur Geschwindigkeit und Flexibilität, sondern ist auch für die Workflows optimiert, die von der Methode für die Anrufqualität entwickelt wurden.
  
## <a name="components-and-topologies-for-cqd"></a>Komponenten und Topologien für CQD

CQD ist mit mehreren Komponenten ausgestattet und hilft, die Anforderungen jeder Komponente und ihrer Beziehung miteinander zu verstehen, um die einfachste und bestmögliche Bereitstellung des Tools zu erhalten. In der folgenden Tabelle wird die abhängige Komponente für jede CQD-Komponente beschrieben.
  

|**Komponentenname**|**Abhängige Komponente**|
|:-----|:-----|
|QoE-Archiv  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Microsoft-Informationsdienste  <br/> |
|Repository-Dienst (Teil der Portal Installation)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Für QoE-Archive und-Cubes erfordern bestimmte Bereitstellungsoptionen Business Intelligence-oder Enterprise-Editionen von Microsoft SQL Server. Weitere Informationen finden Sie im Abschnitt [Infrastrukturanforderungen für CQD](plan.md#Infrastructure_Req) .
  
![CQD-Komponenten](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Konfiguration mit einem einzelnen Server

Alle CQD-Komponenten und abhängigen Komponenten können auf einem Computer installiert werden. Die Konfiguration mit einem einzelnen Knoten ist die einfachste Konfiguration und ermöglicht es, dass CQD eigenständig ist. CQD benötigt lediglich Zugriff auf die QoE-metrikdatenbank auf dem Monitoring Server. Der CQD-Server kann ein eigenständiger Computer, ein virtueller Computer oder sogar der Monitoring Server sein, abhängig von den verfügbaren Ressourcen des Hostcomputers und den Leistungsanforderungen. 
  
Während der Installation muss der Benutzer, der die Installation durchführt, einfach die Microsoft SQL Server-und Microsoft SQL Server Analysis Services-Instanzen bereitstellen, die zuvor auf dem Computer eingerichtet wurden, auf dem das CQD installiert werden soll. Weitere Informationen finden Sie unter [Bereitstellen des Anruf Qualitäts Dashboards für Skype for Business Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>MultiServer-Konfiguration

In einer MultiServer-Konfiguration können sich das QoE-Archiv, der Cube und das Portal auf unterschiedlichen Computern befinden. Für die MultiServer-Konfiguration gibt es zwei hauptsächliche Verwendungsmöglichkeiten:
  
- Hosten des CQD-Webportals und CQD-Cubes auf unterschiedlichen Servern.
    
- Hosten eines "Entwicklungs Portals", das vom Portal "Produktion" getrennt ist. 
    
  **Hosten des CQD-Webportals und CQD-Cubes auf unterschiedlichen Computern.** Organisationen, die möglicherweise Anforderungen zum Trennen des CQD-Portals von der SQL Server-Installation haben oder die SQL Server Editionen für die SQL Server Instanz und SQL Server Analysis Services-Instanz kombinieren und abgleichen möchten, können das CQD-Portal installieren und CQD-Cube auf unterschiedlichen Computern. Die QoE-Archiv Komponente kann auch die einzige CQD-Komponente sein, die installiert wird, wenn die Organisation einfach eine nachhaltige Methode zum Archivieren der QoE-Daten haben möchte, ohne Leistungsgrenzwerte für die Monitoring Server zu erreichen.
  
![CQD mit einem einzelnen Server](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosten eines "Entwicklungs Portals", das vom Portal "Produktion" getrennt ist.** Organisationen, die ihre eigenen benutzerdefinierten Berichte (über die Rest-APIs) entwickeln, bevorzugen möglicherweise die Bereitstellung zusätzlicher (CQD) Portal Instanzen neben dem Produktionsportal, das reguläre Benutzer für die Überwachung oder Untersuchungen der Anrufqualität nutzen. Das Entwicklungsportal kann alle Änderungen am Portal von der Produktionsumgebung isolieren. Die zusätzlichen Webportale können auf unterschiedlichen Computern (unten abgebildet) bereitgestellt oder in unterschiedlichen Webverzeichnissen auf demselben Computer bereitgestellt werden (nicht dargestellt). Um dies zu erreichen, muss das zusätzliche CQD-Webportal manuell auf den Produktionscomputer kopiert werden, da der CQD-Setupprozess immer das CQD-Webportal auf der Standardwebsite mit vordefinierten Webanwendungsnamen bereitstellt.
  
![Planen von CQD-Multi-Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Unterstützte Topologien

CQD führt keine Daten aus mehreren QoEMetrics-Datenbanken zusammen, wie dies bei mehreren Skype for Business Server-Topologien mit jeweils eigenem Monitoring Server der Fall ist. Jede CQD-Instanz muss auf eine QoEMetrics-Datenbank deuten. Da CQD jedoch einen Großteil der Berichts Arbeitslast von der Monitoring Server abzieht, sollten große Organisationen, die für die Bereitstellung einer Monitoring Server pro Skype for Business Server-Topologie eine Monitoring Server für alle Topologien verwenden sollten, eine verwenden.
  
## <a name="infrastructure-requirements-for-cqd"></a>Infrastrukturanforderungen für CQD
<a name="Infrastructure_Req"> </a>

CQD, einschließlich aller Komponenten und abhängigen Komponenten, können auf einem virtuellen Computer, auf einem einzelnen Computer oder auf mehreren Computern bereitgestellt werden. Im folgenden sind die minimalen Software-und Hardwareanforderungen aufgeführt. Die Datenverfügbarkeit und Abfrageleistung kann je nach Anzahl der aktiven Skype for Business Server Benutzer und der Hardware und Konfiguration von Minuten auf Stunden variieren, sodass nachfolgend einige Leistungsmessungen aufgeführt werden.
  
|||
|:-----|:-----|
|Für CQD 2015 <br/> |  <br/> |
|Unterstützte Betriebssysteme   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|Unterstützt SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Für CQD 2019 <br/> |  <br/> |
|Unterstützte Betriebssysteme   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|Unterstützt SQL Server  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD verwendet Microsoft SQL Server, Microsoft SQL Server Analysis Services und Microsoft Internet Information Services, sodass die minimalen Hardware-und Softwareanforderungen von CQD im Wesentlichen denen der abhängigen Komponenten entsprechen. Basierend auf den Anforderungen der Organisation bezüglich der Datenaktualität (die zum Teil vom Umfang der von der Organisation generierten QoE-Daten abhängt) und den Bereitstellungskosten sollten jedoch zusätzliche Überlegungen zur Bereitstellung getroffen werden.
  
Die Datenverarbeitung in CQD ist in zwei Hauptphasen aufgeteilt: 
  
- QoE-Archivierungsprozess
    
- CQD-Cube-Verarbeitung
    
  **QoE-Archivverarbeitung.** Der QoE-Archivierungs Verarbeitungstask kopiert Daten aus der QoE-metrikdatenbank im Monitoring Server in die QoE-Archivdatenbank. Es gibt zwei Situationen, in denen die Verarbeitungszeit der Aufgabe grundlegend unterschiedliche Leistungsmerkmale aufweisen würde. Die erste ist nach der erstmaligen Installation von CQD. Wenn der Task zum ersten Mal nach einer Neuinstallation ausgeführt wird, kopiert der QoE-Archivierungs Verarbeitungstask alle Daten, die sich in der QoE-metrikdatenbank befinden, in die QoE-Archivdatenbank. Der zweite ist die periodische Verarbeitung nach dieser ersten Runde. Der Vorgang der QoE-Archivierungs Verarbeitung wird alle 15 Minuten ausgeführt und verarbeitet alle neuen QoE-Datensätze in der QoE-metrikdatenbank. Im Allgemeinen ist die anfängliche Verarbeitungszeit kein Problem, da Sie nur zum ersten Mal ausgeführt wird, wenn CQD installiert wird. Wenn der CQD-Server jedoch stark unterdimensioniert ist, kann diese Aufgabe mehrere Stunden dauern. In der folgenden Tabelle finden Sie Beispiele für anfängliche QoE-Archivierungs Verarbeitungszeiten.
  
  **CQD-Cube-Verarbeitung.** Der Task Cube-Verarbeitung aggregiert die Daten aus der QoE-Archivdatenbank in den Cube. Die anfängliche Cube-Verarbeitungszeit und die anschließende Zeit der Cube-Verarbeitung werden durch die SQL Server Analysis Services-Edition bestimmt, die für den CQD-Cube verwendet wird. Wenn die Standard Edition verwendet wird, gibt es keinen Unterschied zwischen der anfänglichen Cube-Verarbeitungszeit und der nachfolgenden Cube-Verarbeitungszeit, da jedes Mal, wenn die Cubedaten aktualisiert werden, immer eine vollständige Verarbeitung aller verfügbaren Daten erfolgt. (Dies bedeutet, dass die Verarbeitungszeit des Cubes steigt, wenn sich die Datenmenge in der QoE-Archivdatenbank erhöht.) Da die Business Intelligence Edition und die Enterprise Edition von SQL Server eine Partitions Unterstützung haben, werden nur bei der ersten Ausführung alle Daten in der QoE-Archivdatenbank verarbeitet, wenn eine der beiden Editionen verwendet wird. Bei nachfolgenden Ausführungen wird die Aufgabe, wenn die Aufgabe alle 15 Minuten ausgelöst wird, nur die neuen Datensätze verarbeiten, die der QoE-Archivdatenbank seit der letzten Ausführung der Aufgabe hinzugefügt wurden. Einmal täglich wird auf der Partition, die die Daten des aktuellen Monats enthält, auch eine vollständige Verarbeitung erfolgen.
  
Die physikalischen Eigenschaften des Computers können sich sowohl auf die Leistung von CQD als auch auf die Software Features auswirken, die in den SQL Server Komponenten verfügbar sind. Die QoE-Archiv Komponente ist im Vergleich zu anderen Komponenten stärker Datenträger intensiv, während die Cube-Komponente mehr CPU-und arbeitsspeicherintensiver ist. All diese Faktoren tragen zur gesamten Datenverarbeitungs Zeit von CQD bei, was sich direkt auf die Aktualität und Verfügbarkeit von Daten auswirkt. Organisationen sollten basierend auf den individuellen Anforderungen der Organisation Entscheidungen über Hardware und Software treffen. 
  
### <a name="tested-hardware-configurations"></a>Getestete Hardware Konfigurationen

In diesem Abschnitt wird davon ausgegangen, dass in der Umgebung eine einzelne QoEMetrics-Datenbank vorhanden ist. 
  
**Computerprofile**

|**Maschine**|**CPU-Kerne**|**Arbeitsspeicher**|**QoE-Archiv und Cube auf demselben Datenträger**|**QoE-Archiv und SQL-Temp-DB auf demselben Datenträger**|
|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |4   <br/> |7 GB  <br/> |Ja  <br/> |Ja  <br/> |
|4 Kern  <br/> |4   <br/> |20 GB  <br/> |Ja  <br/> |Nein  <br/> |
|8 Kern  <br/> |8   <br/> |32 GB   <br/> |Ja  <br/> |Nein  <br/> |
|16 Kern  <br/> |16   <br/> |128 GB  <br/> |Nein  <br/> |Nein  <br/> |
   
**Leistungsergebnisse**

|**Maschine**|**Datenbankgröße für QoE-Metriken**|**SQL-Partitionen**|**Datenträgertyp**|**Anzahl der Datenströme**|**Anfänglicher Archiv Prozess**|**Initial Cube-Prozess**|**Anschließender Archivierungsprozess**|**Nachfolgende Cube-Prozess**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |900 MB  <br/> |Single  <br/> |VHD (Variable Größe)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Single  <br/> |VHD (Variable Größe)  <br/> |5 M  <br/> |4 Std.  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Single  <br/> |VHD (feste Größe)  <br/> |5 M  <br/> |2 Std.  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |30 + GB  <br/> |Single  <br/> |VHD (feste Größe)  <br/> |10 M  <br/> |15 Std.  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 Kern  <br/> |9 GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 Std.  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 Kern  <br/> |9 GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 Std.  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 Kern  <br/> |30 + GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 Std.  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 Kern  <br/> |30 + GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 Std.  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 Kern  <br/> |200 GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |125 M  <br/> |6 + Tage  <br/> |7 h  <br/> |2 m  <br/> |6 Std.  <br/> |
|16 Kern  <br/> |500 GB  <br/> |Mehrere  <br/> |Mehrere Spindeln  <br/> |250 M  <br/> |8 Tage  <br/> |2 Std.  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Diese werden in realen Bereitstellungen nicht erwartet, da die QoE-metrikdatenbank jeweils 9 und 18 Monate Daten haben muss, aber Sie werden hier auf Vollständigkeit festgelegt.
  
### <a name="service-account-requirements"></a>Dienstkontoanforderungen

Sie benötigen ein Konto (mit Lesezugriff auf QoEMetrics), das der SQL-Agent auf dem CQD-Server zum Importieren von Daten in das QoEArchiveDB verwenden kann.
  
Möglicherweise müssen Sie auch ein separates Konto für einen SSAS-Auftrag konfigurieren, um Daten aus QoEArchiveDB abzurufen (Dies ist ein optionaler Prozess).
  
IIS verwendet am häufigsten Netzwerkdienst als App-Pool-Identität, kann aber für ein Dienstkonto konfiguriert werden.
  
### <a name="portal-access-control"></a>Portal Zugriffssteuerung

Standardmäßig hat jeder authentifizierte Benutzer Zugriff. Dies kann geändert werden, indem Sie mithilfe von IIS-Autorisierungsregeln auf eine bestimmte Gruppe beschränken.
  
### <a name="pre-install-requirements"></a>Voraussetzungen für die Installation

Bei diesen Anweisungen wird davon ausgegangen, dass eine QoE-metrikdatenbank bereits installiert wurde und irgendwo in der Skype for Business Server-Topologie ausgeführt wird.
  
#### <a name="hardware-requirements"></a>Hardwareanforderungen

CQD verwendet Microsoft SQL Server, Microsoft SQL Analysis Server und Microsoft Internet Information Server, sodass die minimalen Hardware-und Softwareanforderungen von CQD im Wesentlichen denen der abhängigen Komponenten entsprechen. Basierend auf den Anforderungen der Organisation bezüglich der Datenaktualität (die zum Teil vom Umfang der von der Organisation generierten QoE-Daten abhängt) und den Bereitstellungskosten sollten jedoch zusätzliche Überlegungen zur Bereitstellung getroffen werden.
  
#### <a name="software-requirements"></a>Softwareanforderungen

Für CQD sind die folgenden Betriebssysteme erforderlich:
  
- Windows Server 2008 R2 mit IIS 7,5
    
- Windows Server 2012 mit IIS 8,0
    
- Windows Server 2012 R2 mit IIS 8,5

- Windows Server 2016 mit IIS 10,0 (nur Skype for Business Server 2019 CQD)

- Windows Server 2019 (nur Skype for Business Server 2019 CQD)
    
Im folgenden sind die erforderlichen IIS-Rollendienste (in hierarchischer Reihenfolge) aufgeführt:
  
- Webserver
    
  - Allgemeine HTTP-Features
    
  - Statischer Inhalt
    
  - Standarddokument
    
  - Anwendungsentwicklung
    
  - ASP.NET
    
  - ISAPI-Filter
    
  - Integritäts &amp; Diagnose
    
  - HTTP-Protokollierung
    
  - Sicherheit
    
  - URL-Autorisierung
    
  - Windows-Authentifizierung
    
  - Verwaltungstools
    
  - IIS-Verwaltungskonsole
    
> [!NOTE]
>  Beachten Sie Folgendes für die oben genannten Anforderungen: > 3,5-und 4,5-Versionen von .NET Framework stehen zur Verfügung. Beide sind erforderlich (genauer gesagt ist 3,5 SP1 erforderlich). > in einigen Systemen, wenn ASP.net vor dem Installieren von IIS eingerichtet wurde, ist ASP.net möglicherweise nicht in IIS registriert. Das Problem manifestiert sich dadurch, dass keine Anwendungspools für die entsprechende .NET-Version vorhanden sind und auch die .NET CLR-Version in der APP-Poolkonfiguration fehlt. Um ein solches Problem bei Windows Server 2008 R2 zu beheben `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`, führen Sie aus. Auf Windows Server 2012 und Windows Server 2012 R2 wird Execute `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` gefolgt von dem Entfernen des ServiceModel-Moduls von der Standardwebsite in IIS-Manager ausgeführt. >-Verwaltungstools sind optional, werden jedoch empfohlen.
  
Führen Sie die folgenden Schritte aus, um diese Anforderungen mithilfe von PowerShell zu installieren:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Die folgenden Versionen von SQL Server werden unterstützt:
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 (nur Skype for Business Server 2019 CQD)
    
Business Intelligence oder Enterprise Edition wird aus Leistungsgründen empfohlen. Diese Editionen ermöglichen die Verwendung mehrerer Partitionsdateien, die parallel verarbeitet werden können, was für die Verarbeitung von Daten, die mehrere Monate oder länger dauern, vorteilhaft ist. 
  
Obwohl dies nicht empfohlen wird, wird die Standard Edition ebenfalls unterstützt. Die Verarbeitung wird auf eine einzelne Partition eingeschränkt (die während des Setups konfiguriert werden muss). 
  
In allen Fällen müssen "Datenbankmodul-Dienste" und "Analysis Services" installiert sein. Es wird empfohlen, aber nicht erforderlich, um auch die Funktion "Verwaltungs Tools-abgeschlossen" zu installieren, die die SQL Server Management Studio-Unterstützung für Analysis Services hinzufügt. Der Funktionsauswahl Bildschirm sollte wie die Abbildung aussehen.
  
![SQL Server Featureanforderungen](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Wenn Sie das SSAS-Setup konfigurieren, legen Sie in der Analysis Services-Konfiguration "Server Modus" auf "multidimensionaler und Data Mining Mode" fest. 
  
Weitere Informationen zum Installieren und Konfigurieren von SQL Server Business Intelligence-Features finden Sie unter [Installieren von Analysis Services im multidimensionalen und Data Mining-Modus](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Kontoanforderungen

Drei Domänendienstkonten werden nach dem Prinzip der geringsten Rechte empfohlen: 
  
- Eine, die bereits über einen Anmelde Sicherheitsprinzipal für QoE-metrikdatenbank (mit db_datareader Berechtigung) und einen Anmelde Sicherheitsprinzipal im QoE-Archiv SQL Server Instanz (erforderlich zum Erstellen eines verknüpften Server Objekts während des Setups) verfügt. Dieses Konto wird verwendet, um den Schritt "QoE-Archivdaten" des SQL Server-Agent-Auftrags auszuführen.
    
- Eine, die zum Ausführen des Schritts "Prozess Cube" des SQL Server-Agent-Auftrags verwendet wird. Setup erstellt einen Anmelde Sicherheitsprinzipal für die QoE-Archivdatenbank (mit Lese-und Schreibrechten) und erstellt außerdem ein Mitglied in der QoE-Rolle (mit Vollzugriff-Berechtigung) für den Cube.
    
- Eine, die zum Ausführen des IIS-Arbeitsprozesses für die Webportale und Webanwendungen verwendet wird. Setup erstellt einen Anmelde Sicherheitsprinzipal für die QoE-Archivdatenbank (mit Leseberechtigung), einen Anmelde Sicherheitsprinzipal für die Repositorydatenbank (mit Lese-und Schreibberechtigung) und ein Mitglied in QoERole (mit Berechtigung "Vollzugriff") für den Cube. 
    
    > [!NOTE]
    > Wenn sowohl QoE-Archivdatenbank als auch Repository-Datenbank in derselben SQL Server gehostet werden, wird nur ein Anmelde Sicherheitsprinzipal mit zwei Benutzerzuordnungen erstellt. 
  
Die ersten beiden Konten können logisch als "Back-End-Dienstkonten" betrachtet werden, und das letzte Konto ist ein "Front-End-Dienstkonto". Obwohl es nicht empfohlen wird, kann in allen Fällen ein einzelnes Konto verwendet werden.
  
> [!NOTE]
> Das Benutzerkonto, das die Installation initiiert, muss ebenfalls über Lesezugriff auf QoE-Metriken verfügen (zusätzlich zu den Administratorrechten auf dem QoE-Archiv-DB-Server, auf dem die Installation erfolgen muss). 
  
## <a name="capacity-planning"></a>Kapazitätsplanung
<a name="Infrastructure_Req"> </a>

CQD wurde für minimale Auswirkungen auf QoEMetrics entwickelt: der Code wurde so optimiert, dass keine Daten gesperrt werden, und Importaufträge sind Abstimm.
  
Der Typ der zu verwendenden Hardware hängt von Ihren Anforderungen ab, wie schnell Synchronisierungen ausgeführt werden sollen. Die Größe des Datenträgers lautet wie folgt:
  
- QoEArchive ist ~ 1,5 x größer als QoEMetrics DB anfänglich
    
- Der SSIS-Cube komprimiert die Daten im Vergleich zu DB fast 10X.
    
- Die Daten werden monatlich partitioniert. Partitionen können gelöscht werden
    

