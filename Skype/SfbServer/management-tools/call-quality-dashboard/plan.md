---
title: Planen Sie für die Qualitätsdashboard Anruf Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Zusammenfassung: Erfahren Sie mehr über welche Aspekte bei der Planung für das Anrufqualität Dashboard zu.'
ms.openlocfilehash: 8f26ecd90a9804a68656f76080c3865f5cb7360b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915346"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planen Sie für die Qualitätsdashboard Anruf Skype für Business Server 
 
**Zusammenfassung:** Hier erfahren Sie, was Sie berücksichtigen Sie bei der Planung für das Anrufqualität Dashboard.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Übersicht über die Skype für Business Server Anrufqualität Dashboard

Die Skype für Business Server aufrufen Quality Dashboard (CQD) ist eine reporting Ebene auf der Basis der Qualität Erfahrung Datenbank in dem Monitoring Server in Skype für Business Server. CQD wird Microsoft SQL Server Analysis Services verwendet, um die aggregierte Nutzung bereitstellen, und rufen Sie Informationen zur Medienqualität als auch für filtern und das Dataset beim Pivotieren. CQD Merkmale:
  
- **Archivspeicher der QoE-Daten über die QoE-Archiv-Komponente des CQD.** Die QoE-Archiv-Komponente kann für eine viel Dauer länger als die Monitoring Server kann QoE-Daten gespeichert. Dies ermöglicht Trends und Berichte für bis zu sieben Monate Daten zu einem Zeitpunkt die Möglichkeit, das Fenster reporting back soweit Folie Daten vorhanden sind.
    
- **Berichts- und die Leistungsfähigkeit und Geschwindigkeit von Microsoft SQL Server Analysis Services verwenden.** CQD nutzt Microsoft SQL Analysis Services um schnelle Zusammenfassung, Filter und Funktionen, die das Dashboard über einen Analysis-Cube power Pivot-Funktionen bereitzustellen. Reporting Ausführung Geschwindigkeit und die Möglichkeit, die Daten einen Drilldown kann Analysis Zeiten erheblich reduziert werden.
    
- **Neue Datenschema Berichtszwecken Anrufqualität optimiert.** Der Cube enthält ein Schema für VoIP Qualität reporting und Untersuchungen entwickelt wurde. Portal Benutzer können sich auf die Berichtsaufgaben anstelle von herausfinden, wie die QoE-Metriken database Schema Karten auf die benötigten Ansichten konzentrieren. Die Kombination aus der QoE-Archiv und den Cube enthält eine Abstraktion, die die Komplexität der Berichte und Analysen über CQD reduziert. Das Archiv QoE-Datenbankschema enthält auch Tabellen, die mit der Bereitstellung-spezifische Daten optimiert werden den Gesamtwert der Daten aufgefüllt werden können.
    
- **Integrierten Berichts-Designer und Compliance-Bericht zu bearbeiten.** Die Portal-Komponente verfügt über mehrere integrierte Berichte, die nach der aufrufen Qualität Methodik modelliert. Portal Benutzer können die Berichte ändern und neue Berichte über das Portal Bearbeitungsfunktionalität erstellen.
    
- **Web-API für den Zugriff auf die Struktur des Berichts und Cubedaten Analyse.** Das Dashboard reporting-Framework ist nicht die einzige Möglichkeit zum Anzeigen der Daten aus dem Cube. CQD enthält einige Beispiele für die Verwendung von HTML und JavaScript zum Abrufen von Daten aus der CQD Web-APIs und die Daten in ein benutzerdefiniertes Format zu rendern. Die Kombination aus den Bericht-Editor und die CQD Web-APIs ermöglicht eine schnelle Prototypen von Berichten und benutzerdefinierten Berichtslayout.
    
## <a name="cqd-design-goals"></a>CQD Entwurfsziele

Mit CQD können IT-Profis Daten aggregieren, um die Bereiche in ihrer Umgebung zu ermitteln, in denen die Medienqualität beeinträchtigt ist. CQD ermöglicht den Vergleich von Statistiken für verschiedene Benutzergruppen und die Ermittlung von Trends und Mustern. Dabei liegt der Schwerpunkt nicht auf der Lösung individueller Probleme mit Anrufen, sondern auf der Erkennung von Problemen und Lösungen, die auf viele Benutzer in einer bestimmten Umgebung anwendbar sind. 
  
## <a name="call-quality-dashboard-components"></a>Rufen Sie die Qualitätsdashboard-Komponenten

Das Aufrufen Qualitätsdashboard umfasst mehrere Datenbanken, Microsoft SQL Agent Aufträge, Prozesse und Webanwendungen. Die Microsoft SQL-Agent-Aufträge kopieren Daten regelmäßig aus der QoE-Metriken-Datenbank in der Archivdatenbank QoE und Prozesse den Cube mit den Daten in der QoE-Archivdatenbank. Die Repository-Datenbank speichert den Berichtsdefinitionen, Power das Portal. Das Portal bietet Browserzugriff auf die Daten des Cubes. 
  
Die CQD-Komponenten, einschließlich der QoE-Archiv, Cube und Repository-Datenbanken können auf dem Monitoring Server installiert, auf einem eigenen Server installiert werden, oder auf mehreren Servern installiert. Die spezielle Installation-Methode hängt von der optimierte Leistung des CQD als auch Auswirkungen auf andere Prozesse auf den gleichen Servern. Weitere Informationen finden Sie im Abschnitt "Komponenten und Topologien für CQD" weiter unten in diesem Artikel.
  
### <a name="architectural-overview"></a>Übersicht über die Architektur

Zusammenfassend lässt sich sagen, erfordert CQD die folgenden Elemente:
  
- Zwei Datenbanken: ein Archiv und einer Repository-Datenbank.
    
- Visualisieren von einem SSAS-Cubes aggregierte Daten 
    
- IIS hosten CQD Webportal
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Die gleiche CQD Architektur unterstützt Lync Server 2013 und Skype für Unternehmen. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD und Skype für Unternehmen im Vergleich zu Lync 2013

 In einer Skype für nur geschäftsumgebung stehen die folgenden Funktionen:
  
- Wi-Fi reporting Signalstärke
    
- Wi-Fi reporting Chipsatz-Treiber
    
- Meine Anruf Datenrate 
    
## <a name="information-available-through-cqd"></a>Informationen über CQD verfügbar

CQD kann Skype für Business Server Audio-, Video- und Anwendungsfreigabe Stream Bestell- und die Anzahl der im Vergleich zu fehlerhafte Anrufe gute sowie Verhältnisse auf eine gute fehlerhafte Anrufe angezeigt. Die Ansichten können segmentiert und von vielen verschiedenen Dimensionen gefiltert werden. CQD zeichnet Daten aus der QoE-Metriken-Datenbank in den Monitoring Server. Die Daten werden dann mit Kunden bereitgestellten Daten, wie das Netzwerk Subnetz Gebäuden zuordnen, um Berichte wie etwa "Aufrufen Qualität pro Building" zu ermöglichen zusammengeführt. 
  
CQD abstrahiert viele der internen QoE-Daten Besonderheiten wie "Aufrufer" und "angerufenen" auch, so, dass der Benutzer zum Erstellen von Berichtsansichten "Server" und "Client" konzentrieren kann. Nach der Methodik aufrufen Qualität CQD optimiert, um die Bedingungen zu identifizieren, die der Anrufe schlechter Fächer gemeinsam haben – einer der Grundsätze für die Anrufqualität verbessern.
  
## <a name="viewing-data-in-cqd"></a>Anzeigen von Daten in CQD

Die CQD Daten können über das Portal CQD angezeigt und über REST-API-Aufrufe zugegriffen werden.
  
### <a name="cqd-portal"></a>CQD-Portal

Das Portal ist die schnellste Methode zum Anzeigen der Daten im Cube. Das Portal verfügt über mehrere integrierte Berichte, die dann sofort verwendet werden. Integrierte Berichte sind eine strukturierte Bezeichnungen nacheinander kleiner und kleinere Segmente der Anrufdaten im Benutzerhandbuch verknüpft. Integrierte Berichte markieren auch verschiedene unterschiedlichen Möglichkeiten, die die Daten angezeigt werden können, durch eine Kombination von Diagrammen und Tabellen mit unterschiedlichen Pivot-Elemente, Filter und Maßnahmen zu demonstrieren. Jeder Benutzer, die auf das Portal zugreifen, kann ein eigenes Satz von Berichten verfügen, die er anpassen und freigeben können. Weitere Informationen zur Verwendung von dem Webportal CQD finden Sie unter [Verwendung Dashboard Qualität für Skype für Business Server aufrufen](use.md).
  
Unterstützte Betriebssysteme für CQD Portal: Windows 8.1, Windows 8, Windows Server 2012 R2, WindowsServer 2012 und WindowsServer 2016 (Skype für nur für Business Server 2019 CQD).
  
Unterstützte Browser für CQD Portal: InternetExplorer 11, InternetExplorer 10 und InternetExplorer 9.
  
### <a name="rest-apis"></a>REST-APIs

Die Daten des Cubes können auch über REST-API-Aufrufe zugegriffen werden. Über die REST-API-Aufrufe abgerufenen Daten können über den HTML-Seiten gerendert werden. Benutzer können während weiterhin Erstellen benutzerdefinierter Berichte für ihre geschäftlichen Anforderungen geeignet nutzen die Geschwindigkeit der Abfrage und das Schema auf hoher Ebene CQD übernehmen. Weitere Informationen über die API und Beispiele finden Sie unter [Entwickeln von Anrufqualität Dashboard für Skype für Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definieren der Anforderungen Ihrer Organisation für CQD

CQD enthält QoE-Daten Archivierung und schnelle und Tiefe Analyse der Medienqualität Anruf. Das folgenden Handbuch hilft Ihnen, zu entscheiden, wann und warum würden Sie CQD bereitstellen.
  
### <a name="when-to-deploy-cqd"></a>Bereitstellung von CQD

 **CQD kann bereitgestellt werden, um einen Vergleichswert für Anrufqualität, herstellen, auch wenn eine Organisation Anrufqualität Probleme nicht.** Einrichten einen Vergleichswert für den Anrufqualität ist wichtig, da jede Organisation eine unterschiedliche Kombination von Wi-Fi im Vergleich zu verkabelten und im Vergleich zu Office Mitarbeiter remote hat. Beim Aufruf von Parkplätzen entstehen, können die letzten Aufruf Qualität Maße mit vorherigen Zeitintervallen verglichen werden. Trend Features des CQD ermöglicht es leicht Erkennung von Änderungen in die Anrufqualität über einen Zeitraum.
  
 **CQD kann bereitgestellt werden, um proaktiv Problembereiche zu finden, die die Anrufqualität auswirkt.** Auch wenn der Mittelwert aufgerufen Qualität für eine Organisation möglicherweise die Einhaltung der Zielvorgaben von der Organisation erfüllen, Fächer des Anrufs Parkplätzen, die hinter durchschnittliche Metriken ausgeblendet sind möglicherweise. CQD ermöglicht die Pivot-Tabelle-ähnliche Aufschlüsselung der Metriken zur Anrufqualität durch viele Dimensionen in der Datenbank "qoemetrics". Saisonverkäufen Ausreißern in Peer-Gruppen ist eine schnelle Möglichkeit, Anruf Qualitätsprobleme proaktiv gesucht werden soll.
  
 **CQD sollte bereitgestellt werden, wenn Anruf Qualitätsprobleme in der Organisation zur Reduzierung des Zeitaufwand für die Behandlung von Problemen.** CQD kann vorhandene Anrufqualität Untersuchungen fast reporting Leistung und dynamische Drilldown-Funktionen anbieten vereinfachen. CQD ist für viele Arten von Workflows in Anrufqualität Untersuchungen Überprüfung des Reparaturen für die Umgebung vorgesehen.
  
### <a name="why-deploy-cqd"></a>Gründe für die Bereitstellung CQD

 **CQD sollte bereitgestellt werden, wenn reporting QoE für mehr als 3 Monate Daten auftreten muss.** Die Datenbank "qoemetrics" und den monitoring Server-Berichte dienen zum beibehalten und eine kleine Gruppe von Daten zu melden. Die QoE-Metriken Datenbank ist für die schnelle einfügungen optimiert, und daher reporting Leistung durch große Mengen von Anrufen oder konkurrierenden reporting Zugriff auf die Datenbank behindert werden kann. CQD des QoE-Archivdatenbank bietet eine zweite Kopie der QoE-Metriken Daten mit viel mehr Möglichkeiten zum aufbewahren. Das Portal ist auch zum Anzeigen von bis zu sieben Monate Daten zu einem Zeitpunkt optimiert und kann alle Daten in das Archiv QoE angeben, wie gewünscht.
  
 **CQD sollte bereitgestellt werden, wenn benutzerdefinierte QoE-Berichte erforderlich sind.** Das Portal hat ein Bericht-Editors-Feature für Berichte erstellen und Prototypen schnell und einfach. Außerdem wird verfügbare REST-APIs für den programmgesteuerten Zugriff auf die Cubedaten zielgruppenorientierten Präsentation mithilfe von HTML/JavaScript oder viele andere Frameworks ermöglicht. Es ist nicht mehr notwendig, den neue SQL-Abfragen für die Erstellung von benutzerdefinierten Datenansichten für Berichte erstellen.
  
 **CQD sollte bereitgestellt werden, wenn vorhandene QoE Berichtsfunktionen nicht die Geschwindigkeit oder Tiefe der Organisation erforderlichen erfüllt.** CQD verfügt über viele integrierte Berichte. Die Berichte sofort nützlich sind und wie stetig veranschaulichen Drilldown für Daten können Sie zusätzliche Hinweise auf jeder Ebene bieten. Die Berichthierarchie auch hilft bei der Verwaltung der zahlreiche Berichte logisch und fördert die Erstellung von viele weitere Berichte, die leicht zugänglich und verständlich sind. CQD nicht nur Geschwindigkeit und Flexibilität bieten jedoch auch für die Workflows, die von der Qualität-Methodik aufrufen entwickelt wurde optimiert ist.
  
## <a name="components-and-topologies-for-cqd"></a>Komponenten und Topologien für CQD

CQD verfügt über mehrere Komponenten, und es hilft Ihnen, um zu verstehen, die Anforderungen der einzelnen Komponenten und ihre Beziehung miteinander zum Abrufen der bereitstellungs einfachsten und am besten Ausführen des Tools. Die folgende Tabelle beschreibt die abhängige Komponente für die einzelnen Komponenten CQD.
  

|**Komponentenname**|**Abhängige Komponente**|
|:-----|:-----|
|QoE-Archiv  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Informationen zu Microsoft-Dienste  <br/> |
|Repository Service (Teil von Portal Installation)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> QoE-Archiv und Cube erfordern bestimmte Bereitstellungsoptionen für Business Intelligence oder Enterprise Edition von Microsoft SQL Server. Finden Sie im Abschnitt [Anforderungen an die Netzwerkinfrastruktur für CQD](plan.md#Infrastructure_Req) unten für weitere Details.
  
![CQD-Komponenten](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Konfiguration der einzelnen server

Alle CQD Komponenten und abhängige Komponenten können auf einem Computer installiert werden. Die single-Box-Konfiguration ist die einfachste Konfiguration und CQD eigenständig sein kann. CQD würde nur Zugriff auf die QoE-Metriken-Datenbank auf dem Monitoring Server benötigen. Der Server CQD kann einem eigenständigen Computer, einen virtuellen Computer oder den Monitoring Server, je nach der verfügbaren Ressourcen des Hostcomputers und der leistungsanforderungen kann auch sein. 
  
Während der Installation, die Benutzer aus die Installation einfach bereitstellen muss, die Microsoft SQL Server und Microsoft SQL Server Analysis Services-Instanzen, die zuvor auf dem Computer eingerichtet worden ist, auf dem die CQD installiert werden soll. [Bereitstellen von Anrufqualität](deploy-0.md) Dashboard für Skype für Business Server finden Sie weitere Informationen.
  
### <a name="multiserver-configuration"></a>MultiServer-Konfiguration

In einer multiserver-Konfiguration, die QoE-Archiv, Cube und Portal kann alle auf verschiedenen Computern sein. Es gibt zwei Hauptfenster Verwendungsmöglichkeiten für die multiserver-Konfiguration aus:
  
- Hosten von CQD Webportal und CQD Cube auf unterschiedlichen Servern.
    
- Hosten einer separaten aus der Portal "Produktion" Portal "Entwicklung". 
    
  **Hosten von CQD Webportal und CQD Cube auf unterschiedlichen Computern.** Organisationen, die möglicherweise Anforderungen, trennen die CQD Portal in der SQL Server-Installation oder, das Mischen und SQLServer-Editionen übereinstimmen, für den SQL Server-Instanz und die SQL Server Analysis Services-Instanz auswählen können, das CQD-Portal installieren möchten, und CQD Cube auf unterschiedlichen Computern. Die QoE-Archiv-Komponente kann auch die einzige Komponente CQD sein, die installiert ist, wenn die Organisation einfach nachhaltigen Methode, um die QoE-Daten ohne zu erreichen Leistungsgrenzwerte auf dem Monitoring Server archivieren möchte.
  
![CQD für einzelnen Server](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosten einer separaten aus der Portal "Produktion" Portal "Entwicklung".** Organisationen, die ihre eigenen benutzerdefinierten Berichten (über die REST-APIs) entwickeln möchten möglicherweise zusätzliche Instanzen von Portal (CQD) zusammen mit der Produktions-Portal bereitstellen, die für die Qualität bei Aufruf der Überwachung oder Untersuchungen regulären Benutzer zugreifen. Die Entwicklung Portal kann Änderungen an das Portal aus der produktionsumgebung isolieren. Die zusätzlichen Webservern Portale können auf verschiedenen Computern (siehe unten) bereitgestellt oder auf anderes Web-Verzeichnisse auf dem gleichen Computer (nicht dargestellt) bereitgestellt werden. Um den zweiten Inhaltstyp zu erreichen, muss zusätzliche CQD Webportal Produktion Computer manuell kopiert werden, da der Installationsvorgang CQD immer dem Webportal CQD für die Standardwebsite mit vordefinierten Webanwendungsnamen bereitstellt.
  
![Planen des CQD-Multiservers](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Unterstützte Topologien

CQD nicht Daten aus mehreren QoEMetrics Datenbanken zusammenführen, wie der Fall ist, in denen mehrere Skype für Business Server-Topologien jeweils mit einem eigenen Monitoring Server vorhanden sind. Jede Instanz CQD muss auf eine QoEMetrics Datenbank verweisen. Allerdings, da CQD einen Großteil der reporting Arbeitslast von Monitoring Server verschoben werden, sollten große Organisationen, die erforderlich, um einen Monitoring Server pro Skype für Business Server-Topologie bereitstellen verwenden ein Monitoring Server für alle Topologien.
  
## <a name="infrastructure-requirements-for-cqd"></a>Infrastrukturanforderungen für CQD
<a name="Infrastructure_Req"> </a>

CQD, einschließlich aller Komponenten und abhängige Komponenten kann auf einem virtuellen Computer, einem einzelnen Computer oder auf mehreren Computern bereitgestellt werden. Die Mindestanforderungen für Software und Hardware sind unten aufgeführt. Verfügbarkeit der Daten und die Leistung auf Stunden, abhängig von der Anzahl von aktiven Skype für Business Server-Benutzer und Hardware und Konfiguration von Minuten abweichen kann werden nachfolgend einige Methoden für leistungsmessungen angegeben.
  
|||
|:-----|:-----|
|Unterstützte Betriebssysteme  <br/> |Windows Server 2008 R2, WindowsServer 2012, Windows Server 2012 R2  <br/> |
|Unterstützte SQLServer  <br/> |SQLServer 2012, SqlServer 2014, SqlServer 2016  <br/> |
   
CQD verwendet Microsoft SQL Server, Microsoft SQL Server Analysis Services und Microsoft Internet Information Services, damit CQDs Mindestanforderungen für Hardware und Software im Wesentlichen die abhängigen Komponenten identisch sind. Jedoch soll auf Grundlage der Anforderungen der Organisation um Datenaktualität (die Teil des Umfangs der QoE-Daten, die die Organisation generiert, hängen) und Bereitstellungskosten, weitere Bereitstellungsaspekte erfolgen.
  
Verarbeitung der Daten in CQD ist in zwei Hauptphasen unterteilt: 
  
- QoE-Archivierung
    
- Verarbeitung der Cube CQD
    
  **Verarbeiten von QoE-Archiv.** QoE-Archiv Ausführung der Aufgabe kopiert Daten aus der QoE-Metriken-Datenbank auf dem Monitoring Server in der QoE-Archivdatenbank. Es gibt zwei Situationen, in denen die Verarbeitungszeit des Vorgangs grundlegend Leistungsmerkmale über würde. Die erste ist nach der Erstinstallation von CQD. Wenn zum ersten Mal nach einer Neuinstallation der Task ausgeführt wird, kopiert QoE-Archiv Ausführung der Aufgabe alle Daten, die in der QoE-Metriken Datenbank in QoE-Archivdatenbank ist. Die zweite ist die periodische Verarbeitung nach dieser anfänglichen Round. Das QoE-Archiv processing Task alle 15 Minuten ausgeführt und verarbeiten neue QoE-Datensätze, die in der Datenbank QoE-Metriken sind. Im Allgemeinen ist die anfänglichen Verarbeitungszeit kein Problem, da sie nur beim ersten Mal ausgeführt wird, wenn CQD installiert ist. Wenn der Server CQD stark unter bereitgestellt ist, kann diese Aufgabe mehrere Stunden dauern. Finden Sie in der Tabelle unten beispielsweise anfänglichen QoE Archiv Verarbeitungszeit.
  
  **Verarbeitung der Cube CQD.** Ausführung der Aufgabe Cube aggregiert die Daten aus der QoE-Archivdatenbank in den Cube. Die anfängliche Cube Verarbeitungszeit und nachfolgende Cube Verarbeitungszeit werden durch die SQL Server Analysis Services Edition verwendet für den Cube CQD bestimmt. Wenn die Standard Edition verwendet wird, es gibt keinen Unterschied zwischen der ersten Cube-Verarbeitungszeit und den nachfolgenden Cube Verarbeitungszeit, da jedes Mal die Cube-Daten aktualisiert werden, es wird immer eine vollständige Verarbeitung aller verfügbaren Daten sein. (Dies bedeutet, dass, die den Cube Verarbeitungszeit als die Menge der Daten in das Archiv QoE erhöht, die Datenbank zunimmt.) Da die Business Intelligence-Edition und Enterprise Edition von SQL Server die Unterstützung der Partition haben, wenn beide Editionen verwendet wird, wird nur beim erstmaligen Ausführen alle Daten in der QoE-Archivdatenbank verarbeitet. In den nachfolgenden ausgeführt wird beim Auslösen der Aufgabe alle 15 Minuten, wird die Aufgabe nur verarbeitet die neuen Datensätze in der QoE-Archivdatenbank seit der letzten Ausführung die Aufgabe hinzugefügt. Einmal pro Tag auch wird eine vollständige Verarbeitung auf der Partition, die dem aktuellen Monat Daten enthält.
  
CQD Leistung als auch die Software-Features, die von den SQL Server-Komponenten zur Verfügung stehen, können die Merkmale physischem auswirken. Die QoE-Archiv-Komponente wird mehr Datenträger-intensiv sein im Vergleich zu anderen Komponenten, während die Cube-Komponente mehr CPU und Arbeitsspeicher intensive wird. All diese Faktoren teilnehmen für CQDs insgesamt Datenverarbeitung Zeitraum, wirkt sich direkt Datenaktualität und Verfügbarkeit auf. Organisationen sollte die Hardware und Software, die basierend auf den einzelnen Anforderungen der Organisation Entscheidungen. 
  
### <a name="tested-hardware-configurations"></a>Getestete Hardwarekonfigurationen

In diesem Abschnitt wird davon ausgegangen, dass eine einzelne QoEMetrics DB in der Umgebung vorhanden ist. 
  
**Computer Profile**

|**Computer**|**CPU-Kerne**|**RAM**|**QoE-Archiv und des Cubes auf dem gleichen Datenträger**|**QoE-Archiv und SQL Temp DB auf demselben Datenträger**|
|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |4  <br/> |7 GB  <br/> |Ja   <br/> |Ja  <br/> |
|4-core  <br/> |4  <br/> |20 GB  <br/> |Ja  <br/> |Nein  <br/> |
|8-core  <br/> |8  <br/> |32 GB  <br/> |Ja  <br/> |Nein  <br/> |
|16 Prozessorkerne  <br/> |16  <br/> |128 GB  <br/> |Nein  <br/> |Nein  <br/> |
   
**Leistungsergebnisse**

|**Computer**|**QoE-Metriken DB-Größe**|**SQL-Partitionen**|**Datenträgertyp**|**Anzahl der Datenströme**|**Erste Archiv-Prozess**|**Erste Cube-Prozess**|**Nachfolgende Archiv-Prozess**|**Nachfolgende Cube-Prozess**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |900 MB  <br/> |Einzelne  <br/> |Virtuelle Festplatte (variabler Größe)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 Mio.  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Einzelne  <br/> |Virtuelle Festplatte (variabler Größe)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 Mio.  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Einzelne  <br/> |Virtuelle Festplatte (mit fester Größe)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 Mio.  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |30 + GB  <br/> |Einzelne  <br/> |Virtuelle Festplatte (mit fester Größe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8-core  <br/> |9 GB  <br/> |Einzelne  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8-core  <br/> |9 GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8-core  <br/> |30 + GB  <br/> |Einzelne  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 Mio.  <br/> |20 m  <br/> |
|8-core  <br/> |30 + GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4-core  <br/> |200 GB  <br/> |Einzelne  <br/> |Mehrere Datenträger  <br/> |125 M  <br/> |6 + Tage  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 Prozessorkerne  <br/> |500 GB  <br/> |Mehrere  <br/> |Mehrere Spindeln  <br/> |250 M  <br/> |8 Tage  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Diese werden nicht erwartet in realen Bereitstellungen festgestellt werden, da die QoE-Metriken Datenbank müssten 9 und 18 Monate Datengruppe, aufweisen, aber hier Vollständigkeit bereitgestellt sind.
  
### <a name="service-account-requirements"></a>Dienstanforderungen-Konto

Sie benötigen ein Konto (mit Lesezugriff auf den QoEMetrics), die zum Importieren von Daten in die QoEArchiveDB der SQL-Agent auf dem Server CQD verwenden können.
  
Sie müssen auch ein separates Konto für eine SSAS-Auftrag für die Daten abrufen QoEArchiveDB konfigurieren (dieser Schritt ist ein Prozess, der optional).
  
IIS am häufigsten verwendet Netzwerkdienst als Anwendungspoolidentität, aber in ein Dienstkonto konfiguriert werden kann.
  
### <a name="portal-access-control"></a>Zugriff auf das Portal-Steuerelement

Standardmäßig werden alle authentifizierter Benutzer Zugriff hat. Dies kann geändert werden, mithilfe von IIS Autorisierungsregeln, um auf eine bestimmte Gruppe zu beschränken.
  
### <a name="pre-install-requirements"></a>Anforderungen vor der Installation

Diese Anweisungen wird davon ausgegangen, dass eine Datenbank QoE-Metriken bereits installiert wurde und an einer beliebigen Stelle in der Skype für Business Server-Topologie ausgeführt wird.
  
#### <a name="hardware-requirements"></a>Hardwareanforderungen

CQD verwendet Microsoft SQL Server, Microsoft SQL Analysis-Server und Microsoft Internet Information Server, damit CQDs Mindestanforderungen für Hardware und Software im Wesentlichen die abhängigen Komponenten identisch sind. Jedoch soll auf Grundlage der Anforderungen der Organisation um Datenaktualität (die Teil des Umfangs der QoE-Daten, die die Organisation generiert, hängen) und Bereitstellungskosten, weitere Bereitstellungsaspekte erfolgen.
  
#### <a name="software-requirements"></a>Softwareanforderungen

Die folgenden Betriebssysteme werden für CQD benötigt:
  
- Windows Server 2008 R2 mit IIS 7.5
    
- WindowsServer 2012 mit IIS 8.0
    
- Windows Server 2012 R2 mit IIS 8,5

- WindowsServer 2016 mit IIS 10.0 (Skype für nur für Business Server 2019 CQD)
    
Im folgenden sind die erforderlichen IIS-Rollendienste (in einer hierarchischen Reihenfolge):
  
- Webserver
    
  - Allgemeine HTTP-Funktionen
    
  - Statischer Inhalt
    
  - Standarddokument
    
  - Anwendungsentwicklung
    
  - ASP.NET
    
  - ISAPI-Filter
    
  - Integrität &amp; Diagnose
    
  - HTTP-Protokollierung
    
  - Sicherheit
    
  - URL-Autorisierung
    
  - Windows-Authentifizierung
    
  - Verwaltungstools
    
  - IIS-Verwaltungskonsole
    
> [!NOTE]
>  Beachten Sie Folgendes für die oben genannten Anforderungen: > 3.5 und .net Framework 4.5-Versionen verfügbar sind. Beide sind erforderlich (genauer gesagt 3.5 SP1 ist erforderlich) .> In einige Systeme, wenn ASP.NET das Setup vor dem Installieren von IIS und ASP.NET möglicherweise nicht in IIS registriert ist. Das Problem Manifeste über Abwesenheit des Anwendungspools für die entsprechende Version .net und auch die .NET CLR-Version in app-Poolkonfiguration fehlt. Um solche ein Problem unter Windows Server 2008 R2 zu beheben, führen Sie `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. Führen Sie auf Windows Server 2012 und Windows Server 2012 R2 `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` gefolgt von der "ServiceModel" Modul aus der Standardwebsite in IIS Manager.>-Verwaltungstools ist optional, aber empfohlen entfernen.
  
So installieren Sie diesen Anforderungen von PowerShell, führen Sie Folgendes:
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Die folgenden Versionen von SQL Server werden unterstützt:
  
- SQL Server 2012
    
- SQL Server 2014

- SQLServer 2016

- SQLServer 2017
    
Business Intelligence oder Enterprise Edition ist aus Gründen der Systemleistung empfohlen. Diese Editionen ermöglichen die Verwendung von mehreren Partitionsdateien, die gleichzeitig, verarbeitet werden kann, die ist nützlich für die Verarbeitung der Daten übergreifende mehrere Monate oder länger. 
  
Zwar nicht empfohlen, wird die Standard Edition sowie unterstützt. Verarbeitung wird eine einzelne Partition eingeschränkt werden (die während der Installation konfiguriert werden muss). 
  
In allen Fällen muss "Datenbankmoduldienste" und "Analysis Services" installiert werden. Es wird empfohlen, aber nicht erforderlich, auch das Feature "Verwaltungstools - abschließen" zu SQL Server Management Studio für Analysis Services Unterstützung installieren. Feature-Auswahlbildschirm sollte wie in der Abbildung aussehen.
  
![Anforderungen an SQL Server-Funktionen](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Legen Sie beim Konfigurieren des SSAS-Setups in der Analysis Services-Konfiguration "Servermodus" auf "Multidimensionalen und Data Mining-Modus". 
  
Zusätzliche Hilfe bei der Installation und Konfiguration von SQL Server Business Intelligence-Features finden Sie unter [Installieren von Analysis Services in Multidimensional und Data Mining-Modus](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Kontoanforderungen

Drei Domänendienstkonten werden dem Prinzip der geringsten Rechte empfohlen: 
  
- Eine, die bereits über ein Sicherheitsprinzipal Anmeldung für QoE-Metriken Datenbank (mit Db_datareader-Berechtigungen) und ein Sicherheitsprinzipal Anmeldung in QoE-Archiv SQL Server-Instanz (erforderlich zum Erstellen eines Verbindungsservers-Objekts während des Setups) verfügt. Dieses Konto wird zum Ausführen von "QoE-Archivdaten" Schritt des Auftrags für SQL Server-Agent verwendet werden.
    
- Eine, die zum Ausführen von "Cube aufbereiten" Schritt des Auftrags für SQL Server-Agent verwendet werden. Setup erstellt eine Anmeldung Sicherheitsprinzipal in QoE-Archivdatenbank (mit lesen und Schreiben von Berechtigungen) und auch Mitglied in der QoE-Rolle (mit der Berechtigung Vollzugriff) für den Cube erstellen.
    
- Eine, die zum Ausführen von IIS-Arbeitsprozess für die Web-Portale und Web-APIs verwendet werden. Setup erstellt eine Anmeldung Sicherheitsprinzipal in QoE-Archivdatenbank (mit Leseberechtigung), einem Sicherheitsprinzipal Anmeldung Repositorydatenbank (mit lesen und Schreiben von Berechtigungen), und ein Mitglied QoERole (mit der Berechtigung Vollzugriff) für den Cube. 
    
    > [!NOTE]
    > Wenn der QoE-Archivdatenbank und Repository-Datenbank in der gleichen SQL Server gehostet werden, wird nur eine Anmeldung Sicherheitsprinzipal mit zwei benutzerzuordnungen erstellt. 
  
Die ersten beiden Konten logisch als "Back-End-Dienstkonten" betrachtet werden können und das letzte Konto ist ein "Front-End-Dienstkonto". Zwar nicht empfohlen, ist es möglich, ein Konto in allen Fällen verwenden.
  
> [!NOTE]
> Das Benutzerkonto Einleiten der Installation benötigen Lesezugriff auf den QoE-Metriken DB sowie (zusätzlich zum Computer Administratorrechte auf dem QoE-Archiv-DB-Server, auf dem die Installation stattfinden muss). 
  
## <a name="capacity-planning"></a>Planen der Kapazität
<a name="Infrastructure_Req"> </a>

CQD ist für das minimale Beeinträchtigung der QoEMetrics: der Code wurde nicht gesperrt werden Daten optimiert und Importaufträge einstellbare sind.
  
Der Typ der Hardware verwenden, hängt von der Anforderungen für Synchronisierungen wie schnell ausgeführt werden soll. Datenträger Sizing lautet wie folgt:
  
- QoEArchive ist größer als QoEMetrics DB ~1.5x anfänglich
    
- SSIS-Cube komprimiert die Daten fast 10 X im Vergleich zu DB
    
- Monatlich Datenpartitionierung; Partitionen können gelöscht werden
    

