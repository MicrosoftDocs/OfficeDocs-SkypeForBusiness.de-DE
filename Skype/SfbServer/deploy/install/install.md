---
title: Installieren von Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042382"
---
# <a name="install-skype-for-business-server"></a>Installieren von Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)unter: herunter.
  
In diesem Artikel werden Sie durch eine Beispielinstallation von Skype for Business Server geleitet. In diesem Artikel wird nicht versucht, alle Verfahren abzudecken, die Sie zum Ausführen einer vollständigen Skype for Business Server Installation benötigen. Ziel ist es, Beispiel Prozeduren in einer eng definierten Topologie mit grundlegenden Funktionen für die Erfüllung und Freigabe bereitzustellen.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Übersicht über den Installationsvorgang für Skype for Business Server

Eine Installation von Skype for Business Server umfasst viele verschiedene Verfahren. Die Verfahren, die Sie benötigen, um Skype for Business Server in Ihrer Umgebung auszuführen, hängen von den Besonderheiten Ihrer Umgebung ab. Wenn Sie beispielsweise Windows Server für DNS verwenden, können Sie das Beispielverfahren zum Hinzufügen eines DNS-Eintrags nutzen. Wenn Sie ein anderes System für DNS verwenden, müssen Sie die Verfahren für ihr bestimmtes DNS-System befolgen. Dies gilt für viele der Verfahren in diesem Abschnitt.
  
Skype for Business Server ist in Standard Edition und Enterprise Edition verfügbar. Der Hauptunterschied besteht darin, dass die Standard Edition die in Enterprise Edition enthaltenen Features für hohe Verfügbarkeit nicht unterstützt. 
  
Skype for Business Server ist ein erweitertes Produkt, und der genaue Installationsvorgang hängt sehr stark von ihren spezifischen Gegebenheiten ab. In diesem Abschnitt werden die allgemeinen Schritte zum Installieren des Produkts erläutert. Jedes Verfahren kann jedoch je nach ihrer Umgebung und ihren Planungsentscheidungen unterschiedlich sein. Beispielsweise kann für kleine Organisationen ein einzelner Server mit Skype for Business Server Standard Edition geeignet sein, während eine große multinationale Organisation möglicherweise über 50-Server an Standorten auf der ganzen Welt verfügt, die dem Produkt gewidmet sind.
  
> [!NOTE]
> Informationen zu den neuesten kumulativen Updates finden Sie unter [Updates für Skype for Business Server](https://support.microsoft.com/kb/3061064). Nach der Installation des ku1-Patches muss ein Administrator das `Update-CsAdminRole` Cmdlet ausführen. Dieses Cmdlet ist für den Zugriff auf die neuen Clinical-Cmdlets über Remote-PowerShell erforderlich.
  
> [!IMPORTANT]
> Die Verfahren in diesem Abschnitt dienen als Beispiel für die Verwendung eines eng definierten Satzes von Anforderungen und nehmen an, dass bereits konkrete Entscheidungen getroffen wurden. Die tatsächlichen Verfahren, die Sie zum Installieren von Skype for Business Server benötigen, sind wahrscheinlich sehr unterschiedlich. Verwenden Sie die Verfahren in diesem Abschnitt nur als Beispiel und nicht als Schritt-für-Schritt-Anleitung für die Installation von Skype for Business Server in jeder Umgebung. 
  
Das erste Skype for Business Server zum ersten Mal ausgeführt wird, umfasst acht primäre Schritte. Sie sollten verstehen, dass die Beispielverfahren in diesem Abschnitt nicht die einzigen Verfahren sind, die für die Installation von Skype for Business Server erforderlich sind. Die folgenden acht Schritte sind einfach Beispiele, die Ihnen helfen, den Gesamtprozess besser zu verstehen und eine grundlegende Arbeitsumgebung in Betrieb zu nehmen. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Die acht Schritte sind:
  
![Übersicht über den Installationsprozess.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installieren Sie die Voraussetzungen für Skype for Business Server](install-prerequisites.md) : Installieren Sie die erforderlichen Komponenten auf allen Servern, die die Skype for Business Server Topologie bilden. Beachten Sie, dass die Voraussetzungen für alle Rollen nicht identisch sind. Beispielsweise verfügen Server, die die Front-End-Rolle bereitstellen, über eine Reihe von Voraussetzungen, und Server, die eine Director-Rolle bereitstellen, haben einen anderen Voraussetzungen. Weitere Informationen finden Sie unter Voraussetzungs Planungsdokumentation.
    
- [Erstellen Sie eine Dateifreigabe in Skype for Business Server](create-a-file-share.md) : Erstellen einer Dateifreigabe, die von Servern in der Skype for Business Server Topologie verwendet wird.
    
- [Installieren von Verwaltungstools in Skype for Business Server](install-administrative-tools.md) : die Verwaltungstools umfassen den Topologie-Generator und die Systemsteuerung. Sie müssen die Verwaltungstools auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation mit einer Windows-Betriebssystemversion installieren, die für Skype for Business Server unterstützt wird.
    
- [Vorbereiten Active Directory für Skype for Business Server](prepare-active-directory.md) : Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory Domäne so vorbereiten, dass Sie mit Skype for Business Server arbeitet. Hierzu können Sie den Bereitstellungs-Assistenten verwenden, der nur einmal für die Domäne ausgeführt wird. Dies liegt daran, dass der Prozessgruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal durchführen.
    
- [Erstellen von DNS-Einträgen für Skype for Business Server](create-dns-records.md) : damit Skype for Business Server ordnungsgemäß funktioniert, müssen eine Reihe von DNS-Einstellungen vorhanden sein. Dies bedeutet, dass Clients wissen, wie Sie auf die Dienste zugreifen und die Server voneinander wissen. Diese Einstellungen müssen nur einmal pro Bereitstellung ausgeführt werden, da Sie nach dem Zuweisen eines DNS-Eintrags in der gesamten Domäne zur Verfügung stehen.
    
- [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server](create-and-publish-new-topology.md) : bevor Sie das Skype for Business Server-System auf jedem Server in der Topologie installieren können, müssen Sie eine Topologie erstellen und veröffentlichen. Wenn Sie eine Topologie veröffentlichen, laden Sie die Topologieinformationen in die zentraler Verwaltungsspeicher Datenbank. Wenn es sich um einen Enterprise Edition-Pool handelt, erstellen Sie die zentraler Verwaltungsspeicher Datenbank, wenn Sie das erste Mal eine neue Topologie veröffentlichen. Wenn es sich um Standard Edition handelt, müssen Sie den Prozess zum Vorbereiten des ersten Standard Edition-Server aus dem Bereitstellungs-Assistenten ausführen, bevor Sie eine Topologie veröffentlichen. Dadurch wird die Standard Edition vorbereitet, indem eine SQL Server Express Edition-Instanz installiert und das zentraler Verwaltungsspeicher erstellt wird.
    
- [Installieren Sie Skype for Business Server auf Servern in der Topologie](install-skype-for-business-server.md) : Nachdem die Topologie in den zentraler Verwaltungsspeicher geladen wurde und Active Directory weiß, welche Server die Rollen ausführen sollen, müssen Sie das Skype for Business Server System auf jedem Server in der Topologie installieren.
    
- [Überprüfen Sie die Topologie in Skype for Business Server](verify-the-topology.md) : Nachdem Sie die Topologie veröffentlicht haben und die Skype for Business Server Systemkomponenten auf jedem Server in der Topologie installiert sind, können Sie überprüfen, ob die Topologie erwartungsgemäß funktioniert. Dies umfasst die Überprüfung, ob die Konfiguration an alle Active Directory Server weitergegeben wurde, sodass die gesamte Domäne weiß, dass Skype for Business in der Domäne verfügbar ist.
    

