---
title: Installieren von Skype for Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Zusammenfassung: Erfahren Sie, wie Business Server Vorbereitung Ihrer Umgebung für eine Installation von Skype. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: d5c1290e4a7a1beeb2310c69f0c63d7f549e0d76
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026041"
---
# <a name="install-skype-for-business-server"></a>Installieren von Skype for Business Server
 
**Zusammenfassung:** Informationen Sie zur Vorbereitung Ihrer Umgebung für eine Installation von Skype Business Server. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Dieser Artikel führt Sie durch eine Beispiel-Installation von Skype für Business Server. In diesem Artikel Versuch kein, alle Verfahren abdecken müssen Sie eine vollständige Skype für Business Server-Installation ausführen. Ziel des Artikels ist die Darstellung von Vorgehensweisen mit Beispielcharakter in einer eng definierten Topologie, die einfache Besprechungs- und Freigabefunktionen umfasst.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Übersicht über den Installationsvorgang für Skype für Business Server

Eine Installation von Skype für Business Server enthält viele unterschiedliche Prozeduren. Die Verfahren zum Abrufen von Skype für Business Server in Ihrer Umgebung ausgeführt werden müssen, abhängig von den Einzelheiten Ihrer Umgebung ab. Wenn Sie beispielsweise Windows Server für DNS verwenden, ist für Sie das Verfahren zum Hinzufügen eines DNS-Eintrags interessant. Wenn Sie ein anderes System für DNS verwenden, müssen Sie die Verfahren für dieses spezifische System durchführen. Das Gleiche gilt für viele in diesem Abschnitt beschriebene Verfahren.
  
Skype für Business Server ist in der Standard Edition und Enterprise Edition verfügbar. Der Hauptunterschied besteht darin, dass die Standard Edition die Funktionen für hohe Verfügbarkeit der Enterprise Edition nicht unterstützt. 
  
Skype für Business Server ist eine erweiterte Produkt und der genauen Installationsvorgang hängt viel den genauen Umständen. In diesem Abschnitt sind die allgemeinen Schritte zur Installation des Produkts aufgeführt. Die einzelnen Verfahren können jedoch abhängig von Umgebung und Planungsentscheidungen abweichen. Beispielsweise ist für kleine Unternehmen einem Einzelserver Skype Business Server Standard Edition ausgeführt geeignet während ein großen internationales Unternehmen 50 Servern an Standorten auf der ganzen Welt an dem Produkt dedizierte möglicherweise.
  
> [!NOTE]
> Weitere Informationen zu den neuesten kumulativen Updates finden Sie unter [Updates für Skype für Business Server](https://support.microsoft.com/en-us/kb/3061064). Nach der Installation von Patches CU1 Administrator ausführen muss die `Update-CsAdminRole` Cmdlet. Dieses Cmdlet ist erforderlich, damit über die Remote-PowerShell auf die neuen GCP-Cmdlets zugegriffen werden kann.
  
> [!IMPORTANT]
> Die Verfahren in diesem Abschnitt haben Beispielcharakter und basieren auf einer eng definierten Reihe von Anforderungen sowie auf der Annahme, dass bestimmte Entscheidungen bereits getroffen wurden. Die tatsächlichen Verfahren, die Sie Skype für Business Server installieren müssen, werden wahrscheinlich sehr anders lauten. Verwenden Sie die Verfahren in diesem Abschnitt als einzige Beispiel und nicht als ein ausführlicher Leitfaden, für die Installation von Skype für Business Server in jeder Umgebung. 
  
Abrufen von Skype für Business Server einrichten und Ausführen von zum ersten Mal umfasst acht Hauptschritte. Sie sollten wissen, dass die Beispiele in diesem Abschnitt nicht die einzigen Verfahren zum Installieren von Skype für Business Server erforderlich sind. Die nachfolgenden acht Schritte sind lediglich Beispiele zur Erläuterung des Gesamtprozesses und zur Einrichtung einer einfachen funktionierenden Umgebung. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Folgende acht Schritte sind erforderlich:
  
![Übersicht über den Installationsprozess](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installieren erforderlicher Komponenten für Skype für Business Server](install-prerequisites.md) : Installieren der erforderlichen Komponenten auf allen Servern, die die Skype für Business Server-Topologie bilden. Die erforderliche Software ist nicht für alle Rollen gleich. Für Server, die die Front-End-Rolle bereitstellen, sind beispielsweise andere Komponenten erforderlich als für Server, die eine Director-Rolle bereitstellen. Weitere Informationen dazu entnehmen Sie bitte der Planungsdokumentation zu den erforderlichen Komponenten.
    
- [Erstellen Sie eine Dateifreigabe in Skype für Business Server](create-a-file-share.md) : Erstellen einer Dateifreigabe, die von Servern in der gesamten die Skype für Business Server-Topologie verwendet werden.
    
- [Installieren der Verwaltungstools in Skype für Business Server](install-administrative-tools.md) : die Verwaltungstools gehören, Topologie-Generator und auf Systemsteuerung. Sie müssen die Verwaltungstools installieren, auf mindestens einem Server in der Topologie oder einem 64-Bit-Verwaltungscomputer auf dem eine Windows-Betriebssystem-Version, die für Skype für Business Server unterstützt wird.
    
- [Vorbereiten von Active Directory für Skype für Business Server](prepare-active-directory.md) : Skype für Business Server arbeitet eng mit Active Directory. Sie müssen Active Directory-Domäne zur Arbeit mit Skype für Business Server vorbereiten. Hierzu können Sie über den Bereitstellungs-Assistenten, und es erfolgt nur einmal für die Domäne. Dies ist, da der Prozess Gruppen erstellt und ändert die Domäne, und die erforderlich ist, nur einmal.
    
- [Erstellen von DNS-Einträge für Skype für Business Server](create-dns-records.md) : damit Skype für Business Server ordnungsgemäß funktioniert, muss eine Anzahl von DNS-Einstellungen vorhanden sein. Diese steuern den Zugriff der Clients auf die Dienste und sorgen dafür, dass die Server übereinander informiert sind. Diese Einstellungen müssen pro Bereitstellung nur einmal festgelegt werden, da ein einmal zugeordneter DNS-Eintrag domänenübergreifend zur Verfügung steht.
    
- [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server](create-and-publish-new-topology.md) : vor der Installation von der Skype für Business Server-System auf jedem Server in der Topologie müssen Sie eine Topologie erstellen und veröffentlichen. Beim Veröffentlichen einer Topologie laden Sie die Topologieinformationen in die Datenbank des zentralen Verwaltungsspeichers. Bei einem Enterprise Edition-Pool erstellen Sie die Datenbank des zentralen Verwaltungsspeichers beim ersten Veröffentlichen einer neuen Topologie. In der Standard Edition müssen Sie den Vorgang „Ersten Standard Edition-Server vorbereiten“ des Bereitstellungs-Assistenten vor dem Veröffentlichen der Topologie ausführen. Damit wird die Standard Edition durch Installation einer SQL Server Express Edition-Instanz und die Erstellung des zentralen Verwaltungsspeichers vorbereitet.
    
- [Skype für Business Server auf Server in der Topologie installieren](install-skype-for-business-server.md) : Nachdem die Topologie in den zentralen Verwaltungsspeicher geladen wird und Active Directory bekannt ist, welche Server die Rollen ausgeführt werden, müssen Sie auf jedem der Skype für Business Server-System installieren die Server in der Topologie.
    
- [Überprüfen der Topologie in Skype für Business Server](verify-the-topology.md) : Nachdem Sie die Topologie veröffentlicht und die Skype für Business Server Systemkomponenten auf jedem Server in der Topologie installiert haben, sind Sie bereit, um sicherzustellen, dass die Topologie wie erwartet funktioniert. Dazu gehören sichergestellt haben, dass die Konfiguration aller Active Directory-Server weitergegeben wurde, damit die gesamte Domäne bekannt ist, dass Skype für Unternehmen in der Domäne verfügbar ist.
    

