---
title: Zugriff auf Überwachungsdaten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Zusammenfassung: informieren Sie sich über die in Skype for Business Server verwendeten Überwachungsdaten.'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303886"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="d20ed-103">Zugriff auf Überwachungsdaten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d20ed-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="d20ed-104">**Zusammenfassung:** Informieren Sie sich über die in Skype for Business Server verwendeten Überwachungsdaten.</span><span class="sxs-lookup"><span data-stu-id="d20ed-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="d20ed-p101">Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank „LcsCdr“ für Kommunikationsdatensätze und „QoEMetrics“ für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d20ed-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="d20ed-107">Ein Tool, das Sie für den Zugriff auf und die Analyse von Überwachungsdaten in Frage stellen sollten, sind die Überwachungsberichte von Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d20ed-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="d20ed-108">Überwachungsberichte sind eine Reihe von Standardberichten, die vom Microsoft SQL Server-Berichterstattungsdienst veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="d20ed-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="d20ed-109">Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="d20ed-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="d20ed-110">Überwachungsberichte, die mit Skype for Business Server ausgeliefert werden und über den Skype for Business Server-Bereitstellungs-Assistenten installiert werden können, nachdem Skype for Business Server installiert und die Überwachung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d20ed-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="d20ed-p103">Wie bereits an früherer Stelle angemerkt, ist für Monitoring-Berichte SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d20ed-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="d20ed-113">Weitere Informationen finden Sie im Thema [Installieren von Überwachungsberichten in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span><span class="sxs-lookup"><span data-stu-id="d20ed-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

