---
title: Installieren der erforderlichen Komponenten für Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: Erfahren Sie mehr über die Server- und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren.'
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860736"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installieren der erforderlichen Komponenten für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Server- und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren.
  
Die Installation der erforderlichen Komponenten besteht darin, Windows Server einzurichten, indem die erforderlichen Rollen und Features auf jedem der Server in der Topologie installiert werden. Die Anforderungen basieren auf der Rolle, die der Server in der Topologie erfüllt. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Die Installation der erforderlichen Komponenten ist Schritt 1 von 8.
  
![Übersichtsdiagramm – Installationsvoraussetzungen.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Setup Windows Server

Skype for Business Server erfordert das Windows Serverbetriebssystem und eine Reihe von Voraussetzungen, bevor es installiert werden kann. Ausführliche Informationen zur Planung von Voraussetzungen finden Sie unter [Serveranforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Bei diesem Verfahren wird Windows Server 2012 R2 verwendet. Wenn Sie eine andere Version von Windows Server verwenden, kann sich das Verfahren geringfügig unterscheiden. 
  
> [!IMPORTANT]
> Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Schauen Sie sich die **Videoschritte für die Installation der erforderlichen Komponenten an**:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installieren der erforderlichen Rollen und Features für Front-End-Server

Sie können die erforderlichen Rollen und Features mithilfe von Server-Manager installieren. 
    
1. Installieren Sie die erforderlichen Softwarefeatures, die in [den Serveranforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md) aufgeführt sind. Die erforderliche Software muss sich auf dem Server befinden, auf dem Skype for Business Server ausgeführt wird.
    
    > [!CAUTION]
    > Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien für die erforderlichen Features. Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie die Windows Server 2012 R2-Medien einfügen und **einen alternativen Quellpfad angeben** auswählen, um die erforderlichen Features zu installieren. Die Quelldateien befinden sich im Verzeichnis "sources\sxs". Wenn sich beispielsweise das Windows Server 2012 R2-Medium in Laufwerk D befindet, würden Sie den Pfad auf `d:\sources\sxs`festlegen. Es ist wichtig, dass Sie über die neuesten Updates von Windows Update verfügen. Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle Voraussetzungen für die erforderlichen Updates manuell installieren. 
  
1. Wenn das Dialogfeld anzeigt, dass die Installation abgeschlossen ist, müssen Sie den Server neu starten, um den Vorgang abzuschließen.
    
1. Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob Updates für die installierten Rollen und Dienste vorhanden sind.
    
1. Wenn Sie Skype for Business Server Systemsteuerung auf diesem Server verwenden, müssen Sie auch Silverlight installieren. Informationen zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Die Voraussetzungen für Server, die andere Rollen als den Front-End-Server ausführen, z. B. die Rolle des Director, des beständigen Chats oder des Edgeservers, haben ihre eigenen Voraussetzungen. Ausführliche Informationen zu den genauen Voraussetzungen, die für jeden Servertyp erforderlich sind, finden Sie unter [Serveranforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

