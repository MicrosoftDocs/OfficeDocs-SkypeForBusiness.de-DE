---
title: Access Überwachungsdaten in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Zusammenfassung: Erfahren Sie mehr über die Überwachungsdaten in Skype für Business Server verwendet wird.'
ms.openlocfilehash: 096a20119f0d7f368165aae53e2b3164cb817d63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197590"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="d2a87-103">Access Überwachungsdaten in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d2a87-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="d2a87-104">**Zusammenfassung:** Informationen Sie zu den Überwachungsdaten in Skype für Business Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d2a87-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="d2a87-p101">Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank „LcsCdr“ für Kommunikationsdatensätze und „QoEMetrics“ für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2a87-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="d2a87-107">Ein Tool, die, das Sie berücksichtigen sollten, für den Zugriff auf und Analysieren von Überwachungsdaten, ist die Skype für Business Server Monitoring Reports.</span><span class="sxs-lookup"><span data-stu-id="d2a87-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="d2a87-108">Überwachungsberichte sind eine Reihe von Standardberichte, die von Microsoft SQL Server Reporting Services veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="d2a87-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="d2a87-109">Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="d2a87-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="d2a87-110">Monitoring-Berichten im Lieferumfang von Skype für Business Server und von der Skype für Business Server-Bereitstellungs-Assistenten installiert werden, nachdem Skype für Business Server installiert wurde und Überwachung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d2a87-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="d2a87-p103">Wie bereits an früherer Stelle angemerkt, ist für Monitoring-Berichte SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d2a87-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="d2a87-113">Weitere Informationen finden Sie im Thema [Installieren von Überwachungsberichten in Skype für Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span><span class="sxs-lookup"><span data-stu-id="d2a87-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

