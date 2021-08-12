---
title: Einstellungen für Webdienste – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: Im Topologie-Generator können Sie die Porteinstellungen ändern, die für ihre internen und externen Webdienste verwendet werden. Darüber hinaus und wenn Sie einen DNS-Lastenausgleich (Domain Name System) bereitstellen, können Sie den Topologie-Generator verwenden, um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools zu konfigurieren, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird.
ms.openlocfilehash: aafce1b005969c660dc6822e02ceef27ee8be8c0eabff59917c0f8160bed0c50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54291183"
---
# <a name="web-services-settings-expander"></a>Einstellungen für Webdienste – Erweiterung
 
Im Topologie-Generator können Sie die Porteinstellungen ändern, die für ihre internen und externen Webdienste verwendet werden. Darüber hinaus und wenn Sie einen DNS-Lastenausgleich (Domain Name System) bereitstellen, können Sie den Topologie-Generator verwenden, um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools zu konfigurieren, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird.
  
### <a name="editing-web-services-settings"></a>Bearbeiten von Webdiensteinstellungen

1. Wählen Sie den entsprechenden Standard Edition Front-End-Server oder den entsprechenden Enterprise Edition Front-End-Pool aus, und klicken Sie dann auf **Eigenschaften bearbeiten.**
    
2. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf die Registerkarte **Webdienste**.
    
    > [!CAUTION]
    > Wenn Sie über mehrere Front-End-Pools oder Front-End-Server verfügen, muss der externe Webdienst-FQDN eindeutig sein. Wenn Sie beispielsweise den FQDN für externe Webdienste eines Front-End-Servers als **pool01.contoso.com** definieren, können Sie **pool01.contoso.com** nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN der externen Webdienste, der für einen Director- oder Director-Pool definiert ist, von jedem anderen Director- oder Directorpool sowie von jedem Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN überschreiben möchten, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.
  
3. Wenn Sie die Eigenschaften eines Enterprise Edition Pools bearbeiten, können Sie den **FQDN überschreiben** auswählen. Diese Option sollte nur ausgewählt werden, wenn Sie dns-Lastenausgleich (Domain Name System) verwenden. Wählen Sie bei Verwendung des DNS-Lastenausgleichs **Vollqualifizierten Domänennamen außer Kraft setzen** aus, und geben Sie in das Textfeld den vollqualifizierten Domänennamen des Pools ein, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird. Wenn Sie nicht mit dem DNS-Lastenausgleich arbeiten und **Vollqualifizierten Domänennamen außer Kraft setzen** deaktiviert lassen, kann der vollqualifizierte Domänenname der internen Webdienste nicht geändert werden. Der FQDN der internen Webdienste ist die URL, die von internen Benutzern zum Herstellen einer Verbindung mit Skype for Business Server verwendet wird.
    
4. Geben Sie optional für **Überwachungsports** und **Veröffentlichte Ports** neue HTTP-, HTTPS- bzw. HTTP- und HTTPS-Werte ein. Überwachungsports werden von den Internetinformationsdiensten (IIS) zum Überwachen auf eingehenden SIP-Datenverkehr (Session Initiation Protocol) genutzt. Veröffentlichte Ports werden für ein Lastenausgleichsgerät oder Reverseproxyserver konfiguriert und dienen ebenfalls zum Überwachen auf eingehenden SIP-Datenverkehr. In der Standardeinstellung ist sowohl der HTTP-Überwachungsport als auch der veröffentlichte HTTP-Port auf den Wert 80 festgelegt. Die entsprechenden HTTPS-Ports sind auf 443 festgelegt. Der Standardwert für die beiden veröffentlichten HTTP-Ports ist 8080, die entsprechenden HTTPS-Ports sind auf 4443 festgelegt.
    
5. Klicken Sie auf **OK**.
    
Wenn Sie entweder den internen FQDN oder eine der Zuweisungen für den Überwachungsport ändern, müssen Sie die lokale Einrichtung erneut auf allen Servern im Pool vornehmen, damit diese Änderungen wirksam werden.
  

