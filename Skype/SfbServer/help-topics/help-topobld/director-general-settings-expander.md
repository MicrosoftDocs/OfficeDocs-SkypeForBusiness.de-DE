---
title: Allgemeine Einstellungen für Director – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden in den folgenden Abschnitten bearbeitet:'
ms.openlocfilehash: 92ddafb0029f4860f4fd36ddb9a497d21deb97d2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885589"
---
# <a name="director-general-settings-expander"></a>Allgemeine Einstellungen für Director – Erweiterung
 
Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden in den folgenden Abschnitten bearbeitet:
  
- Allgemeine Einstellungen
    
- Webdienste
    


## <a name="general-settings"></a>Allgemeine Einstellungen

Vollqualifizierter Domänenname (FQDN) des Director-Pools. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.
  
In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:
  
Dateifreigabe für den Director-Pool verwenden. Wählen Sie eine vorhandene Dateifreigabe, die bereits im Topologie-Generator definiert wurde, oder klicken Sie auf **neu** , um eine neue Datei freigeben Definition erstellen.
  
Überwachen der SQL Server-Speicher.
  
> [!IMPORTANT]
> Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein. Wenn Sie eine neue Dateifreigabe erstellt haben, muss die Dateifreigabe auf dem Server erstellt werden, die Sie festlegen. 
  
## <a name="web-services"></a>Webdienste

Zum Bearbeiten, oder geben Sie zusätzliche Einstellungen für die Webdienste im Director-Pool, ändern oder Angeben von Einstellungen in der internen und externen Webdiensten.
  
Für die **interne Webdienste** können Sie Folgendes angeben:
  
> [!CAUTION]
> Wenn Sie mehrere Front-End-Pool oder Front-End-Server verfügen muss die externen Webdienste FQDN eindeutig sein. Wenn Sie die externen Webdienste-FQDN des Front-End-Server als **"pool01.contoso.com"** definieren, können nicht Sie beispielsweise **"pool01.contoso.com"** für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Director-Server bereitstellen, die externe Webdienste-FQDN für alle Director definierten oder Director-Pool muss aus einem anderen eindeutig sein Director oder Director-Pools sowie alle Front-End-Pool oder Front-End-Server Wenn Sie die internen Webdienste mit einem selbstdefinierten FQDN überschreiben möchten, muss jeder FQDN eines anderen Front-End-Pools, Director oder Director-Pool eindeutig sein.
  
Wenn Sie Vollqualifizierten Domänennamen außer Kraft setzen auswählen, können Sie einen anderen FQDN für die Identität Interne Webdienste im Pool angeben. Standardmäßig ist die Einstellung der aktuellen Poolname für den Director-Pool definiert wurden.
  
Sie können überwachen und veröffentlichten Ports angeben, für HTTP und HTTPS, die Ihre Bereitstellung erforderlich sind. Die Standardeinstellung von Port 80 für HTTP und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen und müssen in der Regel nicht geändert werden, wenn Sie spezifische Anforderungen innerhalb Ihrer Organisation und den Entwurf der Infrastruktur für verfügen.
  
Für **externe Webdienste**können Sie Folgendes angeben:
  
Sie können den FQDN der externen Webdienste definieren. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.
  
Sie können überwachen und veröffentlichten Ports angeben, für HTTP und HTTPS, die Ihre Bereitstellung erforderlich sind. Die Standardeinstellungen der Port 8080 für HTTP und Port 4443 für HTTPS werden zunächst definiert. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Die veröffentlichten Ports werden festgelegt auf Standardwert von Port 80 für HTTP und Port 443 für HTTPS. Diese Werte bestimmen, welche Ports für eingehende Anforderungen den Director-Pool oder Director-Server überwacht wird. In der Regel müssen diese nicht geändert werden, es sei denn, der Anforderungen in Bezug auf den Pool Konflikt vorliegt. Interne und externe veröffentlichten Ports, die dieselben Portwerte wie verwenden sollten. Dies ist kein Konflikt.
  

