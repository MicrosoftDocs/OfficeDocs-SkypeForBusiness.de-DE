---
title: Installieren von Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: b9a89e73f47922493a6d7add320c21b9b9900103
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306776"
---
# <a name="install-skype-for-business-server"></a>Installieren von Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Ihre Umgebung auf eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Center unter: herunter.
  
Dieser Artikel führt Sie durch eine Beispielinstallation von Skype for Business Server. In diesem Artikel wird nicht versucht, alle Verfahren abzudecken, die Sie zum Ausführen einer vollständigen Skype for Business Server-Installation benötigen. Ziel des Artikels ist die Darstellung von Vorgehensweisen mit Beispielcharakter in einer eng definierten Topologie, die einfache Besprechungs- und Freigabefunktionen umfasst.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Übersicht über den Installationsvorgang für Skype for Business Server

Eine Installation von Skype for Business Server umfasst viele verschiedene Verfahren. Die Verfahren, die Sie für den Einsatz von Skype for Business Server in Ihrer Umgebung benötigen, sind von den Besonderheiten Ihrer Umgebung abhängig. Wenn Sie beispielsweise Windows Server für DNS verwenden, ist für Sie das Verfahren zum Hinzufügen eines DNS-Eintrags interessant. Wenn Sie ein anderes System für DNS verwenden, müssen Sie die Verfahren für dieses spezifische System durchführen. Das Gleiche gilt für viele in diesem Abschnitt beschriebene Verfahren.
  
Skype for Business Server steht in Standard Edition und Enterprise Edition zur Verfügung. Der Hauptunterschied besteht darin, dass die Standard Edition die Funktionen für hohe Verfügbarkeit der Enterprise Edition nicht unterstützt. 
  
Skype for Business Server ist ein fortschrittliches Produkt, und der genaue Installationsvorgang hängt sehr stark von ihren spezifischen Gegebenheiten ab. In diesem Abschnitt sind die allgemeinen Schritte zur Installation des Produkts aufgeführt. Die einzelnen Verfahren können jedoch abhängig von Umgebung und Planungsentscheidungen abweichen. Für kleine Unternehmen kann beispielsweise ein einzelner Server, auf dem Skype for Business Server Standard Edition ausgeführt wird, geeignet sein, während eine große multinationale Organisation möglicherweise über 50-Server an Orten in der ganzen Welt verfügt, die dem Produkt gewidmet sind.
  
> [!NOTE]
> Informationen zu den neuesten kumulativen Updates finden Sie unter [Updates für Skype for Business Server](https://support.microsoft.com/en-us/kb/3061064). Nach der Installation des CU1-Patches muss ein Administrator das `Update-CsAdminRole` Cmdlet ausführen. Dieses Cmdlet ist erforderlich, damit über die Remote-PowerShell auf die neuen GCP-Cmdlets zugegriffen werden kann.
  
> [!IMPORTANT]
> Die Verfahren in diesem Abschnitt haben Beispielcharakter und basieren auf einer eng definierten Reihe von Anforderungen sowie auf der Annahme, dass bestimmte Entscheidungen bereits getroffen wurden. Die eigentlichen Verfahren, die Sie zum Installieren von Skype for Business Server benötigen, sind wahrscheinlich sehr unterschiedlich. Verwenden Sie die Verfahren in diesem Abschnitt nur als Beispiel und nicht als Schritt-für-Schritt-Anleitung zur Installation von Skype for Business Server in jeder Umgebung. 
  
Die erste Inbetriebnahme von Skype for Business Server umfasst acht primäre Schritte. Sie sollten verstehen, dass die Beispielverfahren in diesem Abschnitt nicht die einzigen Verfahren sind, die für die Installation von Skype for Business Server erforderlich sind. Die nachfolgenden acht Schritte sind lediglich Beispiele zur Erläuterung des Gesamtprozesses und zur Einrichtung einer einfachen funktionierenden Umgebung. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Folgende acht Schritte sind erforderlich:
  
![Übersicht über den Installationsprozess](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installieren Sie die Voraussetzungen für Skype for Business Server](install-prerequisites.md) : Installieren Sie die Voraussetzungen auf allen Servern, die die Skype for Business Server-Topologie ausmachen. Die erforderliche Software ist nicht für alle Rollen gleich. Für Server, die die Front-End-Rolle bereitstellen, sind beispielsweise andere Komponenten erforderlich als für Server, die eine Director-Rolle bereitstellen. Weitere Informationen dazu entnehmen Sie bitte der Planungsdokumentation zu den erforderlichen Komponenten.
    
- [Erstellen einer Dateifreigabe in Skype for Business Server](create-a-file-share.md) : Erstellen einer Dateifreigabe, die von Servern in der Skype for Business Server-Topologie verwendet wird.
    
- [Installieren Sie die Verwaltungstools in Skype for Business Server](install-administrative-tools.md) : die Verwaltungstools umfassen den Topologie-Generator und die Systemsteuerung. Sie müssen die Verwaltungstools auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation installieren, auf der eine Windows-Betriebssystemversion ausgeführt wird, die für Skype for Business Server unterstützt wird.
    
- [Vorbereiten von Active Directory für Skype for Business Server](prepare-active-directory.md) : Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory-Domäne für die Zusammenarbeit mit Skype for Business Server vorbereiten. Dies kann über den Bereitstellungs-Assistenten erfolgen, der nur einmal für die Domäne durchgeführt wird. Der Grund hierfür ist, dass der Prozessgruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal tun.
    
- [Erstellen von DNS-Einträgen für Skype for Business Server](create-dns-records.md) : damit Skype for Business Server ordnungsgemäß funktioniert, müssen eine Reihe von DNS-Einstellungen vorhanden sein. Diese steuern den Zugriff der Clients auf die Dienste und sorgen dafür, dass die Server übereinander informiert sind. Diese Einstellungen müssen pro Bereitstellung nur einmal festgelegt werden, da ein einmal zugeordneter DNS-Eintrag domänenübergreifend zur Verfügung steht.
    
- [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server](create-and-publish-new-topology.md) : bevor Sie das Skype for Business Server-System auf jedem Server in der Topologie installieren können, müssen Sie eine Topologie erstellen und veröffentlichen. Beim Veröffentlichen einer Topologie laden Sie die Topologieinformationen in die Datenbank des zentralen Verwaltungsspeichers. Bei einem Enterprise Edition-Pool erstellen Sie die Datenbank des zentralen Verwaltungsspeichers beim ersten Veröffentlichen einer neuen Topologie. In der Standard Edition müssen Sie den Vorgang „Ersten Standard Edition-Server vorbereiten“ des Bereitstellungs-Assistenten vor dem Veröffentlichen der Topologie ausführen. Damit wird die Standard Edition durch Installation einer SQL Server Express Edition-Instanz und die Erstellung des zentralen Verwaltungsspeichers vorbereitet.
    
- [Installieren Sie Skype for Business Server auf Servern in der Topologie](install-skype-for-business-server.md) : Nachdem die Topologie in den zentralen Verwaltungsspeicher geladen wurde und Active Directory weiß, welche Server welche Rollen ausführen sollen, müssen Sie das Skype for Business Server-System auf jedem der die Server in der Topologie.
    
- [Überprüfen Sie die Topologie in Skype for Business Server](verify-the-topology.md) : Nachdem Sie die Topologie veröffentlicht haben und die Systemkomponenten von Skype for Business Server auf jedem der Server in der Topologie installiert sind, können Sie überprüfen, ob die Topologie wie erwartet funktioniert. Dies umfasst die Überprüfung, ob die Konfiguration an alle Active Directory-Server weitergegeben wurde, damit die gesamte Domäne weiß, dass Skype for Business in der Domäne verfügbar ist.
    

