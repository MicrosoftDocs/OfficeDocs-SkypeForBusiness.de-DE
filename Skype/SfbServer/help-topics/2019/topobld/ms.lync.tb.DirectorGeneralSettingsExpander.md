---
title: Allgemeine Einstellungen für Director – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: 62dc9b855937d360a975e5e4035d662da276ce02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822625"
---
# <a name="director-general-settings-expander"></a>Allgemeine Einstellungen für Director – Erweiterung
 
Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden die folgenden Abschnitte angezeigt:
  
- Allgemeine Einstellungen
    
- Webdienste
    

## <a name="general-settings"></a>Allgemeine Einstellungen

Vollqualifizierter Domänenname (FQDN) des Director-Pools. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.
  
In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:
  
Dateifreigabe für den zu verwendenden Director-Pool. Wählen Sie eine vorhandene Dateifreigabe aus, die bereits  im Topologie-Generator definiert wurde, oder klicken Sie auf "Neu", um eine neue Dateifreigabedefinition zu erstellen.
  
SQL Server-Speicher für Überwachung.
  
> [!IMPORTANT]
> Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein. Wenn Sie eine neue Dateifreigabe erstellen, muss die Dateifreigabe auf dem angegebenen Server erstellt werden. 
  
## <a name="web-services"></a>Webdienste

Wenn Sie zusätzliche Einstellungen für die Webdienste im Director-Pool bearbeiten oder angeben möchten, müssen Sie die Einstellungen in den internen und externen Webdiensten ändern oder angeben.
  
Für **Interne Webdienste** können Sie Folgendes angeben:
  
> [!CAUTION]
> Wenn Sie über mehrere Front-End-Pools oder Front-End-Server verfügen, muss der externe Webdienste-FQDN eindeutig sein. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Servers als **pool01.contoso.com** definieren, können Sie pool01.contoso.com nicht für einen anderen Front-End-Pool oder **Front-End-Server** verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN der externen Webdienste, der für einen Director oder Directorpool definiert ist, von allen anderen Director- oder Directorpools sowie front-End-Pools oder Front-End-Servern eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN überschreiben möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder Directorpool eindeutig sein.
  
Wenn Sie die Außerkraftsetzung des FQDN wählen, können Sie einen anderen FQDN für die Identität der internen Webdienste im Pool angeben. In der Standardeinstellung entspricht die Einstellung dem aktuellen Poolnamen, der für den Director-Pool definiert ist.
  
Sie können für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS angeben. Die Standardeinstellungen von Port 80 für HTTP und Port 443 für HTTPS sind die gängigsten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, in Ihrem Organisations- und Infrastrukturentwurf liegen besondere Anforderungen vor.
  
Für **Externe Webdienste** können Sie Folgendes angeben:
  
Sie können den FQDN der externen Webdienste definieren. Der hier angegebene vollqualifizierte Domänenname wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.
  
Sie können für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS angeben. Anfänglich sind die Standardeinstellungen (Port 8080 für HTTP und Port 4443 für HTTPS) definiert. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Die veröffentlichten Ports sind auf die Standardeinstellungen Port 80 für HTTP und Port 443 für HTTPS festgelegt. Diese Werte bestimmen, an welchen Ports der Director-Pool oder Director-Server das System auf eingehende Anforderungen überwacht. Diese Werte müssen zumeist nicht geändert werden, es sei denn, es liegt ein Konflikt bei den Portanforderungen des Pools vor. Interne und externe veröffentlichte Ports mit denselben Portwerten werden erwartet. Dies stellt keinen Konflikt dar.
  

