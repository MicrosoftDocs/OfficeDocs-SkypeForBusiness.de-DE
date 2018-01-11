---
title: "Einrichten Ihres Netzwerks für Skype-Livekonferenz"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 3e4afb09d6a65654af418e14cc124e3c78dc0e0c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Einrichten Ihres Netzwerks für Skype-Livekonferenz

Nach der [Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md) Skype-Livekonferenz müssen Sie Ihr Netzwerk konfigurieren. Führen Sie diesen Schritt aus, wenn Sie Webinare und andere Konferenzen für Personen außerhalb Ihres Unternehmens durchführen möchten.
  
Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.
  
Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, das Sie zu Konferenzen einladen können, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus.
  
## <a name="step-1-set-up-allowed-domains"></a>Schritt 1: Einrichten von zulässigen Domänen

Verwenden Sie **eine** der folgenden Methoden, um zulässige Domänen einzurichten:
  
### 

 **Methode 1: Verwenden des Office 365 Admin Center**
  
1. Besuchen Sie das **Office 365 Administrationscenter** , und klicken Sie dann im linken Navigationsbereich, auf **Einstellungen** > **Services &amp; -add-ins**, und wählen Sie dann **Skype für Unternehmen**.
    
2. Klicken Sie auf der Seite **externe Freigabe** unter **Domäne Ausnahmen**wählen Sie **alle Domänen werden blockiert, es sei denn**, und geben Sie die folgenden Domänen, getrennt durch ein Komma (,):
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. Klicken Sie auf **Speichern**.
    
### 

 **Methode 2: Verwenden von Windows PowerShell**
  
- Wählen Sie im **Startmenü**mit der rechten Maustaste in **Windows PowerShell** , und klicken Sie auf **als Administrator ausführen**. Geben Sie in der **Windows PowerShell** -Fenster jede Zeile, und drücken Sie die EINGABETASTE.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Schritt 2: Hinzufügen von Skype Besprechung übertragen Domänen, URLs und IP-Adressen

Im zweiten Schritt des Setupvorgangs fügen Sie zuerst die benötigten Domänen hinzu. Anschließend fügen Sie die IP-Adressen und URLs hinzu, die erforderlich sind, damit Skype-Livekonferenz funktioniert.
  
- **Fügen Sie die erforderlichen URLs und IP-Adressen für Skype for Business Online-Endpunkte hinzu, die Sie**[hier](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo) finden.
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Einrichten von Skype-Livekonferenz in Hybridbereitstellungen und -organisationen

Wenn Sie einen Skype für Business Online-Organisation und einer lokalen Bereitstellung von Lync Server 2010, Microsoft Lync Server 2013 und Skype für Business Server 2015 und haben Sie beide Benutzer online und lokalen, es sind weitere Schritte zur Setup aus, die Sie benötigen, führen Sie Zusätzlich zu den oben, um Ihre lokale Organisation mit Skype für Business Online kommunizieren und alle Benutzer können zum Erstellen und teilnehmen an einer Besprechung übertragen Skype zulassen aktivieren. Um herauszufinden, was diese Anforderungen sind, finden Sie unter [Konfigurieren der lokalen Bereitstellung für Skype Besprechung übertragen werden](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## <a name="related-topics"></a>Verwandte Themen

[Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md)
  
[URLs und IP-Adressbereiche von Office 365](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

