---
title: Installieren der Dateien für den Vermittlungsserver in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Dateien für den Vermittlungsserver in Skype for Business Server installieren.'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830795"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Installieren der Dateien für den Vermittlungsserver in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Dateien für den Vermittlungsserver in Skype for Business Server installieren.
  
Um dieses Verfahren erfolgreich abschließen zu können, sollten Sie mindestens als lokaler Administrator und Domänenbenutzer, der mindestens Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" ist, am Server angemeldet sein.
  
Führen Sie mithilfe der Schritte in diesem Thema den Skype for Business Server-Bereitstellungs-Assistenten aus, um die Dateien für den Vermittlungsserver auf einem Computer zu installieren, den Sie einem Vermittlungsserverpool hinzugefügt haben, nachdem Sie den Pool mithilfe des Topologie-Generators definiert und veröffentlicht haben. Beim Installieren des Vermittlungsservers für Dateien installieren und weisen Sie auch das zertifikat zu, das für jeden Computer in einem Vermittlungsserverpool erforderlich ist. 
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen Vermittlungsserverpool in Ihrer Topologie definiert und veröffentlicht haben, wie unter Bereitstellen eines Vermittlungsservers [im Topologie-Generator in Skype for Business Server beschrieben.](deploy-a-mediation-server.md) 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool

1. Klicken Sie auf dem Installationsmedium mit der rechten maustaste\Setup\amd64\Setup.exe, und klicken Sie dann _\<installation media\>_ **** **auf "Als Administrator ausführen".**
    
2. Klicken Sie **auf der Seite "Installationsspeicherort"** auf **"OK".**
    
3. Klicken Sie **auf der Seite "Endbenutzer-Lizenzvertrag"** auf **"Ich** akzept", und klicken Sie dann auf **"OK".** (Erforderlich, um fortzufahren.)
    
4. Klicken Sie **auf der Seite des Skype for Business Server-Bereitstellungs-Assistenten** auf "Skype for Business Server System installieren oder **aktualisieren".**
    
5. Next to **Step 1: Install Local Configuration Store,** click **Run**, and then follow the instructions on the screen.
    
6. Übernehmen Sie auf der Seite "Lokales Replikat des zentralen **Verwaltungsspeichers** konfigurieren" die Standardeinstellung "Direkt aus dem zentralen **Verwaltungsspeicher** abrufen", und klicken Sie dann auf **"Weiter".**
    
7. Klicken Sie **auf der Seite "Befehle** ausführen" auf "Fertig stellen", wenn der Vorgangsstatus als abgeschlossen angezeigt **wird.**
    
8. Neben Schritt **2: Skype for Business Server-Komponenten** einrichten oder entfernen, klicken Sie auf **"Ausführen"** und dann auf **"Weiter".**
    
9. Klicken Sie **auf der Seite "Befehle** ausführen" auf "Fertig stellen", wenn der Vorgangsstatus als abgeschlossen angezeigt **wird.**
    
10. Klicken Sie **neben Schritt 3: Zertifikate anfordern, installieren** oder zuweisen auf **"Ausführen".** Folgen Sie den Anweisungen auf dem Bildschirm, und akzeptieren Sie die Standardeinstellungen. Der Vermittlungsserver erfordert ein Zertifikat. Daher führen Sie Schritt **3** zweimal aus: einmal, um das erforderliche Zertifikat aus ausgestellt zu haben, und noch einmal, um es zuzuordnen.
    
11. Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben Schritt **4:** Dienste starten auf **"Ausführen",** und folgen Sie dann den Anweisungen auf dem Bildschirm.
    
12. Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu, und melden Sie sich als Mitglied der Gruppe "DomainAdmins" am Server an.
    
13. Überprüfen Sie auf dem Computer, auf dem die  Skype for Business Server-Systemsteuerung ausgeführt wird, auf der Topologieseite der Skype for Business Server-Systemsteuerung, ob der Dienststatus des Vermittlungsservers als grünes Häkchen angezeigt wird. Wenn stattdessen ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus. Klicken Sie **im Menü "Aktion"** **auf "Alle Dienste starten".** 
    
Wenn Sie dem Vermittlungsserverpool mehrere Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im Vermittlungsserverpool aus. Wenn Sie keine Dateien für den Vermittlungsserver für andere Computer installieren müssen, führen Sie die Verfahren unter "Konfigurieren von [Trunks in Skype for Business Server"](configure-trunks.md) aus, um Einstellungen für die Trunkverbindung zwischen diesem Vermittlungsserverpool (oder allen Vermittlungsservern an einem Standort) und seinem Peer zu konfigurieren.

