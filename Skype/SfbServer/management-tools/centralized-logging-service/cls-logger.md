---
title: CLS Logger für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Zusammenfassung: Erfahren Sie, wie Sie den Logger für den zentralisierten Protokollierungsdienst (Centralized Logging Service, CLS) in Skype for Business Server 2015 verwenden.'
ms.openlocfilehash: a24cdbffc4b7601d325cd132afb5a7cf137b54f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835235"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>CLS Logger für Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie den Logger für den zentralisierten Protokollierungsdienst (Centralized Logging Service, CLS) in Skype for Business Server 2015 verwenden.
  
Der CLS Logger ist ein Tool, mit dem Sie vom zentralisierten Protokollierungsdienst generierte Protokolle verwalten können.
  
## <a name="prerequisites"></a>Voraussetzungen

Um den CLS Logger erfolgreich verwenden zu können, müssen Sie sicherstellen, dass Folgendes zutrifft:
  
- Sie verwenden das Tool auf einem Computer, der Mitglied der Domäne ist, in der der zentralisierte Protokollierungsdienst (Centralized Logging Service, CLS) ausgeführt wird. Das Tool wird derzeit in Remote-PowerShell-Sitzungen nicht unterstützt.
    
- Die Datei "Default.tmx" aus dem Ablaufverfolgungsordner (dem Ordner, in dem Ablaufverfolgungsdaten für den CLS erfasst werden) und Snooper müssen in denselben Ordner kopiert werden, in dem das CLS -Protokollierungstool installiert ist.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Überprüfen des Protokollierungsstatus einer Gruppe von Pools/Computern

Verwenden Sie die folgenden Befehle, um den Protokollierungsstatus zu überprüfen:
  
1. Wählen Sie auf der Registerkarte "Start-/Stoppszenarien" eine Gruppierung von Pools und/oder Computern in der Topologiestrukturansicht aus.
    
2. Klicken Sie auf die Schaltfläche "Protokollierungsstatus".
    
3. Zeigen Sie die Befehlsausgabe im Ausgabebereich des PowerShell-Befehls an, um Spezifisches zum Protokollierungsstatus der ausgewählten Pools und/oder Computer zu erhalten.
    
## <a name="start-an-existing-scenario"></a>Starten eines vorhandenen Szenarios

So starten Sie ein vorhandenes Szenario:
  
1. Wählen Sie auf der Registerkarte "Start/Stop Scenarios" im Dropdownmenü "Szenarien" ein vorhandenes Szenario aus.
    
2. Wählen Sie in der Topologiestrukturansicht eine Gruppierung von Pools und/oder Computern aus.
    
3. Klicken Sie auf die Schaltfläche "Szenario starten". Die Benutzeroberfläche wird deaktiviert, bis der Vorgang abgeschlossen ist. Dies kann bei großen Bereitstellungen langsam sein.
    
4. Die Benutzeroberfläche wird erneut aktiviert, sobald das Szenario erfolgreich gestartet wurde. Die Details der Aktion werden auch im Ausgabebereich des PowerShell-Befehls angezeigt.
    
5. Es kann einige Zeit dauern, bis die Protokollierung von CLS vor neuen Daten aus diesem Szenario abgeholt wird.
    
## <a name="stop-an-existing-scenario"></a>Beenden eines vorhandenen Szenarios

So beenden Sie ein vorhandenes Szenario:
  
1. Wählen Sie auf der Registerkarte "Start/Stop Scenarios" im Dropdownmenü "Szenarien" ein vorhandenes Szenario aus.
    
2. Wählen Sie in der Topologiestrukturansicht eine Gruppierung von Pools und/oder Computern aus.
    
3. Klicken Sie auf die Schaltfläche "Szenario beenden". Die Benutzeroberfläche wird deaktiviert, bis der Vorgang abgeschlossen ist. Dies kann bei großen Bereitstellungen langsam sein.
    
4. Die Benutzeroberfläche wird erneut aktiviert, sobald das Szenario beendet wurde. Die Details der Aktion werden auch im Ausgabebereich des PowerShell-Befehls angezeigt.
    
![Starten und Beenden von CLS Logger](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Suchen nach Protokollen

Um nach Protokollen zu suchen, wählen Sie die Registerkarte "CLS-Protokolle durchsuchen" aus, und klicken Sie nach dem Ausfüllen der angezeigten Felder auf die Schaltfläche "Suchprotokolle", wie unten beschrieben:
  
> **Protokolldateiordner** Der Ordner, in dem die Ergebnisse der Protokollsuche gespeichert werden. (Erforderlich)
> 
> **Protokollebene** Dies bestimmt die niedrigste Ebene, die in den Ergebnissen angezeigt wird. Wenn beispielsweise "Warnung" ausgewählt ist, werden nur "Warnung", "Fehler" und "Fatal" angezeigt. Standardwert ist "Debuggen".
> 
> **Pools** Computerpools, für die die Protokollsuche ausgeführt werden soll. Dies sind die übergeordneten Knoten der Strukturansicht. (Erforderlich)
> 
> **Computer** Einzelne Computer, für die die Protokollsuche ausgeführt werden soll. Dies sind alle untergeordneten Knoten in der Strukturansicht. (Erforderlich)
> 
> **Startzeit** Der Zeitraum, in dem CLS die Protokolle ababfraget. (Erforderlich)
> 
> **Endzeit** Der Zeitraum, in dem CLS die Abfrage der Protokolle beendet. (Erforderlich)
> 
> **Komponenten** Wird verwendet, um auszuwählen, welche Komponenten der Abfrage hinzugefügt werden. (Optional)
> 
> **Anruf-ID** Die Anruf-ID aller SIP-Dialogfelder, nach der gefiltert werden soll. Beachten Sie, dass für dieses Feld die genaue Übereinstimmung verwendet wird. (Optional)
> 
> **Konferenz-ID** Die Konferenz-ID aller Konferenzen, nach der gefiltert werden soll. Beachten Sie, dass für dieses Feld die genaue Übereinstimmung verwendet wird. (Optional)
> 
> **IP-Adresse** Die IP-Adresse, nach der gefiltert werden soll. Beachten Sie, dass für dieses Feld ein exakter Abgleich verwendet wird. (Optional)
> 
> **Korrelations-IDs** Ablaufverfolgungsanweisungen, die durch diese ID logisch miteinander verknüpft sind. (Optional)
> 
> **Telefonnummer** Nach Telefonnummer filtern. (Optional)
> 
> **SIP-URI** Filtern nach SIP-URI. (Optional)
> 
> **Inhalt der SIP-Nachricht enthält** Nach Inhalten von SIP-Nachrichten filtern, wird die Suche in diesem Feld nach Teilzeichenfolgen verwendet. (Optional)
> 
> **Match Any** Sucht mit einem logischen OR, wenn diese Option aktiviert ist. Standardmäßig wird die genaue Übereinstimmung aller Parameter verwendet.
> 
> **Netzwerkprotokolle überspringen** Überspringt die Suche nach Netzwerkprotokollen, wenn diese aktiviert sind.
    
![CLS-Logger-Suchprotokolle](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Erstellen eines Szenarios

1. Klicken Sie **auf der** Registerkarte "Szenarien bearbeiten" auf die Schaltfläche **"Szenario erstellen".**
    
    > [!NOTE]
    > Beim Erstellen eines neuen Szenarios wird die Konfiguration des aktuell ausgewählten Szenarios geklont. Wenn Sie vor **dem Erstellen eines** neuen Szenarios auf "Einstellungen löschen" klicken, wird es ohne ausgewählte Komponenten und Flags gestartet.
  
2. Geben Sie den Namen des Szenarios ein, das Sie erstellen möchten, und drücken Sie die EINGABETASTE, oder klicken Sie auf die Schaltfläche OK.
    
3. Das neue Szenario wird nun erstellt. Nach erfolgreicher Erstellung wird die Dropdownliste "Szenarien" mit dem neu erstellten Szenario ausgewählt.
    
## <a name="modify-a-scenario"></a>Ändern eines Szenarios

![CLS Logger Screenshot, Bearbeitungsszenarien](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Suchen Sie **auf der** Registerkarte "Szenarien bearbeiten" das gewünschte Zu ändernde Szenario.
    
2. Nehmen Sie die gewünschten Änderungen an den Komponenten, Ebenen und Flags vor.
    
3. Klicken Sie auf **die Schaltfläche "Szenario speichern".**
    
4. Nach dem erfolgreichen Speichern des Szenarios wird der Szenarioinformationsbereich mit der aktualisierten Konfiguration aktualisiert.
    
## <a name="delete-a-scenario"></a>Löschen eines Szenarios

1. Wählen Sie **auf der** Registerkarte "Szenarien bearbeiten" im Dropdownmenü "Szenarien" ein vorhandenes Szenario aus.
    
2. Klicken **Sie auf "Szenario löschen",** um das Szenario zu löschen.
    
3. Nach der Bestätigung der Aktion wird das Szenario gelöscht.
    

