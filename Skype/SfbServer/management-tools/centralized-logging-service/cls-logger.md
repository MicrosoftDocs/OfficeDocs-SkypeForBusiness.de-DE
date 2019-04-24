---
title: CLS Logger für Skype for Business Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/25/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Zusammenfassung: Erfahren Sie, wie die Protokollierung Centralized Logging Service (CLS) in Skype für Business Server 2015 verwenden.'
ms.openlocfilehash: 5b2a2f7e447215d291aa763982acae1a6e64b8a1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217738"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>CLS Logger für Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie die Protokollierung Centralized Logging Service (CLS) in Skype für Business Server 2015 verwenden.
  
CLS Logger ist ein Tool, das Sie bei der Verwaltung der durch den zentralisierten Protokollierungsdienst generierten Protokolle unterstützt.
  
## <a name="prerequisites"></a>Voraussetzungen

Damit CLS Logger ordnungsgemäß verwendet werden kann, müssen folgende Voraussetzungen erfüllt sein:
  
- Sie verwenden das Tool auf einem Computer, der Mitglied der Domäne ist, in der der zentralisierte Protokollierungsdienst (Centralized Logging Service, CLS) ausgeführt wird. Das Tool wird zurzeit in Remote-PowerShell-Sitzungen nicht unterstützt.
    
- Die Datei „Default.tmx“ aus dem Ordner „Tracing“ (der Ordner, in dem die Ablaufverfolgungsdaten für den CLS erfasst werden) und Snooper müssen in denselben Ordner kopiert werden, in dem das Tool CLS Logger installiert ist.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Überprüfen Sie den Protokollierungsstatus einer Gruppe von Pools/Computern

Überprüfen Sie den Protokollierungsstatus mithilfe der folgenden Befehle:
  
1. Wählen Sie auf der Registerkarte "Beenden/Starten Szenarien" eine Gruppierung von Pools und/oder Computern in der Strukturansicht Topologie.
    
2. Klicken Sie auf die Schaltfläche „Logging Status“ (Protokollierungsstatus).
    
3. Zeigen Sie die Befehlsausgabe im PowerShell-Befehlsausgabebereich an, um nähere Informationen über den Protokollierungsstatus der ausgewählten Pools und/oder Computer zu erhalten.
    
## <a name="start-an-existing-scenario"></a>Starten Sie ein vorhandenes Szenario

So starten Sie ein vorhandenes Szenario
  
1. Wählen Sie auf der Registerkarte "Beenden/Starten Szenarien" ein vorhandenes Szenario aus dem Dropdownmenü Szenarien.
    
2. Wählen Sie eine Gruppe von Pools und/oder Computern in der Strukturansicht „Topology“ (Topologie) aus.
    
3. Klicken Sie auf die Schaltfläche „Start Scenario“ (Szenario starten). Die Benutzeroberfläche ist deaktiviert, bis der Vorgang abgeschlossen ist. Dies kann in großen Bereitstellungen lange dauern.
    
4. Die Benutzeroberfläche wird wieder aktiviert, sobald das Szenario erfolgreich gestartet wurde. Die Details der Aktion werden auch im PowerShell-Befehlsausgabebereich angezeigt.
    
5. Es wird möglicherweise eine gewisse Zeit benötigt, damit die Protokollierung vom CLS vor etwaigen neuen Daten aus diesem Szenario erfasst werden kann.
    
## <a name="stop-an-existing-scenario"></a>Beenden Sie ein vorhandenes Szenario

So beenden Sie ein vorhandenes Szenario
  
1. Wählen Sie auf der Registerkarte "Beenden/Starten Szenarien" ein vorhandenes Szenario aus dem Dropdownmenü Szenarien.
    
2. Wählen Sie eine Gruppe von Pools und/oder Computern in der Strukturansicht „Topology“ (Topologie) aus.
    
3. Klicken Sie auf die Schaltfläche „Stop Scenario“ (Szenario beenden). Die Benutzeroberfläche ist deaktiviert, bis der Vorgang abgeschlossen ist. Dies kann in großen Bereitstellungen lange dauern.
    
4. Die Benutzeroberfläche wird wieder aktiviert, sobald das Szenario beendet wurde. Die Details der Aktion werden auch im PowerShell-Befehlsausgabebereich angezeigt.
    
![CLS Logger starten und beenden](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Suchen Sie nach Protokollen

Um nach Protokollen gesucht, wählen Sie die Registerkarte "Suche CLS Protokolle", und klicken Sie auf die Schaltfläche "Suche speichern" nach der angezeigten Felder ausfüllen, wie unten beschrieben:
  
> **Log File Folder** (Protokolldateiordner): Der Ordner, in dem die Ergebnisse der Protokollsuche gespeichert werden (erforderlich)
> 
> **Log Level** (Protokollebene): Hiermit wird die unterste Ebene bestimmt, die in den Ergebnissen angezeigt wird. Wenn beispielsweise „Warning“ (Warnung) ausgewählt ist, werden nur „Warning“ (Warnung), „Error“ (Fehler) und „Fatal“ (Schwerwiegend) angezeigt. Die Standardeinstellung ist „Debug“ (Debuggen).
> 
> **Pools** (Pools): Die Computerpools, in denen die Protokollsuche durchgeführt wird. Dies sind die übergeordneten Knoten der Strukturansicht (erforderlich).
> 
> **Computers** (Computer): Einzelne Computer, auf denen die Protokollsuche durchgeführt wird. Dies sind alle untergeordneten Knoten in der Strukturansicht (erforderlich).
> 
> **Start Time** (Startzeit): Der Zeitpunkt, ab dem CLS die Protokolle abfragt. (erforderlich).
> 
> **End Time** (Endzeit): Der Zeitpunkt, bis zu dem CLS die Protokolle abfragt (erforderlich).
> 
> **Components** (Komponenten): Hier können Sie die Komponenten auswählen, die der Abfrage hinzugefügt werden sollen (optional).
> 
> **Call ID** (Anruf-ID): Die Anruf-ID der SIP-Dialogfelder, nach denen gefiltert werden soll. Hinweis: Bei diesem Feld wird die exakte Übereinstimmung verwendet (optional).
> 
> **Conference ID** (Konferenz-ID): Die Konferenz-ID der Konferenzen, nach denen ggf. gefiltert werden soll. Hinweis: Bei diesem Feld wird die exakte Übereinstimmung verwendet (optional).
> 
> **IP Address** (IP-Adresse): Die IP-Adresse, nach der gefiltert werden soll. Hinweis: Bei diesem Feld wird die exakte Übereinstimmung verwendet (optional).
> 
> **Correlation IDs** (Korrelations-IDs): Ablaufverfolgungsanweisungen, die durch diese ID logisch miteinander verknüpft sind (optional).
> 
> **Phone Number** (Telefonnummer): In diesem Feld können Sie nach Telefonnummer filtern (optional).
> 
> **SIP URI** (SIP-URI): In diesem Feld können Sie nach SIP-URIs filtern (optional).
> 
> **SIP Message Content Contains** (Inhalt der SIP-Nachricht enthält): In diesem Feld können Sie nach SIP-Nachrichteninhalten filtern. Dadurch ist eine Suche nach Teilzeichenfolgen in diesem Feld möglich (optional).
> 
> **Match Any** (Übereinstimmung alle): Wenn dieses Kontrollkästchen aktiviert ist, werden Suchvorgänge mit logischem „Oder“ ausgeführt. Standardmäßig werden alle Parameter mit genauer Übereinstimmung gefunden.
> 
> **Skip Network Logs** (Netzwerkprotokolle überspringen): Wenn dieses Kontrollkästchen aktiviert ist, werden keine Netzwerkprotokolle gesucht.
    
![CLS Logger-Suchprotokolle](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Erstellen Sie ein Szenario

1. Die Registerkarte **Szenarien bearbeiten** klicken auf die Schaltfläche **Szenario erstellen** .
    
    > [!NOTE]
    > Beim Erstellen eines neuen Szenarios wird die Konfiguration des aktuell ausgewählten Szenarios geklont. Wenn Sie vor Erstellen eines neuen Szenarios auf **Einstellungen löschen** klicken, beginnt das System ohne ausgewählte Komponenten und Flags.
  
2. Geben Sie den Namen des Szenarios an, das Sie erstellen möchten, und drücken Sie die EINGABETASTE oder OK.
    
3. Das neue Szenario wird jetzt erstellt. Nach erfolgreicher Erstellung wird die Dropdownliste der Szenarien mit dem neu erstellten Szenario ausgewählt.
    
## <a name="modify-a-scenario"></a>Ändern Sie ein Szenario

![Screenshot CLS-Logger, Szenarien bearbeiten](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Suchen Sie auf der Registerkarte **Szenarien bearbeiten** das Szenario, das Sie ändern möchten.
    
2. Nehmen Sie die gewünschten Änderungen bezüglich Komponenten, Ebenen und Kennzeichnungen vor.
    
3. Klicken Sie auf die Schaltfläche **Szenario speichern**.
    
4. Nach erfolgreichem Speichervorgang, wird der Fensterbereich mit den Szenario-Informationen entsprechend der überarbeiteten Konfiguration aktualisiert.
    
## <a name="delete-a-scenario"></a>Löschen Sie ein Szenario

1. Wählen Sie aus der Dropdownliste „Szenarien“ auf der Registerkarte **Szenarien bearbeiten** ein vorhandenes Szenario aus.
    
2. Klicken Sie auf **Szenario löschen**, um das Szenario zu löschen.
    
3. Nach Bestätigung der Aktion wird das Szenario gelöscht.
    

