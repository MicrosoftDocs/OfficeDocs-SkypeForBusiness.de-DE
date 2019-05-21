---
title: Installieren von Voraussetzungen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: informieren Sie sich über die Server und Serverrollen, die Sie vor der Installation von Skype for Business Server konfigurieren müssen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: 7b2369af5a95d027edff0db291af37c710813465
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306605"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installieren von Voraussetzungen für Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die Server und Serverrollen, die Sie vor der Installation von Skype for Business Server konfigurieren müssen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Die Installation der erforderlichen Softwarekomponenten besteht in der Einrichtung von Windows Server durch Installation der erforderlichen Rollen und Funktionen auf jedem Server in der Topologie. Welche Komponenten erforderlich sind, hängt von der Rolle des jeweiligen Servers in der Topologie ab. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Die Installation der erforderlichen Softwarekomponenten ist Schritt 1 von 8.
  
![Übersichtsdiagramm – Voraussetzungen für die Installation](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Einrichten von Windows Server

Skype for Business Server erfordert das Windows Server-Betriebssystem und eine Reihe von Voraussetzungen, bevor es installiert werden kann. Einzelheiten zur Planung von Voraussetzungen finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Das nachfolgende Verfahren basiert auf Windows Server 2012 R2. Wenn Sie eine andere Windows Server-Version verwenden, kann die Vorgehensweise leicht abweichen. 
  
> [!IMPORTANT]
> Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Schauen Sie sich das Video mit den Schritten zum **Imstallieren der erforderlichen Komponenten** an:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installieren der erforderlichen Rollen und Funktionen für Front-End-Server

Sie können die erforderlichen Rollen und Features mit dem Server-Manager installieren. 
    
1. Installieren Sie die erforderlichen Software Features, die unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md)aufgelistet sind. Die erforderliche Software muss sich auf dem Server befinden, auf dem Skype for Business Server ausgeführt wird.
    
    > [!CAUTION]
    > Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien der erforderlichen Funktionen. Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Installationsmedium einlegen und **Alternativen Quellpfad angeben** auswählen, um die erforderlichen Funktionen zu installieren. Die Quelldateien befinden sich im Verzeichnis „sources\sxs“. Wenn sich beispielsweise das Windows Server 2012 R2-Medium auf Laufwerk D befindet, würden Sie den Pfad auf `d:\sources\sxs`festzulegen. Es ist wichtig, dass Sie über die neuesten Updates von Windows Update verfügen. Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle Voraussetzungen für die erforderlichen Updates manuell installieren. 
  
1. Wenn der Abschluss der Installation angezeigt wird, müssen Sie den Server neu starten, um den Vorgang abzuschließen.
    
1. Führen Sie **Windows Update** erneut aus, um zu prüfen, ob es ein Update für die installierten Rollen und Dienste gibt.
    
1. Wenn Sie die Skype for Business Server-Systemsteuerung auf diesem Server verwenden, müssen Sie auch Silverlight installieren. Informationen zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Für Server, die eine andere Funktion als die eines Front-End-Servers haben, z. B. Director, Persistent Chat oder Edge, sind eigene Softwarekomponenten erforderlich. Details zu den genauen Voraussetzungen, die für die einzelnen Servertypen erforderlich sind, finden Sie unter [Server Anforderungen für Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

