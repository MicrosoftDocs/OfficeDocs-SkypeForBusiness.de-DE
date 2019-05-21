---
title: Erstellen einer Dateifreigabe in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe im Rahmen der Installation von Skype for Business Server erstellen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: d6a34ad4807948a5580fc572628a4fd6333dd9f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292165"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Erstellen einer Dateifreigabe in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine Windows Server-Dateifreigabe im Rahmen der Installation von Skype for Business Server erstellen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Center unter: herunter.
  
Für Skype for Business Server ist eine Dateifreigabe erforderlich, damit Computer in der gesamten Topologie Dateien austauschen können. Das Erstellen einer Dateifreigabe ist Schritt 2 von 8 beim Installationsvorgang für Skype for Business Server. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 der Reihe nach ausführen, und zwar nach den Schritten 1 bis 5, wie im Diagramm beschrieben. Informationen zum Planen von Details zur Dateifreigabe finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) -oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Übersichtsdiagramm](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Erstellen einer grundlegenden Dateifreigabe

In diesem Abschnitt werden die Schritte zur Erstellung einer Standarddateifreigabe für Windows Server erläutert. Eine einfache Windows Server-Dateifreigabe wird von Skype for Business Server unterstützt. Es wird jedoch nicht explizit eine höhere Verfügbarkeit bereitgestellt. Für eine solche Umgebung wird eine Dateifreigabe mithilfe von DFS (Distributed File System) empfohlen. Weitere Informationen zu einer Dateifreigabe mit höherer Verfügbarkeit und zu DFS finden Sie unter [Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 hat große Fortschritte bei der Bereitstellung Storage Area Network (SAN)-artiger Dateifreigabelösungen auf der Windows Server-Plattform erzielt. Im Vergleich zu einem herkömmlichen System auf SAN-Basis kann eine Windows Server 2012 R2-Speicherlösung die Kosten bei kaum spürbaren Leistungseinbußen auf die Hälfte reduzieren. Weitere Informationen zu Dateifreigabeoptionen in Windows Server 2012 R2 finden Sie im herunterladbaren Whitepaper [Windows Server 2012 R2-Speicher](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
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
  
> [!NOTE]
>Wenn der Dateispeicher auf einer DFS-Freigabe gehostet wird, wird die folgende Warnung empfangen:

Warnung: auf Freigabeberechtigungen für "\\<domain>\<share>" kann nicht zugegriffen werden.

>Dies wird erwartet, wenn Sie kein Administrator auf dem Dateiserver sind oder wenn es sich um eine DFS-Freigabe (Distributed File System) handelt. Wenn die Freigabeberechtigungen bereits konfiguriert sind, kann diese Warnung ignoriert werden. Wenn es sich um eine neue Freigabe handelt, finden Sie in der Dokumentation Einzelheiten zum manuellen Konfigurieren von Freigabeberechtigungen.

>Da es nicht möglich ist, auf die Freigabeberechtigungen für eine DFS-Freigabe zuzugreifen, kann Skype for Business Server keine expliziten Gruppen für die Dateifreigabe einrichten. Um sicherzustellen, dass Skype for Business Server-Komponenten mit den entsprechenden Berechtigungen auf die Dateifreigabe zugreifen können, stellen Sie sicher, dass die folgenden RTC-Gruppen zusätzlich zu den lokalen Administratoren mit den Freigabeberechtigungen für den Zugriff auf die Freigabeberechtigungen für die Änderungs Ebene hinzugefügt werden.

RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins
