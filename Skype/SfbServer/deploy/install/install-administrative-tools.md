---
title: Verwaltungstools in Skype for Business Server 2015 installieren
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Zusammenfassung: Informationen Sie zum Installieren der Verwaltungstools für eine Installation von Skype für Business Server 2015 erforderlich. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 104919e66ea16777582d28617c78853ba6f2f1e3
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>Verwaltungstools in Skype for Business Server 2015 installieren
 
**Zusammenfassung:** Informationen Sie zum Installieren der erforderlichen für eine Installation von Skype für Business Server 2015 administrative Tools. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung. Auf mindestens einem Server in der Topologie oder einem 64-Bit-Verwaltungscomputer auf dem eine Windows-Betriebssystem-Version, die für Skype für Business Server unterstützt wird, müssen die Verwaltungstools installiert werden. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Die Installation der Verwaltungstools wird in Schritt 3 beschrieben.
  
![Übersichtsdiagramm](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>Skype für Business Server 2015 Verwaltungstools installieren

Das Installationsmedium für Skype für Business Server 2015 bietet flexible. Beim Ausführen von Setup.exe sind die einzigen Tools installiert die Skype für Business Server-Bereitstellungs-Assistenten und den Skype für Business Server-Verwaltungsshell. Mithilfe dieser zwei Tools, bezeichnet als Hauptkomponenten, können Sie den Installationsvorgang fortsetzen, aber sie bieten keine primäre Funktionalität für die allgemeine Skype für Business Server-Umgebung. Der Bereitstellungs-Assistent wird nach Installation der Hauptkomponenten automatisch gestartet. Im Abschnitt des Bereitstellungs-Assistenten mit dem Titel **Verwaltungstools installieren** installiert Skype für Business Server-Topologie-Generator und Skype Business Server-Systemsteuerung.
  
> [!IMPORTANT]
> Jeder Skype für Business Server-Umgebung benötigen Sie mindestens einen Server mit die Verwaltungstools installiert sind. 
  
Schauen Sie sich das Video mit den Schritten zum **Installieren von Verwaltungstools** an:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>Installieren Sie Skype für Business Server 2015 Verwaltungstools aus den Bereitstellungs-Assistenten

1. Legen Sie die Skype für Business Server 2015-Installationsmedien. Wenn das Setup nicht automatisch startet, doppelklicken Sie auf **Setup**.
    
2. Das Installationsmedium erfordert zur Ausführung Microsoft Visual C++. Es wird ein Dialogfeld angezeigt, in dem gefragt wird, ob Sie es installieren möchten. Klicken Sie auf **Ja**.
    
3. Mithilfe der Smart-Setup ein neues Feature in Skype für Business Server 2015, können Sie mit dem Internet während der Installation nach Updates suchen verbinden. Dies ist benutzerfreundlicher, da sichergestellt wird, dass Sie bei der Installation die aktuellen Updates zur Verfügung haben. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
4. Lesen Sie die Lizenzbedingungen sorgfältig durch und klicken Sie auf **Ich stimme den Lizenzbedingungen zu**, wenn Sie diesen zustimmen. Klicken Sie dann auf **OK**.
    
5. Die Skype für Business Server 2015 Kernkomponenten wird auf dem Server installiert. 
    
    Die Hauptkomponenten werden in der Abbildung gezeigt.
    
    ![Hauptkomponenten auf dem Apps-Bildschirm.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **Skype für Business 2015 Bereitstellungsassistenten** Eine Bereitstellung-Programm, das ein Launch Pad bietet für die verschiedenen Komponenten von Skype für Business Server 2015 installieren.
    
  - **Skype für Business Server 2015-Verwaltungsshell** Eine vorkonfigurierte PowerShell-Programm, das für die Verwaltung von Skype für Business Server 2015 ermöglicht.
    
    Nach Abschluss die Installation der Kernkomponenten wird die Skype für Business Server 2015 Installations-Assistent automatisch gestartet, wie in der Abbildung dargestellt. 
    
    ![Skype for Business Server 2015 – Bereitstellungs-Assistent](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Zusätzlich zu den Hauptkomponenten müssen Sie auch Skype für Business Server 2015 Topologie-Generator und Skype Business Server 2015-Systemsteuerung auf mindestens einem Server in der Umgebung zu installieren. Klicken Sie im Bereitstellungs-Assistenten auf **Verwaltungstools installieren**.
    
7. Klicken Sie auf **Weiter**, um den Installationsvorgang zu starten.
    
8. Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig stellen**. Die Verwaltungstools wurden nun dem Server hinzugefügt (siehe Abbildung).
    
    ![Skype for Business Server 2015-Verwaltungstools](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype für Business Server 2015-Topologie-Generator** Ein Programm, das zum Erstellen, bereitstellen und Verwalten von Topologien verwendet.
    
   - **Skype für Business Server 2015-Systemsteuerung** Ein Programm verwendet, um die Installation zu verwalten.
    

