---
title: Erstellen einer Dateifreigabe in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Zusammenfassung: Erfahren Sie, wie eine Windows Server-Dateifreigabe als Teil der Installation von Skype für Business Server 2015 zu erstellen. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 5f91a18a744e73cd65f58efef071978604653b27
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a>Erstellen einer Dateifreigabe in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe als Teil der Installation von Skype für Business Server 2015 erstellen. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype für Business Server erfordert eine Dateifreigabe, damit Computer in der Topologie, Dateien austauschen können. Erstellen einer Dateifreigabe ist Schritt 2 von 8 in den Installationsvorgang für Skype für Business Server 2015. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 der Reihe nach ausführen, und zwar nach den Schritten 1 bis 5, wie im Diagramm beschrieben. Planen von Details zu Dateifreigabe, finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![Übersichtsdiagramm](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Erstellen einer grundlegenden Dateifreigabe

In diesem Abschnitt werden die Schritte zur Erstellung einer Standarddateifreigabe für Windows Server erläutert. Eine grundlegende Windows Server-Dateifreigabe wird mit Skype für Business Server unterstützt. Allerdings bietet nicht explizit hohen Verfügbarkeit. Für eine solche Umgebung wird eine Dateifreigabe mithilfe von DFS (Distributed File System) empfohlen. Weitere Informationen über eine Dateifreigabe für hohe Verfügbarkeit und DFS finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 hat große Fortschritte bei der Bereitstellung Storage Area Network (SAN)-artiger Dateifreigabelösungen auf der Windows Server-Plattform erzielt. Im Vergleich zu einem herkömmlichen System auf SAN-Basis kann eine Windows Server 2012 R2-Speicherlösung die Kosten bei kaum spürbaren Leistungseinbußen auf die Hälfte reduzieren. Weitere Informationen zu den Optionen für Freigabe in Windows Server 2012 R2 finden Sie unter einem herunterladbaren Whitepaper [Windows Server 2012 R2-Speicher](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Sehen Sie sich im Video die Schritte zum **Erstellen einer Dateifreigabe** an:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Erstellen einer grundlegenden Dateifreigabe

1. Melden Sie sich bei dem Computer an, der die Dateifreigabe hosten soll.
    
2. Klicken Sie mit der rechten Maustaste auf den Ordner, den Sie freigegeben möchten, und wählen Sie dann **Eigenschaften** aus.
    
3. Wählen Sie die Registerkarte **Freigabe** aus und klicken Sie auf **Erweiterte Freigabe**.
    
4. Klicken Sie auf **Diesen Ordner freigeben**.
    
5. Klicken Sie auf **Berechtigungen**.
    
6. Fügen Sie die Gruppe lokaler **Administratoren** des Servers hinzu, der die Dateifreigabe hostet, erteilen Sie die Berechtigungen **Einräumen: Vollzugriff, Ändern und Lesen** und klicken Sie dann auf **OK**.
    
7. Klicken Sie erneut auf **OK** und notieren Sie sich den Netzwerkpfad.
    
8. Klicken Sie auf **Fertig**, um den Assistenten zu schließen.
    
     ![Registerkarte „Freigabe“ zur Ordnerfreigabe.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

