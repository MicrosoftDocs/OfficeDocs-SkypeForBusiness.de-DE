---
title: Planen des Anruf Qualitäts Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Zusammenfassung: Hier erfahren Sie, was Sie bei der Planung des Anruf Qualitäts Dashboards Bedenken sollten.'
ms.openlocfilehash: 84fa8672e561cbf91714b3d18276de401f2ab377
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274667"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planen des Anruf Qualitäts Dashboards für Skype for Business Server 
 
**Zusammenfassung:** Informieren Sie sich, was Sie bei der Planung des Anruf Qualitäts Dashboards Bedenken sollten.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Übersicht über das Dashboard für die Anrufqualität in Skype for Business Server

Das Skype for Business Server-Anruf Qualitäts Dashboard (CQD) ist eine Bericht Erstellungs Schicht über der Datenbank "Quality of Experience" auf dem Monitoring Server in Skype for Business Server. CQD verwendet Microsoft SQL Server Analysis Services, um aggregierte Verwendung und Informationen zur Anrufqualität sowie zum Filtern und pivotieren für das Dataset bereitzustellen. Zu den CQD-Features gehören:
  
- **Archivierungsspeicher von QoE-Daten über die QoE-Archivierungs Komponente von CQD.** Die QoE-Archiv Komponente kann QoE-Daten für eine wesentlich längere Dauer als der Überwachungs Server speichern. Dies ermöglicht Trend-und Berichterstellung für bis zu sieben Monate Daten zu einem Zeitpunkt, wobei die Möglichkeit besteht, das Berichtsfenster so weit zurück zu schieben, wie Daten vorhanden sind.
    
- **Berichterstellung und Analyse mithilfe der Leistungsfähigkeit und Geschwindigkeit von Microsoft SQL Server Analysis Services.** CQD verwendet Microsoft SQL Analysis Services, um schnelle Zusammenfassungs-, Filter-und Schwenkfunktionen bereitzustellen, um das Dashboard über einen Analyse Cube zu schalten. Die Berichts Ausführungsgeschwindigkeit und die Möglichkeit, einen Drilldown in die Daten durchführen, können die Analysezeiten drastisch reduzieren.
    
- **Neues Datenschema, das für die Anruf Qualitätsberichterstattung optimiert wurde.** Der Cube verfügt über ein Schema, das für Berichte und Untersuchungen zur Sprachqualität entwickelt wurde. Portal Benutzer können sich auf die Berichterstattungsaufgaben konzentrieren, anstatt herauszufinden, wie das Datenbankschema der QoE-Metrik den Ansichten zugeordnet ist, die Sie benötigen. Die Kombination aus QoE-Archiv und Cube bietet eine Abstraktion, die die Komplexität von Berichterstellung und Analyse mithilfe von CQD verringert. Das QoE-Archivdaten Bank Schema enthält auch Tabellen, die mit bereitstellungsspezifischen Daten aufgefüllt werden können, um den Gesamtwert der Daten zu verbessern.
    
- **Integrierter Berichts-Designer und die direkte Berichts Bearbeitung.** Die Portal-Komponente enthält verschiedene integrierte Berichte, die nach der Methode der Anrufqualität modelliert wurden. Portalbenutzer können mithilfe der Bearbeitungsfunktion des Portals die Berichte ändern und neue Berichte erstellen.
    
- **Web-API-Zugriff auf die Berichtsstruktur und die Analysis-Cubedaten.** Das Dashboard-Berichterstattungs Framework ist nicht die einzige Möglichkeit, die Daten aus dem Cube anzuzeigen. CQD bietet einige Beispiele für die Verwendung von HTML und JavaScript zum Abrufen von Daten aus den CQD-webapis und zum Rendern der Daten in einem benutzerdefinierten Format. Die Kombination aus dem Berichts-Editor und den CQD Web-APIs ermöglicht ein schnelles Prototyping von Berichten und ein benutzerdefiniertes Berichtslayout.
    
## <a name="cqd-design-goals"></a>CQD-Entwurfsziele

Mit CQD können IT-Profis Daten aggregieren, um die Bereiche in ihrer Umgebung zu ermitteln, in denen die Medienqualität beeinträchtigt ist. CQD ermöglicht den Vergleich von Statistiken für verschiedene Benutzergruppen und die Ermittlung von Trends und Mustern. Dabei liegt der Schwerpunkt nicht auf der Lösung individueller Probleme mit Anrufen, sondern auf der Erkennung von Problemen und Lösungen, die auf viele Benutzer in einer bestimmten Umgebung anwendbar sind. 
  
## <a name="call-quality-dashboard-components"></a>Dashboard-Komponenten für Anrufqualität

Das Dashboard für die Anrufqualität besteht aus mehreren Datenbanken, Microsoft SQL Agent-Aufträgen,-Prozessen und-Webanwendungen. Die Microsoft SQL Agent-Aufträge Kopieren in regelmäßigen Abständen Daten aus der Datenbank QoE-Metriken in die QoE-Archivdatenbank und verarbeiten den Cube mit den Daten in der QoE-Archivdatenbank. In der Repository-Datenbank werden die Berichtsdefinitionen gespeichert, die das Portal bereit stehen. Das Portal bietet Browser Zugriff auf die Cubedaten. 
  
Die CQD-Komponenten, einschließlich der QoE-Archiv-, Cube-und Repository-Datenbanken, können auf dem Überwachungsserver installiert, auf einem eigenen Server installiert oder auf mehreren Servern installiert werden. Die jeweilige Installationsmethode hängt von den Leistungsanforderungen von CQD sowie von Auswirkungen auf andere Prozesse auf denselben Servern ab. Weitere Informationen finden Sie im Abschnitt "Komponenten und Topologien für CQD" weiter unten in diesem Artikel.
  
### <a name="architectural-overview"></a>Übersicht über die Architektur

Zum Zusammenfassen erfordert CQD die folgenden Elemente:
  
- Zwei Datenbanken: eine Archivdatenbank und eine Repository-Datenbank.
    
- Ein SSAS-Cube, der aggregierte Daten visualisiert 
    
- IIS-Hosts-CQD-Webportal
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Die gleiche CQD-Architektur unterstützt lync Server 2013 und Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD und Skype for Business vs. lync 2013

 In einer Skype for Business-Umgebung stehen die folgenden Funktionen zur Verfügung:
  
- Wi-Fi-Berichterstattung über die Signal Stärke
    
- Wi-Fi-Berichterstellung für Chipsatztreiber
    
- Meine Anrufdaten veranschlagen 
    
## <a name="information-available-through-cqd"></a>Informationen, die über CQD verfügbar sind

CQD kann Skype for Business Server-Audio-, Video-und Anwendungsfreigabe-Datenstrom Zählungen und die Anzahl der guten und schlechten Anrufe sowie Verhältnisse von schlechten bis guten anrufen darstellen. Die Ansichten können in verschiedenen Dimensionen segmentiert und gefiltert werden. CQD zeichnet Daten aus der QoE Metrics-Datenbank auf dem Monitoring Server. Die Daten werden dann mit beliebigen vom Kunden bereitgestellten Daten zusammengeführt, wie beispielsweise das Netzwerk-Subnetz-zu-Gebäude-Mapping, damit Berichte wie "Anrufqualität pro Gebäude" möglich sind. 
  
CQD abstrahiert auch viele der internen QoE-Daten Eigenheiten wie "Aufrufer" und "aufgerufener", sodass der Benutzer sich auf das Erstellen von Berichtsansichten rund um "Server" und "Client" konzentrieren kann. Nach der Methode für die Anrufqualität wird CQD optimiert, um die Bedingungen zu ermitteln, die von schlechten anrufen gemeinsam sind – eines der Grundsätze für die Verbesserung der Anrufqualität.
  
## <a name="viewing-data-in-cqd"></a>Anzeigen von Daten in CQD

Die CQD-Daten können über das CQD-Portal angezeigt und über Ruhe-API-Aufrufe aufgerufen werden.
  
### <a name="cqd-portal"></a>CQD-Portal

Das Portal ist die schnellste Möglichkeit, die Daten im Cube anzuzeigen. Das Portal enthält mehrere integrierte Berichte, die sofort nutzbar sind. Die integrierten Berichte sind in strukturierter Weise verknüpft, um den Benutzer zu sukzessiven kleineren und kleineren Segmenten der Anrufdaten zu führen. Die integrierten Berichte betonen auch die unterschiedlichen Möglichkeiten, wie die Daten angezeigt werden können, indem Sie eine Kombination aus Diagrammen und Tabellen mit unterschiedlichen Pivots, Filtern und Measures demonstrieren. Jeder Benutzer, der auf das Portal zugreift, kann seinen eigenen Satz von Berichten haben, die er ändern und freigeben kann. Weitere Informationen zur Verwendung des CQD-Webportal finden Sie unter Verwenden des [Anruf Qualitäts Dashboards für Skype for Business Server](use.md).
  
Unterstützte Betriebssysteme für CQD-Portal: Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 und Windows Server 2016 (nur Skype for Business Server 2019 CQD).
  
Unterstützte Browser für das CQD-Portal: Internet Explorer 11, Internet Explorer 10 und Internet Explorer 9.
  
### <a name="rest-apis"></a>Restliche APIs

Auf die Cubedaten kann auch über Ruhe-API-Aufrufe zugegriffen werden. Die über die übrigen API-Aufrufe abgerufenen Daten können über HTML-Seiten gerendert werden. Benutzer können die Abfragegeschwindigkeit und das hochstufige Schema von CQD nutzen, während Sie weiterhin benutzerdefinierte Berichte erstellen, die für Ihre geschäftlichen Anforderungen geeignet sind. Weitere Informationen zu API und Beispielen finden Sie unter [entwickeln des Anruf Qualitäts Dashboards für Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definieren der Anforderungen Ihrer Organisation für CQD

CQD bietet QoE-Datenarchivierung und schnelle und Tiefe Analyse von Daten zur Anrufqualität. Das folgende Handbuch hilft Ihnen, zu entscheiden, wann und warum Sie CQD bereitstellen möchten.
  
### <a name="when-to-deploy-cqd"></a>Zeitpunkt der Bereitstellung von CQD

 **CQD kann bereitgestellt werden, um eine Baseline-Anruf Qualitätsmessung einzurichten, auch wenn eine Organisation keine Probleme mit der Anrufqualität hat.** Das Einrichten einer Baseline-Anruf Qualitätsmessung ist wichtig, da jede Organisation über eine andere Kombination von WLAN-Verbindung im Vergleich zu drahtgebundenen und Remote-oder Office-Mitarbeitern verfügt. Wenn Probleme mit der Anrufqualität auftreten, können die letzten Anruf Qualitätsmessungen mit früheren Zeitintervallen verglichen werden. Die CQD-Trendfunktionen ermöglichen eine einfache Erkennung von Änderungen der Anrufqualität im Laufe der Zeit.
  
 **CQD kann bereitgestellt werden, um Problembereiche proaktiv zu finden, die sich auf die Anrufqualität auswirken können.** Auch wenn die durchschnittliche Anrufqualität für eine Organisation die von der Organisation festgelegten Ziele erfüllen kann, gibt es möglicherweise Probleme mit der Anrufqualität, die hinter den durchschnittlichen Metriken verborgen sind. CQD ermöglicht eine Pivot-tabellenähnliche Aufschlüsselung von Anruf Qualitäts Metriken in vielen Dimensionen in der Datenbank QoEMetrics werden-Datenbank. Das Auffinden von Ausreißer in Peergruppen ist eine schnelle Methode, um Probleme mit der Anrufqualität proaktiv zu finden.
  
 **CQD sollte bereitgestellt werden, wenn Probleme mit der Anrufqualität in der Organisation auftreten, um die für die Problembehandlung erforderliche Zeit zu verringern.** CQD können vorhandene Anruf Qualitäts Ermittlungen vereinfachen, indem Sie eine schnelle Berichterstellungsleistung und dynamische Drilldownfunktionen anbieten. CQD ist für viele Arten von Workflows in der Anruf Qualitätsprüfung für die Validierung von Reparaturen an der Umgebung konzipiert.
  
### <a name="why-deploy-cqd"></a>Gründe für die Bereitstellung von CQD

 **CQD sollte bereitgestellt werden, wenn die QoE-Berichterstellung für mehr als 3 Monate Daten erfolgen muss.** Die Datenbank QoEMetrics werden-Datenbank-und Monitoring Server-Berichte sind so konzipiert, dass Sie eine kleine Gruppe von Daten beibehalten und melden. Die Datenbank für QoE-Metriken ist für schnelle Einfügungen optimiert, und daher kann die Berichtsleistung durch eine große Anzahl von anrufen oder einen konkurrierenden Berichtzugriff auf die Datenbank behindert werden. Die QoE-Archivdatenbank von CQD stellt eine zweite Kopie der QoE-Metrikdaten mit wesentlich längeren Aufbewahrungsfunktionen bereit. Das Portal ist auch optimiert, um bis zu 7 Monate Daten zu einem Zeitpunkt anzuzeigen, und kann bei Bedarf über alle Daten im QoE-Archiv Berichten.
  
 **CQD sollte bereitgestellt werden, wenn benutzerdefinierte QoE-Berichte benötigt werden.** Das Portal verfügt über ein Berichts-Editor-Feature zum schnellen und einfachen Erstellen und Prototypen von Berichten. Darüber hinaus werden die restlichen APIs für den programmgesteuerten Zugriff auf die Cubedaten bereitgestellt, wodurch eine benutzerdefinierte Präsentation mithilfe von HTML/JavaScript oder vielen anderen Frameworks möglich wird. Es ist nicht mehr erforderlich, neue SQL-Abfragen zu erstellen, um benutzerdefinierte Datenansichten für Berichte zu erstellen.
  
 **CQD sollte bereitgestellt werden, wenn die vorhandene QoE-Berichtsfunktion nicht die von der Organisation benötigte Geschwindigkeit oder tiefe erfüllt.** CQD enthält viele integrierte Berichte. Die Berichte sind sofort hilfreich und demonstrieren, wie schrittweise durchbohren in die Daten zusätzliche Einblicke auf jeder Ebene möglich sind. Die Berichtshierarchie hilft auch beim Verwalten der zahlreichen Berichte auf eine logische Art und Weise und unterstützt die Erstellung vieler weiterer Berichte, die leicht zugänglich und verständlich sind. CQD bietet nicht nur Schnelligkeit und Flexibilität, sondern ist auch für die Workflows optimiert, die von der Methode zur Anrufqualität entwickelt wurden.
  
## <a name="components-and-topologies-for-cqd"></a>Komponenten und Topologien für CQD

CQD enthält mehrere Komponenten, und es hilft, die Anforderungen jeder Komponente und ihre Beziehung zueinander zu verstehen, um die einfachste und bestmögliche Bereitstellung des Tools zu erhalten. In der folgenden Tabelle wird die abhängige Komponente für die einzelnen CQD-Komponenten beschrieben.
  

|**Komponentenname**|**Abhängige Komponente**|
|:-----|:-----|
|QoE-Archiv  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Microsoft-Informationsdienste  <br/> |
|Repository-Dienst (Teil der Portal Installation)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Für QoE-Archive und Cubes erfordern bestimmte Bereitstellungsoptionen Business Intelligence-oder Enterprise-Editionen von Microsoft SQL Server. Weitere Informationen finden Sie im Abschnitt [Infrastrukturanforderungen für CQD](plan.md#Infrastructure_Req) .
  
![CQD-Komponenten](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Konfiguration eines einzelnen Servers

Alle CQD-Komponenten und abhängigen Komponenten können auf einem Computer installiert werden. Die Konfiguration mit einem einzelnen Feld ist die einfachste Konfiguration und ermöglicht es, dass CQD in sich geschlossen ist. CQD bräuchte einfach nur Zugriff auf die QoE Metrics-Datenbank auf dem Monitoring Server. Der CQD-Server kann ein eigenständiger Computer, ein virtueller Computer oder sogar der Überwachungsserver sein, abhängig von den verfügbaren Ressourcen des Hostcomputers und den Leistungsanforderungen. 
  
Während der Installation muss der Benutzer, der die Installation ausführt, einfach die Microsoft SQL Server-und Microsoft SQL Server Analysis Services-Instanzen bereitstellen, die zuvor auf dem Computer eingerichtet wurden, auf dem die CQD installiert werden soll. Weitere Informationen finden Sie unter [Bereitstellen eines Anruf Qualitäts Dashboards für Skype for Business Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>MultiServer-Konfiguration

In einer MultiServer-Konfiguration können das QoE-Archiv, der Cube und das Portal alle auf unterschiedlichen Computern sein. Es gibt zwei Haupt Verwendungsmöglichkeiten für die MultiServer-Konfiguration:
  
- Hosten von CQD Web Portal und CQD Cube auf verschiedenen Servern.
    
- Hosten eines Portals für "Entwicklung", das vom Portal "Produktion" getrennt ist. 
    
  **Hosten des CQD-Webportals und des CQD-Cubes auf unterschiedlichen Computern** Organisationen, die möglicherweise Anforderungen zum Trennen des CQD-Portals von der SQL Server-Installation haben oder die SQL Server-Editionen für die SQL Server-Instanz und die SQL Server Analysis Services-Instanz kombinieren oder vergleichen möchten, können das CQD-Portal installieren und CQD-Cube auf unterschiedlichen Computern Die QoE-Archivierungs Komponente kann auch die einzige CQD-Komponente sein, die installiert wird, wenn die Organisation einfach eine nachhaltige Methode zum Archivieren der QoE-Daten haben möchte, ohne auf dem Überwachungs Server Leistungsgrenzwerte zu erreichen.
  
![CQD für einzelnen Server](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosten eines Portals für "Entwicklung", das vom Portal "Produktion" getrennt ist.** Organisationen, die eigene benutzerdefinierte Berichte (über die übrigen APIs) entwickeln, möchten möglicherweise zusätzliche (CQD)-Portal Instanzen neben dem Produktionsportal bereitstellen, auf das reguläre Benutzer für die Anruf Qualitätsüberwachung oder-Untersuchungen zugreifen. Das Entwicklungsportal kann alle Änderungen am Portal von der Produktionsumgebung isolieren. Die zusätzlichen Web-Portale können auf unterschiedlichen Computern (siehe unten) bereitgestellt oder in verschiedenen Webverzeichnissen auf demselben Computer bereitgestellt werden (nicht dargestellt). Um letztere zu erreichen, muss das zusätzliche CQD-Webportal manuell auf den Produktionscomputer kopiert werden, da der CQD-Setupprozess das CQD-Webportal immer auf der Standardwebsite mit vordefinierten Webanwendungsnamen bereitstellt.
  
![Planen des CQD-Multiservers](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Unterstützte Topologien

CQD führt keine Daten aus mehreren Datenbank QoEMetrics werden-Datenbanken zusammen, wie es der Fall ist, wenn mehrere Skype for Business Server-Topologien vorhanden sind, die jeweils einen eigenen Überwachungs Server aufweisen. Jede CQD-Instanz muss auf eine Datenbank QoEMetrics werden-Datenbank verweisen. Da CQD jedoch einen Großteil der Berichts Arbeitsauslastung auf dem Überwachungsserver verlagert, sollten große Organisationen, die für die Bereitstellungeines Überwachungsservers pro Skype for Business Server-Topologie erforderlich sind, einen Überwachungsserver für alle Topologien verwenden.
  
## <a name="infrastructure-requirements-for-cqd"></a>Infrastrukturanforderungen für CQD
<a name="Infrastructure_Req"> </a>

CQD, einschließlich aller Komponenten und abhängigen Komponenten, kann auf einem virtuellen Computer, einem einzelnen Computer oder auf mehreren Computern bereitgestellt werden. Die Mindestanforderungen an Software und Hardware sind nachfolgend aufgeführt. Die Datenverfügbarkeit und die Abfrageleistung können je nach Anzahl der aktiven Skype for Business Server-Benutzer und-Hardware und-Konfiguration von Minuten bis Stunden variieren, sodass nachfolgend einige Leistungsmaße angegeben werden.
  
|||
|:-----|:-----|
|Unterstützte Betriebssysteme  <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|Unterstützte SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |
   
CQD nutzt Microsoft SQL Server, Microsoft SQL Server Analysis Services und Microsoft Internet Information Services, damit die Mindestanforderungen an Hardware und Software von CQD im Grunde dieselben sind wie diese abhängigen Komponenten. Basierend auf den Anforderungen der Organisation bezüglich der Datenaktualität (die zum Teil vom Umfang der von der Organisation generierten QoE-Daten abhängen wird) und den Bereitstellungskosten sollten jedoch weitere Überlegungen zur Bereitstellung getroffen werden.
  
Die Datenverarbeitung in CQD ist in zwei Hauptphasen aufgeteilt: 
  
- QoE-Archivierungsprozess
    
- CQD-Cube-Verarbeitung
    
  **QoE-Archivverarbeitung.** Der QoE-Archiv Verarbeitungstask kopiert Daten aus der QoE-metrikdatenbank auf dem Überwachungs Server in die QoE-Archivdatenbank. Es gibt zwei Situationen, in denen die Verarbeitungszeit der Aufgabe grundlegend unterschiedliche Leistungsmerkmale aufweist. Die erste ist nach der ersten Installation von CQD. Wenn die Aufgabe zum ersten Mal nach einer Neuinstallation ausgeführt wird, kopiert der QoE-Archivierungs Verarbeitungstask alle Daten, die sich in der QoE-metrikdatenbank befinden, in die QoE-Archivdatenbank. Die zweite ist die periodische Verarbeitung nach dieser anfangs Runde. Der QoE-Archivierungs Verarbeitungstask wird alle 15 Minuten ausgeführt und verarbeitet alle neuen QoE-Datensätze, die sich in der QoE Metrics-Datenbank befinden. Im Allgemeinen ist die anfängliche Verarbeitungszeit kein Problem, da Sie nur zum ersten Mal ausgeführt wird, wenn CQD installiert ist. Wenn der CQD-Server jedoch stark unter bereitgestellt ist, kann diese Aufgabe mehrere Stunden dauern. In der folgenden Tabelle finden Sie beispielsweise die anfänglichen Verarbeitungszeiten für QoE-Archive.
  
  **CQD-Cube-Verarbeitung.** Der Cube-Verarbeitungstask aggregiert die Daten aus der QoE-Archivdatenbank in den Cube. Die anfängliche Cube-Verarbeitungszeit und die nachfolgende Cube-Verarbeitungszeit werden von der für den CQD-Cube verwendeten SQL Server Analysis Services-Edition bestimmt. Wenn die Standard Edition verwendet wird, gibt es keinen Unterschied zwischen der anfänglichen Cube-Verarbeitungszeit und der nachfolgenden Cube-Verarbeitungszeit, da jedes Mal, wenn die Cubedaten aktualisiert werden, immer alle verfügbaren Daten vollständig verarbeitet werden. (Dies bedeutet, dass sich die Verarbeitungszeit des Cubes erhöht, wenn die Datenmenge in der QoE-Archivdatenbank zunimmt.) Da die Business Intelligence Edition und Enterprise Edition von SQL Server über Partitions Unterstützung verfügen, wird bei Verwendung einer der beiden Editionen nur der anfängliche Durchlauf alle Daten in der QoE-Archivdatenbank verarbeiten. Bei nachfolgenden Läufen wird die Aufgabe, wenn die Aufgabe alle 15 Minuten ausgelöst wird, nur die neuen Datensätze verarbeiten, die seit der letzten Ausführung der Aufgabe der QoE-Archivdatenbank hinzugefügt wurden. Einmal täglich wird die Partition, die die Daten des aktuellen Monats enthält, vollständig verarbeitet.
  
Die Eigenschaften des physikalischen Computers können die CQD-Leistung sowie die Software Features beeinflussen, die über die SQL Server-Komponenten zur Verfügung stehen. Die QoE-Archivierungs Komponente ist im Vergleich zu anderen Komponenten stärker Festplatten intensiv, während die Cube-Komponente mehr CPU-und arbeitsspeicherintensiv sein wird. Alle diese Faktoren tragen zur Gesamt Datenverarbeitungs Zeit von CQD bei, was sich direkt auf die Aktualität und Verfügbarkeit von Daten auswirkt. Organisationen sollten auf der Grundlage der individuellen Anforderungen der Organisation Entscheidungen über Hardware und Software treffen. 
  
### <a name="tested-hardware-configurations"></a>Getestete Hardware Konfigurationen

In diesem Abschnitt wird davon ausgegangen, dass es in der Umgebung eine einzelne Datenbank QoEMetrics werden-DB gibt. 
  
**Computerprofile**

|**Maschine**|**CPU-Kerne**|**RAM**|**QoE-Archiv und Cube auf demselben Datenträger**|**QoE-Archiv und SQL Temp DB auf demselben Datenträger**|
|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |4  <br/> |7 GB  <br/> |Ja   <br/> |Ja  <br/> |
|4 Kern  <br/> |4  <br/> |20 GB  <br/> |Ja  <br/> |Nein  <br/> |
|8 Kern  <br/> |8  <br/> |32 GB  <br/> |Ja  <br/> |Nein  <br/> |
|16 Kern  <br/> |16  <br/> |128 GB  <br/> |Nein  <br/> |Nein  <br/> |
   
**Leistungsergebnisse**

|**Maschine**|**QoE-Metriken DB-Größe**|**SQL-Partitionen**|**Datenträgertyp**|**Anzahl der Datenströme**|**Anfänglicher Archivierungsvorgang**|**Initialer cubeprozess**|**Späterer Archivierungsvorgang**|**Weiterer cubeprozess**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Virtueller Computer  <br/> |900 MB  <br/> |Einzel  <br/> |VHD (Variable Größe)  <br/> |5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Einzel  <br/> |VHD (Variable Größe)  <br/> |5 M  <br/> |4 Std.  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |9 GB  <br/> |Einzel  <br/> |VHD (feste Größe)  <br/> |5 M  <br/> |2 Std.  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Virtueller Computer  <br/> |30 + GB  <br/> |Einzel  <br/> |VHD (feste Größe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 Kern  <br/> |9 GB  <br/> |Einzel  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 Std.  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 Kern  <br/> |9 GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |5 M  <br/> |2 Std.  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 Kern  <br/> |30 + GB  <br/> |Einzel  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 Std.  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 Kern  <br/> |30 + GB  <br/> |Mehrere  <br/> |Mehrere Datenträger  <br/> |20 M  <br/> |9 Std.  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 Kern  <br/> |200 GB  <br/> |Einzel  <br/> |Mehrere Datenträger  <br/> |125 M  <br/> |6 + Tage  <br/> |7 h  <br/> |2 m  <br/> |6 Std.  <br/> |
|16 Kern  <br/> |500 GB  <br/> |Mehrere  <br/> |Mehrere Spindeln  <br/> |250 M  <br/> |8 Tage  <br/> |2 Std.  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Es wird davon ausgegangen, dass diese nicht in realen Bereitstellungen auftreten, da die Datenbank für QoE-Metriken mindestens 9 und 18 Monate Daten aufweisen muss, die aber hier zur Verfügung stehen.
  
### <a name="service-account-requirements"></a>Dienstkontoanforderungen

Sie benötigen ein Konto (mit Lesezugriff auf Datenbank QoEMetrics werden), das der SQL-Agent auf dem CQD-Server zum Importieren von Daten in die QoEArchiveDB verwenden kann.
  
Möglicherweise müssen Sie auch ein separates Konto für einen SSAS-Auftrag konfigurieren, um Daten aus QoEArchiveDB zu ziehen (Dies ist ein optionaler Prozess).
  
IIS verwendet am häufigsten Netzwerkdienst als App-Pool Identität, kann aber für ein Dienstkonto konfiguriert werden.
  
### <a name="portal-access-control"></a>Portal-Zugriffssteuerung

Standardmäßig hat jeder authentifizierte Benutzer Zugriff. Dies kann geändert werden, indem IIS-Autorisierungsregeln verwendet werden, um auf eine bestimmte Gruppe zu beschränken.
  
### <a name="pre-install-requirements"></a>Voraussetzungen für die Installation

Bei diesen Anweisungen wird davon ausgegangen, dass eine QoE Metrics-Datenbank bereits installiert ist und irgendwo in der Skype for Business Server-Topologie ausgeführt wird.
  
#### <a name="hardware-requirements"></a>Hardware Anforderungen

CQD nutzt Microsoft SQL Server, Microsoft SQL Analysis Server und Microsoft Internet Information Server, damit die Mindestanforderungen an Hardware und Software von CQD im Grunde dieselben sind wie diese abhängigen Komponenten. Basierend auf den Anforderungen der Organisation bezüglich der Datenaktualität (die zum Teil vom Umfang der von der Organisation generierten QoE-Daten abhängen wird) und den Bereitstellungskosten sollten jedoch weitere Überlegungen zur Bereitstellung getroffen werden.
  
#### <a name="software-requirements"></a>Software Anforderungen

Die folgenden Betriebssysteme sind für CQD erforderlich:
  
- Windows Server 2008 R2 mit IIS 7,5
    
- Windows Server 2012 mit IIS 8,0
    
- Windows Server 2012 R2 mit IIS 8,5

- Windows Server 2016 mit IIS 10,0 (nur Skype for Business Server 2019 CQD)
    
Im folgenden finden Sie die erforderlichen IIS-Rollendienste (in hierarchischer Reihenfolge):
  
- Web Server
    
  - Allgemeine HTTP-Funktionen
    
  - Statischer Inhalt
    
  - Standarddokument
    
  - Anwendungsentwicklung
    
  - ASP.net
    
  - ISAPI-Filter
    
  - Integritäts &amp; Diagnose
    
  - HTTP-Protokollierung
    
  - Sicherheit
    
  - URL-Autorisierung
    
  - Windows-Authentifizierung
    
  - Verwaltungstools
    
  - IIS-Verwaltungskonsole
    
> [!NOTE]
>  Beachten Sie die folgenden Punkte für die oben genannten Anforderungen: > 3,5-und 4,5-Versionen von .NET Framework stehen zur Verfügung. Beide sind erforderlich (genauer gesagt, 3,5 SP1 erforderlich). > in einigen Systemen, wenn ASP.net vor der IIS-Installation eingerichtet ist, ist ASP.net möglicherweise nicht in IIS registriert. Das Problem manifestiert sich dadurch, dass für die entsprechende .NET-Version keine Anwendungspools vorhanden sind und auch die .NET CLR-Version in der APP-Pool-Konfiguration fehlt. Wenn Sie ein solches Problem unter Windows Server 2008 R2 beheben `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`möchten, führen Sie. Unter Windows Server 2012 und Windows Server 2012 R2 wird Execute `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` befolgt, indem das ServiceModel-Modul von der Standardwebsite in IIS-Manager entfernt wird. >-Verwaltungstools sind optional, werden jedoch empfohlen.
  
Führen Sie die folgenden Schritte aus, um diese Anforderungen mithilfe von PowerShell zu installieren:
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Die folgenden Versionen von SQL Server werden unterstützt:
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017
    
Business Intelligence oder Enterprise Edition wird aus Leistungsgründen empfohlen. Diese Editionen ermöglichen die Verwendung mehrerer Partitionsdateien, die parallel verarbeitet werden können, was für die Verarbeitung von Daten, die mehrere Monate oder länger dauern, vorteilhaft ist. 
  
Obwohl die Standard Edition nicht empfohlen wird, wird Sie ebenfalls unterstützt. Die Verarbeitung wird auf eine einzelne Partition beschränkt (die während des Setups konfiguriert werden muss). 
  
In allen Fällen müssen "Datenbankmoduldienste" und "Analysis Services" installiert sein. Es wird empfohlen, aber es ist nicht erforderlich, auch die Funktion "Verwaltungs Tools-abgeschlossen" zu installieren, die SQL Server Management Studio-Unterstützung für Analysis Services hinzufügt. Der Funktionsauswahl Bildschirm sollte wie die Abbildung aussehen.
  
![Anforderungen an SQL Server-Funktionen](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Bei der Konfiguration des SSAS-Setups setzen Sie in der Analysis Services-Konfiguration "Server Modus" auf "multidimensionaler und Data Mining-Modus". 
  
Weitere Hilfe zum Installieren und Konfigurieren von SQL Server Business Intelligence-Features finden Sie unter [Installieren von Analysis Services im multidimensionalen und Data Mining-Modus](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Kontoanforderungen

Für das Prinzip der geringsten Rechte werden drei Domänendienstkonten empfohlen: 
  
- Eine Person, die bereits über einen Anmelde Sicherheitsprinzipal für QoE Metrics-Datenbank (mit db_datareader-Berechtigung) und einen Anmelde Sicherheitsprinzipal in der QoE-Archiv-SQL Server-Instanz verfügt (zum Erstellen eines verknüpften Server Objekts während des Setups erforderlich). Dieses Konto wird zum Ausführen des Schritts "QoE-Archivdaten" des SQL Server-Agent-Auftrags verwendet.
    
- Eine, die zum Ausführen des Schritts "Prozess Cube" des SQL Server-Agent-Auftrags verwendet wird. Mit dem Setup wird ein Anmelde Sicherheitsprinzipal für die QoE-Archivdatenbank (mit Lese-und Schreibberechtigungen) erstellt und außerdem ein Mitglied in der QoE-Rolle (mit Vollzugriff) für den Cube erstellt.
    
- Eine, die zum Ausführen des IIS-Arbeitsprozesses für die Webportale und Web-APIs verwendet wird. Mit dem Setup wird ein Anmelde Sicherheitsprinzipal für die QoE-Archivdatenbank (mit Leseberechtigung), ein Anmelde Sicherheitsprinzipal für die Repository-Datenbank (mit Lese-und Schreibberechtigungen) und ein Mitglied in QoERole (mit Berechtigung "Vollzugriff") für den Cube erstellt. 
    
    > [!NOTE]
    > Wenn sowohl die QoE-Archivdatenbank als auch die Repository-Datenbank auf demselben SQL Server gehostet werden, wird nur ein Anmelde Sicherheitsprinzipal mit zwei Benutzerzuordnungen erstellt. 
  
Die ersten beiden Konten können logisch als "Back-End-Dienstkonten" betrachtet werden, und das letzte Konto ist ein "Front-End-Dienstkonto". Obwohl dies nicht empfohlen wird, ist es möglich, in allen Fällen ein einzelnes Konto zu verwenden.
  
> [!NOTE]
> Das Benutzerkonto, das die Installation initiiert, muss auch über Lesezugriff auf QoE Metrics DB verfügen (zusätzlich zu den Computeradministratorrechten auf dem QoE-Archiv-DB-Server, auf dem die Installation erfolgen muss). 
  
## <a name="capacity-planning"></a>Kapazitätsplanung
<a name="Infrastructure_Req"> </a>

CQD ist für minimale Auswirkungen auf Datenbank QoEMetrics werden konzipiert: der Code wurde optimiert, um keine Daten zu sperren, und Importaufträge sind einstellbar.
  
Die Art der zu verwendenden Hardware hängt von Ihren Anforderungen ab, wie schnell Synchronisierungen ausgeführt werden sollen. Die Datenträgergröße lautet wie folgt:
  
- QoEArchive ist ~ 1,5 x größer als Datenbank QoEMetrics werden DB zunächst
    
- Der SSIS-Cube komprimiert die Daten im Vergleich zu DB nahezu 10X
    
- Daten werden monatlich partitioniert; Partitionen können gelöscht werden
    

