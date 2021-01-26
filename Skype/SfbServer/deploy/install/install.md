---
title: Installieren von Skype for Business Server
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
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: ef562a56e1129481954f9345a46483156bd1202f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801915"
---
# <a name="install-skype-for-business-server"></a>Installieren von Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) herunter.
  
Dieser Artikel führt Sie durch eine Beispielinstallation von Skype for Business Server. In diesem Artikel werden nicht alle Verfahren behandelt, die Sie zum Ausführen einer vollständigen Skype for Business Server-Installation benötigen. Ziel ist es, Beispielprozeduren in einer eng definierten Topologie bereitzustellen, die grundlegende Meet-and-Share-Funktionen umfasst.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Übersicht über den Installationsprozess für Skype for Business Server

Eine Installation von Skype for Business Server umfasst viele verschiedene Verfahren. Die Verfahren, die Sie zum Ausführen von Skype for Business Server in Ihrer Umgebung benötigen, hängen von den Besonderheiten Ihrer Umgebung ab. Wenn Sie beispielsweise Windows Server für DNS verwenden, profitieren Sie von dem Beispielverfahren zum Hinzufügen eines DNS-Eintrags. Wenn Sie ein anderes System für DNS verwenden, müssen Sie die Verfahren für Ihr bestimmtes DNS-System befolgen. Dies gilt für viele der Verfahren in diesem Abschnitt.
  
Skype for Business Server ist in Standard Edition und Enterprise Edition verfügbar. Der Hauptunterschied besteht darin, dass die Standard Edition die in der Enterprise Edition enthaltenen Features für hohe Verfügbarkeit nicht unterstützt. 
  
Skype for Business Server ist ein erweitertes Produkt, und der genaue Installationsvorgang hängt stark von Ihren spezifischen Umständen ab. Dieser Abschnitt führt Sie durch die allgemeinen Schritte zum Installieren des Produkts. Jedes Verfahren kann jedoch je nach Umgebung und Planungsentscheidungen unterschiedlich sein. Beispielsweise kann für kleine Organisationen ein einzelner Server geeignet sein, skype for Business Server Standard Edition zu verwenden, während eine große multinationale Organisation über 50 Server an Standorten auf der ganzen Welt verfügen kann, die ausschließlich für das Produkt zuständig sind.
  
> [!NOTE]
> Informationen zu den neuesten kumulativen Updates finden Sie unter [Updates für Skype for Business Server](https://support.microsoft.com/kb/3061064). Nach der Installation des CU1-Patches muss ein Administrator das  `Update-CsAdminRole` Cmdlet ausführen. Dieses Cmdlet ist für den Zugriff auf die neuen GCP-Cmdlets über Remote PowerShell erforderlich.
  
> [!IMPORTANT]
> Die Verfahren in diesem Abschnitt dienen als Beispiel für eine eng definierte Reihe von Anforderungen und gehen davon aus, dass bereits spezifische Entscheidungen getroffen wurden. Die tatsächlichen Verfahren, die Sie zum Installieren von Skype for Business Server benötigen, sind wahrscheinlich sehr unterschiedlich. Verwenden Sie die Verfahren in diesem Abschnitt nur als Beispiel und nicht als schrittweise Anleitung für die Installation von Skype for Business Server in jeder Umgebung. 
  
Das erste Einrichten von Skype for Business Server umfasst acht primäre Schritte. Sie sollten wissen, dass die Beispielprozeduren in diesem Abschnitt nicht die einzigen Verfahren sind, die für die Installation von Skype for Business Server erforderlich sind. Die folgenden acht Schritte sind einfach Beispiele, die Ihnen dabei helfen, den gesamtprozess besser zu verstehen und eine grundlegende Arbeitsumgebung zu erstellen und zu starten. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die acht Schritte sind:
  
![Übersicht über den Installationsvorgang.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installieren Sie die erforderlichen Komponenten für Skype for Business Server:](install-prerequisites.md) Installieren Sie die erforderlichen Komponenten auf allen Servern, aus denen die Skype for Business Server-Topologie ist. Beachten Sie, dass die Voraussetzungen nicht für alle Rollen identisch sind. Beispielsweise gelten für Server, die die Front-End-Rolle bereitstellen, eine Reihe von Voraussetzungen, und für Server, die eine Directorrolle bereitstellen, gelten andere Voraussetzungen. Weitere Informationen finden Sie in der Dokumentation zur Planung der Voraussetzungen.
    
- [Erstellen Sie eine Dateifreigabe in Skype for Business Server:](create-a-file-share.md) Erstellen Sie eine Dateifreigabe, die von Servern in der gesamten Skype for Business Server-Topologie verwendet wird.
    
- [Installieren von Verwaltungstools in Skype for Business Server:](install-administrative-tools.md) Die Verwaltungstools umfassen den Topologie-Generator und die Systemsteuerung. Sie müssen die Verwaltungstools auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation mit einer Windows-Betriebssystemversion installieren, die für Skype for Business Server unterstützt wird.
    
- [Vorbereiten von Active Directory für Skype for Business Server:](prepare-active-directory.md) Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory-Domäne für die Zusammenarbeit mit Skype for Business Server vorbereiten. Sie können dies über den Bereitstellungsassistenten tun, und dies erfolgt nur einmal für die Domäne. Dies liegt daran, dass der Prozess Gruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal tun.
    
- [Erstellen von DNS-Einträgen](create-dns-records.md) für Skype for Business Server: Damit Skype for Business Server ordnungsgemäß funktioniert, müssen eine Reihe von DNS-Einstellungen vorhanden sein. Dies bedeutet, dass Clients wissen, wie sie auf die Dienste zugreifen können, und die Server wissen, wie sie sich gegenseitig kennen. Diese Einstellungen müssen nur einmal pro Bereitstellung abgeschlossen werden, da nach dem Zuweisen eines DNS-Eintrags dieser in der gesamten Domäne verfügbar ist.
    
- Erstellen und Veröffentlichen einer neuen [Topologie in Skype for Business Server:](create-and-publish-new-topology.md) Bevor Sie das Skype for Business Server System auf jedem Server in der Topologie installieren können, müssen Sie eine Topologie erstellen und veröffentlichen. Wenn Sie eine Topologie veröffentlichen, laden Sie die Topologieinformationen in die Datenbank des zentralen Verwaltungsspeichers. Wenn es sich um einen Enterprise Edition-Pool handelt, erstellen Sie die Datenbank des zentralen Verwaltungsspeichers, wenn Sie zum ersten Mal eine neue Topologie veröffentlichen. Wenn dies Standard Edition ist, müssen Sie den Prozess "Ersten Standard Edition-Server vorbereiten" im Bereitstellungsassistenten ausführen, bevor Sie eine Topologie veröffentlichen. Dadurch wird die Standard Edition vorbereitet, indem eine SQL Server Express Edition installiert und der zentrale Verwaltungsspeicher erstellt wird.
    
- Installieren Sie Skype for Business Server auf Servern in der [Topologie:](install-skype-for-business-server.md) Sobald die Topologie in den zentralen Verwaltungsspeicher geladen wurde und Active Directory weiß, welche Server welche Rollen übernehmen werden, müssen Sie das Skype for Business Server System auf jedem Server in der Topologie installieren.
    
- Überprüfen Sie die [Topologie in Skype for Business Server:](verify-the-topology.md) Nachdem Sie die Topologie veröffentlicht und die Skype for Business Server-Systemkomponenten auf jedem Server in der Topologie installiert haben, können Sie überprüfen, ob die Topologie wie erwartet funktioniert. Dazu gehört die Überprüfung, ob die Konfiguration an alle Active Directory-Server verteilt wurde, damit die gesamte Domäne weiß, dass Skype for Business in der Domäne verfügbar ist.
    

