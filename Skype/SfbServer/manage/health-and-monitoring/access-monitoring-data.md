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
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Access Überwachungsdaten in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Überwachungsdaten in Skype für Business Server verwendet wird.
  
Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank „LcsCdr“ für Kommunikationsdatensätze und „QoEMetrics“ für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.
  
Ein Tool, die, das Sie berücksichtigen sollten, für den Zugriff auf und Analysieren von Überwachungsdaten, ist die Skype für Business Server Monitoring Reports. Überwachungsberichte sind eine Reihe von Standardberichte, die von Microsoft SQL Server Reporting Services veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken. Monitoring-Berichten im Lieferumfang von Skype für Business Server und von der Skype für Business Server-Bereitstellungs-Assistenten installiert werden, nachdem Skype für Business Server installiert wurde und Überwachung konfiguriert wurde.
  
Wie bereits an früherer Stelle angemerkt, ist für Monitoring-Berichte SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.
  
Weitere Informationen finden Sie im Thema [Installieren von Überwachungsberichten in Skype für Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

