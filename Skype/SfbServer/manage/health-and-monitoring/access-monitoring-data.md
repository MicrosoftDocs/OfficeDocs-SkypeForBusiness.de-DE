---
title: Zugriff auf Überwachungsdaten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Zusammenfassung: informieren Sie sich über die in Skype for Business Server verwendeten Überwachungsdaten.'
ms.openlocfilehash: b4eca36a09c4aa56b7216b476e0f0c5fa06d7a45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818186"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Zugriff auf Überwachungsdaten in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die in Skype for Business Server verwendeten Überwachungsdaten.
  
Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank „LcsCdr“ für Kommunikationsdatensätze und „QoEMetrics“ für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.
  
Ein Tool, das Sie für den Zugriff auf und die Analyse von Überwachungsdaten in Frage stellen sollten, sind die Überwachungsberichte von Skype for Business Server. Überwachungsberichte sind eine Reihe von Standardberichten, die vom Microsoft SQL Server-Berichterstattungsdienst veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken. Überwachungsberichte, die mit Skype for Business Server ausgeliefert werden und über den Skype for Business Server-Bereitstellungs-Assistenten installiert werden können, nachdem Skype for Business Server installiert und die Überwachung konfiguriert wurde.
  
Wie bereits an früherer Stelle angemerkt, ist für Monitoring-Berichte SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.
  
Weitere Informationen finden Sie im Thema [Installieren von Überwachungsberichten in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

