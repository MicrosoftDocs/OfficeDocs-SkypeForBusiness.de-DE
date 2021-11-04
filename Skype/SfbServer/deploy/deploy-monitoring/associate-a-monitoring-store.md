---
title: Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Zusammenfassung: Erfahren Sie, wie Sie Front-End-Pools einem überwachungsspeicher zuordnen, der von Skype for Business Server verwendet wird.'
ms.openlocfilehash: 7261f86e86bc06426afd0cac8ca9142ab4398fe5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778905"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server 
**Zusammenfassung:** Erfahren Sie, wie Sie Front-End-Pools einem überwachungsspeicher zuordnen, der von Skype for Business Server verwendet wird.
  
In Skype for Business Server können Überwachungsdaten nur in Front-End-Pools gesammelt werden, die einem Überwachungsspeicher zugeordnet wurden. Eine Aufgabe, die in der Regel ausgeführt wird, wenn Sie einen Front-End-Pool im Topologie-Generator definieren.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool

 Um einen Überwachungsspeicher einem neuen Front-End-Pool zuzuordnen, stellen Sie sicher, dass Sie die Option **Überwachung (Aufzeichnung von Kommunikationsdatensätzen und Protokollierung von QoE-Metriken)** auf der Seite **"Features auswählen"** des Assistenten zum Definieren eines neuen Front-End-Pools auswählen. Beachten Sie, dass Sie bei Auswahl dieser Option auch einen SQL Speicher angeben müssen, um den Assistenten abzuschließen. Dieser Speicher muss jedoch nicht zum Zeitpunkt der Ausführung des Assistenten vorhanden sein. Das bedeutet, dass Sie zuerst einen Pool einem Überwachungsspeicher zuordnen, dann später diesen Speicher einrichten und konfigurieren können.
  
Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:
  
1. Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business Server 2015"** und dann auf **Skype for Business Server Topologie-Generator.**
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein, und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.
    
4. Erweitern Sie im Topologie-Generator **Skype for Business Server,** erweitern Sie den Namen des Standorts, der den Front-End-Pool enthält, und klicken Sie dann auf **Enterprise Edition Front-End-Pools** erweitern.
    
5. Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus, und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL Server-Computers im Feld **SQL Server-FQDN** ein. Wenn Sie die SQL Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.
    
    Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Um die Spiegelung zu aktivieren, wählen Sie **"T" aus, SQL Instanz sich in der Spiegelungsbeziehung befindet,** und geben Sie die Portnummer für den Spiegelserver in das Feld **"Spiegelportnummer"** ein.
    
7. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.
    
Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Zum Veröffentlichen der neuen Topologie führen Sie die folgenden Schritte im Topologie-Generator aus:
  
1. Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie**, und klicken Sie dann auf **Veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.
    
Nachdem die Topologie veröffentlicht wurde, können Sie die Überwachungsdatenbank auf dem Computer installieren, auf dem der Überwachungsspeicher gehostet wird. Die Überwachungsdatenbank kann mithilfe der Skype for Business Server-Verwaltungsshell und Windows PowerShell installiert werden. Um die Datenbank lokal zu installieren (d. a. um die Datenbank auf demselben Computer zu installieren, auf dem Sie die Skype for Business Server Verwaltungsshell ausführen), starten Sie die Verwaltungsshell auf dem entsprechenden Computer, geben Sie dann den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Wenn Sie den vorherigen Befehl ausführen, liest Install-CsDatabase die aktuelle Skype for Business Server Topologie, bestimmt, welche Datenbanken auf dem lokalen Computer installiert werden müssen, und installiert und konfiguriert dann automatisch jede dieser Datenbanken.
  
Um die Datenbank auf einem Remotecomputer (d. h. einem anderen Computer als dem Computer, auf dem die Verwaltungsshell ausgeführt wird) zu installieren, müssen Sie mindestens zwei Parameter angeben: den Parameter "ConfiguredDatabases" und den Parameter "SqlServerFqdn". Diese Parameter weisen das cmdlet Install-CsDatabase an, die Skype for Business Server Topologie abzurufen und dann die erforderlichen Datenbanken auf dem durch den SqlServerFqdn-Parameter angegebenen Computer zu installieren und zu konfigurieren. Der Parameter "SqlServerFqdn" muss einen Parameterwert verwenden, der den vollqualifizierten Domänennamen des Computers darstellt, auf dem die Datenbanken installiert werden sollen.
  
Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Alternativ können Sie die Überwachungsdatenbank installieren, indem Sie den Skype for Business Server Bereitstellungs-Assistenten auf dem Computer ausführen, auf dem der Überwachungsspeicher gehostet wird. Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:
  
1. Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business Server 2015** und dann auf **Skype for Business Server Bereitstellungs-Assistenten.**
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **"Installieren" oder "Aktualisieren" Skype for Business Server System.**
    
3. Klicken Sie auf der Seite **"Bereitstellen"** unter **Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten** auf **"Erneut ausführen".**
    
4. Klicken Sie im Setup Skype for Business Server Komponenten-Assistenten auf der Seite **"Setup Skype for Business Server Komponenten"** auf **"Weiter".**
    
5. Geben Sie auf der Seite **"Pfad zu MSIs angeben"** den Pfad zu der Datei Ocscore.msi ein (eine Datei, die im Skype for Business Server Installationsmedium enthalten ist), und klicken Sie dann auf **"Weiter".**
    
6. Klicken Sie auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
Um sicherzustellen, dass alle erforderlichen Skype for Business Server Dienste gestartet wurden, klicken Sie unter der Überschrift **"Schritt 4: Dienste starten"** auf der Seite **"Bereitstellen"** auf **"Ausführen".**
  

