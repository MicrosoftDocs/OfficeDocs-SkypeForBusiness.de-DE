---
title: Installieren der erforderlichen Komponenten für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server 2015 konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Installieren der erforderlichen Komponenten für Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server 2015 konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Die Installation der erforderlichen Softwarekomponenten besteht in der Einrichtung von Windows Server durch Installation der erforderlichen Rollen und Funktionen auf jedem Server in der Topologie. Welche Komponenten erforderlich sind, hängt von der Rolle des jeweiligen Servers in der Topologie ab. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Die Installation der erforderlichen Softwarekomponenten ist Schritt 1 von 8.
  
![Übersichtsdiagramm – Voraussetzungen für die Installation](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Einrichten von Windows Server

Skype für Business Server 2015 erfordert das Betriebssystem Windows Server und eine Anzahl von erforderlichen Komponenten, bevor es installiert werden kann. Weitere Informationen zur Planung der erforderlichen Komponenten finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Das nachfolgende Verfahren basiert auf Windows Server 2012 R2. Wenn Sie eine andere Windows Server-Version verwenden, kann die Vorgehensweise leicht abweichen. 
  
> [!IMPORTANT]
> Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Schauen Sie sich das Video mit den Schritten zum **Imstallieren der erforderlichen Komponenten** an:
  
![Ihr Browser unterstützt kein Video. Installieren von Microsoft Silverlight, Adobe Flash Player oder Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installieren der erforderlichen Rollen und Funktionen für Front-End-Server

1. Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.
    
2. Lesen Sie die Seite **Bevor Sie beginnen** , um sich bei der Installation von Rollen und Features in Windows Server vertraut zu machen, und klicken Sie dann auf **Weiter**.
    
3. Wählen Sie **Rollenbasierte oder funktionsbasierte Installation** aus und klicken Sie auf **Weiter**.
    
4. Wählen Sie den Server, auf dem Sie werden Installieren von Skype für Business Server 2015, und klicken Sie auf **Weiter**.
    
5. Wählen Sie die Rolle **Webserver (IIS)** aus und klicken Sie im daraufhin geöffneten Fenster auf **Funktionen hinzufügen** und dann auf **Weiter**.
    
6. Stellen Sie sicher, die Software-Features aufgeführt, die in der [Software, die vor einem Skype für Business Server 2015 Bereitstellung installiert werden muss,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) auf dem Server, auf denen Skype für Business Server 2015 ausgeführt wird. Hier ist eine verkürzte Liste:
    
   - .NET Framework-Features
    
   - WCF-Dienste
    
   - HTTP-Aktivierung
    
    > [!NOTE]
    > HTTP-Aktivierung erfordert zusätzliche Funktionen. Klicken Sie im Warndialogfeld, das bei Auswahl von „HTTP-Aktivierung“ angezeigt wird, auf **Funktionen hinzufügen**.
  
   - Media Foundation (von Front-End-Servern und Standard Edition-Servern für Konferenzen verwendet erforderlich.)
    
   - Remoteserver-Verwaltungstools
    
   - Verwaltungstools für Rollen
    
   - AD DS 
    
   - AD LDS
    
   - Windows Identity Foundation 3.5
    
7. Klicken Sie auf **Weiter**, um mit dem Assistenten fortzufahren.
    
8. Lesen Sie die Anmerkungen zur **Webserverrolle (IIS)** und klicken Sie auf **Weiter**.
    
9. Wählen Sie folgende **Webserver (IIS)-Rollendienste** aus.
    
   - Allgemeine HTTP-Funktionen
    
   - Standarddokument
    
   - Verzeichnissuche
    
   - HTTP-Fehler
    
   - Statischer Inhalt
    
   - Integrität und Diagnose
    
   - HTTP-Protokollierung
    
   - Protokollierungstools
    
   - Ablaufverfolgung
    
   - Leistung
    
   - Komprimierung statischer Inhalte
    
   - Komprimierung dynamischer Inhalte
    
   - Sicherheit
    
   - Anforderungsfilterung
    
   - Clientzertifikatzuordnungs-Authentifizierung
    
   - Windows-Authentifizierung
    
   - Anwendungsentwicklung
    
   - .NET-Erweiterbarkeit 3.5
    
   - .NET-Erweiterbarkeit 4.5
    
   - ASP.NET 3.5
    
   - ASP.NET 4.5
    
   - ISAPI-Erweiterungen
    
   - ISAPI-Filter
    
   - Verwaltungstools
    
   - IIS-Verwaltungskonsole
    
   - IIS-Verwaltungsskripts und -tools
    
10. Klicken Sie auf **Weiter**, um mit dem Assistenten fortzufahren.
    
11. Prüfen Sie die Installationsauswahl, um sicherzustellen, dass alle Anforderungen erfüllt sind, und klicken Sie auf **Installieren**.
    
    > [!CAUTION]
    > Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien der erforderlichen Funktionen. Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Installationsmedium einlegen und **Alternativen Quellpfad angeben** auswählen, um die erforderlichen Funktionen zu installieren. Die Quelldateien befinden sich im Verzeichnis „sources\sxs“. Wenn das Windows Server 2012 R2-Medium beispielsweise in Laufwerk D eingelegt wurde, würde der Pfad `d:\sources\sxs` lauten. > Es ist wichtig, dass Sie die neuesten Updates von Windows Update verfügen. Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle erforderlichen Komponenten über die erforderlichen Updates manuell zu installieren. 
  
12. Wenn der Abschluss der Installation angezeigt wird, müssen Sie den Server neu starten, um den Vorgang abzuschließen.
    
13. Führen Sie **Windows Update** erneut aus, um zu prüfen, ob es ein Update für die installierten Rollen und Dienste gibt.
    
14. Wenn Sie Skype Business Server-Systemsteuerung auf diesem Server verwenden müssen Sie auch Silverlight installieren. Zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).
    
Die erforderlichen Softwarekomponenten können über den nachfolgend aufgeführten PowerShell-Befehl installiert werden. Der Befehl sucht Quelldateien in einer spezifischen Reihenfolge. Wenn eine Verbindung mit dem Internet besteht, greift der Befehl auf Windows Update zu. Ohne Verbindung mit dem Internet müssen Sie dafür sorgen, dass alle Quelldateien für den Befehl zur Verfügung stehen. Weitere Informationen zum Verwenden von PowerShell-Rollen und-Features installieren finden Sie unter [installieren oder Deinstallieren von Rollen, Rollendienste oder Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) und [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx). Denken Sie daran, nach Installation der erforderlichen Softwarekomponenten Windows Update erneut auszuführen, selbst wenn Sie den PowerShell-Befehl verwendet haben.
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> Für Server, die eine andere Funktion als die eines Front-End-Servers haben, z. B. Director, Persistent Chat oder Edge, sind eigene Softwarekomponenten erforderlich. Ausführliche Informationen zum die genauen erforderlichen Komponenten erforderlich, die für jeden Servertyp finden Sie unter [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

