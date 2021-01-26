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
description: 'Zusammenfassung: Erfahren Sie mehr über die Server und Serverrollen, die Sie vor der Installation von Skype for Business Server konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801715"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installieren der erforderlichen Komponenten für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Server und Serverrollen, die Sie vor der Installation von Skype for Business Server konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center herunter.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Die Installation der erforderlichen Komponenten besteht aus dem Einrichten von Windows Server durch Installieren der erforderlichen Rollen und Features auf den einzelnen Servern in der Topologie. Die Anforderungen basieren auf der Rolle, die der Server in der Topologie erfüllt. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die Installation der erforderlichen Komponenten ist Schritt 1 von 8.
  
![Übersichtsdiagramm – Installationsvoraussetzungen.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Einrichten von Windows Server

Skype for Business Server erfordert das Windows Server-Betriebssystem und eine Reihe von Voraussetzungen, bevor es installiert werden kann. Einzelheiten zur Planung der Voraussetzungen finden Sie unter ["Serveranforderungen für Skype for Business Server".](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> In diesem Verfahren wird Windows Server 2012 R2 verwendet. Wenn Sie eine andere Version von Windows Server verwenden, kann das Verfahren etwas anders sein. 
  
> [!IMPORTANT]
> Bevor Sie beginnen, stellen Sie mithilfe von Windows Update sicher, dass Windows Server auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Sehen Sie sich die Videoschritte zur **Installation der erforderlichen Komponenten an:**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installieren der erforderlichen Rollen und Features für Front-End-Server

Sie können die erforderlichen Rollen und Features mithilfe des Server-Managers installieren. 
    
1. Installieren Sie die erforderlichen Softwarefeatures, die in [den Serveranforderungen für Skype for Business Server aufgeführt sind.](../../../SfBServer2019/plan/system-requirements.md) Die erforderliche Software muss sich auf dem Server befinden, auf dem Skype for Business Server ausgeführt wird.
    
    > [!CAUTION]
    > Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien für die erforderlichen Features. Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das  Windows Server 2012 -R2-Medium einfügen und einen alternativen Quellpfad angeben, um die erforderlichen Features zu installieren. Die Quelldateien befinden sich im Verzeichnis "sources\sxs". Wenn sich das Windows Server 2012 R2-Medium beispielsweise auf Laufwerk D befindet, würden Sie den Pfad auf `d:\sources\sxs` festlegen. Es ist wichtig, dass Sie über die neuesten Updates von Windows Update verfügen. Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle erforderlichen Komponenten für die erforderlichen Updates manuell installieren. 
  
1. Wenn das Dialogfeld angibt, dass die Installation abgeschlossen ist, müssen Sie den Server neu starten, um den Vorgang abzuschließen.
    
1. Führen **Sie Windows Update** erneut aus, um zu überprüfen, ob Updates für die installierten Rollen und Dienste verfügbar sind.
    
1. Wenn Sie die Skype for Business Server-Systemsteuerung auf diesem Server verwenden, müssen Sie auch Silverlight installieren. Informationen zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Die Voraussetzungen für Server, die andere Rollen als Front-End-Server ausführen, z. B. die Rolle des Director, des beständigen Chats oder des Edgeservers, müssen eigene Voraussetzungen erfüllen. Details zu den genauen Voraussetzungen, die für jeden Servertyp erforderlich sind, finden Sie unter ["Serveranforderungen für Skype for Business Server".](../../../SfBServer2019/plan/system-requirements.md) 
  

