---
title: Allgemeine Einstellungen für Director – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Wenn Sie die Einstellungen für einen vorhandenen Director bearbeiten möchten, werden Ihnen die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: ffdfd169095175346a89eb6d6d001161bec0f465
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793853"
---
# <a name="director-general-settings-expander"></a>Allgemeine Einstellungen für Director – Erweiterung
 
Wenn Sie die Einstellungen für einen vorhandenen Director bearbeiten möchten, werden Ihnen die folgenden Abschnitte angezeigt:
  
- Allgemeine Einstellungen
    
- Webdienste
    

## <a name="general-settings"></a>Allgemeine Einstellungen

Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Director-Pools. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.
  
In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:
  
Dateifreigabe, die der Director-Pool verwenden soll. Wählen Sie eine vorhandene Dateifreigabe aus, die bereits im Topologie-Generator definiert wurde, oder klicken Sie auf **neu** , um eine neue Dateifreigabe Definition zu erstellen.
  
Überwachen des SQL Server-Speichers
  
> [!IMPORTANT]
> Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein. Wenn Sie eine neue Dateifreigabe erstellt haben, muss die Dateifreigabe auf dem von Ihnen festgelegten Server erstellt werden. 
  
## <a name="web-services"></a>Webdienste

Zum Bearbeiten oder angeben zusätzlicher Einstellungen für die Webdienste im Director-Pool ändern oder spezifizieren Sie die Einstellungen in den internen Webdiensten und externen Webdiensten.
  
Bei **internen Webdiensten** können Sie Folgendes angeben:
  
> [!CAUTION]
> Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als **pool01.contoso.com**definieren, können Sie **pool01.contoso.com** nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie sich entscheiden, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.
  
Wenn Sie Vollqualifizierten Domänennamen außer Kraft setzen auswählen, können Sie einen anderen FQDN für die Identität Interne Webdienste im Pool angeben. Standardmäßig ist die Einstellung der Name des aktuellen Pools, wie er für den Director-Pool definiert ist.
  
Sie können Überwachungs-und veröffentlichte Ports für http und HTTPS angeben, die für die Bereitstellung erforderlich sind. Die Standardeinstellung von Port 80 für http und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen, die normalerweise nicht geändert werden müssen, es sei denn, Sie verfügen über bestimmte Anforderungen innerhalb Ihres Unternehmens-und Infrastruktur Designs.
  
Bei **externen Webdiensten**können Sie Folgendes angeben:
  
Sie können den FQDN der externen Webdienste definieren. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.
  
Sie können Überwachungs-und veröffentlichte Ports für http und HTTPS angeben, die für die Bereitstellung erforderlich sind. Die Standardeinstellungen von Port 8080 für http und Port 4443 für HTTPS werden zunächst definiert. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Die veröffentlichten Ports sind auf Standard Port 80 für http und Port 443 für HTTPS eingestellt. Diese Werte legen fest, welche Ports der Director-Pool oder Director-Server auf eingehende Anforderungen überwacht. In der Regel müssen diese nicht geändert werden, es sei denn, es gibt einen Konflikt zwischen den Portanforderungen im Pool. Interne und externe veröffentlichte Ports, die die gleichen Portwerte verwenden, werden erwartet. Dies ist kein Konflikt.
  

