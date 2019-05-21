---
title: Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Front-End-Pools einem von Skype for Business Server verwendeten Überwachungsspeicher zuordnen.'
ms.openlocfilehash: 4af58fe6bb4d8ed1e23a7a95bc428a9615150766
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306664"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server 
**Zusammenfassung:** Erfahren Sie, wie Sie Front-End-Pools mit einem von Skype for Business Server verwendeten Überwachungsspeicher verknüpfen.
  
In Skype for Business Server können Überwachungsdaten nur in Front-End-Pools gesammelt werden, die einem Überwachungsspeicher zugeordnet wurden, eine Aufgabe, die normalerweise beim Definieren eines Front-End-Pools im Topologie-Generator durchgeführt wird.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool

 Zum Zuordnen eines Überwachungsspeichers zu einem neuen Front-End-Pool müssen Sie auf der Seite **Funktionen auswählen** des Assistenten zum Definieren eines neuen Front-End-Pools die Option **Überwachung (Aufzeichnung von Kommunikationsdatensätzen und Quality of Experience-Metriken) aktivieren** auswählen. Wenn Sie diese Option auswählen, müssen Sie auch einen SQL-Speicher angeben, um den Assistenten abzuschließen. Dieser Speicher muss jedoch zum Zeitpunkt der Ausführung des Assistenten nicht vorhanden sein. Dies bedeutet, dass Sie zuerst einem Pool einen Überwachungsspeicher zuordnen und diesen Speicher später einrichten und konfigurieren können.
  
Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:
  
1. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server Topology Builder**.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.
    
4. Erweitern Sie im Topologie-Generator **Skype for Business Server**, erweitern Sie den Namen der Website, die den Front-End-Pool enthält, und klicken Sie dann auf **Enterprise Edition-Front-End-Pools**erweitern.
    
5. Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL-Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL-Server-Computers im Feld **SQL-Server-FQDN** ein. Wenn Sie die SQL-Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.
    
    Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Zum Aktivieren der Spiegelung wählen Sie T aus, **dessen SQL-Instanz sich in der Spiegelungs Beziehung befindet** , und geben Sie im Feld **Spiegelungs-Portnummer** die Portnummer für den Spiegelserver ein.
    
7. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.
    
Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Führen Sie die folgenden Schritte im Topologie-Generator aus, um Ihre neue Topologie zu veröffentlichen:
  
1. Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie** und klicken Sie dann auf **Veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertigstellen**.
    
Nachdem die Topologie veröffentlicht wurde, können Sie die Überwachungsdatenbank auf dem Computer installieren, auf dem der Überwachungsspeicher gehostet wird. Die Überwachungsdatenbank kann mithilfe der Skype for Business Server-Verwaltungsshell und Windows PowerShell installiert werden. Wenn Sie die Datenbank lokal installieren möchten (um die Datenbank auf demselben Computer zu installieren, auf dem Sie die Skype for Business Server-Verwaltungsshell ausführen), starten Sie die Verwaltungsshell auf dem entsprechenden Computer, und geben Sie dann den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
  
```
Install-CsDatabase -LocalDatabases
```

Wenn Sie den vorhergehenden Befehl ausführen, liest install-CsDatabase die aktuelle Skype for Business Server-Topologie, ermittelt, welche Datenbanken auf dem lokalen Computer installiert werden müssen, und installiert und konfiguriert dann jede dieser Datenbankenautomatisch.
  
Zum Installieren der Datenbank auf einem Remotecomputer (also einem anderen Computer als dem Computer, auf dem die Verwaltungsshell ausgeführt wird) müssen Sie mindestens zwei Parameter einbeziehen: den ConfiguredDatabases-Parameter und den SqlServerFqdn-Parameter. Diese Parameter weisen das Cmdlet "Install-CsDatabase" an, die Skype for Business Server-Topologie abzurufen und dann die erforderlichen Datenbanken auf dem durch den SqlServerFqdn-Parameter angegebenen Computer zu installieren und zu konfigurieren. Der SqlServerFqdn-Parameter muss einen Parameterwert verwenden, der den vollqualifizierten Domänennamen des Computers darstellt, auf dem die Datenbanken installiert werden sollen.
  
Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Alternativ können Sie die Überwachungsdatenbank installieren, indem Sie den Bereitstellungs-Assistenten für Skype for Business Server auf dem Computer ausführen, auf dem der Überwachungsspeicher gehostet wird. Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:
  
1. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server**-Bereitstellungs-Assistent.
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **Skype for Business Server-System installieren oder aktualisieren**.
    
3. Klicken Sie auf der Seite **Deploy** unter **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten** **erneut auf Ausführen**.
    
4. Klicken Sie im Assistenten zum Einrichten von Skype for Business Server-Komponenten auf der Seite **Einrichten von Skype for Business Server-Komponenten** auf **weiter**.
    
5. Geben Sie auf der Seite **Pfad zur MSIs angeben** den Pfad zur Datei OCSCore. msi ein (eine Datei, die im Lieferumfang Ihres Skype for Business Server-Installationsmediums enthalten ist), und klicken Sie dann auf **weiter**.
    
6. Klicken Sie auf der Seite **Befehle ausführen** auf **Fertigstellen**.
    
Wenn Sie sicherstellen möchten, dass alle erforderlichen Skype for Business Server-Dienste gestartet wurden, klicken Sie unter der Überschrift **Schritt 4: Starten von Diensten** auf der Seite **Deploy** auf **Ausführen** .
  

