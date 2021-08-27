---
title: Zugreifen auf Überwachungsdaten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Zusammenfassung: Erfahren Sie mehr über die Überwachungsdaten, die in Skype for Business Server verwendet werden.'
ms.openlocfilehash: 2df5bf8bd1e1536b4de046ff4b6a4290e276039d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612244"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Zugreifen auf Überwachungsdaten in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die in Skype for Business Server verwendeten Überwachungsdaten.
  
Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank "LcsCdr" für Kommunikationsdatensätze und "QoEMetrics" für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.
  
Ein Tool, das Sie für den Zugriff auf und die Analyse von Überwachungsdaten in Betracht ziehen sollten, sind die Skype for Business Server Überwachungsberichte. Überwachungsberichte sind eine Reihe von Standardberichten, die von Microsoft SQL Server Reporting Service veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken. Überwachungsberichte werden mit Skype for Business Server ausgeliefert und können über den Skype for Business Server Bereitstellungs-Assistenten installiert werden, nachdem Skype for Business Server installiert und die Überwachung konfiguriert wurde.
  
Wie bereits an früherer Stelle angemerkt, ist bei den Monitoring-Berichten SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.
  
Weitere Informationen finden Sie im Thema [Installieren von Überwachungsberichten in Skype for Business Server.](../../deploy/deploy-monitoring/install-monitoring-reports.md)
  

