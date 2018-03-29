---
title: Installieren der Dateien für den Vermittlungsserver in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Zusammenfassung: Informationen Sie zum Installieren der Dateien für den Vermittlungsserver in Skype für Business Server 2015.'
ms.openlocfilehash: 8b7b68142c180ee1b06963afbb1b7a9ca6d4319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server-2015"></a>Installieren der Dateien für den Vermittlungsserver in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Installieren der Dateien für den Vermittlungsserver in Skype für Business Server 2015.
  
Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als lokaler Administrator beim Server angemeldet sein und ein Domänenbenutzerkonto verwenden, das mindestens Mitglied der Gruppe „RTCUniversalReadOnlyAdmins“ ist.
  
Verwenden Sie die Schritte in diesem Thema ausführen Skype für Business Server-Bereitstellungs-Assistenten zum Installieren der Dateien für den Vermittlungsserver auf einem Computer, die Sie in einen Pool Mediation Server hinzugefügt haben, nachdem Sie der Topologie-Generator zum Definieren und veröffentlichen den Pool verwendet haben. Bei der Installation von Dateien Mediation Server auch installieren und Zuweisen des Zertifikats von jedem Computer in einem Pool Mediation Server erforderlich. 
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen vermittlungsserverpool in Ihrer Topologie veröffentlicht und definiert, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015](deploy-a-mediation-server.md)beschrieben. 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool

1. Dem Installationsmedium mit der rechten Maustaste _ \<-Installationsmedium\> _ **\Setup\amd64\Setup.exe**, und klicken Sie dann auf **als Administrator ausführen**.
    
2. Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.
    
3. Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich stimme zu** und klicken Sie anschließend auf **OK**. (Dieser Schritt ist erforderlich, um fortfahren zu können.)
    
4. Klicken Sie auf der Seite **Skype für Business Server-Bereitstellungs-Assistenten** auf **installieren oder aktualisieren Skype für Business Server-System**.
    
5. Klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.
    
6. Übernehmen Sie auf der Seite **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** die Standardeinstellung **Direkt aus zentralem Verwaltungsspeicher abrufen** und klicken Sie auf **Weiter**.
    
7. Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.
    
8. Neben **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**, klicken Sie auf **Ausführen**, und klicken Sie dann auf **Weiter**.
    
9. Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.
    
10. Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**. Folgen Sie den Anweisungen auf dem Bildschirm und übernehmen Sie die Standardeinstellungen. Da der Vermittlungsserver ein Zertifikat benötigt, müssen Sie **Schritt 3** zweimal ausführen: einmal zum Ausstellen und noch einmal zum Zuweisen des erforderlichen Zertifikats.
    
11. Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.
    
12. Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu und melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ an.
    
13. Auf dem Computer, auf dem Sie Skype Business Server-Systemsteuerung ausführen, vergewissern Sie sich auf der Seite **Topologie** von Skype Business Server-Systemsteuerung, die der Status des Vermittlungsservers als ein grünes Häkchen angezeigt werden. Wenn ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus. Klicken Sie im Menü **Aktion** auf **Alle Dienste starten**. 
    
Wenn Sie mehrere Computer auf den Pool Mediation Server hinzugefügt haben, führen Sie die Schritte aus, in diesem Verfahren auf allen anderen Computern im Pool Vermittlungsserver. Wenn Sie keine Dateien für den Vermittlungsserver für alle anderen Computern installieren müssen, führen Sie die Verfahren in [Konfigurieren von Trunks in Skype für Business Server 2015](configure-trunks.md) , konfigurieren Sie Einstellungen für die trunkverbindung zwischen diesen Mediation Server-Pool (oder alle Der Vermittlungsserver an einem Standort) und seinen Peer.

