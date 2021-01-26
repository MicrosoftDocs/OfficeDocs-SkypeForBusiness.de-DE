---
title: Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Zusammenfassung: Erfahren Sie, wie Sie Front-End-Pools einem von Skype for Business Server verwendeten Überwachungsspeicher zuordnen.'
ms.openlocfilehash: 4ec48e99da9a827cdc40d87c42ec764bda66a416
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830545"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server 
**Zusammenfassung:** Erfahren Sie, wie Sie Front-End-Pools einem Überwachungsspeicher zuordnen, der von Skype for Business Server verwendet wird.
  
In Skype for Business Server können Überwachungsdaten nur in Front-End-Pools gesammelt werden, die einem Überwachungsspeicher zugeordnet sind. Diese Aufgabe wird normalerweise ausgeführt, wenn Sie einen Front-End-Pool im Topologie-Generator definieren.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool

 Wenn Sie einen Überwachungsspeicher einem neuen Front-End-Pool zuordnen möchten, müssen Sie auf der Seite  "Features auswählen" des Assistenten zum Definieren eines neuen Front-End-Pools die Option "Überwachung" (Aufzeichnung von Anrufdetails und Protokollierung der Erlebnisqualitätsmetriken) **auswählen.** Beachten Sie, dass Sie bei Auswahl dieser Option auch einen SQL angeben müssen, um den Assistenten abschließen zu können. Dieser Speicher muss jedoch zum Zeitpunkt der Ausführung des Assistenten nicht vorhanden sein. Dies bedeutet, dass Sie zuerst einen Pool einem Überwachungsspeicher zuordnen und diesen speicher später einrichten und konfigurieren können.
  
Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:
  
1. Klicken **Sie auf "Start",** **"Alle Programme",** **"Skype for Business Server 2015"** und dann auf **"Skype for Business Server-Topologie-Generator".**
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein, und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.
    
4. Erweitern Sie im Topologie-Generator **Skype for Business Server,** erweitern Sie den Namen des Standorts, der den Front-End-Pool enthält, und klicken Sie dann auf **"Enterprise Edition-Front-End-Pools erweitern".**
    
5. Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus, und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL Server-Computers im Feld **SQL Server-FQDN** ein. Wenn Sie die SQL Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.
    
    Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Um die Spiegelung zu aktivieren, wählen Sie **"T" SQL** instanz befindet sich in einer Spiegelungsbeziehung, und geben Sie die Portnummer für den Spiegelserver in das Feld mit der Nummer des **Spiegelungsports** ein.
    
7. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.
    
Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Zum Veröffentlichen der neuen Topologie führen Sie die folgenden Schritte im Topologie-Generator aus:
  
1. Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie**, und klicken Sie dann auf **Veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.
    
Nachdem die Topologie veröffentlicht wurde, können Sie die Überwachungsdatenbank auf dem Computer installieren, auf dem der Überwachungsspeicher hosten wird. Die Überwachungsdatenbank kann mithilfe der Skype for Business Server-Verwaltungsshell und der Windows PowerShell. Um die Datenbank lokal zu installieren (d. h. um die Datenbank auf demselben Computer zu installieren, auf dem Sie die Skype for Business Server-Verwaltungsshell ausführen), starten Sie die Verwaltungsshell auf dem entsprechenden Computer, geben Sie dann den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Wenn Sie den vorstehenden Befehl ausführen, liest Install-CsDatabase die aktuelle Skype for Business Server-Topologie, bestimmt, welche Datenbanken auf dem lokalen Computer installiert werden müssen, und installiert und konfiguriert dann automatisch jede dieser Datenbanken.
  
Zum Installieren der Datenbank auf einem Remotecomputer (d. h. einem anderen Computer als dem Computer, auf dem die Verwaltungsshell ausgeführt wird) müssen Sie mindestens zwei Parameter angeben: den Parameter "ConfiguredDatabases" und den Parameter "SqlServerFqdn". Diese Parameter teilen dem Install-CsDatabase cmdlet mit, die Skype for Business Server-Topologie abzurufen und anschließend die erforderlichen Datenbanken auf dem computer zu installieren und zu konfigurieren, der durch den Parameter "SqlServerFqdn" angegeben wird. Der Parameter "SqlServerFqdn" muss einen Parameterwert verwenden, der den vollqualifizierten Domänennamen des Computers darstellt, auf dem die Datenbanken installiert werden sollen.
  
Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Alternativ können Sie die Überwachungsdatenbank installieren, indem Sie den Skype for Business Server-Bereitstellungs-Assistenten auf dem Computer ausführen, auf dem der Überwachungsspeicher hosten wird. Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:
  
1. Klicken **Sie auf "Start",** **"Alle Programme",** **"Skype for Business Server 2015"** und dann auf **"Skype for Business Server Deployment Wizard".**
    
2. Klicken Sie im Bereitstellungsassistenten auf **"Skype for Business Server System installieren oder aktualisieren".**
    
3. Klicken Sie **auf der Seite** "Bereitstellen" unter Schritt **2: Skype for Business Server-Komponenten** einrichten oder entfernen auf **"Erneut ausführen".**
    
4. Klicken Sie im Assistenten zum Einrichten von Skype for Business Server-Komponenten auf der Seite **"Skype for Business Server-Komponenten** einrichten" auf **"Weiter".**
    
5. Geben Sie auf der Seite "Pfad zu **MSIs** angeben" den Pfad zur Datei Ocscore.msi ein (eine Datei, die in Ihrem Skype for Business Server-Installationsmedium enthalten ist), und klicken Sie dann auf **"Weiter".**
    
6. Klicken Sie auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
Um sicherzustellen, dass alle erforderlichen Skype for  Business Server-Dienste gestartet wurden, klicken Sie auf der Seite "Bereitstellen" unter der Überschrift "Schritt **4:** Dienste starten" auf "Ausführen". 
  

