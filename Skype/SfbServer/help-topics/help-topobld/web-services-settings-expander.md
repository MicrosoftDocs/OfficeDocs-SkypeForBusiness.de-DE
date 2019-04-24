---
title: Einstellungen für Webdienste – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: Im Topologie-Generator, können Sie die Einstellungen für externe Ports für die interne und externe Webdienste verwendete ändern. Darüber hinaus und wenn die Domain Name System (DNS) zum Lastenausgleich bereitgestellt werden, können Topologie-Generator so konfigurieren Sie den vollqualifizierten Domänennamen (FQDN) des Pools, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird.
ms.openlocfilehash: 776ff33dabc331a3cf0a2107e7f0006bf2291fdb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218994"
---
# <a name="web-services-settings-expander"></a>Einstellungen für Webdienste – Erweiterung
 
Im Topologie-Generator, können Sie die Einstellungen für externe Ports für die interne und externe Webdienste verwendete ändern. Darüber hinaus und wenn die Domain Name System (DNS) zum Lastenausgleich bereitgestellt werden, können Topologie-Generator so konfigurieren Sie den vollqualifizierten Domänennamen (FQDN) des Pools, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird.
  
### <a name="editing-web-services-settings"></a>Bearbeiten von Webdiensteinstellungen

1. Wählen Sie den entsprechenden Front-End-Server der Standard Edition oder den Front-End-Pool der Enterprise Edition aus und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf die Registerkarte **Webdienste**.
    
    > [!CAUTION]
    > Wenn Sie mehrere Front-End-Pool oder Front-End-Server verfügen, muss die externe Webdienste FQDN eindeutig sein. Wenn Sie die externen Webdienste-FQDN des Front-End-Server als **"pool01.contoso.com"** definieren, können nicht Sie beispielsweise **"pool01.contoso.com"** für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Director-Server bereitstellen, die externe Webdienste-FQDN für alle Director definierten oder Director-Pool muss aus einem anderen eindeutig sein Director oder Director-Pools sowie alle Front-End-Pool oder Front-End-Server Wenn Sie die internen Webdienste mit einem selbstdefinierten FQDN überschreiben möchten, muss jeder FQDN eines anderen Front-End-Pools, Director oder Director-Pool eindeutig sein.
  
3. Wenn Sie die Eigenschaften eines Enterprise Edition-Pools bearbeiten, steht die Option **FQDN überschreiben** zur Verfügung. Diese Option darf nur ausgewählt werden, wenn Sie mit dem DNS-Lastenausgleich (Domain Name System) arbeiten. Wählen Sie bei Verwendung des DNS-Lastenausgleichs **FQDN überschreiben** aus, und geben Sie in das Textfeld den vollqualifizierten Domänennamen des Pools ein, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird. Wenn Sie nicht mit dem DNS-Lastenausgleich arbeiten und **FQDN überschreiben** deaktiviert lassen, kann der vollqualifizierte Domänenname der internen Webdienste nicht geändert werden. Die internen Webdienste FQDN ist die URL für Business Server eine Verbindung mit Skype von internen Benutzern verwendet.
    
4. Geben Sie optional für **Überwachungsports** und **Veröffentlichte Ports** neue HTTP-, HTTPS- bzw. HTTP- und HTTPS-Werte ein. Überwachungsports werden von den Internetinformationsdiensten (IIS) zum Überwachen auf eingehenden SIP-Datenverkehr (Session Initiation Protocol) genutzt. Veröffentlichte Ports werden für ein Lastenausgleichsgerät oder einen Reverseproxyserver konfiguriert und dienen ebenfalls zum Überwachen auf eingehenden SIP-Datenverkehr. In der Standardeinstellung sind sowohl der HTTP-Überwachungsport als auch der veröffentlichte HTTP-Port auf den Wert 80 festgelegt. Die entsprechenden HTTPS-Ports sind auf 443 festgelegt. Der Standardwert für die beiden veröffentlichten HTTP-Ports ist 8080, die entsprechenden HTTPS-Ports sind auf 4443 festgelegt.
    
5. Klicken Sie auf **OK**.
    
Wenn Sie entweder den internen vollqualifizierten Domänennamen oder beliebige Überwachungsportzuweisungen ändern, müssen Sie das lokale Setup auf allen Servern im Pool erneut ausführen, damit diese Änderungen wirksam werden.
  

