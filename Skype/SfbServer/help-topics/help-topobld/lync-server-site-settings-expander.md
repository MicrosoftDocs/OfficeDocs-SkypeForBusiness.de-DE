---
title: Lync Server-Website-Einstellungen – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Führen Sie folgende Schritte aus, um die Eigenschaften einer vorhandenen Website zu bearbeiten:'
ms.openlocfilehash: 6ae0154da4e53cffb9d0b6bb02a2eda3cb0cbaa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="lync-server-site-settings-expander"></a>Lync Server-Website-Einstellungen – Erweiterung
 
Führen Sie folgende Schritte aus, um die Eigenschaften einer vorhandenen Website zu bearbeiten:
  
## 

### <a name="site-properties"></a>Site-Standardeigenschaften

In Site-Standardeigenschaften können Sie ändern oder ändern den Standortnamen (erforderlich), Beschreibung (optional), Ort (optional), Bundesland/Kanton (optional) und Länder-/Regionscode (optional).
  
Ausführliche Informationen zu Standorteigenschaften finden Sie unter [Add Branch Sites to Your Topology](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).
  
### <a name="federation-route-properties"></a>Eigenschaften von Partnerverbundrouten

Wenn eine Zuweisung der partnerverbundroute Route festlegen möchten, müssen Sie zuerst den Verbund aktiviert auf einem Edge-Server oder einem Edge-Server-Pool verfügen. Wenn Verbund auf einem Edge-Server oder Pool nicht aktiviert ist, werden die Federation Route Zuordnung Einstellungen für die Website nicht geändert werden.
  
Wenn die partnerverbundeinstellung für den Edge-Server oder Pool konfiguriert wurde, wählen Sie auf der Websiteebene **Aktivieren** aus. Wählen Sie dann aus der Dropdown-Liste als partnerverbundroute Festlegen einer Kante oder einen Director aus.
  
> [!CAUTION]
> Diese Einstellung wirkt sich auf alle Websites. Stellen Sie sicher, dass die Einstellung, die Sie an diesem Standort konfigurieren für alle Websites geeignet ist. 
  
### 

Weitere Informationen hierzu finden Sie unter [Topologien für den Zugriff externer Benutzer](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).
  

