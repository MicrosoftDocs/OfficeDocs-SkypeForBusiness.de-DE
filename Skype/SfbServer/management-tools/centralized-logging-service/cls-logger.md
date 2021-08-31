---
title: CLS Logger for Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Zusammenfassung: Erfahren Sie, wie Sie die CLS-Protokollierung (Centralized Logging Service) in Skype for Business Server 2015 verwenden.'
ms.openlocfilehash: e35375dd1715f2d9b2e64cc42339af7247d098d4
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730234"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>CLS Logger for Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie die CLS-Protokollierung (Centralized Logging Service) in Skype for Business Server 2015 verwenden.
  
Die CLS-Protokollierung ist ein Tool, das Sie beim Verwalten von Protokollen unterstützt, die vom zentralisierten Protokollierungsdienst generiert werden.
  
## <a name="prerequisites"></a>Voraussetzungen

Um cls Logger erfolgreich zu verwenden, müssen Sie sicherstellen, dass Folgendes zutrifft:
  
- Sie verwenden das Tool auf einem Computer, der Mitglied der Domäne ist, in der der zentralisierte Protokollierungsdienst (Centralized Logging Service, CLS) ausgeführt wird. Das Tool wird derzeit in Remote-PowerShell-Sitzungen nicht unterstützt.
    
- Die Datei Default.tmx aus dem Ablaufverfolgungsordner (dem Ordner, in dem Ablaufverfolgungsdaten für den CLS erfasst werden) und Snooper müssen in denselben Ordner kopiert werden, in dem das CLS-Protokollierungstool installiert ist.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Überprüfen des Protokollierungsstatus einer Gruppe von Pools/Computern

Verwenden Sie die folgenden Befehle, um den Protokollierungsstatus zu überprüfen:
  
1. Wählen Sie auf der Registerkarte "Start-/Stoppszenarien" in der Topologiestrukturansicht eine Gruppierung von Pools und/oder Computern aus.
    
2. Klicken Sie auf die Schaltfläche "Protokollierungsstatus".
    
3. Zeigen Sie die Befehlsausgabe im PowerShell-Befehlsausgabebereich an, um Informationen zum Protokollierungsstatus der ausgewählten Pools und/oder Computer zu erhalten.
    
## <a name="start-an-existing-scenario"></a>Starten eines vorhandenen Szenarios

So starten Sie ein vorhandenes Szenario:
  
1. Wählen Sie auf der Registerkarte "Start-/Stoppszenarien" im Dropdownmenü "Szenarien" ein vorhandenes Szenario aus.
    
2. Wählen Sie in der Topologiestrukturansicht eine Gruppierung von Pools und/oder Computern aus.
    
3. Klicken Sie auf die Schaltfläche "Startszenario". Die Benutzeroberfläche wird deaktiviert, bis der Vorgang abgeschlossen ist. Dies kann bei großen Bereitstellungen langsam sein.
    
4. Die Benutzeroberfläche wird wieder aktiviert, sobald das Szenario erfolgreich gestartet wurde. Die Details der Aktion werden auch im PowerShell-Befehlsausgabebereich angezeigt.
    
5. Es kann einige Zeit dauern, bis die Protokollierung von CLS übernommen wird, bevor neue Daten aus diesem Szenario abgerufen werden.
    
## <a name="stop-an-existing-scenario"></a>Beenden eines vorhandenen Szenarios

So beenden Sie ein vorhandenes Szenario:
  
1. Wählen Sie auf der Registerkarte "Start-/Stoppszenarien" im Dropdownmenü "Szenarien" ein vorhandenes Szenario aus.
    
2. Wählen Sie in der Topologiestrukturansicht eine Gruppierung von Pools und/oder Computern aus.
    
3. Klicken Sie auf die Schaltfläche "Szenario beenden". Die Benutzeroberfläche wird deaktiviert, bis der Vorgang abgeschlossen ist. Dies kann bei großen Bereitstellungen langsam sein.
    
4. Die Benutzeroberfläche wird erneut aktiviert, nachdem das Szenario beendet wurde. Die Details der Aktion werden auch im PowerShell-Befehlsausgabebereich angezeigt.
    
![CLS Logger starten und beenden.](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Suchen nach Protokollen

Um nach Protokollen zu suchen, wählen Sie die Registerkarte "CLS-Protokolle durchsuchen" aus, und klicken Sie auf die Schaltfläche "Suchprotokolle", nachdem Sie die angezeigten Felder wie unten beschrieben ausgefüllt haben:
  
> **Protokolldateiordner** Der Ordner, in dem die Ergebnisse der Protokollsuche gespeichert werden sollen. (Erforderlich)
> 
> **Protokollebene** Dadurch wird die niedrigste Ebene bestimmt, die in den Ergebnissen angezeigt wird. Wenn beispielsweise "Warnung" ausgewählt ist, werden nur Warnung, Fehler und schwerwiegend angezeigt. Standardmäßig wird debuggen.
> 
> **Pools** Computerpools, mit denen die Protokollsuche ausgeführt werden soll. Hierbei handelt es sich um die übergeordneten Knoten der Strukturansicht. (Erforderlich)
> 
> **Computer** Bei einzelnen Computern, für die die Protokollsuche durchgeführt werden soll, handelt es sich um alle untergeordneten Knoten in der Strukturansicht. (Erforderlich)
> 
> **Startzeit** Der Zeitraum, in dem CLS die Protokolle abfragt. (Erforderlich)
> 
> **Endzeit** Der Zeitraum, in dem CLS die Abfrage der Protokolle beendet. (Erforderlich)
> 
> **Komponenten** Wird verwendet, um auszuwählen, welche Komponenten der Abfrage hinzugefügt werden sollen. (Optional)
> 
> **Anruf-ID** Die Anruf-ID aller SIP-Dialogfelder, nach denen gefiltert werden soll. Beachten Sie, dass in diesem Feld die genaue Übereinstimmung verwendet wird. (Optional)
> 
> **Konferenz-ID** Die Konferenz-ID aller Konferenzen, nach denen gefiltert werden soll. Beachten Sie, dass in diesem Feld die genaue Übereinstimmung verwendet wird. (Optional)
> 
> **IP-Adresse** Die IP-Adresse, nach der gefiltert werden soll. Beachten Sie, dass in diesem Feld die genaue Übereinstimmung verwendet wird. (Optional)
> 
> **Korrelations-IDs** Ablaufverfolgungsanweisungen, die logisch durch diese ID miteinander verknüpft sind. (Optional)
> 
> **Telefon Zahl** Filtern nach Telefonnummer. (Optional)
> 
> **SIP-URI** Filtern nach SIP-URI. (Optional)
> 
> **Inhalt der SIP-Nachricht enthält** Filtert nach SIP-Nachrichteninhalten. Dadurch wird innerhalb dieses Felds eine Teilzeichenfolgensuche ausgeführt. (Optional)
> 
> **Übereinstimmung mit "Beliebig"** Sucht mithilfe eines logischen OR, falls aktiviert. Standardmäßig wird die genaue Übereinstimmung aller Parameter verwendet.
> 
> **Überspringen von Netzwerkprotokollen** Überspringt die Suche nach Netzwerkprotokollen, wenn diese aktiviert sind.
    
![CLS Logger-Suchprotokolle.](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Erstellen eines Szenarios

1. Klicken Sie auf der Registerkarte **"Szenarien bearbeiten"** auf die Schaltfläche **"Szenario erstellen".**
    
    > [!NOTE]
    > Beim Erstellen eines neuen Szenarios wird die Konfiguration des aktuell ausgewählten Szenarios geklont. Wenn Sie vor dem Erstellen eines neuen Szenarios **auf "Einstellungen löschen"** klicken, werden keine Komponenten und Flags ausgewählt.
  
2. Geben Sie den Namen des Szenarios ein, das Sie erstellen möchten, und drücken Sie die EINGABETASTE, oder klicken Sie auf die Schaltfläche "Ok".
    
3. Das neue Szenario wird nun erstellt. Nach erfolgreicher Erstellung wird die Dropdownliste "Szenarien" mit dem neu erstellten Szenario ausgewählt.
    
## <a name="modify-a-scenario"></a>Ändern eines Szenarios

![CLS Logger Screen shot, edit scenarios.](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Suchen Sie auf der Registerkarte **"Szenarien bearbeiten"** das gewünschte Szenario, das Sie ändern möchten.
    
2. Nehmen Sie die gewünschten Änderungen an den Komponenten, Ebenen und Flags vor.
    
3. Klicken Sie auf die Schaltfläche **"Szenario speichern".**
    
4. Nach dem erfolgreichen Speichern des Szenarios wird der Bereich mit den Szenarioinformationen mit der aktualisierten Konfiguration aktualisiert.
    
## <a name="delete-a-scenario"></a>Löschen eines Szenarios

1. Wählen Sie auf der Registerkarte **"Szenarien bearbeiten"** im Dropdownmenü "Szenarien" ein vorhandenes Szenario aus.
    
2. Klicken Sie auf **"Szenario löschen",** um das Szenario zu löschen.
    
3. Nachdem Sie die Aktion bestätigt haben, wird das Szenario gelöscht.
    

