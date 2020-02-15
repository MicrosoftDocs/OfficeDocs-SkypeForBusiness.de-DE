---
title: Installieren der Voraussetzungen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: Hier erfahren Sie mehr über die Server und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018256"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installieren der Voraussetzungen für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Server und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Die Installation von Voraussetzungen besteht darin, Windows Server einzurichten, indem die erforderlichen Rollen und Features auf jedem Server in der Topologie installiert werden. Die Anforderungen basieren auf der Rolle, die der Server in der Topologie erfüllen wird. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Installieren von Voraussetzungen ist Schritt 1 von 8.
  
![Overview-Diagramm – installieren Sie die erforderlichen Komponenten.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Setup von Windows Server

Skype for Business Server erfordert das Windows Server-Betriebssystem und eine Reihe von Voraussetzungen, bevor es installiert werden kann. Ausführliche Informationen zur Planung von Voraussetzungen finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Bei diesem Verfahren wird Windows Server 2012 R2 verwendet. Wenn Sie eine andere Version von Windows Server verwenden, ist die Prozedur möglicherweise etwas anders. 
  
> [!IMPORTANT]
> Bevor Sie beginnen, stellen Sie sicher, dass Windows Server auf dem neuesten Stand ist, indem Sie Windows Update verwenden. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Sehen Sie sich die Video Schritte für **Installationsvoraussetzungen**an:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installieren der erforderlichen Rollen und Funktionen für Front-End-Server

Sie können die erforderlichen Rollen und Funktionen mit dem Server-Manager installieren. 
    
1. Installieren Sie die unter Server Anforderungen aufgeführten erforderlichen Software Features [für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). Die erforderliche Software muss sich auf dem Server befinden, auf dem Skype for Business Server ausgeführt wird.
    
    > [!CAUTION]
    > In Windows Server 2012 R2 werden standardmäßig nicht alle Quelldateien für die erforderlichen Features installiert. Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Medium einfügen und dann **einen alternativen Quell Pfad angeben** , um die erforderlichen Features zu installieren. Die Quelldateien befinden sich im sources\sxs-Verzeichnis. Wenn sich beispielsweise das Windows Server 2012 R2-Medium in Laufwerk D befindet, legen Sie den Pfad auf `d:\sources\sxs`fest. Es ist wichtig, dass Sie über die neuesten Updates von Windows Update verfügen. Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle Voraussetzungen für die erforderlichen Updates manuell installieren. 
  
1. Wenn das Dialogfeld angibt, dass die Installation abgeschlossen ist, müssen Sie den Server neu starten, um den Vorgang abzuschließen.
    
1. Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob die Rollen und Dienste, die installiert wurden, aktualisiert werden.
    
1. Wenn Sie Skype for Business Server Systemsteuerung auf diesem Server verwenden, müssen Sie auch Silverlight installieren. Informationen zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Die Voraussetzungen für Server, die andere Rollen als Front-End-Server ausführen, wie die Rolle von Director, beständiger Chat oder Edge, haben ihre eigenen Voraussetzungen. Ausführliche Informationen zu den genauen Voraussetzungen, die für die einzelnen Servertypen erforderlich sind, finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

