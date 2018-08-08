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
description: 'Zusammenfassung: Überprüfen der Windows-Client-Support-Anforderungen beim Planen von Skype für Business Server.'
ms.openlocfilehash: 161933f5982919376dd6c9610d47c78866316cdc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984953"
---
# <a name="windows-client-requirements-and-software-support"></a>Clientanforderungen für Windows und Software-support
 
**Zusammenfassung:** Überprüfen Sie die Windows-Client-Support-Anforderungen beim Planen von Skype für Business Server.
  
In diesem Abschnitt werden die Software erforderlich, um die Skype für Unternehmen Windows-Clients unterstützen.  Diese Clients werden bei der Installation von Office 365 installiert und auch unter [Herunterladen Skype für Unternehmen für alle Ihre Geräte](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)verfügbar sind.
  
> [!NOTE]
> Das Onlinebesprechungs-Add-in für Skype für Unternehmen, das die besprechungsverwaltung aus dem Outlook-Client für messaging und Zusammenarbeit unterstützt, wird automatisch mit Skype für Unternehmen installiert. 
  
**Skype für Business-Client und das Onlinebesprechungs-Add-in für die erforderliche Software**

|**Systemkomponente**|**Unterstützte Versionen**|
|:-----|:-----|
|Windows-Betriebssystem  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7-Betriebssystem  <br/> Windows Server 2008 R2 oder höher mit dem neuesten Servicepack  <br/> **Hinweis:** Skype für Unternehmen und das Onlinebesprechungs-Add-in für Skype für Unternehmen werden unter Windows Vista oder Windows XP (beliebige Version) nicht unterstützt. <br/> |
|Installation und Updates  <br/> |Administratorrechte und -berechtigungen  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11 als browser  <br/>  Internet Explorer 10-Internetbrowser <br/> Internet Explorer 9-Internetbrowser  <br/> Internet Explorer 8-Internetbrowser  <br/> Internet Explorer 7-Internetbrowser  <br/> Webbrowser Mozilla Firefox  <br/>  Google Chrome-Webbrowser  <br/>**Hinweis:** Bei Verwendung von Skype für Unternehmen mit Microsoft Exchange Online und Ihre Organisation einen authentifizierenden HTTP-Proxy, Internet Explorer 8 bereitgestellt hat, oder höher ist erforderlich.           |
|Microsoft Office-Integration  <br/> | Outlook 2010 oder höher |
|Microsoft Exchange-Integration  <br/> | Microsoft Exchange Server 2010 oder höher  | 
   
## <a name="hardware"></a>Hardware

Verweisen Sie auf die Office 365- [Systemanforderungen](https://products.office.com/en-us/office-system-requirements) für die Hardware zum Ausführen der Skype für Business Client erforderlich sind.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype-Besprechungen App und Skype für Business Web App 

Unterstützen bestimmte Kombinationen von Betriebssystemen und Browsern, der Skype Besprechungen App und Skype für Web-Geschäfts-App. Weitere Informationen hierzu finden Sie unter [Planen von Besprechungen-Clients (Web App und Besprechungen App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Verwenden von verbindlichen Profilen

Wenn Sie planen, verwenden die Skype für Business-Konferenzfunktionen, vermeiden der Verwendung von Active Directory-Domänendienste verbindlicher Profiles zur Anmeldung bei der Skype für Business-Client. Da verbindlichen Profilen Benutzerprofile schreibgeschützt sind, können die public Key-Infrastruktur (PKI)-Schlüssel, die für die Skype für Business-Konferenzen erforderlich sind auf das Profil gespeichert werden. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Systemanforderungen für Skype for Business für Windows Phone
 
 
Microsoft Skype für Business für Windows Phone bietet Sofortnachrichten (IM), erweiterte Anwesenheit und Telefonie für Benutzer in Ihrer Organisation, die über ein Smartphone oder ein mobiles Windows Professional-Gerät Verbindungen herstellen. Mobile Geräte können Benutzer die Reichweite von Skype für Unternehmen zu erweitern. In diesem Thema werden Planungsaspekte für Skype für Business für Windows Phone, die darunter das Identifizieren von erforderlichen Komponenten und technische Anforderungen, erforderliche Komponenten und Bereitstellung.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Voraussetzungen für Skype for Business Windows Phone

Es folgen die Skype Business für Windows Phone erforderliche Komponenten.
  
- Windows Phone 8.1 oder höher.
    
- Das Windows Phone-Gerät muss über die neuesten Updates verfügen, die von Microsoft bereitgestellt wurden. Weitere Informationen hierzu finden Sie unter dem Windows Phone 8.1-Abschnitt an der [Windows Phone 8-Verlauf zu aktualisieren](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- Auf dem Gerät müssen 22 MB Speicherplatz verfügbar sein.
    
- Der Benutzer muss einen Sprach- und Datendienstvertrag bei einem Netzbetreiber abgeschlossen haben.


## <a name="see-also"></a>Siehe auch

[Planen von Besprechungen-Clients (Web App und Besprechungen App)](meetings-clients.md)
  
[Skype für Unternehmen auf Mac-Clientanforderungen](mac-requirements.md)

[Laden Sie für alle Ihre Geräte Skype für Unternehmen](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 – Systemanforderungen](https://products.office.com/en-us/office-system-requirements)