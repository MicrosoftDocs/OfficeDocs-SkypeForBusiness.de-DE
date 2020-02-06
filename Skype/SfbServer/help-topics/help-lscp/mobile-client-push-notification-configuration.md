---
title: Push-Benachrichtigungskonfiguration für mobile Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Wenn Sie die Microsoft Push-Benachrichtigungen und Apple Push-Benachrichtigungen konfigurieren möchten, müssen Sie eine Richtlinie erstellen, um festzulegen, welche Arten von Push-Benachrichtigungen Sie benötigen.
ms.openlocfilehash: 3fde99c3f026f87197492417cd10611d96f7e20e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822658"
---
# <a name="mobile-client-push-notification-configuration"></a>Mobiler Client: Konfiguration für Pushbenachrichtigung
 
Wenn Sie die **Microsoft Push-Benachrichtigungen** und **Apple Push-Benachrichtigungen**konfigurieren möchten, müssen Sie eine Richtlinie erstellen, um festzulegen, welche Arten von Push-Benachrichtigungen Sie benötigen.
  
Auf dem Hauptbildschirm der Konfiguration können Sie auf **Aktualisieren** klicken, um die Liste der Richtlinien zu aktualisieren und neu zu füllen. Ein Suchfeld wird zum Einschränken der Liste der angezeigten Richtlinien bereitgestellt. Wenn Sie den gesuchten Namen eingeben, wird die Liste der Richtlinien automatisch eingeschränkt.
  
> [!IMPORTANT]
> Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt. 
  
Für die Richtlinienerstellung und-Bearbeitung stehen zwei Optionen zur Verfügung:
  
1. **Neu**: Klicken Sie hier, um eine neue Richtlinie zu erstellen. Sie müssen eine Website angeben, auf die die Richtlinie angewendet werden soll. Anschließend konfigurieren Sie die Einstellungen für die Push-Benachrichtigung. Für die **Konfiguration der Push-Benachrichtigung**können Sie nur Richtlinien für Websites erstellen, die Sie bereits erstellt haben.
    
2. **Bearbeiten**: Wählen Sie eine Richtlinie aus, und klicken Sie auf Bearbeiten, um eine Aktion aus einer Dropdownliste auszuwählen. Sie können nur Websites bearbeiten, die Sie bereits erstellt haben, oder die globale Richtlinie bearbeiten:
    
   - **Details anzeigen**: zeigt Informationen zur aktuell ausgewählten Richtlinie an. Sie werden in der Lage sein, Änderungen an der vorhandenen Richtlinie vorzunehmen.
    
   - **Alle auswählen**: Wenn Sie über eine Reihe von Richtlinien verfügen und alle Richtlinien auswählen müssen, klicken Sie auf alle auswählen.
    
   - **Löschen**: entfernt die ausgewählte Richtlinie. Durch Verwenden von **"Alles auswählen" und "** **Löschen** " werden alle Richtlinien entfernt
    
     > [!NOTE]
     > Sie können die standardmäßige **globale** Richtlinie nicht löschen. Wenn Sie versuchen, Sie zu löschen, werden Sie darauf hingewiesen, dass die globale Richtlinie an die Standardwerte zurückgegeben wurde (das heißt, alle Einstellungen werden gelöscht), aber die Richtlinie kann nicht entfernt werden.
  
Das Erstellen einer neuen Richtlinie oder das Bearbeiten einer vorhandenen Richtlinie ist mit zwei Aktionen verknüpft:
  
- **Commit** Die Commit-Aktion erstellt oder aktualisiert die Richtlinie und speichert die Änderungen
    
- **Abbrechen** Mit der Aktion Cancel werden alle Änderungen verworfen, die seit der letzten Commit-Aktion vorgenommen wurden. Wenn Sie kündigen, gehen die vorgenommenen Änderungen verloren.
    
Für die **Konfiguration der Push-Benachrichtigung**sind zwei Einstellungen möglich. Die Einstellungen sind den Push Notification Services für Microsoft und für Apple zugeordnet. Sie aktivieren die Push-Benachrichtigung für beide Dienste, indem Sie das Kontrollkästchen neben dem Namen des Diensts aktivieren. Sie können das Kontrollkästchen deaktivieren, indem Sie es auswählen, um es zu löschen. Nachdem Sie Ihre Auswahl getroffen haben, müssen Sie entweder committen oder stornieren. Durch Klicken auf Commit werden die Änderungen an der Richtlinie gespeichert.
  

