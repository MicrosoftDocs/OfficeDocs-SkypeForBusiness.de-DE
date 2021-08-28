---
title: Konfiguration von Pushbenachrichtigungen für mobile Clients
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Um die Microsoft-Pushbenachrichtigungen und Apple-Pushbenachrichtigungen zu konfigurieren, müssen Sie eine Richtlinie erstellen und darin definieren, welche Arten von Pushbenachrichtigungen Sie benötigen.
ms.openlocfilehash: c26788cbe351888aef633cc21a08d46bf3f74deb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613194"
---
# <a name="mobile-client-push-notification-configuration"></a>Mobiler Client: Konfiguration für Pushbenachrichtigung
 
Um die **Microsoft-Pushbenachrichtigungen** und **Apple-Pushbenachrichtigungen** zu konfigurieren, müssen Sie eine Richtlinie erstellen und darin definieren, welche Arten von Pushbenachrichtigungen Sie benötigen.
  
Im Hauptfenster der Konfiguration können Sie auf **Aktualisieren** klicken, um die Liste mit den Richtlinien zu aktualisieren und neu aufzufüllen. Mithilfe eines Suchfelds können Sie den Umfang der Liste mit den angezeigten Richtlinien eingrenzen. Wenn Sie den gesuchten Namen eingeben, wird die Liste mit den Richtlinien automatisch eingegrenzt.
  
> [!IMPORTANT]
> Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen überschreiben, die auf eine andere Richtlinienebene angewendet wurden. Richtlinienrangfolge: Benutzerrichtlinie (größter Einfluss) setzt eine Standortrichtlinie außer Kraft, und dann überschreibt eine Standortrichtlinie eine globale Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie. 
  
Für die Erstellung und Bearbeitung von Richtlinien sind zwei Auswahlmöglichkeiten vorhanden:
  
1. **Neu**: Klicken Sie auf diese Option, um eine neue Richtlinie zu erstellen. Sie müssen einen Standort angeben, für den die Richtlinie gelten soll. Anschließend konfigurieren Sie die Einstellungen für die Pushbenachrichtigung. Unter **Pushbenachrichtigungskonfiguration** können Sie nur Richtlinien für Standorte erstellen, die Sie bereits erstellt haben.
    
2. **Bearbeiten**: Markieren Sie eine Richtlinie, und klicken Sie auf "Bearbeiten", um in der Dropdownliste eine Aktion auszuwählen. Sie können nur Standorte bearbeiten, die Sie bereits erstellt haben, oder die globale Richtlinie bearbeiten:
    
   - **Details einblenden…**: Zeigt Informationen zur derzeit ausgewählten Richtlinie an. Sie können Änderungen an der vorhandenen Richtlinie vornehmen.
    
   - **Alles auswählen**: Klicken Sie auf diese Option, wenn Sie alle Richtlinien auswählen möchten.
    
   - **Löschen**: Entfernt die ausgewählte Richtlinie. Wenn Sie **Alles auswählen** und **Löschen** nacheinander verwenden, werden alle Richtlinien entfernt.
    
     > [!NOTE]
     > Die Standardrichtlinie **Global** kann nicht gelöscht werden. Wenn Sie dies versuchen, wird eine Meldung angezeigt, dass die Richtlinie "Global" auf die Standardwerte zurückgesetzt wurde (alle Einstellungen werden gelöscht), die Richtlinie jedoch nicht entfernt werden kann.
  
Die Erstellung einer neuen Richtlinie bzw. die Bearbeitung einer vorhandenen Richtlinie ist mit zwei Aktionen verbunden:
  
- **Commit ausführen** Die Commitaktion erstellt oder aktualisiert die Richtlinie und speichert die Änderungen.
    
- **Abbrechen** Die Abbruchaktion verwirft alle Änderungen, die seit der letzten Commitaktion vorgenommen wurden. Alle vorgenommenen Änderungen gehen verloren.
    
Für **Pushbenachrichtigungskonfiguration** sind zwei Einstellungen möglich. Die Einstellungen sind den Pushbenachrichtigungsdiensten für Microsoft und Apple zugeordnet. Sie können Pushbenachrichtigungen für die Dienste aktivieren, indem Sie jeweils das Kontrollkästchen neben dem Namen des Diensts aktivieren. Ebenso können Sie das Kontrollkästchen auch deaktivieren. Nachdem Sie Ihre Auswahl getroffen haben, können Sie entweder einen Commit ausführen oder den Vorgang abbrechen. Wenn Sie einen Commit ausführen, werden die Änderungen an der Richtlinie gespeichert.
  

