---
title: Erstellen einer Dateifreigabe in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie im Rahmen der Installation von Skype for Business Server eine Windows Server-Dateifreigabe erstellen. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812235"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Erstellen einer Dateifreigabe in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie im Rahmen der Installation von Skype for Business Server eine Windows Server-Dateifreigabe erstellen. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) herunter.
  
Skype for Business Server erfordert eine Dateifreigabe, damit Computer in der gesamten Topologie Dateien austauschen können. Das Erstellen einer Dateifreigabe ist Schritt 2 von 8 im Installationsprozess für Skype for Business Server. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Planungsdetails zur Dateifreigabe finden Sie unter "Umgebungsanforderungen für [Skype for Business Server-](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Serveranforderungen für Skype for Business Server 2019".](../../../SfBServer2019/plan/system-requirements.md)
  
![Übersichtsdiagramm](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Erstellen einer einfachen Dateifreigabe

Dieser Abschnitt führt Sie durch das Erstellen einer einfachen Windows Server-Dateifreigabe. Eine einfache Windows Server-Dateifreigabe wird mit Skype for Business Server unterstützt. Es bietet jedoch nicht explizit hohe Verfügbarkeit. Für eine Hochverfügbarkeitsumgebung wird eine Dateifreigabe des verteilten Dateisystems (Distributed File System, DFS) empfohlen. Weitere Informationen zu einer Dateifreigabe mit hoher Verfügbarkeit und DFS finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 hat große Sprünge bei der Bereitstellung von San (Storage Area Network)- like File Share Solutions mithilfe der Windows Server-Plattform gemacht. Im Vergleich zu einer herkömmlichen SAN-basierten Appliance kann eine Windows Server 2012 R2-Speicherlösung die Kosten halbiert und die Leistung minimal beeinträchtigen. Weitere Informationen zu Dateifreigabeoptionen in Windows Server 2012 R2 finden Sie im Whitepaper zum Herunterladen [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Sehen Sie sich die Videoschritte zum **Erstellen einer Dateifreigabe an:**
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Erstellen einer einfachen Dateifreigabe

1. Melden Sie sich an dem Computer an, auf dem die Dateifreigabe hosten wird.
    
2. Klicken Sie mit der rechten Maustaste auf den Ordner, den Sie freigeben möchten, und wählen Sie **"Eigenschaften" aus.**
    
3. Wählen Sie die **Registerkarte** "Freigabe" aus, und klicken Sie auf **"Erweiterte Freigabe".**
    
4. Klicken **Sie auf "Diesen Ordner freigeben".**
    
5. Klicken Sie auf **Berechtigungen**.
    
6. Fügen Sie die lokale **Administratorgruppe** des Servers hinzu, der die Dateifreigabe hosten soll, erteilen Sie **"Zulassen:** Vollsteuerung", "Ändern" und "Lesen", und klicken Sie dann auf **"OK".**
    
7. Klicken Sie **erneut auf "OK",** und notieren Sie sich den Netzwerkpfad.
    
8. Klicken Sie **auf "Fertig",** um den Assistenten zu schließen.
    
     ![Registerkarte "Freigabe" zum Freigeben eines Ordners.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Wenn der Dateispeicher auf einer DFS-Freigabe gehostet wird, wird die folgende Warnung angezeigt:

Warnung: Der Zugriff auf Freigabeberechtigungen für " " \\ <domain> \<share> ist nicht möglich.

>Dies wird erwartet, wenn Sie kein Administrator auf dem Dateiserver sind oder wenn es sich um eine DFS (Distributed File System)-Freigabe handelt. Wenn die Freigabeberechtigungen bereits konfiguriert wurden, kann diese Warnung ignoriert werden. Wenn es sich um eine neue Freigabe handelt, finden Sie in der Dokumentation ausführliche Informationen zum manuellen Konfigurieren von Freigabeberechtigungen.

>Da der Zugriff auf die Freigabeberechtigungen für eine DFS-Freigabe nicht möglich ist, kann Skype for Business Server keine Gruppen für die Dateifreigabe explizit festlegen. Um sicherzustellen, dass Skype for Business Server-Komponenten auf die Dateifreigabe mit den entsprechenden Berechtigungen zugreifen können, stellen Sie sicher, dass die folgenden RTC-Gruppen zusätzlich zu den lokalen Administratoren mit Vollzugriffsfreigabeberechtigungen mit Lese- und Änderungsebenenfreigaben hinzugefügt werden.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
