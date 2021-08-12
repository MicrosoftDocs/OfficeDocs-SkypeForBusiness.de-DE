---
title: Installieren der erforderlichen Komponenten für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Erfahren Sie mehr über die Server und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 5d44a95be8c05b8a171b7bd72b9aaeaf19ff8fbc67247388e89cfea16dc6e21a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280300"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installieren der erforderlichen Komponenten für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Server und Serverrollen, die Sie konfigurieren müssen, bevor Sie Skype for Business Server installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Die Installation der erforderlichen Komponenten besteht darin, Windows Server einzurichten, indem die erforderlichen Rollen und Features auf jedem Server in der Topologie installiert werden. Die Anforderungen basieren auf der Rolle, die der Server in der Topologie erfüllen wird. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die Installation der erforderlichen Komponenten ist Schritt 1 von 8.
  
![Übersichtsdiagramm – Installationsvoraussetzungen.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Einrichten Windows Servers

Skype for Business Server erfordert das Windows Server-Betriebssystem und eine Reihe von Voraussetzungen, bevor es installiert werden kann. Ausführliche Informationen zur Planung der Voraussetzungen finden Sie unter [Serveranforderungen für Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> In diesem Verfahren wird Windows Server 2012 R2 verwendet. Wenn Sie eine andere Version von Windows Server verwenden, kann sich das Verfahren geringfügig unterscheiden. 
  
> [!IMPORTANT]
> Bevor Sie beginnen, stellen Sie mithilfe von Windows Update sicher, dass Windows Server auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Sehen Sie sich die Videoschritte für **die Installationsvoraussetzungen an:**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installieren der erforderlichen Rollen und Features für Front-End-Server

Sie können die erforderlichen Rollen und Features mit dem Server-Manager installieren. 
    
1. Installieren Sie die erforderlichen Softwarefeatures, die in den [Serveranforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md)aufgeführt sind. Die erforderliche Software muss sich auf dem Server befinden, auf dem Skype for Business Server ausgeführt wird.
    
    > [!CAUTION]
    > Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien für die erforderlichen Features. Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie die Windows Server 2012 R2-Medien einfügen und **einen alternativen Quellpfad angeben** auswählen, um die erforderlichen Features zu installieren. Die Quelldateien befinden sich im Verzeichnis "sources\sxs". Wenn sich das Windows Server 2012 R2-Medium beispielsweise auf Laufwerk D befindet, legen Sie den Pfad auf `d:\sources\sxs` fest. Es ist wichtig, dass Sie über die neuesten Updates von Windows Update verfügen. Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle erforderlichen Komponenten für die erforderlichen Updates manuell installieren. 
  
1. Wenn das Dialogfeld angibt, dass die Installation abgeschlossen ist, müssen Sie den Server neu starten, um den Vorgang abzuschließen.
    
1. Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob Updates für die installierten Rollen und Dienste vorhanden sind.
    
1. Wenn Sie Skype for Business Server Systemsteuerung auf diesem Server verwenden, müssen Sie auch Silverlight installieren. Informationen zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight.](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> Die Voraussetzungen für Server, die andere Rollen als den Front-End-Server ausführen, z. B. die Rolle des Director, des beständigen Chats oder edge, haben ihre eigenen Voraussetzungen. Ausführliche Informationen zu den genauen Voraussetzungen, die für jeden Servertyp erforderlich sind, finden Sie unter [Serveranforderungen für Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) 
  

