---
title: Installieren der Dateien für den Vermittlungsserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Dateien für den Vermittlungsserver in Skype for Business Server installieren.'
ms.openlocfilehash: 8ecd5b20f7f3dfac625851c94f313a50fa71af29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299443"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Installieren der Dateien für den Vermittlungsserver in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Dateien für den Vermittlungsserver in Skype for Business Server installieren.
  
Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als lokaler Administrator beim Server angemeldet sein und ein Domänenbenutzerkonto verwenden, das mindestens Mitglied der Gruppe „RTCUniversalReadOnlyAdmins“ ist.
  
Führen Sie die Schritte in diesem Thema aus, um den Assistenten für die Bereitstellung von Skype for Business Server auszuführen, um die Dateien für den Vermittlungsserver auf einem Computer zu installieren, den Sie einem vermittlungsserverpool hinzugefügt haben, nachdem Sie den Pool mithilfe des Topologie-Generators definiert und veröffentlicht haben. Wenn Sie den Mediationsserver für Dateien installieren, können Sie auch das für jeden Computer in einem vermittlungsserverpool erforderliche Zertifikat installieren und zuweisen. 
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen vermittlungsserverpool in Ihrer Topologie definiert und veröffentlicht haben, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server](deploy-a-mediation-server.md)beschrieben. 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool

1. Klicken Sie auf dem Installationsmedium mit der rechten Maustaste auf _ \<Installationsmedien\> _ **\Setup\amd64\Setup.exe**, und klicken Sie dann auf **als Administrator ausführen**.
    
2. Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.
    
3. Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich stimme zu** und klicken Sie anschließend auf **OK**. (Dieser Schritt ist erforderlich, um fortfahren zu können.)
    
4. Klicken Sie auf der Seite des **Skype for Business Server** -Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**.
    
5. Klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.
    
6. Übernehmen Sie auf der Seite **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** die Standardeinstellung **Direkt aus zentralem Verwaltungsspeicher abrufen** und klicken Sie auf **Weiter**.
    
7. Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.
    
8. Klicken Sie neben **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**auf **Ausführen**, und klicken Sie dann auf **weiter**.
    
9. Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.
    
10. Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**. Folgen Sie den Anweisungen auf dem Bildschirm und übernehmen Sie die Standardeinstellungen. Da der Vermittlungsserver ein Zertifikat benötigt, müssen Sie **Schritt 3** zweimal ausführen: einmal zum Ausstellen und noch einmal zum Zuweisen des erforderlichen Zertifikats.
    
11. Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.
    
12. Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu und melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ an.
    
13. Überprüfen Sie auf dem Computer, auf dem Sie die Skype for Business Server-Systemsteuerung ausführen, auf der Seite **Topologie** des Skype for Business Server Control Panels, dass der Dienststatus des Vermittlungsservers als grünes Häkchen angezeigt wird. Wenn ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus. Klicken Sie im Menü **Aktion** auf **Alle Dienste starten**. 
    
Wenn Sie dem vermittlungsserverpool mehr als einen Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im vermittlungsserverpool aus. Wenn Sie keine Dateien für den Vermittlungsserver für andere Computer installieren müssen, führen Sie die Verfahren unter [Konfigurieren von Trunks in Skype for Business Server](configure-trunks.md) aus, um die Einstellungen für die trunk-Verbindung zwischen diesem vermittlungsserverpool zu konfigurieren (oder aller Mediation Server an einer Website) und deren Peer.

