---
title: Installieren der erforderlichen Komponenten für Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: ffd286262686d1faf55591f88df75b0e0323acc2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972920"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installieren der erforderlichen Komponenten für Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Die Installation der erforderlichen Softwarekomponenten besteht in der Einrichtung von Windows Server durch Installation der erforderlichen Rollen und Funktionen auf jedem Server in der Topologie. Welche Komponenten erforderlich sind, hängt von der Rolle des jeweiligen Servers in der Topologie ab. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Die Installation der erforderlichen Softwarekomponenten ist Schritt 1 von 8.
  
![Übersichtsdiagramm – Voraussetzungen für die Installation](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Einrichten von Windows Server

Skype für Business Server erfordert das Betriebssystem Windows Server und eine Anzahl von erforderlichen Komponenten, bevor es installiert werden kann. Weitere Informationen zur Planung der erforderlichen Komponenten finden Sie unter [Server-Anforderungen für Skype für Business Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Das nachfolgende Verfahren basiert auf Windows Server 2012 R2. Wenn Sie eine andere Windows Server-Version verwenden, kann die Vorgehensweise leicht abweichen. 
  
> [!IMPORTANT]
> Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Schauen Sie sich das Video mit den Schritten zum **Imstallieren der erforderlichen Komponenten** an:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installieren der erforderlichen Rollen und Funktionen für Front-End-Server

Sie können der erforderlichen Rollen und Funktionen, die mit dem Server-Manager installieren. 
    
1. Installieren Sie die erforderliche Software Features, die in [Server-Anforderungen für Skype für Business Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)aufgelistet. Die erforderliche Software muss auf dem Server, auf denen Skype für Business Server ausgeführt wird.
    
    > [!CAUTION]
    > Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien der erforderlichen Funktionen. Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Installationsmedium einlegen und **Alternativen Quellpfad angeben** auswählen, um die erforderlichen Funktionen zu installieren. Die Quelldateien befinden sich im Verzeichnis „sources\sxs“. Wenn das Windows Server 2012 R2-Medium beispielsweise in Laufwerk D eingelegt wurde, würde der Pfad `d:\sources\sxs` lauten. Es ist wichtig, dass Sie die neuesten Updates von Windows Update verfügen. Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle erforderlichen Komponenten über die erforderlichen Updates manuell zu installieren. 
  
1. Wenn der Abschluss der Installation angezeigt wird, müssen Sie den Server neu starten, um den Vorgang abzuschließen.
    
1. Führen Sie **Windows Update** erneut aus, um zu prüfen, ob es ein Update für die installierten Rollen und Dienste gibt.
    
1. Wenn Sie Skype Business Server-Systemsteuerung auf diesem Server verwenden müssen Sie auch Silverlight installieren. Zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Für Server, die eine andere Funktion als die eines Front-End-Servers haben, z. B. Director, Persistent Chat oder Edge, sind eigene Softwarekomponenten erforderlich. Ausführliche Informationen zum die genauen erforderlichen Komponenten erforderlich, die für jeden Servertyp finden Sie unter [Anforderungen für Skype für Business Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

