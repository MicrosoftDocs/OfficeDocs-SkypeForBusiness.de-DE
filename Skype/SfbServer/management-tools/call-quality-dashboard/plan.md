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
description: 'Zusammenfassung: Erfahren Sie, was Sie bei der Planung des Anrufqualitätsdashboards berücksichtigen sollten.'
ms.openlocfilehash: 6a1fc39dd26f6c4e9e455babcecb124888629179
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803175"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planen des Anrufqualitätsdashboards für Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie, was Sie bei der Planung des Anrufqualitätsdashboards berücksichtigen sollten.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Übersicht über das Skype for Business Server Call Quality Dashboard

Das Skype for Business Server Call Quality Dashboard (CQD) ist eine Berichtsebene, die über der Quality of Experience Database im Monitoring Server in Skype for Business Server steht. CQD verwendet Microsoft SQL Server Analysis Services, um aggregierte Informationen zur Nutzung und Anrufqualität sowie zum Filtern und Pivotieren des Datasets zur Verfügung zu stellen. Zu den CQD-Features gehören:
  
- **Archivieren von QoE-Daten über die QoE-Archivkomponente von CQD.** Die QoE-Archivkomponente kann die Daten von QoE viel länger speichern als der Monitoring Server. Auf diese Weise können Daten für bis zu sieben Monate gleichzeitig im Trend und für Berichte angezeigt werden, mit der Möglichkeit, das Berichterstellungsfenster so weit zurück zu verschieben, dass Daten enthalten sind.
- **Berichterstellung und Analyse mithilfe der Leistung und Geschwindigkeit von Microsoft SQL Server Analysis Services.** CQD nutzt Microsoft SQL Analysis Services, um schnelle Zusammenfassungs-, Filter- und Pivotfunktionen zur Verfügung zu stellen, um das Dashboard über einen Analysecube zu unterstützen. Die Geschwindigkeit der Berichterstellung und die Möglichkeit, einen Drilldown in die Daten durchzuführen, können die Analysezeiten erheblich reduzieren.
- **Neues Datenschema, das für die Anrufqualitätsberichterstattung optimiert wurde.** Der Cube verfügt über ein Schema für Berichte und Untersuchungen zur Sprachqualität. Portalbenutzer können sich auf die Berichterstellungsaufgaben konzentrieren, anstatt herauszufinden, wie das QoE-Metrik-Datenbankschema den benötigten Ansichten zu ordnet wird. Die Kombination aus dem QoE-Archiv und dem Cube bietet eine Abstraktion, die die Komplexität der Berichterstellung und Analyse über CQD reduziert. Das Datenbankschema des QoE-Archivs enthält auch Tabellen, die mit bereitstellungsspezifischen Daten aufgefüllt werden können, um den Gesamtwert der Daten zu verbessern.
- **Integrierter Berichtsdesigner und bearbeitung von integrierten Berichten.** Die Portalkomponente enthält mehrere integrierte Berichte, die nach der Anrufqualitätsmethode modelliert wurden. Portalbenutzer können die Berichte ändern und neue Berichte über die Bearbeitungsfunktion des Portals erstellen.
- **Web-API-Zugriff auf berichtsstruktur- und Analysecubedaten.** Das Dashboardberichtsframework ist nicht die einzige Möglichkeit, die Daten aus dem Cube anzuzeigen. CQD bietet mehrere Beispiele für die Verwendung von HTML und JavaScript zum Abrufen von Daten aus den CQD-Web-APIs und Rendern der Daten in einem benutzerdefinierten Format. Die Kombination aus dem Berichtseditor und den CQD-Web-APIs ermöglicht eine schnelle Prototyperstellung von Berichten und ein benutzerdefiniertes Berichtslayout.

> [!NOTE]
> Ein Administrator kann Skype for Business Server 2019 jetzt mit [CQD, Version 3,](https://cqd.teams.microsoft.com) verwalten (melden Sie sich mit Administratoranmeldeinformationen an). Dies erfordert eine Hybridimplementierung und die Verwendung von Call Data Connector (CDC). Weitere Informationen zum Aktivieren von CDC finden Sie unter ["Plan Call Data Connector".](/SkypeForBusiness/hybrid/plan-call-data-connector) Weitere Informationen zu CQD, Version 3, finden Sie unter "Aktivieren und Verwenden des Anrufqualitätsdashboards für Microsoft Teams und [Skype for Business Online".](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)

## <a name="cqd-design-goals"></a>CQD-Entwurfsziele

CQD ermöglicht es IT-Profis, aggregierte Daten zu verwenden, um Fokusbereiche in ihrer Umgebung zu identifizieren, die Probleme mit der Medienqualität haben. It allows an IT Pro to compare statistics for different groups of users and identify trends and patterns. Der Schwerpunkt liegt nicht auf der Lösung einzelner Anrufprobleme, sondern auf der Identifizierung von Problemen und Lösungen, die für viele Benutzer in einer bestimmten Umgebung gelten. 
  
## <a name="call-quality-dashboard-components"></a>Komponenten des Anrufqualitätsdashboards

Das Anrufqualitätsdashboard besteht aus mehreren Datenbanken, Microsoft SQL Agent-Aufträgen, Prozessen und Webanwendungen. Die Microsoft SQL -Agent-Aufträge kopieren regelmäßig Daten aus der QoE-Metrikdatenbank in die QoE-Archivdatenbank und verarbeitet den Cube mit den Daten in der QoE-Archivdatenbank. In der Repositorydatenbank werden die Berichtsdefinitionen gespeichert, die das Portal unterstützen. Das Portal bietet Browserzugriff auf die Cubedaten. 
  
Die CQD-Komponenten, einschließlich der QoE-Archiv-, Cube- und Repositorydatenbanken, können auf dem Monitoring Server, auf einem eigenen Server oder auf mehreren Servern installiert werden. Die spezielle Installationsmethode hängt von den Leistungsanforderungen von CQD sowie von Auswirkungen auf andere Prozesse auf denselben Servern ab. Weitere Informationen finden Sie im Abschnitt "Komponenten und Topologien für CQD" weiter unten in diesem Artikel.
  
### <a name="architectural-overview"></a>Übersicht über die Architektur

Zusammenfassend lässt sich zusammenfassen, dass für CQD die folgenden Elemente erforderlich sind:
  
- Zwei Datenbanken: eine Archivdatenbank und eine Repositorydatenbank.
    
- Ein SSAS-Cube, der aggregierte Daten visualisiert 
    
- IIS hostet das CQD-Webportal
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Dieselbe CQD-Architektur unterstützt Lync Server 2013 und Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD und Skype for Business im Vergleich zu Lync 2013

 Nur in einer Skype for Business-Umgebung stehen die folgenden Funktionen zur Verfügung:
  
- Wi-Fi von Signalstärkeberichten
    
- Wi-Fi von Chipsatztreibern
    
- Bewerten von Anrufdaten 
    
## <a name="information-available-through-cqd"></a>Über CQD verfügbare Informationen

CQD kann Audio-, Video- und Anwendungsfreigabedatenstrom von Skype for Business Server sowie die Anzahl der guten und schlechten Anrufe sowie das Verhältnis von schlecht zu gut anrufen anzeigen. Die Ansichten können nach vielen verschiedenen Dimensionen segmentiert und gefiltert werden. CQD zeichnet Daten aus der QoE-Metrikdatenbank auf dem Monitoring Server. Die Daten werden dann mit allen vom Kunden bereitgestellten Daten zusammengeführt, z. B. der Zuordnung von Netzwerksubnetz zu Gebäude, um Berichte wie "Anrufqualität pro Gebäude" zu ermöglichen. 
  
CQD abstracts also many of the internal QoE data idiosyncrasies such as "caller" and "callee" such that the user can focus on building report views around "server" and "client". Im Anschluss an die Anrufqualitätsmethode wurde das CQD optimiert, um die Bedingungen zu identifizieren, die schlechte Anrufe gemeinsam haben – eines der Grundsätze zur Verbesserung der Anrufqualität.
  
## <a name="viewing-data-in-cqd"></a>Anzeigen von Daten in CQD

Die CQD-Daten können über das CQD-Portal angezeigt und über REST-API-Aufrufe zugegriffen werden.
  
### <a name="cqd-portal"></a>CQD Portal

Das Portal ist die schnellste Möglichkeit zum Anzeigen der Daten im Cube. Das Portal enthält mehrere integrierte Berichte, die sofort verwendet werden können. Die integrierten Berichte sind strukturiert verknüpft, um den Benutzer zu nacheinander kleineren und kleineren Segmenten der Anrufdaten zu führen. In den integrierten Berichten werden auch die verschiedenen Möglichkeiten zum Anzeigen der Daten hervorgehoben, indem eine Kombination aus Diagrammen und Tabellen mit unterschiedlichen Pivots, Filtern und Measures gezeigt wird. Jeder Benutzer, der auf das Portal zutritt, kann über eigene Berichte verfügen, die er ändern und freigeben kann. Weitere Informationen zur Verwendung des CQD-Webportals finden Sie unter "Verwenden des Anrufqualitätsdashboards [für Skype for Business Server".](use.md)
  
Unterstützte Betriebssysteme für das CQD-Portal: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 und Windows Server 2016 (nur Skype for Business Server 2019 CQD).
  
Unterstützte Browser für das CQD-Portal: Internet Explorer 11, Internet Explorer 10 und Internet Explorer 9.
  
### <a name="rest-apis"></a>REST-APIs

Auf die Cubedaten kann auch über REST-API-Aufrufe zugegriffen werden. Die über die REST-API-Aufrufe abgerufenen Daten können über HTML-Seiten gerendert werden. Benutzer können die Abfragegeschwindigkeit und das hohe Schema von CQD nutzen und gleichzeitig benutzerdefinierte Berichte erstellen, die für ihre Geschäftsanforderungen geeignet sind. Weitere Informationen zur API und Beispiele finden Sie unter ["Entwickeln des Anrufqualitätsdashboards für Skype for Business Server".](develop.md) 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definieren der Anforderungen Ihrer Organisation für CQD

CQD bietet die QoE-Datenarchivierung und eine schnelle und tiefgehende Analyse von Anrufqualitätsdaten. Im folgenden Leitfaden können Sie entscheiden, wann und warum Sie CQD bereitstellen möchten.
  
### <a name="when-to-deploy-cqd"></a>Bereitstellungs-CQD

 **CQD kann bereitgestellt werden, um eine grundlegende Messung der Anrufqualität zu erstellen, auch wenn in einer Organisation keine Probleme mit der Anrufqualität auftreten.** Das Einrichten einer grundlegenden Messung der Anrufqualität ist wichtig, da jede Organisation eine andere Mischung aus Wi-Fi und Verkabelten und Remotemitarbeitern im Vergleich zu Büromitarbeitern hat. Wenn Probleme mit der Anrufqualität auftreten, können die neuesten Messungen der Anrufqualität mit früheren Zeitintervallen verglichen werden. Die CQD-Trendfeatures ermöglichen die einfache Erkennung von Änderungen der Anrufqualität im Laufe der Zeit.
  
 **CQD kann bereitgestellt werden, um proaktiv Problembereiche zu finden, die sich auf die Anrufqualität auswirken können.** Selbst wenn die durchschnittliche Anrufqualität für eine Organisation möglicherweise die von der Organisation festgelegten Ziele erfüllt, kann es zu Problemen mit der Anrufqualität kommen, die hinter durchschnittlichen Metriken verborgen sind. CQD ermöglicht in der QoEMetrics-Datenbank eine aufschlüsselbare Aufschlüsselung der Anrufqualitätsmetriken nach vielen Dimensionen. Die Ausr ung in Peergruppen ist eine schnelle Möglichkeit, Probleme mit der Anrufqualität proaktiv zu ermitteln.
  
 **CQD sollte bereitgestellt werden, wenn probleme mit der Anrufqualität in der Organisation auftreten, um den Zeitaufwand für die Problembehandlung zu reduzieren.** CQD kann vorhandene Untersuchungen der Anrufqualität vereinfachen, indem es eine schnelle Berichterstellungsleistung und dynamische Drilldownfunktionen bietet. CQD ist für viele Arten von Workflows in der Überprüfung der Anrufqualität von Reparaturen an der Umgebung konzipiert.
  
### <a name="why-deploy-cqd"></a>Gründe für die Bereitstellung von CQD

 **CQD sollte bereitgestellt werden, wenn die QoE-Berichterstellung für mehr als 3 Monate an Daten möglich sein muss.** Die Berichte der Datenbank und des Monitoring Servers von QoEMetrics sind so konzipiert, dass sie eine kleine Datendatei speichern und melden. Die QoE-Metrik-Datenbank ist für schnelle Einfügungen optimiert, und daher kann die Berichterstellungsleistung durch eine große Anzahl von Aufrufen oder einen konkurrierten Berichterstellungszugriff auf die Datenbank beeinträchtigt werden. Die QoE-Archivdatenbank von CQD stellt eine zweite Kopie der QoE-Metrikdaten mit wesentlich längeren Aufbewahrungsfunktionen bereit. Das Portal ist außerdem für die gleichzeitige Anzeigen von Daten von bis zu 7 Monaten optimiert und kann nach Bedarf Berichte zu allen Daten im QoE-Archiv erstellen.
  
 **CQD sollte bereitgestellt werden, wenn benutzerdefinierte QoE-Berichte erforderlich sind.** Das Portal verfügt über ein Berichts-Editor-Feature zum schnellen und einfachen Erstellen und Erstellen von Prototypberichten. Es stellt außerdem REST-APIs für den programmgesteuerten Zugriff auf die Cubedaten zur Verfügung, sodass eine benutzerdefinierte Präsentation mithilfe von HTML/JavaScript oder vielen anderen Frameworks möglich ist. Es ist nicht mehr erforderlich, neue SQL zum Erstellen von benutzerdefinierten Datenansichten für die Berichterstellung zu erstellen.
  
 **CQD sollte bereitgestellt werden, wenn die vorhandene QoE-Berichterstellungsfunktion nicht die von der Organisation erforderliche Geschwindigkeit oder Tiefe erfüllt.** CQD enthält viele integrierte Berichte. Die Berichte sind sofort nützlich und veranschaulichen, wie schrittweises Drilling in die Daten auf jeder Ebene zusätzliche Einblicke bieten kann. Die Berichthierarchie hilft auch bei der logischen Verwaltung der zahlreichen Berichte und fördert die Erstellung von vielen weiteren Berichten, die leicht zugänglich und verständlich sind. CQD bietet nicht nur Geschwindigkeit und Flexibilität, sondern ist auch für die Workflows optimiert, die von der Call Quality Methodology entwickelt wurden.
  
## <a name="components-and-topologies-for-cqd"></a>Komponenten und Topologien für CQD

CQD umfasst mehrere Komponenten und hilft dabei, die Anforderungen der einzelnen Komponenten und ihre Beziehung zueinander zu verstehen, um die einfachste und beste Bereitstellung des Tools zu erhalten. In der folgenden Tabelle wird die abhängige Komponente für jede CQD-Komponente beschrieben.
  

|**Komponentenname**|**Abhängige Komponente**|
|:-----|:-----|
|QoE Archive  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Microsoft Information Services  <br/> |
|Repositorydienst (Teil der Portalinstallation)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Für QoE Archive und Cube erfordern bestimmte Bereitstellungsoptionen Business Intelligence- oder Enterprise-Editionen Microsoft SQL Server. Weitere Informationen finden Sie weiter unten im Abschnitt ["Infrastrukturanforderungen für CQD".](plan.md#Infrastructure_Req)
  
![CQD-Komponenten](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Einzelserverkonfiguration

Alle CQD-Komponenten und abhängigen Komponenten können auf einem Computer installiert werden. Die Einzelfeldkonfiguration ist die einfachste Konfiguration und ermöglicht die eigenständige CQD-Konfiguration. CQD benötigt nur Zugriff auf die QoE-Metrikdatenbank auf dem Monitoring Server. Der CQD Server kann ein eigenständiger Computer, ein virtueller Computer oder sogar der Monitoring Server sein, je nach den verfügbaren Ressourcen des Hostcomputers und den Leistungsanforderungen. 
  
Während der Installation muss der Benutzer, der die Installation ausgeführt hat, lediglich die Microsoft SQL Server- und Microsoft SQL Server Analysis Services-Instanzen bereitstellen, die zuvor auf dem Computer eingerichtet wurden, auf dem das CQD installiert werden soll. Weitere Informationen finden [Sie unter "Bereitstellen des Anrufqualitätsdashboards](deploy-0.md) für Skype for Business Server".
  
### <a name="multiserver-configuration"></a>Konfiguration mit mehreren Server

In einer Konfiguration mit mehreren Server können sich das QoE-Archiv, der Cube und das Portal auf unterschiedlichen Computern benennen. Es gibt zwei Hauptverwendungszwecke für die Konfiguration mit mehreren Servern:
  
- Hosten von CQD Web Portal und CQD Cube auf verschiedenen Servern.
    
- Hosten eines "Entwicklungsportals" getrennt vom "Produktionsportal". 
    
  **Hosten von CQD Web Portal und CQD Cube auf verschiedenen Computern.** Organisationen, die möglicherweise Anforderungen zum Trennen des CQD-Portals von der SQL Server-Installation haben oder die SQL Server-Editionen für die SQL Server-Instanz mischen und anpassen möchten, und SQL Server Analysis Services-Instanz können das CQD-Portal und den CQD-Cube auf verschiedenen Computern installieren. Die QoE-Archivkomponente kann auch die einzige CQD-Komponente sein, die installiert wird, wenn die Organisation einfach eine dauerhafte Methode zum Archivieren der QoE-Daten haben möchte, ohne die Leistungsgrenzen auf dem Monitoring Server zu erreichen.
  
![Single Server CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosten eines "Entwicklungsportals" getrennt vom "Produktionsportal".** Organisationen, die ihre eigenen benutzerdefinierten Berichte (über die REST-APIs) entwickeln, möchten möglicherweise neben dem Produktionsportal zusätzliche (CQD)-Portalinstanzen bereitstellen, auf die reguläre Benutzer für die Überwachung der Anrufqualität oder Untersuchungen zugreifen. Das Entwicklungsportal kann alle Änderungen am Portal von der Produktionsumgebung isolieren. Die zusätzlichen Webportale können auf verschiedenen Computern (siehe unten) oder in verschiedenen Webverzeichnissen auf demselben Computer (nicht angezeigt) bereitgestellt werden. Um letzteres zu erreichen, muss das zusätzliche CQD-Webportal manuell auf den Produktionscomputer kopiert werden, da der CQD-Setupprozess immer das CQD-Webportal auf der Standardwebsite mit vordefinierten Webanwendungsnamen bereitgestellt.
  
![Planen von CQD Multi Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Unterstützte Topologien

CQD führt keine Daten aus mehreren QoEMetrics-Datenbanken zusammen, wie dies der Fall ist, wenn mehrere Skype for Business Server-Topologien mit jeweils einem eigenen Monitoring Server vorhanden sind. Jede CQD-Instanz muss auf eine QoEMetrics-Datenbank verweisen. Da CQD jedoch einen Großteil der Berichtsarbeitsauslastung vom Monitoring Server verschiebt, sollten große Organisationen, die einen Monitoring Server pro Skype for Business Server-Topologie bereitstellen mussten, die Verwendung eines Monitoring Servers für alle Topologien in Betracht ziehen.
  
## <a name="infrastructure-requirements-for-cqd"></a>Infrastrukturanforderungen für CQD
<a name="Infrastructure_Req"> </a>

CQD, einschließlich aller Komponenten und abhängigen Komponenten, kann auf einem virtuellen Computer, einem einzelnen Computer oder auf mehreren Computern bereitgestellt werden. Die mindesten Software- und Hardwareanforderungen sind unten aufgeführt. Datenverfügbarkeit und Abfrageleistung können je nach Anzahl der aktiven Skype for Business Server-Benutzer sowie Hardware und Konfiguration zwischen Minuten und Stunden variieren, sodass unten einige Leistungsmessungen durchgeführt werden.
  
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
   
CQD nutzt Microsoft SQL Server, Microsoft SQL Server Analysis Services und Microsoft-Internetinformationsdienste, sodass die Mindesthardware- und Softwareanforderungen von CQD im Wesentlichen mit diesen abhängigen Komponenten identisch sind. Basierend auf den Anforderungen der Organisation im Rahmen der Datenerfrischung (die zum Teil vom Volumen der von der Organisation generierten QoE-Daten abhängen) und den Bereitstellungskosten sollten jedoch zusätzliche Bereitstellungsüberlegungen berücksichtigt werden.
  
Die Datenverarbeitung in CQD ist in zwei Hauptphasen unterteilt: 
  
- Prozess der QoE-Archivierung
    
- Verarbeitung von CQD-Cubes
    
  **QoE-Archivverarbeitung.** Die Verarbeitung der QoE-Archiv-Aufgabe kopiert Daten aus der QoE-Metrikdatenbank auf dem Monitoring Server in die QoE-Archivdatenbank. Es gibt zwei Situationen, in denen die Verarbeitungszeit der Aufgabe grundlegend unterschiedliche Leistungsmerkmale aufweisen würde. Die erste ist nach der Erstinstallation von CQD. Wenn die Aufgabe nach einer Neuinstallation zum ersten Mal ausgeführt wird, kopiert die Verarbeitungsaufgabe für das QoE-Archiv alle Daten in der QoE-Metrikdatenbank in die QoE-Archivdatenbank. Die zweite ist die periodische Verarbeitung nach dieser ersten Runde. Die Verarbeitungsaufgabe für das QoE-Archiv wird alle 15 Minuten ausgeführt und verarbeitet alle neuen QoE-Datensätze, die sich in der QoE-Metrikdatenbank befinden. Im Allgemeinen ist die anfängliche Verarbeitungszeit kein Problem, da sie nur beim ersten Mal ausgeführt wird, wenn CQD installiert wird. Wenn der CQD-Server jedoch stark unter bereitgestellt ist, kann diese Aufgabe mehrere Stunden dauern. In der folgenden Tabelle finden Sie z. B. anfängliche Verarbeitungszeiten des QoE-Archivs.
  
  **CQD Cubeverarbeitung.** Die Cubeverarbeitungsaufgabe aggregiert die Daten aus der QoE-Archivdatenbank in den Cube. Die anfängliche Cubeverarbeitungszeit und die nachfolgende Cubeverarbeitungszeit werden durch die SQL Server Analysis Services Edition bestimmt, die für den CQD Cube verwendet wird. Wenn die Standard Edition verwendet wird, besteht kein Unterschied zwischen der anfänglichen Cubeverarbeitungszeit und der nachfolgenden Cubeverarbeitungszeit, da bei jeder Aktualisierung der Cubedaten immer eine vollständige Verarbeitung aller verfügbaren Daten vor sich geht. (Dies bedeutet, dass die Cubeverarbeitungszeit mit der Zunahme der Datenmenge in der QoE-Archivdatenbank zunimmt.) Da die Business Intelligence Edition und die Enterprise Edition von SQL Server Partitionsunterstützung haben, werden bei Verwendung einer der Editionen nur bei der ersten Ausführung alle Daten in der QoE-Archivdatenbank verarbeiten. Wenn die Aufgabe in nachfolgenden Durchläufen alle 15 Minuten ausgelöst wird, werden von der Aufgabe nur die neuen Datensätze, die der QoE-Archivdatenbank seit der letzten Ausführung der Aufgabe hinzugefügt wurden, ausgeführt. Einmal am Tag wird auch eine vollständige Verarbeitung der Partition mit den Daten des aktuellen Monats erstellt.
  
Die Merkmale des physischen Computers können sich auf die Leistung des AQD sowie auf die Softwarefeatures auswirken, die in den SQL Server sind. Die QoE-Archivkomponente ist im Vergleich zu anderen Komponenten datenträgerintensiver, während die Cubekomponente cpu- und arbeitsspeicherintensiver ist. Alle diese Faktoren tragen zur Gesamtdatenverarbeitungszeit des CQD bei, was sich direkt auf die Datenerfrischung und -verfügbarkeit auswirkt. Organisationen sollten basierend auf den individuellen Anforderungen der Organisation Entscheidungen zu Hardware und Software treffen. 
  
### <a name="tested-hardware-configurations"></a>Getestete Hardwarekonfigurationen

In diesem Abschnitt wird davon ausgegangen, dass es eine einzelne QoEMetrics-DB in der Umgebung gibt. 
  
**Computerprofile**

|**Maschine**|**CPU Cores**|**RAM**|**QoE Archive and Cube on same disk**|**QoE Archive and SQL Temp DB on same disk**|
|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |4   <br/> |7 GB  <br/> |Ja  <br/> |Ja  <br/> |
|4 Kerne  <br/> |4   <br/> |20 GB  <br/> |Ja  <br/> |Nein  <br/> |
|8 Kerne  <br/> |8   <br/> |32 GB   <br/> |Ja  <br/> |Nein  <br/> |
|16 Kerne  <br/> |16   <br/> |128 GB  <br/> |Nein  <br/> |Nein  <br/> |
   
**Leistungsergebnisse**

|**Maschine**|**QoE-Metrik-DB-Größe**|**SQL Partitionen**|**Datenträgertyp**|**Anzahl der Datenströme**|**Anfänglicher Archivierungsprozess**|**Anfänglicher Cubeprozess**|**Nachfolgender Archivprozess**|**Nachfolgender Cubeprozess**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |900 MB  <br/> |Single  <br/> |VHD (variable Größe)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Single  <br/> |VHD (variable Größe)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Single  <br/> |VHD (feste Größe)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |30+ GB  <br/> |Single  <br/> |VHD (feste Größe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 Kerne  <br/> |9 GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 Kerne  <br/> |9 GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 Kerne  <br/> |30+ GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 Kerne  <br/> |30+ GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 Kerne  <br/> |200 GB  <br/> |Single  <br/> |Mehrere Datenträger  <br/> |125 M  <br/> |6+ Tage  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 Kerne  <br/> |500 GB  <br/> |Mehrere  <br/> |Mehrere Spindeln  <br/> |250 M  <br/> |8 Tage  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Es wird nicht erwartet, dass diese in echten Bereitstellungen auftreten, da die QoE-Metriken-Datenbank 9 bzw. 18 Monate Daten enthalten müsste, diese werden hier jedoch der Vollständigkeit halber bereitgestellt.
  
### <a name="service-account-requirements"></a>Dienstkontoanforderungen

Sie benötigen ein Konto (mit Lesezugriff auf QoEMetrics), das der SQL Agent auf dem CQD Server zum Importieren von Daten in die QoEArchiveDB verwenden kann.
  
Möglicherweise müssen Sie auch ein separates Konto für einen SSAS-Auftrag konfigurieren, um Daten aus QoEArchiveDB zu ziehen (dies ist ein optionaler Prozess).
  
IIS verwendet netzwerkdienst am häufigsten als App-Pool-Identität, kann jedoch für ein Dienstkonto konfiguriert werden.
  
### <a name="portal-access-control"></a>Portalzugriffssteuerung

Standardmäßig hat jeder authentifizierte Benutzer Zugriff. Dies kann mithilfe von IIS-Autorisierungsregeln geändert werden, um auf eine bestimmte Gruppe zu beschränken.
  
### <a name="pre-install-requirements"></a>Voraussetzungen vor der Installation

In diesen Anweisungen wird davon ausgegangen, dass eine QoE-Metrikdatenbank bereits installiert wurde und an einer anderen Stelle in der Skype for Business Server-Topologie ausgeführt wird.
  
#### <a name="hardware-requirements"></a>Hardwareanforderungen

CQD nutzt Microsoft SQL Server, Microsoft SQL Analysis Server und Microsoft Internet Information Server, sodass die Mindesthardware- und Softwareanforderungen von CQD im Wesentlichen mit diesen abhängigen Komponenten identisch sind. Basierend auf den Anforderungen der Organisation im Rahmen der Datenerfrischung (die zum Teil vom Volumen der von der Organisation generierten QoE-Daten abhängen) und den Bereitstellungskosten sollten jedoch zusätzliche Bereitstellungsüberlegungen berücksichtigt werden.
  
#### <a name="software-requirements"></a>Softwareanforderungen

Die folgenden Betriebssysteme sind für CQD erforderlich:
  
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
>  Beachten Sie für die oben genannten Anforderungen Folgendes: > 3.5- und 4.5-Versionen von .Net Framework sind verfügbar. Beide sind erforderlich (genauer gesagt: 3.5 SP1 ist erforderlich).> Wenn ASP.NET in einigen Systemen vor der Installation von IIS eingerichtet wird, ist ASP.NET möglicherweise nicht in IIS registriert. Das Problem manifestiert sich durch das Fehlen von Anwendungspools für die entsprechende .Net-Version und das Fehlen der .NET-CLR-Version in der App-Pool-Konfiguration. Führen Sie zum Beheben eines solchen Problems Windows Server 2008 R2 `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` aus. Führen Windows Server 2012 und Windows Server 2012 R2 aus, gefolgt vom Entfernen des Moduls "ServiceModel" aus der Standardwebsite im IIS-Manager.>-Verwaltungstools ist optional, wird jedoch  `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` empfohlen.
  
Führen Sie die folgenden Schritte aus, um diese Anforderungen mithilfe von PowerShell zu installieren:
  
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
  
Die Standard Edition wird zwar nicht empfohlen, wird aber auch unterstützt. Die Verarbeitung wird auf eine einzelne Partition beschränkt (die während des Setups konfiguriert werden muss). 
  
In allen Fällen müssen "Datenbankmoduldienste" und "Analysis Services" installiert sein. Es wird empfohlen, aber nicht erforderlich, auch das Feature "Verwaltungstools – Vollständig" zu installieren, wodurch SQL Server Management Studio Analysis Services unterstützt wird. Der Bildschirm für die Featureauswahl sollte wie die Abbildung aussehen.
  
![SQL Server von Features](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Legen Sie beim Konfigurieren des SSAS-Setups in der Analysis Services-Konfiguration "Servermodus" auf "Mehrdimensionaler und Data Mining-Modus" festgelegt. 
  
Weitere Hilfe zum Installieren und Konfigurieren SQL Server Business SQL Server Finden Sie unter [Install Analysis Services in Multidimensional and Data Mining Mode](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Kontoanforderungen

Drei Domänendienstkonten werden nach dem Prinzip der geringsten Rechte empfohlen: 
  
- Eine, die bereits über einen Anmeldesicherheitsprinzipal für die QoE-Metrikdatenbank (mit db_datareader-Berechtigungen) und einen Anmeldesicherheitsprinzipal in der Instanz des QoE-Archivs SQL Server verfügt (erforderlich zum Erstellen eines Linked Server-Objekts während des Setups). Dieses Konto wird zum Ausführen des Schritts "QoE-Archivdaten" des SQL Server Agent-Auftrags verwendet.
    
    > [!NOTE]
    > Wenn Sie in einer stark gesperrten Umgebung arbeiten, müssen Sie überprüfen, ob diesem Dienstkonto die Benutzerrechte "Anmelden als Batchauftrag" und "Lokale Anmeldung zulassen" sowohl für die QoE-Metriküberwachungsdatenbank SQL Server als auch für die QoE-Archiv-SQL Server erteilt wurden.
    
- Eine, die zum Ausführen des Schritts "Prozesscube" des SQL Server Agent-Auftrags verwendet wird. Setup erstellt einen Anmeldesicherheitsprinzipal für die QoE-Archivdatenbank (mit Lese- und Schreibberechtigungen) und erstellt außerdem ein Mitglied in der Rolle "QoE" (mit Vollzugriff) für den Cube.
    
- Eine, die zum Ausführen des IIS-Arbeitsprozesses für die Webportale und Web-APIs verwendet wird. Setup erstellt einen Anmeldesicherheitsprinzipal für die QoE-Archivdatenbank (mit Leseberechtigung), einen Anmeldesicherheitsprinzipal für die Repositorydatenbank (mit Lese- und Schreibberechtigung) und ein Mitglied in QoERole (mit Vollzugriff) für den Cube. 
    
    > [!NOTE]
    > Wenn sowohl die QoE-Archivdatenbank als auch die Repositorydatenbank in derselben SQL Server, wird nur ein Anmeldesicherheitsprinzipal mit zwei Benutzerzuordnungen erstellt. 
  
Die ersten beiden Konten können logisch als "Back-End-Dienstkonten" betrachtet werden, und das letzte Konto ist ein "Front-End-Dienstkonto". Es wird zwar nicht empfohlen, es ist jedoch in allen Fällen möglich, ein einzelnes Konto zu verwenden.
  
> [!NOTE]
> Das Benutzerkonto, mit dem die Installation initiiert wird, muss auch über Lesezugriff auf die QoE-Metrik-DB verfügen (zusätzlich zu den Computeradministratorrechten auf dem QoE-Archiv-DB-Server, auf dem die Installation stattfinden muss). 
  
## <a name="capacity-planning"></a>Kapazitätsplanung
<a name="Infrastructure_Req"> </a>

CQD ist für minimale Auswirkungen auf QoEMetrics konzipiert: Der Code wurde so optimiert, dass keine Daten gesperrt werden, und Importaufträge sind abstimmbar.
  
Welche Art von Hardware verwendet werden soll, hängt von Ihren Anforderungen ab, wie schnell Synchronisierungen ausgeführt werden sollen. Die Größe des Datenträgers lautet wie folgt:
  
- QoEArchive ist ca. 1,5x größer als QoEMetrics DB
    
- Der SSIS Cube komprimiert die Daten im Vergleich zu DB fast 10x.
    
- Daten werden monatlich partitioniert. Partitionen können gelöscht werden
    

