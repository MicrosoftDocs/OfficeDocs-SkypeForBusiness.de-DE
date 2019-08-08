---
title: Installieren von Verwaltungstools in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Verwaltungstools installieren, die für die Installation von Skype for Business Server erforderlich sind. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: 168202048fcd72b16d93cfd410f678cad01b3058
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244620"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installieren von Verwaltungstools in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Verwaltungstools installieren, die für die Installation von Skype for Business Server erforderlich sind. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Center unter: herunter.
  
Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung. Die Verwaltungstools müssen auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation installiert sein, auf der eine Windows-Betriebssystemversion ausgeführt wird, die für Skype for Business Server unterstützt wird. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Die Installation der Verwaltungstools wird in Schritt 3 beschrieben.
  
![Übersichtsdiagramm](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installieren von Skype for Business Server-Verwaltungstools

Das Installationsmedium für Skype for Business Server bietet eine flexible Funktionalität. Beim ersten Ausführen von Setup. exe sind die einzigen installierten Tools der Skype for Business Server-Bereitstellungs-Assistent und die Skype for Business Server-Verwaltungsshell. Durch die Verwendung dieser beiden Tools, so genannten Core-Komponenten, können Sie den Installationsvorgang fortsetzen, Sie bieten jedoch keine primäre Funktionalität für die gesamte Skype for Business Server-Umgebung. Der Bereitstellungs-Assistent wird nach Installation der Hauptkomponenten automatisch gestartet. Der Abschnitt des Bereitstellungs-Assistenten mit dem Titel **install Administration Tools** installiert den Skype for Business Server Topology Builder und die Skype for Business Server-Systemsteuerung.
  
> [!IMPORTANT]
> Jede Skype for Business Server-Umgebung muss mindestens einen Server besitzen, auf dem die Verwaltungstools installiert sind. 
  
Schauen Sie sich das Video mit den Schritten zum **Installieren von Verwaltungstools** an:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installieren von Skype for Business Server-Verwaltungstools aus dem Bereitstellungs-Assistenten

1. Legen Sie das Skype for Business Server-Installationsmedium ein. Wenn das Setup nicht automatisch startet, doppelklicken Sie auf **Setup**.
    
2. Das Installationsmedium erfordert zur Ausführung Microsoft Visual C++. Es wird ein Dialogfeld angezeigt, in dem gefragt wird, ob Sie es installieren möchten. Klicken Sie auf **Ja**.
    
3. Durch die Verwendung von Smart Setup, einer neuen Funktion in Skype for Business Server, können Sie eine Verbindung mit dem Internet herstellen, um während des Installationsvorgangs nach Updates zu suchen. Dies ist benutzerfreundlicher, da sichergestellt wird, dass Sie bei der Installation die aktuellen Updates zur Verfügung haben. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
4. Lesen Sie die Lizenzbedingungen sorgfältig durch und klicken Sie auf **Ich stimme den Lizenzbedingungen zu**, wenn Sie diesen zustimmen. Klicken Sie dann auf **OK**.
    
5. Die Skype for Business Server-Core-Komponenten werden auf dem Server installiert. 
    
    Die Hauptkomponenten werden in der Abbildung gezeigt.
    
    ![Hauptkomponenten auf dem Apps-Bildschirm.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server** -Bereitstellungs-Assistent Ein Bereitstellungsprogramm, das eine Startrampe zum Installieren der verschiedenen Komponenten von Skype for Business Server bietet.
    
   - **Skype for Business Server-Verwaltungsshell** Ein vorkonfiguriertes PowerShell-Programm, das die Verwaltung von Skype for Business Server ermöglicht.
    
     Nachdem die Installation der Kernkomponenten abgeschlossen ist, wird der Skype for Business Server-Bereitstellungs-Assistent automatisch gestartet, wie in der Abbildung dargestellt. 
    
     ![Skype for Business Server-Bereitstellungsassistent](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Zusätzlich zu den Kernkomponenten müssen Sie auch den Skype for Business Server Topology Builder und die Skype for Business Server-Systemsteuerung auf mindestens einem Server in der Umgebung installieren. Klicken Sie im Bereitstellungs-Assistenten auf **Verwaltungstools installieren**.
    
7. Klicken Sie auf **Weiter**, um den Installationsvorgang zu starten.
    
8. Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig stellen**. Die Verwaltungstools wurden nun dem Server hinzugefügt (siehe Abbildung).
    
    ![Skype for Business Server-Verwaltungs Tools](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server-Topologie-Generator** Ein Programm, das zum Erstellen, bereitstellen und Verwalten von Topologien verwendet wird.
    
   - **Skype for Business Server-System** Steuerung Ein Programm, das zum Verwalten der Installation verwendet wird.
    

