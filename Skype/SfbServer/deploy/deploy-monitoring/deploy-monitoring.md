---
title: Bereitstellen der Überwachung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Zusammenfassung: Informationen Sie zum Bereitstellen der Überwachung in Skype für Business Server 2015.'
ms.openlocfilehash: a25165add0ca6f9acd08e77efeda42cf7a8819ef
ms.sourcegitcommit: 4eae947e339e728e5e1f338677860b910aafc029
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="deploy-monitoring-in-skype-for-business-server-2015"></a>Bereitstellen der Überwachung in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Bereitstellen der Überwachung in Skype für Business Server 2015.
 
Überprüfen Sie vor dem Ausführen dieser Aufgaben [Planen der Überwachung in Skype für Business Server 2015](../../plan-your-deployment/monitoring.md).
 
Anhand der folgenden beiden Schritte können Sie Überwachungsdienste in Ihrer Topologie implementieren:
  
1. Aktivieren der Überwachung gleichzeitig richten Sie eine neue Skype für Business Server-Pool. (In Skype für Business Server 2015, Überwachung aktiviert oder deaktiviert ist auf Basis von Pools.) Beachten Sie, dass Sie für einen Pool ohne tatsächlich Sammeln von Überwachungsdaten, Überwachung aktivieren können, ein Prozesses im Abschnitt Konfigurieren von Call Detail Recording and Quality of Experience Settings in dieser Dokumentation beschrieben.
    
2. Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) zum neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Abhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.
    
Oft ist es zwar einfacher, die Überwachung gleichzeitig mit der Erstellung eines neuen Pools zu aktivieren, es ist jedoch auch möglich, bei deaktivierter Überwachung einen neuen Pool zu erstellen. In diesem Fall können Sie später den Topologie-Generator verwenden, um den Dienst zu aktivieren. Mithilfe des Topologie-Generators kann die Überwachung für einen Pool aktiviert bzw. deaktiviert oder ein Pool kann einem anderen Überwachungsspeicher zugeordnet werden. Beachten Sie, dass weiterhin mindestens ein Überwachungsspeicher erstellt werden muss, auch wenn keine Monitoring Server-Rolle mehr vorhanden ist: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten dienen. Diese Back-End-Datenbanken können mithilfe von Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012 oder Microsoft SQL Server 2014 erstellt werden.
  
> [!NOTE]
> Wenn die Überwachung für einen Pool aktiviert wurde können Sie den Vorgang des erfassen Überwachungsdaten ohne Ändern Ihrer Topologie deaktivieren: Skype für Business Server bietet die Möglichkeit deaktivieren (und später wieder aktivieren können) Sie Aufzeichnung von Kommunikationsdatensätzen (KDS) oder die Qualität Erfassung Experience (QoE). Weitere Informationen finden Sie in diesem Dokument im Abschnitt „Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen)“ und „QoE (Quality of Experience)-Einstellungen“. 
  
Eine andere wichtige Erweiterung für die Überwachung in Skype für Business Server 2015 die Tatsache ist, dass Skype für Business Server-Überwachungsberichte unterstützen nun eine IPv6: Berichte, verwenden das Feld IP-Adresse, zeigt entweder IPv4 oder IPv6-Adressen, je nachdem, welche: 1) die SQL-Anweisung die Abfrage verwendet wird; und 2), in dem oder nicht die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist.
  
> [!NOTE]
> Vergewissern Sie sich, dass der Starttyp des SQL Server-Agent-Diensts „Automatisch“ ist und der SQL Server-Agent-Dienst für die SQL-Instanz mit den Überwachungsdatenbanken ausgeführt wird, damit die SQL Server-Wartungsaufträge für die Standardüberwachung plangemäß unter der Kontrolle des SQL Server-Agent-Diensts ausgeführt werden können. 
  
In dieser Dokumentation führt Sie schrittweise durch die Installation und Konfiguration der Überwachung und Monitoring-Berichte für Skype für Business Server 2015. Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:
  
- Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.
    
- Installieren Sie SQL Server Reporting Services und die Skype für Business Server Überwachungsberichten. Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.
    
- Konfigurieren der Aufzeichnung von Kommunikationsdatensätzen (KDS) und der Sammlung von QoE (Quality of Experience)-Daten. Die Aufzeichnung von kommunikationsdatensätzen bietet eine Möglichkeit zum Nachverfolgen der Verwendung von Skype für Business Server-Funktionen wie Voice over IP (VoIP) Telefonanrufe. Instant messaging (Sofortnachrichten); dateiübertragungen; Audio/Video (A / V) Konferenzen; und die Anwendungsfreigabe Sitzungen. QoE-Metriken dienen zur Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei der Paketverzögerung (Jitter).
    
- Manuelles Löschen von KDS und/oder QoE-Datensätzen aus der Überwachungsdatenbank.
    
## <a name="deployment-checklist-for-monitoring"></a>Prüfliste zur Bereitstellung für die Überwachung

Obwohl monitoring ist bereits installiert und auf jedem Front-End-Server aktiviert, sind weiterhin mehrere Schritte, die Sie durchführen müssen, bevor Sie monitoring Erfassen von Daten für Skype für Business Server 2015 tatsächlich wird können. Diese Schritte werden in der nachstehenden Prüfliste aufgeführt:
  
|**Phase**|**Schritte**|**Rolle und Gruppenmitgliedschaft**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> |Installieren einer unterstützten Version von Microsoft SQL Server auf dem Computer, der als Back-End-Datenspeicher für die Überwachung fungiert.  <br/> |Domänenbenutzer, der auch Mitglied der lokalen Administratorgruppe ist.  <br/> |[Unterstützte Hardware](http://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Serversoftware and Infrastructure Support](http://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung der Überwachung** <br/> |Verwendung Skype für Business Server 2015 Topologie-Generator hinzufügen veröffentlicht Überwachungsdatenbanken zur Topologie, klicken Sie dann die aktualisierte Topologie.  <br/> |Definieren einer Topologie, ein Benutzer, der Mitglied der lokalen Benutzergruppe ist.  <br/> Veröffentlichen der Topologie, ein Benutzer, der Mitglied der Domänenadministratorgruppe und der RTCUniversalServerAdmins-Gruppe ist.  <br/> |[Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype für Business Server 2015](associate-a-monitoring-store.md) <br/> |
|**Aktivieren der entsprechenden Überwachungseinstellungen** <br/> |Aktivieren Sie die Aufzeichnung von Kommunikationsdatensätzen und/oder die QoE-Überwachung (Quality of Experience) auf globaler und/oder auf Standortebene.  <br/> |Ein Benutzer, der Mitglied der RTCUniversalServerAdmins-Gruppe ist oder dem eine RBAC-Rolle mit Zugriff auf das Cmdlet CsCdrConfiguration und auf das Cmdlet CsQoEConfiguration zugewiesen wurde.  <br/> |[Konfigurieren Sie die Aufzeichnung von kommunikationsdatensätzen und Quality of Experience Settings in Skype für Business Server 2015](call-detail-recording-and-qoe.md) <br/> |
   
## <a name="enable-monitoring"></a>Aktivieren der Überwachung

Obwohl die unified datenerfassungs-Agenten automatisch installiert und auf jedem Front-End-Server aktiviert werden, bedeutet dies nicht, dass Sie automatisch die Überwachungsdaten von dem Zeitpunkt, zu sammeln Abschluss der Installation von Skype für Business Server 2015 beginnen. Stattdessen müssen Sie zwei Schritte vornehmen: Sie müssen Ihre Front-End-Server/Front-End-Pools einer Überwachungsdatenbank zuweisen und die Überwachung der Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder von QoE (Quality of Experience) auf globaler und/oder Standortebene aktivieren.
  
Anleitung zum Zuordnen von Front-End-Server oder Front-End-Pools zu eine Überwachungsdatenbank finden Sie unter dem Thema [Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype für Business Server 2015](associate-a-monitoring-store.md) im Bereitstellungshandbuch. Nachdem diese Zuordnung vorgenommen wurden, und Ihre neue Skype für Business Server-Topologie veröffentlicht wurde, werden Sie noch nicht Überwachungsdaten sammeln können. Das liegt daran, wird standardmäßig bei der Installation von Skype für Business Server 2015 KDS und QoE-Datenerfassung deaktiviert ist.
  
Um die Datensammlung beginnen müssen Sie zum Aktivieren von KDS und/oder QoE-Überwachung. (Beachten Sie, dass Sie keine So aktivieren Sie beide KDS und QoE-Überwachung; Wenn Sie es vorziehen, können Sie eine Art der Überwachung, während die anderen Typs deaktiviert lassen). So aktivieren Sie KDS-Überwachung auf globaler Ebene das Führen Sie den folgenden Befehl aus, in der Skype für Business Server-Verwaltungsshell
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Alternativ können Sie die Überwachung von innerhalb der Skype für Business Server-Systemsteuerung KDS aktivieren. Innerhalb der Skype Business Server-Systemsteuerung, führen Sie die folgende Schritte aus:
  
1. Klicken Sie auf **Überwachung**.
    
2. Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.
    
3. Wählen Sie im Bereich **KDS-Einstellungen (Aufzeichnung von Kommunikationsdatensätzen) bearbeiten** die Option **Überwachung von KDS-Aufzeichnungen aktivieren** aus und klicken Sie auf **Commit ausführen**.
    
Um QoE-Überwachung auf globaler Ebene zu aktivieren, führen Sie folgenden Befehl in der Skype für Business Server-Verwaltungsshell aus:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Wenn Sie es vorziehen, können Sie auch die QoE-Überwachung von innerhalb der Skype Business Server-Systemsteuerung aktivieren. Führen Sie in der Systemsteuerung die folgenden Schritte aus:
  
1. Klicken Sie auf **Überwachung**.
    
2. Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.
    
3. Wählen Sie im Bereich **QoE-Einstellungen (Quality of Experience) bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus und klicken Sie dann auf **Commit ausführen**.
    
Wie bereits erwähnt, wird in den vorherigen Beispielen Überwachung auf globaler Ebene aktivieren; d. h., aktivieren sie KDS und QoE-Überwachung in der gesamten Organisation. Alternativ, Sie können erstellen separate KDS und QoE-Konfigurationseinstellungen auf Standortebene, und klicken Sie dann selektiv aktivieren oder deaktivieren monitoring für jeden Standort. Beispielsweise konnten Sie KDS-Überwachung für Ihr Standort "Redmond" noch deaktivieren KDS für Ihre Website Dublin Überwachung aktivieren. Weitere Informationen zum Verwalten der Konfigurationseinstellungen finden Sie unter Deployment Guide Thema [Configure die Aufzeichnung von kommunikationsdatensätzen und Quality of Experience Settings in Skype für Business Server 2015](call-detail-recording-and-qoe.md).
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen der Überwachung in Skype für Business Server 2015](../../plan-your-deployment/monitoring.md)