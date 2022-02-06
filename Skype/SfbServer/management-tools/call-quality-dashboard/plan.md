---
title: 'Skype for Business Server: Planen des Anrufqualitäts-Dashboards'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Zusammenfassung: Erfahren Sie, was Sie berücksichtigen sollten, wenn Sie das Anrufqualitäts-Dashboard planen.'
---

# <a name="skype-for-business-server-plan-for-call-quality-dashboard"></a>Skype for Business Server: Planen des Anrufqualitäts-Dashboards 
 
**Zusammenfassung:** Erfahren Sie, was Sie berücksichtigen sollten, wenn Sie das Anrufqualitäts-Dashboard planen.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Übersicht über das Skype for Business Server-Anrufqualitäts-Dashboard

Das Skype for Business Server Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) ist eine Berichtsebene, die sich über der Quality of Experience-Datenbank im Monitoring Server in Skype for Business Server befindet. CQD verwendet Microsoft SQL Server Analysis Services, um aggregierte Informationen zur Nutzung und Anrufqualität sowie zum Filtern und Pivotieren des Datasets bereitzustellen. Zu den CQD-Features gehören:
  
- **Archivieren der QoE-Daten über die QoE-Archivkomponente von CQD.** Die QoE-Archivkomponente kann QoE-Daten für eine viel längere Dauer speichern, als der Monitoring Server kann. Dies ermöglicht eine Trend- und Berichterstellung für daten bis zu sieben Monate gleichzeitig, mit der Möglichkeit, das Berichterstellungsfenster so weit zurück zu schieben, wie Daten vorhanden sind.
- **Berichterstellung und Analyse mithilfe der Leistungsfähigkeit und Geschwindigkeit von Microsoft SQL Server Analysis Services.** CQD nutzt Microsoft SQL Analysis Services, um schnelle Zusammenfassungs-, Filter- und Pivotingfunktionen bereitzustellen, um das Dashboard über einen Analysis Cube zu unterstützen. Das Melden der Ausführungsgeschwindigkeit und die Möglichkeit, einen Drilldown in die Daten durchzuführen, kann die Analysezeiten erheblich reduzieren.
- **Neues Datenschema für die Anrufqualitätsberichterstellung optimiert.** Der Cube verfügt über ein Schema, das für berichte und Untersuchungen zur Sprachqualität entwickelt wurde. Portalbenutzer können sich auf die Berichtsaufgaben konzentrieren, anstatt herauszufinden, wie das QoE Metrics-Datenbankschema den benötigten Ansichten zugeordnet wird. Die Kombination aus dem QoE-Archiv und dem Cube bietet eine Abstraktion, die die Komplexität der Berichterstellung und Analyse über CQD reduziert. Das QoE-Archivdatenbankschema enthält auch Tabellen, die mit bereitstellungsspezifischen Daten aufgefüllt werden können, um den Gesamtwert der Daten zu verbessern.
- **Integrierte Berichts-Designer und in-situ-Berichtbearbeitung.** Die Portalkomponente enthält mehrere integrierte Berichte, die nach der Call Quality Methodology modelliert wurden. Portalbenutzer können die Berichte ändern und neue Berichte über die Bearbeitungsfunktionalität des Portals erstellen.
- **Web-API-Zugriff auf die Berichtstruktur- und Analyse-Cube-Daten.** Das Dashboard-Berichterstellungsframework ist nicht die einzige Möglichkeit zum Anzeigen der Daten aus dem Cube. CQD enthält mehrere Beispiele für die Verwendung von HTML und JavaScript zum Abrufen von Daten aus den CQD-Web-APIs und zum Rendern der Daten in einem benutzerdefinierten Format. Die Kombination aus dem Berichts-Editor und den CQD-Web-APIs ermöglicht eine schnelle Prototyperstellung von Berichten und benutzerdefiniertem Berichtslayout.

> [!NOTE]
> Ein Administrator kann jetzt Skype for Business Server 2019 mit [CQD Version 3](https://cqd.teams.microsoft.com) verwalten (melden Sie sich mit Administratoranmeldeinformationen an). Dies erfordert eine Hybridimplementierung und die Verwendung von Call Data Connector (CDC). Weitere Informationen zum Aktivieren von CDC finden Sie unter ["Plan Call Data Connector](../../../SfbHybrid/hybrid/plan-call-data-connector.md) ". Weitere Informationen zu CQD Version 3 finden Sie unter [Aktivieren und Verwenden des Anrufqualitäts-Dashboards für Microsoft Teams und Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="cqd-design-goals"></a>CQD-Entwurfsziele

CQD ermöglicht IT-Experten die Verwendung aggregierter Daten, um Fokusbereiche in ihrer Umgebung zu identifizieren, in denen Probleme mit der Medienqualität auftreten. It-Pro ermöglicht es, Statistiken für verschiedene Benutzergruppen zu vergleichen und Trends und Muster zu identifizieren. Der Schwerpunkt liegt nicht auf der Lösung einzelner Anrufprobleme, sondern auf der Identifizierung von Problemen und Lösungen, die für viele Benutzer in einer bestimmten Umgebung gelten. 
  
## <a name="call-quality-dashboard-components"></a>Komponenten des Anrufqualitätsdashboards

Das Anrufqualitäts-Dashboard besteht aus mehreren Datenbanken, Microsoft SQL Agent-Aufträgen, Prozessen und Webanwendungen. Die Microsoft SQL Agent-Aufträge kopieren regelmäßig Daten aus der QoE-Metrikdatenbank in die QoE-Archivdatenbank und verarbeiten den Cube mit den Daten in der QoE-Archivdatenbank. In der Repository-Datenbank werden die Berichtsdefinitionen gespeichert, die das Portal unterstützen. Das Portal bietet Browserzugriff auf die Cube-Daten. 
  
Die CQD-Komponenten, einschließlich der QoE-Archiv-, Cube- und Repository-Datenbanken, können auf dem Monitoring Server, auf einem eigenen Server oder auf mehreren Servern installiert werden. Die jeweilige Installationsmethode hängt von den Leistungsanforderungen von CQD sowie von den Auswirkungen auf andere Prozesse auf denselben Servern ab. Weitere Informationen finden Sie im Abschnitt "Komponenten und Topologien für CQD" weiter unten in diesem Artikel.
  
### <a name="architectural-overview"></a>Übersicht über die Architektur

Zusammenfassend lässt sich feststellen, dass das CQD die folgenden Elemente erfordert:
  
- Zwei Datenbanken: eine Archivdatenbank und eine Repositorydatenbank.
    
- Ein SSAS-Cube zur Visualisierung aggregierter Daten 
    
- IIS hostet das CQD-Webportal
    
![CQD-Komponenten.](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Dieselbe CQD-Architektur unterstützt Lync Server 2013 und Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD und Skype for Business im Vergleich zu Lync 2013

 Nur in einer Skype for Business Umgebung stehen die folgenden Funktionen zur Verfügung:
  
- Wi-Fi Melden der Signalstärke
    
- Wi-Fi Berichterstellung für Chipsatztreiber
    
- Bewerten der Anrufdaten 
    
## <a name="information-available-through-cqd"></a>Über CQD verfügbare Informationen

CQD kann Skype for Business Server Anzahl der Audio-, Video- und Anwendungsfreigabedatenströme sowie die Anzahl von guten und fehlerhaften Anrufen sowie das Verhältnis von schlechten zu guten Anrufen anzeigen. Die Ansichten können in segmentiert und nach vielen verschiedenen Dimensionen gefiltert werden. CQD zeichnet Daten aus der QoE-Metrikdatenbank im Monitoring Server. Die Daten werden dann mit allen vom Kunden bereitgestellten Daten zusammengeführt, z. B. der Netzwerk-Subnetz-zu-Gebäude-Zuordnung, um Berichte wie "Anrufqualität pro Gebäude" zu ermöglichen. 
  
CQD abstrahiert auch viele der internen QoE-Daten-Idiosyncrasen wie "Caller" und "callee", sodass sich der Benutzer auf die Erstellung von Berichtsansichten rund um "Server" und "Client" konzentrieren kann. Im Anschluss an die Anrufqualitätsmethodik wurde das Anrufqualitäts-AQD optimiert, um die Gemeinsamkeiten schlechter Anrufe zu ermitteln – eine der Grundsätze zur Verbesserung der Anrufqualität.
  
## <a name="viewing-data-in-cqd"></a>Anzeigen von Daten im CQD

Die CQD-Daten können über das CQD-Portal angezeigt und über REST-API-Aufrufe aufgerufen werden.
  
### <a name="cqd-portal"></a>CQD-Portal

Das Portal ist die schnellste Möglichkeit zum Anzeigen der Daten im Cube. Das Portal enthält mehrere integrierte Berichte, die sofort verwendet werden können. Die integrierten Berichte werden strukturiert verknüpft, um den Benutzer zu schrittweisen kleineren und kleineren Segmenten der Anrufdaten zu führen. In den integrierten Berichten werden auch die verschiedenen Möglichkeiten zum Anzeigen der Daten hervorgehoben, indem eine Kombination aus Diagrammen und Tabellen mit verschiedenen Pivots, Filtern und Kennzahlen veranschaulicht wird. Jeder Benutzer, der auf das Portal zugreift, kann über eigene Berichte verfügen, die er ändern und freigeben kann. Weitere Informationen zur Verwendung des CQD-Webportals finden Sie unter [Verwenden des Anrufqualitäts-Dashboards für Skype for Business Server](use.md).
  
Unterstützte Betriebssysteme für das CQD-Portal: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 und Windows Server 2016 (Skype for Business Server Nur 2019 CQD).
  
Unterstützte Browser für das CQD-Portal: Internet Explorer 11, Internet Explorer 10 und Internet Explorer 9.
  
### <a name="rest-apis"></a>REST-APIs

Auf die Cube-Daten kann auch über REST-API-Aufrufe zugegriffen werden. Die über die REST-API-Aufrufe abgerufenen Daten können über HTML-Seiten gerendert werden. Benutzer können die Abfragegeschwindigkeit und das allgemeine Schema von CQD nutzen, während sie weiterhin benutzerdefinierte Berichte erstellen, die ihren geschäftlichen Anforderungen entsprechen. Weitere Informationen zur API und zu Beispielen finden Sie unter ["Entwickeln des Anrufqualitäts-Dashboards für Skype for Business Server](develop.md)". 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definieren der Anforderungen Ihrer Organisation für CQD

CQD bietet QoE-Datenarchivierung und schnelle und umfassende Analyse von Anrufqualitätsdaten. Im folgenden Leitfaden können Sie entscheiden, wann und warum Sie CQD bereitstellen möchten.
  
### <a name="when-to-deploy-cqd"></a>Wann sollte CQD bereitgestellt werden?

 **CQD kann bereitgestellt werden, um eine grundlegende Messung der Anrufqualität einzurichten, auch wenn in einer Organisation keine Probleme mit der Anrufqualität auftreten.** Das Einrichten einer grundlegenden Messung der Anrufqualität ist wichtig, da jede Organisation eine andere Mischung aus Wi-Fi und nicht mit kabelgebundenen und Remote- und Büromitarbeitern hat. Wenn Probleme mit der Anrufqualität auftreten, können die neuesten Messungen der Anrufqualität mit früheren Zeitintervallen verglichen werden. Die trendigen Features von CQD ermöglichen eine einfache Erkennung von Änderungen der Anrufqualität im Laufe der Zeit.
  
 **CQD kann bereitgestellt werden, um proaktiv Problembereiche zu finden, die sich auf die Anrufqualität auswirken können.** Auch wenn die durchschnittliche Anrufqualität für eine Organisation die von der Organisation festgelegten Ziele erreichen könnte, gibt es möglicherweise Probleme mit der Anrufqualität, die hinter durchschnittlichen Metriken verborgen sind. CQD ermöglicht eine pivottabellenähnliche Aufschlüsselung der Anrufqualitätsmetriken nach vielen Dimensionen in der QoEMetrics-Datenbank. Das Auffinden von Ausreißern in Peergruppen ist eine schnelle Möglichkeit, Probleme mit der Anrufqualität proaktiv zu finden.
  
 **CQD sollte bereitgestellt werden, wenn es Probleme mit der Anrufqualität in der Organisation gibt, um den Zeitaufwand für die Problembehandlung zu reduzieren.** CQD kann vorhandene Untersuchungen zur Anrufqualität vereinfachen, indem es eine schnelle Berichterstellungsleistung und dynamische Drilldownfunktionen bietet. CQD ist für viele Arten von Workflows bei der Überprüfung von Reparaturen an der Umgebung in der Anrufqualität konzipiert.
  
### <a name="why-deploy-cqd"></a>Gründe für die Bereitstellung von CQD

 **CQD sollte bereitgestellt werden, wenn QoE-Berichte für mehr als 3 Monate von Daten erfolgen müssen.** Die QoEMetrics-Datenbank- und Überwachungsserverberichte sind darauf ausgelegt, einen kleinen Satz von Daten beizubehalten und zu melden. Die QoE Metrics-Datenbank ist für schnelle Einfügungen optimiert. Daher kann die Berichterstellungsleistung durch eine große Anzahl von Anrufen oder einen erschwerten Berichterstellungszugriff auf die Datenbank beeinträchtigt werden. Die QoE-Archivdatenbank von CQD stellt eine zweite Kopie der QoE-Metrikdaten mit wesentlich längeren Aufbewahrungsfunktionen bereit. Das Portal ist auch so optimiert, dass daten bis zu 7 Monate gleichzeitig angezeigt werden und alle Daten im QoE-Archiv nach Bedarf gemeldet werden können.
  
 **CQD sollte bereitgestellt werden, wenn benutzerdefinierte QoE-Berichte erforderlich sind.** Das Portal verfügt über ein Bericht-Editor-Feature zum schnellen und einfachen Erstellen und Erstellen von Prototypen für Berichte. Es stellt auch REST-APIs für den programmgesteuerten Zugriff auf die Cube-Daten zur Verfügung, sodass eine benutzerdefinierte Präsentation mit HTML/JavaScript oder vielen anderen Frameworks möglich ist. Es ist nicht mehr erforderlich, neue SQL Abfragen zu erstellen, um benutzerdefinierte Datenansichten für die Berichterstellung zu erstellen.
  
 **CQD sollte bereitgestellt werden, wenn vorhandene QoE-Berichterstellungsfunktionen nicht die von der Organisation erforderliche Geschwindigkeit oder Tiefe erfüllen.** CQD enthält viele integrierte Berichte. Die Berichte sind sofort nützlich und zeigen, wie schrittweises Drillthrough in die Daten zusätzliche Einblicke auf jeder Ebene bieten kann. Die Berichtshierarchie hilft auch bei der logischen Verwaltung der zahlreichen Berichte und fördert die Erstellung vieler weiterer Berichte, die leicht zugänglich und verständlich sind. CQD bietet nicht nur Geschwindigkeit und Flexibilität, sondern ist auch für die workflows optimiert, die von der Call Quality Methodology entwickelt wurden.
  
## <a name="components-and-topologies-for-cqd"></a>Komponenten und Topologien für CQD

CQD enthält mehrere Komponenten und hilft dabei, die Anforderungen der einzelnen Komponenten und deren Beziehung zueinander zu verstehen, um die einfachste und leistungsfähigste Bereitstellung des Tools zu erhalten. In der folgenden Tabelle wird die abhängige Komponente für jede CQD-Komponente beschrieben.
  

|Komponentenname|Abhängige Komponente|
|:-----|:-----|
|QoE-Archiv   |Microsoft SQL Server   |
|Cube   |Microsoft SQL Server Analysis Services   |
|Portal   |Microsoft Information Services   |
|Repository-Dienst (Teil der Portalinstallation)   |Microsoft SQL Server   |
   
> [!NOTE]
> Für QoE Archive und Cube erfordern bestimmte Bereitstellungsoptionen Business Intelligence oder Enterprise Editionen von Microsoft SQL Server. Weitere Informationen finden Sie weiter unten im Abschnitt " [Infrastrukturanforderungen für CQD](plan.md#Infrastructure_Req) ".
  
![CQD-Komponenten.](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Konfiguration mit einem einzelnen Server

Alle CQD-Komponenten und abhängigen Komponenten können auf einem Computer installiert werden. Die Konfiguration mit einem einzigen Feld ist die einfachste Konfiguration und ermöglicht die eigenständige CQD-Konfiguration. CQD würde nur Zugriff auf die QoE-Metrikdatenbank auf dem Monitoring Server benötigen. Der CQD-Server kann ein eigenständiger Computer, ein virtueller Computer oder sogar der Monitoring Server sein, abhängig von den verfügbaren Ressourcen des Hostcomputers und den Leistungsanforderungen. 
  
Während der Installation muss der Benutzer, der die Installation ausführt, einfach die Microsoft SQL Server und Microsoft SQL Server Analysis Services-Instanzen bereitstellen, die zuvor auf dem Computer eingerichtet wurden, auf dem das CQD installiert werden soll. Weitere Informationen finden Sie unter [Bereitstellen des Anrufqualitätsdashboards für Skype for Business Server](deploy-0.md).
  
### <a name="multiserver-configuration"></a>Multiserverkonfiguration

In einer Multiserverkonfiguration können sich das QoE-Archiv, der Cube und das Portal auf verschiedenen Computern befinden. Es gibt zwei Hauptmöglichkeiten für die Konfiguration von Multiservern:
  
- Hosten des CQD-Webportals und des CQD-Cubes auf verschiedenen Servern.
    
- Hosten eines vom "Produktionsportal" getrennten "Entwicklungsportals". 
    
  **Hosten des CQD-Webportals und des CQD-Cubes auf verschiedenen Computern.** Organisationen, die möglicherweise Anforderungen haben, um das CQD-Portal von der SQL Server-Installation zu trennen, oder die SQL Server Editionen für die SQL Server Instanz kombinieren und abgleichen möchten, und SQL Server Analysis Services-Instanz das CQD-Portal und den CQD-Cube auf verschiedenen Computern installieren möchten. Die QoE-Archivkomponente kann auch die einzige CQD-Komponente sein, die installiert wird, wenn die Organisation einfach eine dauerhafte Methode zum Archivieren der QoE-Daten haben möchte, ohne leistungsbeschränkungen auf dem Monitoring Server zu erreichen.
  
![Single Server CQD.](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosten eines vom "Produktionsportal" getrennten "Entwicklungsportals".** Organisationen, die ihre eigenen benutzerdefinierten Berichte (über die REST-APIs) entwickeln, möchten möglicherweise zusätzliche (CQD)-Portalinstanzen zusammen mit dem Produktionsportal bereitstellen, auf das reguläre Benutzer zur Überwachung der Anrufqualität oder untersuchungen zugreifen. Das Entwicklungsportal kann alle Änderungen am Portal von der Produktionsumgebung isolieren. Die zusätzlichen Webportale können auf verschiedenen Computern (siehe unten) oder in verschiedenen Webverzeichnissen auf demselben Computer bereitgestellt werden (nicht angezeigt). Um letzteres zu erreichen, muss das zusätzliche CQD-Webportal manuell auf den Produktionscomputer kopiert werden, da der CQD-Setupprozess das CQD-Webportal immer auf der Standardwebsite mit vordefinierten Webanwendungsnamen bereitstellt.
  
![Planen Sie CQD Multi Server.](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Unterstützte Topologien

CQD führt keine Daten aus mehreren QoEMetrics-Datenbanken zusammen, ebenso wie bei mehreren Skype for Business Server Topologien, die jeweils über einen eigenen Monitoring Server verfügen. Jede CQD-Instanz muss auf eine QoEMetrics-Datenbank verweisen. Da das CQD jedoch einen Großteil der Berichtsarbeitslast vom Monitoring Server entfernt, sollten große Organisationen, die einen Überwachungsserver pro Skype for Business Server Topologie bereitstellen mussten, die Verwendung eines Monitoring Servers für alle Topologien in Betracht ziehen.
  
## <a name="infrastructure-requirements-for-cqd"></a>Infrastrukturanforderungen für CQD
<a name="Infrastructure_Req"> </a>

CQD, einschließlich aller komponenten und abhängigen Komponenten, kann auf einem virtuellen Computer, einem einzelnen Computer oder auf mehreren Computern bereitgestellt werden. Die Mindestanforderungen an Software und Hardware sind unten aufgeführt. Die Datenverfügbarkeit und Abfrageleistung kann von Minuten zu Stunden variieren, abhängig von der Anzahl der aktiven Skype for Business Server Benutzern und der Hardware und Konfiguration, sodass unten einige Leistungsmessungen durchgeführt werden.
  

|Für CQD 2015 |&nbsp;  |
|:-----|:-----|
|Unterstützte Betriebssysteme    |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2   |
|Unterstützte SQL Server   |SQL Server 2012, SQL Server 2014, SQL Server 2016   |


|Für CQD 2019  |&nbsp;  |
|:-----|:-----|
|Unterstützte Betriebssysteme    |Windows Server 2016, Windows Server 2019   |
|Unterstützte SQL Server   |SQL Server 2017, SQL Server 2019   |
   
CQD nutzt Microsoft SQL Server, Microsoft SQL Server Analysis Services und Microsoft-Internetinformationsdienste, sodass die Mindestanforderungen an Hardware und Software von CQD im Wesentlichen mit diesen abhängigen Komponenten identisch sind. Basierend auf den Anforderungen der Organisation in Bezug auf die Aktualität von Daten (die teilweise von der Menge der von der Organisation generierten QoE-Daten abhängen) und den Bereitstellungskosten sollten zusätzliche Bereitstellungsaspekte berücksichtigt werden.
  
Die Datenverarbeitung im CQD ist in zwei Hauptphasen unterteilt: 
  
- QoE-Archivprozess
    
- CQD-Cubeverarbeitung
    
  **QoE-Archivverarbeitung.** Die QoE-Archivierungsverarbeitungsaufgabe kopiert Daten aus der QoE-Metrikdatenbank auf dem Überwachungsserver in die QoE-Archivdatenbank. Es gibt zwei Situationen, in denen die Verarbeitungszeit der Aufgabe grundlegend unterschiedliche Leistungsmerkmale aufweisen würde. Der erste ist nach der ersten Installation von CQD. Wenn die Aufgabe zum ersten Mal nach einer Neuinstallation ausgeführt wird, kopiert die QoE-Archivverarbeitungsaufgabe alle Daten, die sich in der QoE-Metrikdatenbank befinden, in die QoE-Archivdatenbank. Die zweite ist die regelmäßige Verarbeitung nach dieser ersten Runde. Die QoE-Archivierungsverarbeitungsaufgabe wird alle 15 Minuten ausgeführt und verarbeitet alle neuen QoE-Datensätze, die sich in der QoE-Metrikdatenbank befinden. Im Allgemeinen ist die anfängliche Verarbeitungszeit kein Problem, da sie nur beim ersten Mal ausgeführt wird, wenn CQD installiert wird. Wenn der CQD-Server jedoch stark unterverlastet ist, kann diese Aufgabe mehrere Stunden dauern. In der folgenden Tabelle finden Sie Beispiele für die anfänglichen QoE-Archivverarbeitungszeiten.
  
  **CQD Cube-Verarbeitung.** Der Cube-Verarbeitungsvorgang aggregiert die Daten aus der QoE-Archivdatenbank in den Cube. Die anfängliche Cubeverarbeitungszeit und die anschließende Cubeverarbeitungszeit werden durch die SQL Server Analysis Services-Edition bestimmt, die für den CQD-Cube verwendet wird. Wenn die Standard Edition verwendet wird, gibt es keinen Unterschied zwischen der anfänglichen Cubeverarbeitungszeit und der nachfolgenden Cubeverarbeitungszeit, da bei jeder Aktualisierung der Cube-Daten immer eine vollständige Verarbeitung aller verfügbaren Daten erfolgt. (Dies bedeutet, dass die Verarbeitungszeit des Cubes mit zunehmender Datenmenge in der QoE-Archivdatenbank zunimmt.) Da die Business Intelligence Edition und Enterprise Edition von SQL Server Partitionsunterstützung haben, werden bei Verwendung einer der editionen nur bei der ersten Ausführung alle Daten in der QoE-Archivdatenbank verarbeitet. Wenn die Aufgabe in nachfolgenden Ausführungen alle 15 Minuten ausgelöst wird, verarbeitet die Aufgabe nur die neuen Datensätze, die der QoE-Archivdatenbank seit der letzten Ausführung der Aufgabe hinzugefügt wurden. Einmal täglich erfolgt auch eine vollständige Verarbeitung der Partition, die die Daten des aktuellen Monats enthält.
  
Die Merkmale des physischen Computers können sich auf die CQD-Leistung sowie auf die Softwarefeatures auswirken, die in den SQL Server-Komponenten verfügbar sind. Die QoE-Archivkomponente ist im Vergleich zu anderen Komponenten festplattenintensiver, während die Cube-Komponente cpu- und speicherintensiver ist. Alle diese Faktoren tragen zur gesamten Datenverarbeitungszeit von CQD bei, was sich direkt auf die Aktualität und Verfügbarkeit von Daten auswirkt. Organisationen sollten Entscheidungen hinsichtlich der Hardware und Software auf der Grundlage der individuellen Anforderungen der Organisation treffen. 
  
### <a name="tested-hardware-configurations"></a>Getestete Hardwarekonfigurationen

In diesem Abschnitt wird davon ausgegangen, dass eine einzelne QoEMetrics DB in der Umgebung vorhanden ist. 
  
**Computerprofile**

|Maschine|CPU-Kerne|RAM|QoE-Archiv und Cube auf demselben Datenträger|QoE-Archiv und SQL Temp DB auf demselben Datenträger|
|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer   |4   |7 GB   |Ja   |Ja   |
|4 Kerne   |4   |20 GB   |Ja   |Nein   |
|8 Kerne   |8    |32 GB    |Ja   |Nein   |
|16 Kerne   |16   |128 GB   |Nein   |Nein   |
   
**Leistungsergebnisse**

|Maschine|QoE-Metriken – DB-Größe|SQL Partitionen|Datenträgertyp|Anzahl der Datenströme|Anfänglicher Archivierungsprozess|Anfänglicher Cubeprozess|Nachfolgender Archivierungsprozess|Nachfolgender Cube-Prozess|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer   |900 MB   |Single   |VHD (variable Größe)   |0,5 M   |30 m   |2 m   |30 s   |1 m   |
|Virtueller Computer   |9 GB   |Single   |VHD (variable Größe)   |5 M   |4 h   |15 m   |1 m   |5 m   |
|Virtueller Computer   |9 GB   |Single   |VHD (feste Größe)   |5 M   |2 h   |5 m   |1 m   |5 m   |
|Virtueller Computer   |30+ GB   |Single   |VHD (feste Größe)   |10 M   |15 h   |20 m   |2 m   |45 m   |
|8 Kerne   |9 GB   |Single   |Mehrere Datenträger   |5 M   |2 h   |5 m   |25 s   |5 m   |
|8 Kerne   |9 GB   |Mehrere   |Mehrere Datenträger   |5 M   |2 h   |15 m   |35 s   |2 m   |
|8 Kerne   |30+ GB   |Single   |Mehrere Datenträger   |20 M   |9 h   |20 m   |1 m   |20 m   |
|8 Kerne   |30+ GB   |Mehrere   |Mehrere Datenträger   |20 M   |9 h   |30 m   |2 m   |2 m   |
|4 Kerne   |200 GB   |Single   |Mehrere Datenträger   |125 M   |6+ Tage   |7 h   |2 m   |6 h   |
|16 Kerne   |500 GB   |Mehrere   |Mehrere Ausschlüsse   |250 M   |8 Tage   |2 h   |2 m   |10 m   |
   
\*Es wird nicht erwartet, dass diese in echten Bereitstellungen auftreten, da die QoE-Metrikdatenbank daten über 9 bzw. 18 Monate verfügen müsste, aber sie werden hier zur Vollständigkeit bereitgestellt.
  
### <a name="service-account-requirements"></a>Dienstkontoanforderungen

Sie benötigen ein Konto (mit Lesezugriff auf QoEMetrics), das der SQL-Agent auf dem CQD-Server zum Importieren von Daten in QoEArchiveDB verwenden kann.
  
Möglicherweise müssen Sie auch ein separates Konto für einen SSAS-Auftrag konfigurieren, um Daten aus QoEArchiveDB abzurufen (dies ist ein optionaler Prozess).
  
IIS verwendet den Netzwerkdienst am häufigsten als App-Poolidentität, kann aber für ein Dienstkonto konfiguriert werden.
  
### <a name="portal-access-control"></a>Portalzugriffssteuerung

Standardmäßig hat jeder authentifizierte Benutzer Zugriff. Dies kann mithilfe von IIS-Autorisierungsregeln geändert werden, um eine bestimmte Gruppe einzuschränken.
  
### <a name="pre-install-requirements"></a>Voraussetzungen für die Vorinstallation

Bei diesen Anweisungen wird davon ausgegangen, dass eine QoE Metrics-Datenbank bereits installiert wurde und an einer stelle stelle in der Skype for Business Server Topologie ausgeführt wird.
  
#### <a name="hardware-requirements"></a>Hardwareanforderungen

CQD verwendet Microsoft SQL Server, Microsoft SQL Analysis Server und Microsoft Internet Information Server, sodass die Mindestanforderungen an Hardware und Software von CQD im Wesentlichen mit diesen abhängigen Komponenten identisch sind. Basierend auf den Anforderungen der Organisation in Bezug auf die Aktualität von Daten (die teilweise von der Menge der von der Organisation generierten QoE-Daten abhängen) und den Bereitstellungskosten sollten zusätzliche Bereitstellungsaspekte berücksichtigt werden.
  
#### <a name="software-requirements"></a>Softwareanforderungen

Für CQD sind die folgenden Betriebssysteme erforderlich:
  
- Windows Server 2008 R2 mit IIS 7.5
    
- Windows Server 2012 mit IIS 8.0
    
- Windows Server 2012 R2 mit IIS 8.5

- Windows Server 2016 mit IIS 10.0 (nur Skype for Business Server 2019 CQD)

- Windows Server 2019 (nur Skype for Business Server 2019 CQD)
    
Es folgen die erforderlichen IIS-Rollendienste (in hierarchischer Reihenfolge):
  
- Webserver
    
  - Allgemeine HTTP-Features
    
  - Statischer Inhalt
    
  - Standarddokument
    
  - Anwendungsentwicklung
    
  - ASP.NET
    
  - ISAPI-Filter
    
  - Integritätsdiagnose &amp;
    
  - HTTP-Protokollierung
    
  - Sicherheit
    
  - URL-Autorisierung
    
  - Windows-Authentifizierung
    
  - Verwaltungstools
    
  - IIS-Verwaltungskonsole
    
> [!NOTE]
>  Beachten Sie für die oben genannten Anforderungen Folgendes: > Versionen 3.5 und 4.5 des .Net Frameworks sind verfügbar. Beides ist erforderlich (genauer gesagt: 3.5 SP1 ist erforderlich).> In einigen Systemen, wenn ASP.NET vor der IIS-Installation eingerichtet ist, werden ASP.NET möglicherweise nicht in IIS registriert. Das Problem manifestiert sich durch das Fehlen von Anwendungspools für die entsprechende .Net-Version und fehlende .NET CLR-Version in der App-Poolkonfiguration. Um ein solches Problem auf Windows Server 2008 R2 zu beheben, führen Sie `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. Führen `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` Sie Windows Server 2012 und Windows Server 2012 R2 aus, und entfernen Sie anschließend das Modul "ServiceModel" von der Standardwebsite in IIS Manager.> Verwaltungstools ist optional, wird jedoch empfohlen.
  
Führen Sie folgende Schritte aus, um diese Anforderungen mithilfe von PowerShell zu installieren:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Die folgenden Versionen von SQL Server werden unterstützt:

- CQD 2015: SQL Server 2012, SQL Server 2014, SQL Server 2016
- CQD 2019: SQL Server 2017, SQL Server 2019 
    
Business Intelligence oder Enterprise Edition wird aus Leistungsgründen empfohlen. Diese Editionen ermöglichen die Verwendung mehrerer Partitionsdateien, die parallel verarbeitet werden können, was für die Verarbeitung von Daten über mehrere Monate oder länger von Vorteil ist. 
  
Standard Edition wird zwar nicht empfohlen, aber auch unterstützt. Die Verarbeitung wird auf eine einzelne Partition beschränkt (die während des Setups konfiguriert werden muss). 
  
In allen Fällen müssen "Datenbank-Engine Services" und "Analysis Services" installiert werden. Es wird empfohlen, aber nicht erforderlich, auch das Feature "Management Tools - Complete" zu installieren, das SQL Server Management Studio Unterstützung für Analysis Services hinzufügt. Der Bildschirm für die Featureauswahl sollte wie in der Abbildung aussehen.
  
![SQL Server Featureanforderungen.](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Wenn Sie das SSAS-Setup konfigurieren, legen Sie in der Analysis Services-Konfiguration "Servermodus" auf "Multidimensional and Data Mining Mode" fest. 
  
Weitere Hilfe zum Installieren und Konfigurieren SQL Server Business Intelligence-Features finden Sie unter [Installieren von Analysis Services im multidimensionalen modus und Data Mining-Modus](/previous-versions/sql/sql-server-2012/ms143708(v=sql.110)).
  
#### <a name="account-requirements"></a>Kontoanforderungen

Drei Domänendienstkonten werden nach dem Prinzip der geringsten Rechte empfohlen: 
  
- Einer, der bereits über einen Anmeldesicherheitsprinzipal für die QoE-Metrikdatenbank (mit db_datareader Berechtigung) und einen Anmeldesicherheitsprinzipal im QoE-Archiv SQL Server Instanz verfügt (erforderlich, um während der Einrichtung ein Linked Server-Objekt zu erstellen). Dieses Konto wird verwendet, um den Schritt "QoE-Archivdaten" des SQL Server Agent-Auftrags auszuführen.
    
    > [!NOTE]
    > Wenn Sie in einer stark gesperrten Umgebung arbeiten, müssen Sie überprüfen, ob diesem Dienstkonto die Benutzerrechte "Anmeldung als Batchauftrag" und "Lokale Anmeldung zulassen" sowohl für die QoE Metrics Monitoring-Datenbank SQL Server als auch für die QoE-Archiv-SQL Server gewährt werden.
    
- Eine, die zum Ausführen des Schritts "Prozess-Cube" des SQL Server Agent-Auftrags verwendet wird. Setup erstellt einen Anmeldesicherheitsprinzipal für die QoE-Archivdatenbank (mit Lese- und Schreibberechtigungen) und erstellt außerdem ein Mitglied in der QoE-Rolle (mit Vollzugriffsberechtigungen) für den Cube.
    
- Eine, die zum Ausführen des IIS-Arbeitsprozesses für die Webportale und Web-APIs verwendet wird. Setup erstellt einen Anmeldesicherheitsprinzipal für die QoE-Archivdatenbank (mit Leseberechtigung), einen Anmeldesicherheitsprinzipal für die Repository-Datenbank (mit Lese- und Schreibberechtigungen) und ein Mitglied in QoERole (mit Vollzugriffsberechtigung) für den Cube. 
    
    > [!NOTE]
    > Wenn sowohl die QoE-Archivdatenbank als auch die Repository-Datenbank in demselben SQL Server gehostet werden, wird nur ein Anmeldesicherheitsprinzipal mit zwei Benutzerzuordnungen erstellt. 
  
Die ersten beiden Konten können logisch als "Back-End-Dienstkonten" betrachtet werden, und das letzte Konto ist ein "Front-End-Dienstkonto". Es wird zwar nicht empfohlen, es ist jedoch in allen Fällen möglich, ein einzelnes Konto zu verwenden.
  
> [!NOTE]
> Das Benutzerkonto, das die Installation initiiert, muss auch über Lesezugriff auf QoE Metrics DB verfügen (zusätzlich zu den Computeradministratorrechten auf dem QoE Archive DB-Server, auf dem die Installation erfolgen muss). 
  
## <a name="capacity-planning"></a>Kapazitätsplanung
<a name="Infrastructure_Req"> </a>

CQD wurde für minimale Auswirkungen auf QoEMetrics entwickelt: Der Code wurde so optimiert, dass keine Daten gesperrt werden, und Importaufträge können optimiert werden.
  
Die Art der zu verwendenden Hardware hängt von Ihren Anforderungen ab, wie schnell Synchronisierungen ausgeführt werden sollen. Die Größe des Datenträgers lautet wie folgt:
  
- QoEArchive ist ~1,5x größer als QoEMetrics DB anfänglich
    
- SSIS Cube komprimiert die Daten fast 10x im Vergleich zu DB
    
- Daten werden monatlich partitioniert. Partitionen können gelöscht werden
