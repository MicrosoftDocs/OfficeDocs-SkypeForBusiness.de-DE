---
title: Installieren von Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten.'
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860586"
---
# <a name="install-skype-for-business-server"></a>Installieren von Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten.
  
Dieser Artikel führt Sie durch eine Beispielinstallation von Skype for Business Server. In diesem Artikel werden nicht alle Verfahren behandelt, die Sie zum Ausführen einer vollständigen Skype for Business Server Installation benötigen. Das Ziel besteht darin, Beispielverfahren in einer eng definierten Topologie bereitzustellen, die grundlegende Meet-and-Share-Funktionen umfasst.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Übersicht über den Installationsprozess für Skype for Business Server

Eine Installation von Skype for Business Server umfasst viele verschiedene Verfahren. Die Verfahren, die Sie benötigen, um Skype for Business Server in Ihrer Umgebung auszuführen, hängen von den Besonderheiten Ihrer Umgebung ab. Wenn Sie z. B. Windows Server für DNS verwenden, profitieren Sie von dem Beispielverfahren zum Hinzufügen eines DNS-Eintrags. Wenn Sie ein anderes System für DNS verwenden, müssen Sie die Verfahren für Ihr bestimmtes DNS-System befolgen. Dies gilt für viele der Verfahren in diesem Abschnitt.
  
Skype for Business Server ist in Standard Edition und Enterprise Edition verfügbar. Der Hauptunterschied besteht darin, dass Standard Edition die in Enterprise Edition enthaltenen Features für hohe Verfügbarkeit nicht unterstützt. 
  
Skype for Business Server ist ein fortschrittliches Produkt, und der genaue Installationsprozess hängt stark von Ihren spezifischen Umständen ab. Dieser Abschnitt führt Sie durch die allgemeinen Schritte zum Installieren des Produkts. Jedes Verfahren kann jedoch je nach Umgebung und Planungsentscheidungen unterschiedlich sein. Für kleine Organisationen kann beispielsweise ein einzelner Server mit Skype for Business Server Standard Edition geeignet sein, während eine große multinationale Organisation möglicherweise 50 Server an Standorten auf der ganzen Welt hat, die für das Produkt vorgesehen sind.
  
> [!NOTE]
> Informationen zu den neuesten kumulativen Updates finden Sie unter [Updates für Skype for Business Server](https://support.microsoft.com/kb/3061064). Nach der Installation des CU1-Patches muss ein Administrator das  `Update-CsAdminRole` Cmdlet ausführen. Dieses Cmdlet ist für den Zugriff auf die neuen GCP-Cmdlets über Remote PowerShell erforderlich.
  
> [!IMPORTANT]
> Die Verfahren in diesem Abschnitt dienen als Beispiel unter Verwendung eines eng definierten Anforderungssatzes und gehen davon aus, dass bereits bestimmte Entscheidungen getroffen wurden. Die eigentlichen Verfahren, die Sie zum Installieren Skype for Business Server benötigen, sind wahrscheinlich sehr unterschiedlich. Verwenden Sie die Verfahren in diesem Abschnitt nur als Beispiel und nicht als Schritt-für-Schritt-Anleitung für die Installation Skype for Business Server in jeder Umgebung. 
  
Um Skype for Business Server zum ersten Mal zu starten, sind acht primäre Schritte erforderlich. Sie sollten wissen, dass die Beispielprotektionen in diesem Abschnitt nicht die einzigen Prozeduren sind, die zum Installieren von Skype for Business Server erforderlich sind. Die folgenden acht Schritte sind nur Beispiele, die Ihnen helfen, den allgemeinen Prozess besser zu verstehen und eine grundlegende Arbeitsumgebung einzurichten. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Die acht Schritte lauten:
  
![Übersicht über den Installationsprozess.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installationsvoraussetzungen für Skype for Business Server](install-prerequisites.md): Installieren Sie die erforderlichen Komponenten auf allen Servern, aus denen die Skype for Business Server Topologie besteht. Beachten Sie, dass die Voraussetzungen nicht für alle Rollen identisch sind. Beispielsweise verfügen Server, die die Front-End-Rolle bereitstellen, über eine Reihe von Voraussetzungen, und Server, die eine Directorrolle bereitstellen, über einen anderen Satz von Voraussetzungen. Weitere Informationen finden Sie in der Planungsdokumentation zu voraussetzungen.
    
- [Erstellen einer Dateifreigabe in Skype for Business Server](create-a-file-share.md): Erstellen Sie eine Dateifreigabe, die von Servern in der Skype for Business Server Topologie verwendet wird.
    
- [Installieren von Verwaltungstools in Skype for Business Server](install-administrative-tools.md): Zu den Verwaltungstools gehören der Topologie-Generator und Systemsteuerung. Sie müssen die Verwaltungstools auf mindestens einem Server in der Topologie oder einer 64-Bit-Verwaltungsarbeitsstation installieren, auf der eine Windows Betriebssystemversion ausgeführt wird, die für Skype for Business Server unterstützt wird.
    
- [Vorbereiten von Active Directory für Skype for Business Server](prepare-active-directory.md): Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory-Domäne für die Arbeit mit Skype for Business Server vorbereiten. Sie können dies über den Bereitstellungs-Assistenten tun, und dies erfolgt nur einmal für die Domäne. Dies liegt daran, dass der Prozess Gruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal tun.
    
- [Erstellen von DNS-Einträgen für Skype for Business Server](create-dns-records.md): Damit Skype for Business Server ordnungsgemäß funktioniert, müssen eine Reihe von DNS-Einstellungen vorhanden sein. Dies ist so, dass Clients wissen, wie sie auf die Dienste zugreifen und die Server voneinander wissen. Diese Einstellungen müssen nur einmal pro Bereitstellung abgeschlossen werden, da sie nach dem Zuweisen eines DNS-Eintrags in der gesamten Domäne verfügbar sind.
    
- [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server](create-and-publish-new-topology.md): Bevor Sie das Skype for Business Server System auf jedem server in der Topologie installieren können, müssen Sie eine Topologie erstellen und veröffentlichen. Wenn Sie eine Topologie veröffentlichen, laden Sie die Topologieinformationen in die Zentrale Verwaltung Store Datenbank. Wenn dies ein Enterprise Edition-Pool ist, erstellen Sie die zentrale Verwaltungsdatenbank Store, wenn Sie zum ersten Mal eine neue Topologie veröffentlichen. Wenn dies Standard Edition ist, müssen Sie den Prozess "Vorbereiten des ersten Standard Edition-Servers" aus dem Bereitstellungs-Assistenten ausführen, bevor Sie eine Topologie veröffentlichen. Dadurch wird die Standard Edition vorbereitet, indem eine SQL Server Express Edition-Instanz installiert und die zentrale Verwaltungs-Store erstellt wird.
    
- [Installieren sie Skype for Business Server auf Servern in der Topologie](install-skype-for-business-server.md): Sobald die Topologie in die zentrale Verwaltungs-Store geladen wurde und Active Directory weiß, welche Server welche Rollen ausführen, müssen Sie das Skype for Business Server System auf jedem der Server in der Topologie installieren.
    
- [Überprüfen Sie die Topologie in Skype for Business Server](verify-the-topology.md): Nachdem Sie die Topologie veröffentlicht und die Skype for Business Server Systemkomponenten auf jedem der Server in der Topologie installiert haben, können Sie überprüfen, ob die Topologie wie erwartet funktioniert. Dazu gehört die Überprüfung, ob die Konfiguration an alle Active Directory-Server weitergegeben wurde, damit die gesamte Domäne weiß, dass Skype for Business in der Domäne verfügbar ist.
    

