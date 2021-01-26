---
title: Installieren von Verwaltungstools in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Zusammenfassung: Erfahren Sie, wie Sie die verwaltungstechnischen Tools installieren, die für eine Installation von Skype for Business Server erforderlich sind. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812105"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installieren von Verwaltungstools in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die verwaltungstechnischen Tools installieren, die für eine Installation von Skype for Business Server erforderlich sind. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) herunter.
  
Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung. Die Verwaltungstools müssen auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation mit einer Windows-Betriebssystemversion installiert sein, die für Skype for Business Server unterstützt wird. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die Installation der Verwaltungstools ist Schritt 3 von 8.
  
![Übersichtsdiagramm](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installieren von Skype for Business Server-Verwaltungstools

Die Installationsmedien für Skype for Business Server bieten eine flexible Erfahrung. Bei der ersten Ausführung Setup.exe nur der Skype for Business Server-Bereitstellungs-Assistent und die Skype for Business Server-Verwaltungsshell installiert. Mithilfe dieser beiden Tools, die als Hauptkomponenten bezeichnet werden, können Sie den Installationsvorgang fortsetzen, bieten jedoch keine primäre Funktionalität für die gesamte Skype for Business Server-Umgebung. Der Bereitstellungs-Assistent wird nach der Installation der Hauptkomponenten automatisch gestartet. Im Abschnitt des Bereitstellungsassistenten mit dem Titel **"Verwaltungstools** installieren" werden der Skype for Business Server-Topologie-Generator und die Skype for Business Server-Systemsteuerung installiert.
  
> [!IMPORTANT]
> Jede Skype for Business Server-Umgebung muss über mindestens einen Server verfügen, auf dem die Verwaltungstools installiert sind. 
  
Sehen Sie sich die Videoschritte für die **Installation von Verwaltungstools an:**
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installieren von Skype for Business Server-Verwaltungstools über den Bereitstellungsassistenten

1. Fügen Sie das Skype for Business Server-Installationsmedium ein. Wenn das Setup nicht automatisch gestartet wird, doppelklicken Sie auf **Setup**.
    
2. Für die Ausführung des Installationsmediums muss Microsoft Visual C++ ausgeführt werden. Es wird ein Dialogfeld angezeigt, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie auf **Ja**.
    
3. Mithilfe von Smart Setup, einem neuen Feature in Skype for Business Server, können Sie eine Verbindung mit dem Internet herstellen, um während des Installationsvorgangs nach Updates zu suchen. Dadurch wird die Benutzererfahrung verbessert, indem Sichergestellt wird, dass Sie bei der Installation über die neuesten Updates für das Produkt verfügen. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
4. Überprüfen Sie den Lizenzvertrag sorgfältig, und wenn Sie zustimmen, wählen Sie "Ich stimme den **Bedingungen** des Lizenzvertrags zu, und klicken Sie auf **OK".**
    
5. Die Hauptkomponenten von Skype for Business Server werden auf dem Server installiert. 
    
    Die Hauptkomponenten bestehen aus folgenden Komponenten, wie in der Abbildung dargestellt.
    
    ![Bildschirm "Hauptkomponenten in Apps".](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server Deployment Wizard** Ein Bereitstellungsprogramm, das ein Startpad für die Installation der verschiedenen Komponenten von Skype for Business Server bietet.
    
   - **Skype for Business Server Management Shell** Ein vorkonfiguriertes PowerShell-Programm, das die Verwaltung von Skype for Business Server ermöglicht.
    
     Sobald die Installation der Hauptkomponenten abgeschlossen ist, wird der Skype for Business Server-Bereitstellungs-Assistent automatisch gestartet, wie in der Abbildung dargestellt. 
    
     ![Skype for Business Server Deployment Wizard](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Zusätzlich zu den Hauptkomponenten müssen Sie den Skype for Business Server Topology Builder und die Skype for Business Server-Systemsteuerung auf mindestens einem Server in der Umgebung installieren. Klicken **Sie auf "Verwaltungstools installieren"** im Bereitstellungs-Assistenten.
    
7. Klicken Sie auf **Weiter**, um die Installation zu starten.
    
8. Klicken Sie nach Abschluss der Installation auf **"Fertig stellen".** Die Verwaltungstools werden nun dem Server hinzugefügt, wie in der Abbildung dargestellt.
    
    ![Skype for Business Server -Verwaltungstools](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server Topology Builder** Ein Programm zum Erstellen, Bereitstellen und Verwalten von Topologien.
    
   - **Skype for Business Server -Systemsteuerung** Ein Programm, das zum Verwalten der Installation verwendet wird.
    

