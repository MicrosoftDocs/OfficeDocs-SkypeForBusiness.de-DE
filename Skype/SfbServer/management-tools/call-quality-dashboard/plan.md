---
title: Planen des Anrufqualitätsdashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Zusammenfassung: Erfahren Sie, was Sie bei der Planung des Dashboards für die Anrufqualität beachten sollten.'
ms.openlocfilehash: d75e7a07d6f461c6b4b8e1e33ae86869984aae08
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095189"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planen des Anrufqualitätsdashboards für Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie, was Sie bei der Planung des Anrufqualitätsdashboards berücksichtigen sollten.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Übersicht über das Skype for Business Server Call Quality Dashboard

Das Skype for Business Server Call Quality Dashboard (CQD) ist eine Berichtsebene, die auf der Quality of Experience Database im Monitoring Server in Skype for Business Server steht. CQD verwendet Microsoft SQL Server Analysis Services, um aggregierte Informationen zur Nutzungs- und Anrufqualität sowie zum Filtern und Pivotieren des Datasets zur Verfügung zu stellen. Zu den CQD-Features gehören:
  
- **Archivieren von QoE-Daten über die QoE-Archivkomponente von CQD.** Die QoE-Archivkomponente kann QoE-Daten viel länger speichern als der Monitoring Server. Dies ermöglicht eine Trendentwicklung und Berichterstellung für bis zu sieben Monate Daten gleichzeitig, mit der Möglichkeit, das Berichterstellungsfenster so weit zurück zu verschieben, wie Daten enthalten sind.
- **Berichterstellung und Analyse mithilfe der Leistung und Geschwindigkeit Microsoft SQL Server Analysis Services.** CQD verwendet Microsoft SQL Analysis Services, um schnelle Zusammenfassungs-, Filter- und Pivotfunktionen zur Verfügung zu stellen, um das Dashboard über einen Analysis Cube zu unterstützen. Die Ausführungsgeschwindigkeit der Berichterstellung und die Möglichkeit, einen Drilldown auf die Daten durchzuführen, können die Analysezeiten erheblich reduzieren.
- **Neues Datenschema, das für die Anrufqualitätsberichte optimiert wurde.** The Cube has a schema designed for voice quality reporting and investigations. Portalbenutzer können sich auf die Berichterstellungsaufgaben konzentrieren, anstatt herauszufinden, wie das QoE-Metrik-Datenbankschema den benötigten Ansichten zuteil wird. Die Kombination aus QoE Archive und Cube bietet eine Abstraktion, die die Komplexität der Berichterstellung und Analyse über CQD reduziert. Das QoE Archive-Datenbankschema enthält auch Tabellen, die mit bereitstellungsspezifischen Daten aufgefüllt werden können, um den Gesamtwert der Daten zu verbessern.
- **Integrierter Berichtsdesigner und bearbeitung von integrierten Berichten.** Die Portal-Komponente enthält mehrere integrierte Berichte, die nach der Anrufqualitätsmethodik modelliert wurden. Portalbenutzer können die Berichte ändern und neue Berichte über die Bearbeitungsfunktionalität des Portals erstellen.
- **Web-API-Zugriff auf die Berichtsstruktur und Analysis Cube-Daten.** Das Dashboard-Berichtsframework ist nicht die einzige Möglichkeit, die Daten aus dem Cube anzuzeigen. CQD bietet mehrere Beispiele für die Verwendung von HTML und JavaScript zum Abrufen von Daten aus den CQD-Web-APIs und Rendern der Daten in einem benutzerdefinierten Format. Die Kombination aus dem Berichts-Editor und den CQD-Web-APIs ermöglicht eine schnelle Prototyperstellung von Berichten und benutzerdefiniertem Berichtslayout.

> [!NOTE]
> Ein Administrator kann Skype for Business Server 2019 jetzt mithilfe von [CQD Version 3](https://cqd.teams.microsoft.com) verwalten (melden Sie sich mit Administratoranmeldeinformationen an). Dies erfordert eine Hybridimplementierung und die Verwendung von Call Data Connector (CDC). Weitere Informationen zum Aktivieren von CDC finden Sie unter [Plan Call Data Connector.](../../../SfbHybrid/hybrid/plan-call-data-connector.md) Weitere Informationen zur CQD-Version 3 finden Sie unter Aktivieren und Verwenden des Anrufqualitätsdashboards für Microsoft Teams und [Skype for Business Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)

## <a name="cqd-design-goals"></a>CQD-Designziele

Mit CQD können IT-Profis aggregierte Daten verwenden, um Fokusbereiche in ihrer Umgebung zu identifizieren, in denen Probleme mit der Medienqualität auftreten. It allows an IT Pro to compare statistics for different groups of users and identify trends and patterns. Es konzentriert sich nicht auf die Lösung einzelner Anrufprobleme, sondern auf die Identifizierung von Problemen und Lösungen, die für viele Benutzer in einer bestimmten Umgebung gelten. 
  
## <a name="call-quality-dashboard-components"></a>Komponenten des Anrufqualitätsdashboards

Das Anrufqualitätsdashboard besteht aus mehreren Datenbanken, Microsoft SQL Agent-Aufträgen, Prozessen und Webanwendungen. Die Microsoft SQL-Agent-Aufträge kopieren regelmäßig Daten aus der QoE-Metrikdatenbank in die QoE-Archivdatenbank und verarbeitet den Cube mit den Daten in der QoE-Archivdatenbank. In der Repositorydatenbank werden die Berichtsdefinitionen gespeichert, die das Portal unterstützen. Das Portal bietet Browserzugriff auf die Cubedaten. 
  
Die CQD-Komponenten, einschließlich der QoE-Archiv-, Cube- und Repository-Datenbanken, können auf dem Monitoring Server installiert, auf einem eigenen Server oder auf mehreren Servern installiert werden. Die bestimmte Installationsmethode hängt von den Leistungsanforderungen von CQD sowie von Auswirkungen auf andere Prozesse auf denselben Servern ab. Weitere Informationen finden Sie im Abschnitt "Komponenten und Topologien für CQD" weiter unten in diesem Artikel.
  
### <a name="architectural-overview"></a>Übersicht über die Architektur

Zusammenfassend sind für CQD die folgenden Elemente erforderlich:
  
- Zwei Datenbanken: eine Archivdatenbank und eine Repositorydatenbank.
    
- Ein SSAS-Cube, der aggregierte Daten visualisiert 
    
- IIS hostet das CQD-Webportal
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Dieselbe CQD-Architektur unterstützt Lync Server 2013 und Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD und Skype for Business im Vergleich zu Lync 2013

 Nur in einer Skype for Business-Umgebung stehen die folgenden Funktionen zur Verfügung:
  
- Wi-Fi der Signalstärke
    
- Wi-Fi von Chipsatztreibern
    
- Bewerten von Anrufdaten 
    
## <a name="information-available-through-cqd"></a>Über CQD verfügbare Informationen

CQD kann Audio-, Video- und Anwendungsfreigabedaten von Skype for Business Server sowie die Anzahl der guten und schlechten Anrufe sowie das Verhältnis von schlechten zu guten Anrufen anzeigen. Die Ansichten können nach vielen verschiedenen Dimensionen segmentiert und gefiltert werden. CQD zeichnet Daten aus der QoE-Metrikdatenbank im Monitoring Server. Die Daten werden dann mit allen vom Kunden bereitgestellten Daten zusammengeführt, z. B. der Netzwerksubnetz-zu-Gebäude-Zuordnung, um Berichte wie "Anrufqualität pro Gebäude" möglich zu machen. 
  
CQD abstracts also many of the internal QoE data idiosyncrasies such as "caller" and "callee" such that the user can focus on building report views around "server" and "client". Im Anschluss an die Anrufqualitätsmethodik wird CQD optimiert, um die Bedingungen zu identifizieren, über die die Telefonate schlechter Anrufe gemeinsam sind – eine der Grundsätze für die Verbesserung der Anrufqualität.
  
## <a name="viewing-data-in-cqd"></a>Anzeigen von Daten in CQD

Die CQD-Daten können über das CQD-Portal angezeigt und über REST-API-Aufrufe zugegriffen werden.
  
### <a name="cqd-portal"></a>CQD-Portal

Das Portal ist die schnellste Möglichkeit zum Anzeigen der Daten im Cube. Das Portal enthält mehrere integrierte Berichte, die sofort verwendet werden können. Die integrierten Berichte sind strukturiert verknüpft, um den Benutzer zu sukzessive kleineren und kleineren Datenschnitten der Anrufdaten zu leiten. In den integrierten Berichten werden auch die verschiedenen Möglichkeiten hervorgehoben, wie die Daten angezeigt werden können, indem eine Kombination aus Diagrammen und Tabellen mit verschiedenen Pivots, Filtern und Measures demonstriert wird. Jeder Benutzer, der auf das Portal zutritt, kann über eigene Berichte verfügen, die er ändern und freigeben kann. Weitere Informationen zur Verwendung des CQD-Webportals finden Sie unter [Use Call Quality Dashboard for Skype for Business Server](use.md).
  
Unterstützte Betriebssysteme für das CQD-Portal: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 und Windows Server 2016 (nur Skype for Business Server 2019 CQD).
  
Unterstützte Browser für das CQD-Portal: Internet Explorer 11, Internet Explorer 10 und Internet Explorer 9.
  
### <a name="rest-apis"></a>REST-APIs

Auf die Cubedaten kann auch über REST-API-Aufrufe zugegriffen werden. Die über die REST-API-Aufrufe abgerufenen Daten können über HTML-Seiten gerendert werden. Benutzer können die Abfragegeschwindigkeit und das CQD-Schema auf hoher Ebene nutzen und dennoch benutzerdefinierte Berichte erstellen, die für ihre Geschäftlichen Anforderungen geeignet sind. Weitere Informationen zur API und Beispiele finden Sie unter [Entwickeln des Anrufqualitätsdashboards für Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definieren der Anforderungen Ihrer Organisation für CQD

CQD bietet die QoE-Datenarchivierung und eine schnelle und tiefe Analyse von Daten zur Anrufqualität. Die folgende Anleitung hilft Ihnen bei der Entscheidung, wann und warum Sie CQD bereitstellen würden.
  
### <a name="when-to-deploy-cqd"></a>Bereitstellung von CQD

 **CQD kann bereitgestellt werden, um eine grundlegende Messung der Anrufqualität zu erstellen, auch wenn in einer Organisation keine Probleme mit der Anrufqualität auftreten.** Das Einrichten einer grundlegenden Messung der Anrufqualität ist wichtig, da jede Organisation eine andere Mischung aus Wi-Fi und Remote im Vergleich zu Büromitarbeitern hat. Wenn Probleme mit der Anrufqualität auftreten, können die neuesten Messungen der Anrufqualität mit früheren Zeitintervallen verglichen werden. Die Trendfunktionen von CQD ermöglichen eine einfache Erkennung von Änderungen an der Anrufqualität im Laufe der Zeit.
  
 **CQD kann bereitgestellt werden, um proaktiv Problembereiche zu finden, die sich auf die Anrufqualität auswirken können.** Auch wenn die durchschnittliche Anrufqualität für eine Organisation möglicherweise die von der Organisation festgelegten Ziele erfüllt, kann es zu Problemen mit der Anrufqualität kommen, die hinter durchschnittlichen Metriken verborgen sind. CQD ermöglicht eine tabellenmäßige Aufschlüsselung der Anrufqualitätsmetriken nach vielen Dimensionen in der QoEMetrics-Datenbank. Das Ermitteln von Ausreißern in Peergruppen ist eine schnelle Möglichkeit, Probleme mit der Anrufqualität proaktiv zu ermitteln.
  
 **CQD sollte bereitgestellt werden, wenn probleme mit der Anrufqualität in der Organisation auftreten, um den Zeitaufwand für die Problembehandlung zu reduzieren.** CQD kann vorhandene Untersuchungen zur Anrufqualität vereinfachen, indem schnelle Berichterstellungsleistung und dynamische Drilldownfunktionen angeboten werden. CQD ist für viele Arten von Workflows in der Überprüfung der Anrufqualität von Reparaturen an der Umgebung konzipiert.
  
### <a name="why-deploy-cqd"></a>Gründe für die Bereitstellung von CQD

 **CQD sollte bereitgestellt werden, wenn die QoE-Berichterstellung mehr als 3 Monate dauern muss.** Die QoEMetrics-Datenbank- und Überwachungsserverberichte sind so konzipiert, dass sie einen kleinen Satz von Daten beibehalten und melden. Die QoE-Metrikdatenbank ist für schnelle Einfügungen optimiert, und daher kann die Berichterstellungsleistung durch eine große Anzahl von Anrufen oder den konkurrierenden Berichtsdatenzugriff auf die Datenbank beeinträchtigt werden. Die QoE-Archivdatenbank von CQD bietet eine zweite Kopie der QoE-Metrikdaten mit wesentlich längeren Aufbewahrungsfunktionen. Das Portal ist außerdem so optimiert, dass bis zu 7 Monate Daten gleichzeitig angezeigt werden und alle Daten im QoE-Archiv nach Bedarf angezeigt werden können.
  
 **CQD sollte bereitgestellt werden, wenn benutzerdefinierte QoE-Berichte erforderlich sind.** Das Portal verfügt über ein Berichts-Editor-Feature zum schnellen und einfachen Erstellen und Erstellen von Prototypberichten. Außerdem stehen REST-APIs für den programmgesteuerten Zugriff auf die Cubedaten zur Verfügung, wodurch eine benutzerdefinierte Präsentation mithilfe von HTML/JavaScript oder vielen anderen Frameworks ermöglicht wird. Es ist nicht mehr erforderlich, neue SQL zum Erstellen von benutzerdefinierten Datenansichten für die Berichterstellung zu erstellen.
  
 **CQD sollte bereitgestellt werden, wenn vorhandene QoE-Berichtsfunktionen nicht die von der Organisation erforderliche Geschwindigkeit oder Tiefe erfüllen.** CQD enthält viele integrierte Berichte. Die Berichte sind sofort hilfreich und zeigen, wie schrittweises Drilling in die Daten zusätzliche Einblicke auf jeder Ebene bieten kann. Die Berichtehierarchie hilft auch bei der logischen Verwaltung der zahlreichen Berichte und fördert die Erstellung von vielen weiteren Berichten, die leicht zugänglich und verständlich sind. CQD bietet nicht nur Geschwindigkeit und Flexibilität, sondern ist auch für die Workflows optimiert, die von der Anrufqualitätsmethode entwickelt wurden.
  
## <a name="components-and-topologies-for-cqd"></a>Komponenten und Topologien für CQD

CQD verfügt über mehrere Komponenten und hilft dabei, die Anforderungen der einzelnen Komponenten und deren Beziehung zueinander zu verstehen, um die einfachste und optimale Bereitstellung des Tools zu erhalten. In der folgenden Tabelle wird die abhängige Komponente für jede CQD-Komponente beschrieben.
  

|**Komponentenname**|**Abhängige Komponente**|
|:-----|:-----|
|QoE-Archiv  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Microsoft Information Services  <br/> |
|Repository-Dienst (Teil der Portalinstallation)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Für QoE Archive und Cube erfordern bestimmte Bereitstellungsoptionen Business Intelligence- oder Enterprise-Editionen von Microsoft SQL Server. Weitere Informationen finden Sie im Abschnitt Infrastrukturanforderungen für [CQD.](plan.md#Infrastructure_Req)
  
![CQD-Komponenten](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Konfiguration mit einem Einzelnen Server

Alle CQD-Komponenten und abhängigen Komponenten können auf einem Computer installiert werden. Die Einzelfeldkonfiguration ist die einfachste Konfiguration und ermöglicht die eigenständige CQD-Konfiguration. CQD benötigt nur Zugriff auf die QoE-Metrikdatenbank auf dem Monitoring Server. Der CQD Server kann ein eigenständiger Computer, ein virtueller Computer oder sogar der Monitoring Server sein, je nach den verfügbaren Ressourcen des Hostcomputers und den Leistungsanforderungen. 
  
Während der Installation muss der Benutzer, der die Installation ausgeführt hat, lediglich die instanzen Microsoft SQL Server und Microsoft SQL Server Analysis Services bereitstellen, die zuvor auf dem Computer eingerichtet wurden, auf dem die CQD installiert werden soll. Weitere Informationen finden Sie [unter Deploy Call Quality Dashboard for Skype for Business Server.](deploy-0.md)
  
### <a name="multiserver-configuration"></a>Multiserverkonfiguration

In einer Konfiguration mit mehreren Server können sich das QoE-Archiv, der Cube und das Portal auf unterschiedlichen Computern enthalten. Es gibt zwei Hauptverwendungszwecke für die Multiserverkonfiguration:
  
- Hosten von CQD Web Portal und CQD Cube auf verschiedenen Servern.
    
- Hosten eines "Entwicklungsportals" getrennt vom "Produktionsportal". 
    
  **Hosten von CQD Web Portal und CQD Cube auf verschiedenen Computern.** Organisationen, die anforderungen zum Trennen des CQD-Portals von der SQL Server-Installation haben oder die SQL Server-Editionen für die SQL Server-Instanz und die SQL Server Analysis Services-Instanz kombinieren möchten, können das CQD-Portal und den CQD-Cube auf verschiedenen Computern installieren. Die QoE-Archivkomponente kann auch die einzige CQD-Komponente sein, die installiert wird, wenn die Organisation einfach über eine dauerhafte Methode zum Archivieren der QoE-Daten verfügen möchte, ohne Leistungsbeschränkungen auf dem Monitoring Server zu erreichen.
  
![Single Server CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosten eines "Entwicklungsportals" getrennt vom "Produktionsportal".** Organisationen, die ihre eigenen benutzerdefinierten Berichte (über die REST-APIs) entwickeln, möchten möglicherweise zusätzliche (CQD)-Portalinstanzen zusammen mit dem Produktionsportal bereitstellen, auf die reguläre Benutzer für die Überwachung der Anrufqualität oder Untersuchungen zugreifen. Das Entwicklungsportal kann alle Änderungen am Portal von der Produktionsumgebung isolieren. Die zusätzlichen Webportale können auf verschiedenen Computern (siehe unten) oder auf verschiedenen Webverzeichnissen auf demselben Computer bereitgestellt werden (nicht angezeigt). Um letzteres zu erreichen, muss das zusätzliche CQD-Webportal manuell auf den Produktionscomputer kopiert werden, da das CQD-Webportal beim CQD-Setupvorgang immer auf der Standardwebsite mit vordefinierten Webanwendungsnamen bereitgestellt wird.
  
![Planen von CQD Multi Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Unterstützte Topologien

CQD führt keine Daten aus mehreren QoEMetrics-Datenbanken zusammen, wie dies der Fall ist, wenn mehrere Skype for Business Server-Topologien mit jeweils einem eigenen Monitoring Server vorhanden sind. Jede CQD-Instanz muss auf eine QoEMetrics-Datenbank verweisen. Da CQD jedoch einen Großteil der Berichtsarbeitsauslastung vom Monitoring Server verschiebt, sollten große Organisationen, die einen Monitoring Server pro Skype for Business Server-Topologie bereitstellen mussten, die Verwendung eines Monitoring Servers für alle Topologien in Betracht ziehen.
  
## <a name="infrastructure-requirements-for-cqd"></a>Infrastrukturanforderungen für CQD
<a name="Infrastructure_Req"> </a>

CQD, einschließlich aller Komponenten und abhängigen Komponenten, kann auf einem virtuellen Computer, einem einzelnen Computer oder auf mehreren Computern bereitgestellt werden. Die Mindestanforderungen an Software und Hardware sind unten aufgeführt. Datenverfügbarkeit und Abfrageleistung können je nach Anzahl der aktiven Skype for Business Server-Benutzer und Hardware und Konfiguration zwischen Minuten und Stunden variieren, sodass nachfolgend einige Leistungsmessungen durchgeführt werden.
  
|||
|:-----|:-----|
|Für CQD 2015 <br/> |  <br/> |
|Unterstützte Betriebssysteme   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|Unterstützte SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Für CQD 2019 <br/> |  <br/> |
|Unterstützte Betriebssysteme   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|Unterstützte SQL Server  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD verwendet Microsoft SQL Server, Microsoft SQL Server Analysis Services und Microsoft-Internetinformationsdienste daher sind die Hardware- und Softwareanforderungen von CQD im Wesentlichen identisch mit diesen abhängigen Komponenten. Basierend auf den Anforderungen der Organisation im Rahmen der Datenfrischheit (die zum Teil vom Volumen der von der Organisation generierten QoE-Daten abhängen) und den Bereitstellungskosten sollten jedoch zusätzliche Bereitstellungsüberlegungen berücksichtigt werden.
  
Die Datenverarbeitung in CQD ist in zwei Hauptphasen unterteilt: 
  
- QoE-Archivprozess
    
- CQD Cube-Verarbeitung
    
  **QoE-Archivverarbeitung.** Die QoE Archive-Verarbeitungsaufgabe kopiert Daten aus der QoE-Metrikdatenbank auf dem Monitoring Server in die QoE-Archivdatenbank. Es gibt zwei Situationen, in denen die Verarbeitungszeit des Vorgangs grundlegend unterschiedliche Leistungsmerkmale aufweisen würde. Die erste ist nach der Erstinstallation von CQD. Wenn die Aufgabe nach einer Neuinstallation zum ersten Mal ausgeführt wird, kopiert die QoE Archive-Verarbeitungsaufgabe alle Daten in der QoE-Metrikdatenbank in die QoE-Archivdatenbank. Die zweite ist die periodische Verarbeitung nach dieser ersten Runde. Die QoE-Archivverarbeitungsaufgabe wird alle 15 Minuten ausgeführt und verarbeitet alle neuen QoE-Datensätze, die sich in der QoE-Metrikdatenbank befinden. Im Allgemeinen ist die Anfängliche Verarbeitungszeit kein Problem, da sie nur beim ersten Mal ausgeführt wird, wenn CQD installiert wird. Wenn der CQD-Server jedoch stark unter bereitgestellt ist, kann diese Aufgabe mehrere Stunden dauern. In der folgenden Tabelle finden Sie z. B. erste Verarbeitungszeiten des QoE-Archivs.
  
  **CQD Cube-Verarbeitung.** Die Cubeverarbeitungsaufgabe aggregiert die Daten aus der QoE-Archivdatenbank in den Cube. Die anfängliche Cubeverarbeitungszeit und die nachfolgende Cubeverarbeitungszeit werden durch die SQL Server Analysis Services-Edition bestimmt, die für den CQD-Cube verwendet wird. Wenn die Standard-Edition verwendet wird, besteht kein Unterschied zwischen der anfänglichen Cubeverarbeitungszeit und der nachfolgenden Cubeverarbeitungszeit, da bei jeder Aktualisierung der Cubedaten immer alle verfügbaren Daten vollständig verarbeitet werden. (Dies bedeutet, dass die Cubeverarbeitungszeit mit der Zunahme der Datenmenge in der QoE-Archivdatenbank zunimmt.) Da business Intelligence Edition und Enterprise Edition von SQL Server Partitionsunterstützung haben, werden bei Verwendung einer der Editionen nur bei der ersten Ausführung alle Daten in der QoE-Archivdatenbank verarbeiten. Bei nachfolgenden Ausführungen, wenn der Vorgang alle 15 Minuten ausgelöst wird, verarbeiten die Aufgaben nur die neuen Datensätze, die der QoE-Archivdatenbank seit dem letzten Ausführen der Aufgabe hinzugefügt wurden. Einmal am Tag wird auch eine vollständige Verarbeitung der Partition mit den Daten des aktuellen Monats erstellt.
  
Die Eigenschaften des physischen Computers können sich auf die CQD-Leistung sowie auf die Softwarefeatures auswirken, die in den SQL Server sind. Die QoE-Archivkomponente ist im Vergleich zu anderen Komponenten datenträgerintensiver, während die Cubekomponente cpu- und arbeitsspeicherintensiver ist. All diese Faktoren tragen zur Gesamtverarbeitungszeit von CQD bei, was sich direkt auf die Datenfrischheit und -verfügbarkeit auswirkt. Organisationen sollten Entscheidungen zu Hardware und Software treffen, die auf den individuellen Anforderungen der Organisation basieren. 
  
### <a name="tested-hardware-configurations"></a>Getestete Hardwarekonfigurationen

In diesem Abschnitt wird davon ausgegangen, dass es in der Umgebung einen einzelnen QoEMetrics-DB gibt. 
  
**Computerprofile**

|**Maschine**|**CPU-Kerne**|**RAM**|**QoE-Archiv und Cube auf demselben Datenträger**|**QoE Archive and SQL Temp DB on same disk**|
|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |4   <br/> |7 GB  <br/> |Ja  <br/> |Ja  <br/> |
|4 Kerne  <br/> |4   <br/> |20 GB  <br/> |Ja  <br/> |Nein  <br/> |
|8 Kerne  <br/> |8   <br/> |32 GB   <br/> |Ja  <br/> |Nein  <br/> |
|16 Kerne  <br/> |16   <br/> |128 GB  <br/> |Nein  <br/> |Nein  <br/> |
   
**Leistungsergebnisse**

|**Maschine**|**QoE-Metriken DB-Größe**|**SQL Partitionen**|**Datenträgertyp**|**Anzahl der Datenströme**|**Anfänglicher Archivierungsprozess**|**Anfänglicher Cubeprozess**|**Nachfolgender Archivierungsprozess**|**Nachfolgender Cubeprozess**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |900 MB  <br/> |Single  <br/> |VHD (variable Größe)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Single  <br/> |VHD (variable Größe)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Single  <br/> |VHD (feste Größe)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |30 GB  <br/> |Single  <br/> |VHD (feste Größe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 Kerne  <br/> |9 GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 Kerne  <br/> |9 GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 Kerne  <br/> |30 GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 Kerne  <br/> |30 GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 Kerne  <br/> |200 GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |125 M  <br/> |6+ Tage  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 Kerne  <br/> |500 GB  <br/> |Mehrere  <br/> |Mehrere Spindeln  <br/> |250 M  <br/> |8 Tage  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Diese werden in echten Bereitstellungen nicht erwartet, da die QoE-Metrikdatenbank 9 bzw. 18 Monate Daten haben müsste, aber sie werden hier zur Vollständigkeit bereitgestellt.
  
### <a name="service-account-requirements"></a>Dienstkontoanforderungen

Sie benötigen ein Konto (mit Lesezugriff auf QoEMetrics), das der SQL-Agent auf dem CQD-Server zum Importieren von Daten in die QoEArchiveDB verwenden kann.
  
Möglicherweise müssen Sie auch ein separates Konto für einen SSAS-Auftrag konfigurieren, um Daten aus QoEArchiveDB zu ziehen (dies ist ein optionaler Prozess).
  
IIS verwendet den Netzwerkdienst am häufigsten als App-Poolidentität, kann jedoch für ein Dienstkonto konfiguriert werden.
  
### <a name="portal-access-control"></a>Portalzugriffssteuerung

Standardmäßig hat jeder authentifizierte Benutzer Zugriff. Dies kann mithilfe von IIS-Autorisierungsregeln geändert werden, um auf eine bestimmte Gruppe zu beschränken.
  
### <a name="pre-install-requirements"></a>Anforderungen vor der Installation

In diesen Anweisungen wird davon ausgegangen, dass eine QoE-Metrikdatenbank bereits installiert wurde und irgendwo in der Skype for Business Server-Topologie ausgeführt wird.
  
#### <a name="hardware-requirements"></a>Hardwareanforderungen

CQD verwendet Microsoft SQL Server, Microsoft SQL Analysis Server und Microsoft Internet Information Server, sodass die Hardware- und Softwareanforderungen von CQD im Wesentlichen mit diesen abhängigen Komponenten identisch sind. Basierend auf den Anforderungen der Organisation im Rahmen der Datenfrischheit (die zum Teil vom Volumen der von der Organisation generierten QoE-Daten abhängen) und den Bereitstellungskosten sollten jedoch zusätzliche Bereitstellungsüberlegungen berücksichtigt werden.
  
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
    
  - &amp;Integritätsdiagnose
    
  - HTTP-Protokollierung
    
  - Sicherheit
    
  - URL-Autorisierung
    
  - Windows-Authentifizierung
    
  - Verwaltungstools
    
  - IIS-Verwaltungskonsole
    
> [!NOTE]
>  Beachten Sie folgendes für die obigen Anforderungen: > 3.5- und 4.5-Versionen des .Net-Frameworks sind verfügbar. Beides ist erforderlich (genauer gesagt: 3,5 SP1 ist erforderlich).> Wenn ASP.NET in einigen Systemen vor der IIS-Installation eingerichtet wird, wird ASP.NET möglicherweise nicht in IIS registriert. Das Problem manifestiert sich durch das Fehlen von Anwendungspools für die entsprechende .Net-Version und das Fehlen der .NET CLR-Version in der App-Poolkonfiguration. Führen Sie zum Beheben eines solchen Problems Windows Server 2008 R2 `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` aus. Führen Windows Server 2012 und Windows Server 2012 R2 aus, gefolgt vom Entfernen des Moduls "ServiceModel" aus der Standardwebsite  `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` in IIS Manager.> Verwaltungstools ist optional, wird jedoch empfohlen.
  
Führen Sie folgendes aus, um diese Anforderungen mithilfe von PowerShell zu installieren:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Die folgenden Versionen von SQL Server werden unterstützt:
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
Business Intelligence oder Enterprise Edition wird aus Leistungsgründen empfohlen. Diese Editionen ermöglichen die Verwendung mehrerer Partitionsdateien, die parallel verarbeitet werden können, was für die Verarbeitung von Daten über mehrere Monate oder länger von Vorteil ist. 
  
Die Standard edition wird zwar nicht empfohlen, aber auch unterstützt. Die Verarbeitung wird auf eine einzelne Partition beschränkt (die während des Setups konfiguriert werden muss). 
  
In allen Fällen müssen "Database Engine Services" und "Analysis Services" installiert werden. Es wird empfohlen, aber nicht erforderlich, auch das Feature "Verwaltungstools – Vollständig" zu installieren, das SQL Server Management Studio Analysis Services hinzufügt. Der Bildschirm für die Featureauswahl sollte wie die Abbildung aussehen.
  
![SQL Server Featureanforderungen](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Legen Sie beim Konfigurieren des SSAS-Setups in der Analysis Services-Konfiguration den "Servermodus" auf "Mehrdimensionaler und Data Mining-Modus" festgelegt. 
  
Weitere Hilfe zum Installieren und Konfigurieren SQL Server Business Intelligence Features finden Sie unter [Install Analysis Services in Multidimensional and Data Mining Mode](/previous-versions/sql/sql-server-2012/ms143708(v=sql.110)).
  
#### <a name="account-requirements"></a>Kontoanforderungen

Drei Domänendienstkonten werden nach dem Prinzip der geringsten Rechte empfohlen: 
  
- Einer, der bereits über einen Anmeldesicherheitsprinzipal für die QoE-Metrikdatenbank (mit db_datareader-Berechtigungen) und einen Anmeldesicherheitsprinzipal in der QoE Archive SQL Server-Instanz verfügt (erforderlich, um während des Setups ein Linked Server-Objekt zu erstellen). Dieses Konto wird verwendet, um den Schritt "QoE-Archivdaten" des SQL Server ausführen.
    
    > [!NOTE]
    > Wenn Sie in einer stark gesperrten Umgebung arbeiten, müssen Sie überprüfen, ob diesem Dienstkonto die Benutzerrechte "Anmelden als Batchauftrag" und "Lokale Anmeldung zulassen" sowohl für die QoE-Metriküberwachungsdatenbank SQL Server als auch für das QoE-Archiv SQL Server.
    
- Einer, der zum Ausführen des Schritts "Prozesscube" des SQL Server-Agent-Auftrags verwendet wird. Setup erstellt einen Anmeldesicherheitsprinzipal für die QoE-Archivdatenbank (mit Lese- und Schreibberechtigungen) und erstellt außerdem ein Mitglied in der QoE-Rolle (mit Vollzugriffsberechtigung) für den Cube.
    
- Eine, die zum Ausführen des IIS-Arbeitsprozesses für die Webportale und Web-APIs verwendet wird. Setup erstellt einen Anmeldesicherheitsprinzipal für die QoE-Archivdatenbank (mit Leseberechtigung), einen Anmeldesicherheitsprinzipal für die Repositorydatenbank (mit Lese- und Schreibberechtigung) und ein Mitglied in QoERole (mit Vollzugriffsberechtigung) für den Cube. 
    
    > [!NOTE]
    > Wenn sowohl die QoE-Archivdatenbank als auch die Repositorydatenbank in derselben SQL Server, wird nur ein Anmeldesicherheitsprinzipal mit zwei Benutzerzuordnungen erstellt. 
  
Die ersten beiden Konten können logisch als "Back-End-Dienstkonten" betrachtet werden, und das letzte Konto ist ein "Front-End-Dienstkonto". Es wird zwar nicht empfohlen, es ist jedoch möglich, in allen Fällen ein einzelnes Konto zu verwenden.
  
> [!NOTE]
> Das Benutzerkonto, das die Installation initiiert, muss auch über Lesezugriff auf QoE Metrics DB verfügen (zusätzlich zu den Administratorrechten des Computers auf dem QoE Archive DB-Server, auf dem die Installation stattfinden muss). 
  
## <a name="capacity-planning"></a>Kapazitätsplanung
<a name="Infrastructure_Req"> </a>

CQD ist für minimale Auswirkungen auf QoEMetrics konzipiert: Der Code wurde so optimiert, dass keine Daten gesperrt werden, und Importaufträge können angepasst werden.
  
Die Art der zu verwendenden Hardware hängt von Ihren Anforderungen ab, wie schnell Synchronisierungen ausgeführt werden sollen. Die Datenträgeranpassung lautet wie folgt:
  
- QoEArchive ist ca. 1,5x größer als QoEMetrics DB
    
- SSIS Cube komprimiert die Daten fast 10x im Vergleich zu DB
    
- Daten werden monatlich partitioniert. Partitionen können gelöscht werden
