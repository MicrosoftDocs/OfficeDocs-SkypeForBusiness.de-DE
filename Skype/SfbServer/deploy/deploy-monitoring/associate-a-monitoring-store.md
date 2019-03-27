---
title: Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Zusammenfassung: Erfahren Sie, wie ein Speicher für Überwachung von Skype für Business Server verwendeten Front-End-Pools zuordnen.'
ms.openlocfilehash: 1156883202218dd536926f44f40e6ba774b17cb7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887144"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype für Business Server 
**Zusammenfassung:** Erfahren Sie, wie ein Speicher für Überwachung von Skype für Business Server verwendeten Front-End-Pools zuordnen.
  
In Skype für Business Server kann Überwachungsdaten nur auf Front-End-Pools erfasst werden, die mit einem Speicher für Überwachung, eine Aufgabe in der Regel durchgeführt, wenn Sie einen Front-End-Pool im Topologie-Generator definieren verknüpft wurden.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool

 Zum Zuordnen eines Überwachungsspeichers zu einem neuen Front-End-Pool müssen Sie auf der Seite **Funktionen auswählen** des Assistenten zum Definieren eines neuen Front-End-Pools die Option **Überwachung (Aufzeichnung von Kommunikationsdatensätzen und Quality of Experience-Metriken) aktivieren** auswählen. Wenn Sie diese Option auswählen, müssen Sie auch einen SQL-Speicher angeben, um den Assistenten abzuschließen. Dieser Speicher muss jedoch zum Zeitpunkt der Ausführung des Assistenten nicht vorhanden sein. Dies bedeutet, dass Sie zuerst einem Pool einen Überwachungsspeicher zuordnen und diesen Speicher später einrichten und konfigurieren können.
  
Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:
  
1. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server-Topologie-Generator**.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.
    
4. Im Topologie-Generator erweitern Sie **Skype für Business Server**, erweitern Sie den Namen der Website ein, den Front-End-Pool und dann auf **Enterprise Edition-Front-End-Pools**.
    
5. Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL-Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL-Server-Computers im Feld **SQL-Server-FQDN** ein. Wenn Sie die SQL-Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.
    
    Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Um die Spiegelung zu aktivieren, wählen Sie T **seine SQL-Instanz ist in einer spiegelverbindung** aus, und geben Sie die Portnummer für den Spiegelserver im Feld **Portnummer Spiegelung** .
    
7. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.
    
Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Um die neue Topologie zu veröffentlichen, führen Sie die folgenden Schritte im Topologie-Generator:
  
1. Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie** und klicken Sie dann auf **Veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertigstellen**.
    
Nach der Veröffentlichung der Topologie können Sie die Überwachungsdatenbank klicken Sie dann auf dem Computer installieren, die den Überwachungsspeicher hostet. Die Überwachungsdatenbank kann mithilfe der Skype für Business Server-Verwaltungsshell und Windows PowerShell installiert werden. So installieren Sie die Datenbank lokal (d. h., um die Datenbank auf demselben Computer installieren, auf dem Sie die Skype für Business Server-Verwaltungsshell ausgeführt werden), Starten der-Verwaltungsshell auf dem entsprechenden Computer, und klicken Sie dann geben Sie in den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
  
```
Install-CsDatabase -LocalDatabases
```

Wenn Sie mit dem vorstehenden Befehl ausführen, wird Install-CsDatabase lesen Sie die aktuellen Skype für Business Server-Topologie, bestimmen, welche Datenbanken müssen Sie auf dem lokalen Computer installiert werden automatisch installieren und konfigurieren Sie jeden dieser Datenbanken.
  
So installieren Sie die Datenbank auf einem Remotecomputer (d. h., einem anderen Computer als dem Computer, auf dem der-Verwaltungsshell ausgeführt wird) müssen Sie mindestens zwei Parameter einschließen: die Parameter "ConfiguredDatabases" und "SqlServerFqdn" nicht. Diese Parameter weisen Sie das Install-CsDatabase-Cmdlet zum Abrufen der Skype für Business Server-Topologie, und klicken Sie dann installieren und konfigurieren die erforderlichen Datenbanken auf dem Computer durch "SqlServerFqdn" nicht angegeben. "SqlServerFqdn" nicht muss einen Parameterwert zur Darstellung der vollqualifizierte Domänenname des Computers verwenden und sind, auf dem die Datenbanken installiert werden soll.
  
Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Alternativ können Sie die Überwachungsdatenbank installieren, durch Ausführen der Skype für Business Server-Bereitstellungs-Assistenten auf dem Computer, auf der den Speicher für überwachen gehostet wird. Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:
  
1. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**und klicken Sie dann auf **Skype für Business Server-Bereitstellungs-Assistenten**.
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **installieren oder aktualisieren Skype für Business Server-System**.
    
3. Klicken Sie auf der Seite **Bereitstellen** unter **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**, klicken Sie auf **Erneut ausführen**.
    
4. Klicken Sie in der Setup-Skype für Business Server-Komponenten-Assistenten auf der Seite **Setup Skype für Business Server-Komponenten** auf **Weiter**.
    
5. Klicken Sie auf der Seite **Pfad zu MSIs angeben** Geben Sie den Pfad zur Datei Ocscore.msi ein (eine Datei mit Ihrer Skype für Business Server-Installationsmedien enthalten), und klicken Sie dann auf **Weiter**.
    
6. Klicken Sie auf der Seite **Befehle ausführen** auf **Fertigstellen**.
    
Um sicherzustellen, dass alle erforderlichen Skype für Business Server-Dienste gestartet haben, klicken Sie auf **Ausführen** unter der Überschrift **Schritt 4: Dienste starten** auf der Seite **Bereitstellen**
  

