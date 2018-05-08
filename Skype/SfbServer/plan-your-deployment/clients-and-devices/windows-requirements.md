---
title: Clientanforderungen für Windows und Software-support
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Zusammenfassung: Überprüfen der Windows-Client-Support-Anforderungen beim Planen der Business Server 2015 Skype.'
ms.openlocfilehash: 3dac3a8e15e53cec5605aa2b003150f491d8f2b5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Clientanforderungen für Windows und Software-support
 
**Zusammenfassung:** Überprüfen Sie die Windows-Client-Support-Anforderungen beim Planen der Business Server 2015 Skype.
  
In diesem Abschnitt werden die Software erforderlich, um die Skype für Business 2015 und 2016 Windows-Clients unterstützen.
  
Diese Clients werden bei der Installation von Office 365 installiert und auch unter [Herunterladen Skype für Unternehmen für alle Ihre Geräte](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)verfügbar sind.
  
> [!NOTE]
> Das Onlinebesprechungs-Add-in für Skype für Unternehmen, das die besprechungsverwaltung aus dem Outlook-Client für messaging und Zusammenarbeit unterstützt, wird automatisch mit Skype für Unternehmen installiert. 
  
**Software, die Skype für Unternehmen und die Online Meeting-Add-in für Skype für Unternehmen**


|**Systemkomponente**|**Unterstützte Versionen**|
|:-----|:-----|
|Windows-Betriebssystem  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7-Betriebssystem  <br/> Windows Server 2008 R2 mit dem neuesten Servicepack  <br/> **Hinweis:** Skype für Unternehmen und das Onlinebesprechungs-Add-in für Skype für Unternehmen werden unter Windows Vista oder Windows XP (beliebige Version) nicht unterstützt. <br/> |
|Installation und Updates  <br/> |Administratorrechte und -berechtigungen  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11 als browser  <br/>  Internet Explorer 10-Internetbrowser <br/> Internet Explorer 9-Internetbrowser  <br/> Internet Explorer 8-Internetbrowser  <br/> Internet Explorer 7-Internetbrowser  <br/> Webbrowser Mozilla Firefox  <br/> **Hinweis:** Bei Verwendung von Skype für Unternehmen mit Microsoft Exchange Online und Ihre Organisation einen authentifizierenden HTTP-Proxy, Internet Explorer 8 bereitgestellt hat, oder höher ist erforderlich.           |
|Microsoft Office-Integration  <br/> |Alle Integrationsfunktionen:  <br/> • 2016 Outlook-Client für messaging und Zusammenarbeit  <br/> • Outlook 2013-Client für messaging und Zusammenarbeit  <br/> • Outlook 2010-Client für messaging und Zusammenarbeit  <br/> |
|Microsoft Exchange-Integration  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>Hardware

Verweisen Sie auf die Office 365- [Systemanforderungen](https://products.office.com/en-us/office-system-requirements) für die Hardware zum Ausführen der Skype für Business Client erforderlich sind.
  
## <a name="skype-for-business-web-app-browsers"></a>Skype für Business App Webbrowser

Skype für Web-Geschäfts-App werden bestimmte Kombinationen von Betriebssystemen und Browsern unterstützt. Weitere Informationen hierzu finden Sie unter [Planen von Besprechungen-Clients (Web App und Besprechungen App)](meetings-clients.md). 
  
## <a name="microsoft-office-supportability"></a>Microsoft Office-Unterstützbarkeit

Skype für Business Server 2015 Clients unterstützen die Integration mit verschiedenen Versionen von Microsoft Office.
  
- Skype für Business-Integrationsfunktionen werden auf Outlook 2016, Outlook 2013 und Outlook 2010 unterstützt.
    
- Skype für Business-Integrationsfunktionen werden auf Microsoft Exchange Server 2016, Microsoft Exchange Server 2013 und Microsoft Exchange Server 2010 unterstützt.
    
- Das Onlinebesprechungs-Add-in für Skype für Unternehmen mit Office 2016, Office 2013 und Microsoft Office 2010 unterstützt.
    
## <a name="using-mandatory-profiles"></a>Verwenden von verbindlichen Profilen

Wenn Sie planen, verwenden die Skype für Business-Konferenzfunktionen, vermeiden der Verwendung von Active Directory-Domänendienste verbindlicher Profiles zur Anmeldung bei der Skype für Business-Client. Da verbindlichen Profilen Benutzerprofile schreibgeschützt sind, können die public Key-Infrastruktur (PKI)-Schlüssel, die für die Skype für Business-Konferenzen erforderlich sind auf das Profil gespeichert werden. 
  
## <a name="macintosh-operating-systems"></a>Macintosh-Betriebssysteme

Die Skype für Unternehmen auf Mac-Support-Anforderungen werden in [Skype für Unternehmen auf Mac-Clientanforderungen](mac-requirements.md)beschrieben.
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen von Besprechungen-Clients (Web App und Besprechungen App)](meetings-clients.md)
  
[Skype für Unternehmen auf Mac-Clientanforderungen](mac-requirements.md)
#### 

[Laden Sie für alle Ihre Geräte Skype für Unternehmen](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 – Systemanforderungen](https://products.office.com/en-us/office-system-requirements)

