---
title: Einstellungen für Webdienste – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: Im Topologie-Generator können Sie die Porteinstellungen ändern, die sowohl für interne als auch für externe Webdienste verwendet werden. Darüber hinaus können Sie beim Bereitstellen des Lastenausgleichs für das Domain Name System (DNS) den Vollqualifizierten Domänennamen (FQDN) des Pools konfigurieren, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird.
ms.openlocfilehash: 00fbf89b6e8121b5e2cd8d1b8d544531cc411e3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817815"
---
# <a name="web-services-settings-expander"></a>Einstellungen für Webdienste – Erweiterung
 
Im Topologie-Generator können Sie die Porteinstellungen ändern, die sowohl für interne als auch für externe Webdienste verwendet werden. Darüber hinaus können Sie beim Bereitstellen des Lastenausgleichs für das Domain Name System (DNS) den Vollqualifizierten Domänennamen (FQDN) des Pools konfigurieren, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird.
  
### <a name="editing-web-services-settings"></a>Bearbeiten von Webdiensteinstellungen

1. Wählen Sie den entsprechenden Front-End-Server der Standard Edition oder den entsprechenden Front-End-Pool der Enterprise Edition aus, und klicken Sie dann **auf "Eigenschaften bearbeiten".**
    
2. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf die Registerkarte **Webdienste**.
    
    > [!CAUTION]
    > Wenn Sie über mehrere Front-End-Pools oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Servers als **pool01.contoso.com** definieren, können Sie pool01.contoso.com nicht für einen anderen Front-End-Pool oder **Front-End-Server** verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN der externen Webdienste, der für einen Director oder Directorpool definiert ist, von allen anderen Director- oder Directorpools sowie front-End-Pools oder Front-End-Servern eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN überschreiben möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder Directorpool eindeutig sein.
  
3. Wenn Sie die Eigenschaften eines Enterprise Edition-Pools bearbeiten, können Sie den **FQDN** außer Kraft setzen auswählen. Diese Option sollte nur ausgewählt werden, wenn Sie den Dns-Lastenausgleich (Domain Name System) verwenden. Wählen Sie bei Verwendung des DNS-Lastenausgleichs **Vollqualifizierten Domänennamen außer Kraft setzen** aus, und geben Sie in das Textfeld den vollqualifizierten Domänennamen des Pools ein, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird. Wenn Sie nicht mit dem DNS-Lastenausgleich arbeiten und **Vollqualifizierten Domänennamen außer Kraft setzen** deaktiviert lassen, kann der vollqualifizierte Domänenname der internen Webdienste nicht geändert werden. Der FQDN der internen Webdienste ist die URL, die von internen Benutzern verwendet wird, um eine Verbindung mit Skype for Business Server herzustellen.
    
4. Geben Sie optional für **Überwachungsports** und **Veröffentlichte Ports** neue HTTP-, HTTPS- bzw. HTTP- und HTTPS-Werte ein. Überwachungsports werden von den Internetinformationsdiensten (IIS) zum Überwachen auf eingehenden SIP-Datenverkehr (Session Initiation Protocol) genutzt. Veröffentlichte Ports werden für ein Lastenausgleichsgerät oder Reverseproxyserver konfiguriert und dienen ebenfalls zum Überwachen auf eingehenden SIP-Datenverkehr. In der Standardeinstellung ist sowohl der HTTP-Überwachungsport als auch der veröffentlichte HTTP-Port auf den Wert 80 festgelegt. Die entsprechenden HTTPS-Ports sind auf 443 festgelegt. Der Standardwert für die beiden veröffentlichten HTTP-Ports ist 8080, die entsprechenden HTTPS-Ports sind auf 4443 festgelegt.
    
5. Klicken Sie auf **OK**.
    
Wenn Sie entweder den internen FQDN oder eine der Zuweisungen für abhörende Ports ändern, müssen Sie das lokale Setup auf allen Servern im Pool erneut vornehmen, damit diese Änderungen wirksam werden.
  

