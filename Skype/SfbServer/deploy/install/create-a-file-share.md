---
title: Erstellen einer Dateifreigabe in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe im Rahmen der Installation von Skype for Business Server erstellen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028296"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Erstellen einer Dateifreigabe in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe im Rahmen der Installation von Skype for Business Server erstellen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)unter: herunter.
  
Skype for Business Server erfordert eine Dateifreigabe, sodass Computer in der gesamten Topologie Dateien austauschen können. Das Erstellen einer Dateifreigabe ist der Schritt 2 von 8 im Installationsprozess für Skype for Business Server. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge ausführen, und nach den Schritten 1 bis 5, wie im Diagramm dargestellt. Informationen zur Planung von Details zur Dateifreigabe finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Übersicht Diagramm](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Erstellen einer einfachen Dateifreigabe

In diesem Abschnitt erfahren Sie, wie Sie eine grundlegende Windows Server-Dateifreigabe erstellen. Eine grundlegende Windows Server-Dateifreigabe wird mit Skype for Business Server unterstützt. Es bietet jedoch nicht explizit hohe Verfügbarkeit. Für eine Umgebung mit hoher Verfügbarkeit wird eine DFS-Dateifreigabe (Distributed File System) empfohlen. Weitere Informationen zu einer Dateifreigabe mit hoher Verfügbarkeit und zu DFS finden Sie unter [Plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 hat bei der Bereitstellung von San-basierten Dateifreigabe Lösungen (Storage Area Network) mit der Windows Server-Plattform große Fortschritte gemacht. Im Vergleich zu einer herkömmlichen SAN-basierten Appliance kann eine Windows Server 2012 R2-Speicherlösung die Kosten in der Hälfte reduzieren und die Leistung nur sehr geringfügig beeinträchtigen. Weitere Informationen zu Dateifreigabeoptionen in Windows Server 2012 R2 finden Sie im herunterladbaren Whitepaper [Windows Server 2012 R2-Speicher](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Sehen Sie sich die Video Schritte zum **Erstellen einer Dateifreigabe**an:
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Erstellen einer einfachen Dateifreigabe

1. Melden Sie sich an dem Computer an, auf dem die Dateifreigabe gehostet wird.
    
2. Klicken Sie mit der rechten Maustaste auf den Ordner, den Sie freigeben möchten, und wählen Sie **Eigenschaften**aus.
    
3. Wählen Sie die Registerkarte **Freigabe** aus, und klicken Sie auf **Erweiterte Freigabe**.
    
4. Klicken Sie auf **diesen Ordner freigeben**.
    
5. Klicken Sie auf **Berechtigungen**.
    
6. Fügen Sie die lokale Gruppe **Administratoren** des Servers hinzu, der die Dateifreigabe hostet, Grant **Allow: Vollzugriff, Änderungen und Lese** Berechtigungen, und klicken Sie dann auf **OK**.
    
7. Klicken Sie erneut auf **OK** , und notieren Sie sich den Netzwerkpfad.
    
8. Klicken Sie auf **Fertig** , um den Assistenten zu schließen.
    
     ![Registerkarte Freigabe für die Freigabe eines Ordners.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Wenn der Dateispeicher in einer DFS-Freigabe gehostet wird, wird die folgende Warnung empfangen:

Warnung: auf Freigabeberechtigungen für "\\<domain>\<Share>" kann nicht zugegriffen werden.

>Dies wird erwartet, wenn Sie kein Administrator auf dem Dateiserver sind oder wenn es sich um eine DFS-Freigabe (Distributed File System) handelt. Wenn die Freigabeberechtigungen bereits konfiguriert wurden, kann diese Warnung ignoriert werden. Wenn es sich um eine neue Freigabe handelt, lesen Sie in der Dokumentation ausführliche Informationen zur manuellen Konfiguration von Freigabeberechtigungen.

>Aufgrund der Unfähigkeit, auf die Freigabeberechtigungen für eine DFS-Freigabe zuzugreifen, können Skype for Business Server Gruppen nicht explizit auf der Dateifreigabe festlegen. Um sicherzustellen, dass Skype for Business Server Komponenten mit den entsprechenden Berechtigungen auf die Dateifreigabe zugreifen können, stellen Sie sicher, dass die folgenden RTC-Gruppen zusätzlich zu den lokalen Administratoren mit der Vollzugriff-Freigabe mit Lese-und Änderungs Ebenen-Freigabeberechtigungen hinzugefügt werden. Berechtigungen.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
