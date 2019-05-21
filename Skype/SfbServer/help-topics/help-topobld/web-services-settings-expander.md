---
title: Einstellungen für Webdienste – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: In Topology Builder können Sie die Porteinstellungen ändern, die für interne und externe Webdienste verwendet werden. Darüber hinaus können Sie mithilfe des Topologie-Generators den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools konfigurieren, der auf die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird, wenn Sie einen DNS-Lastenausgleich (Domain Name System) bereitstellen.
ms.openlocfilehash: 8b68a2318434c8849c180bdde188e0fe69dfd61f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282063"
---
# <a name="web-services-settings-expander"></a>Einstellungen für Webdienste – Erweiterung
 
In Topology Builder können Sie die Porteinstellungen ändern, die für interne und externe Webdienste verwendet werden. Darüber hinaus können Sie mithilfe des Topologie-Generators den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools konfigurieren, der auf die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird, wenn Sie einen DNS-Lastenausgleich (Domain Name System) bereitstellen.
  
### <a name="editing-web-services-settings"></a>Bearbeiten von Webdiensteinstellungen

1. Wählen Sie den entsprechenden Front-End-Server der Standard Edition oder den Front-End-Pool der Enterprise Edition aus und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf die Registerkarte **Webdienste**.
    
    > [!CAUTION]
    > Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als **pool01.contoso.com**definieren, können Sie **pool01.contoso.com** nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie sich entscheiden, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.
  
3. Wenn Sie die Eigenschaften eines Enterprise Edition-Pools bearbeiten, steht die Option **FQDN überschreiben** zur Verfügung. Diese Option darf nur ausgewählt werden, wenn Sie mit dem DNS-Lastenausgleich (Domain Name System) arbeiten. Wählen Sie bei Verwendung des DNS-Lastenausgleichs **FQDN überschreiben** aus, und geben Sie in das Textfeld den vollqualifizierten Domänennamen des Pools ein, der in die physischen IP-Adressen aller Server in diesem Pool aufgelöst wird. Wenn Sie nicht mit dem DNS-Lastenausgleich arbeiten und **FQDN überschreiben** deaktiviert lassen, kann der vollqualifizierte Domänenname der internen Webdienste nicht geändert werden. Der interne Webdienste-FQDN ist die URL, die von internen Benutzern zum Herstellen einer Verbindung mit Skype for Business Server verwendet wird.
    
4. Geben Sie optional für **Überwachungsports** und **Veröffentlichte Ports** neue HTTP-, HTTPS- bzw. HTTP- und HTTPS-Werte ein. Überwachungsports werden von den Internetinformationsdiensten (IIS) zum Überwachen auf eingehenden SIP-Datenverkehr (Session Initiation Protocol) genutzt. Veröffentlichte Ports werden für ein Lastenausgleichsgerät oder einen Reverseproxyserver konfiguriert und dienen ebenfalls zum Überwachen auf eingehenden SIP-Datenverkehr. In der Standardeinstellung sind sowohl der HTTP-Überwachungsport als auch der veröffentlichte HTTP-Port auf den Wert 80 festgelegt. Die entsprechenden HTTPS-Ports sind auf 443 festgelegt. Der Standardwert für die beiden veröffentlichten HTTP-Ports ist 8080, die entsprechenden HTTPS-Ports sind auf 4443 festgelegt.
    
5. Klicken Sie auf **OK**.
    
Wenn Sie entweder den internen vollqualifizierten Domänennamen oder beliebige Überwachungsportzuweisungen ändern, müssen Sie das lokale Setup auf allen Servern im Pool erneut ausführen, damit diese Änderungen wirksam werden.
  

