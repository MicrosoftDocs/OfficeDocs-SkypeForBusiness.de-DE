---
title: Windows-Clientanforderungen und Software Support
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Zusammenfassung: Überprüfen Sie die Supportanforderungen für Windows-Clients beim Planen von Skype for Business Server.'
ms.openlocfilehash: bbcbf11da53b2895f04725fda57342c17989b7f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277272"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows-Clientanforderungen und Software Support
 
**Zusammenfassung:** Überprüfen Sie die Anforderungen des Windows-Client-Supports während der Planung von Skype for Business Server.
  
In diesem Abschnitt wird die Software zusammengefasst, die zur Unterstützung der Skype for Business-Windows-Clients erforderlich ist.  Diese Clients werden installiert, wenn Office 365 installiert wird, und sind auch unter [Herunterladen von Skype for Business auf allen ihren Geräten](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)verfügbar.
  
> [!NOTE]
> Das Online Besprechungs-Add-in für Skype for Business, das die Besprechungsverwaltung innerhalb des Outlook-Messaging-und Zusammenarbeits-Clients unterstützt, wird automatisch mit Skype for Business installiert. 
  
**Software, die für den Skype for Business-Client und das Online Besprechungs-Add-in erforderlich ist**

|**Systemkomponente**|**Unterstützte Versionen**|
|:-----|:-----|
|Windows-Betriebssystem  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7-Betriebssystem  <br/> Windows Server 2008 R2 oder höher mit dem neuesten Service Pack  <br/> **Hinweis:** Skype for Business und das Online-Besprechungs-Add-in für Skype for Business werden unter Windows Vista oder Windows XP (jeder Version) nicht unterstützt. <br/> |
|Installation und Updates  <br/> |Administratorrechte und -berechtigungen  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet Browser  <br/>  Internet Explorer 10 Internet Browser <br/> Internet Explorer 9 Internet Browser  <br/> Internet Explorer 8 Internet Browser  <br/> Internet Explorer 7 Internet Browser  <br/> Webbrowser Mozilla Firefox  <br/>  Google Chrome-Webbrowser  <br/>**Hinweis:** Wenn Sie Skype for Business mit Microsoft Exchange Online verwenden und Ihre Organisation einen authentifizierenden http-Proxy bereitgestellt hat, ist Internet Explorer 8 oder höher erforderlich.           |
|Microsoft Office-Integration  <br/> | Outlook 2010 oder höher |
|Microsoft Exchange-Integration  <br/> | Microsoft Exchange Server 2010 oder höher  | 
   
## <a name="hardware"></a>Hardware

Lesen Sie die [System Anforderungen](https://products.office.com/en-us/office-system-requirements) von Office 365 für die Hardware, die zum Ausführen des Skype for Business-Clients erforderlich ist.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype-Besprechungs-APP und Skype for Business Web App 

Die Skype-Besprechungs-APP und die Skype for Business-Web-App unterstützen bestimmte Kombinationen von Betriebssystemen und Browsern. Ausführliche Informationen finden Sie unter [Planen von Besprechungs Clients (app für Web App und Besprechungen)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Verwenden von verbindlichen Profilen

Wenn Sie beabsichtigen, die Skype for Business-Konferenzfeatures zu verwenden, vermeiden Sie die Verwendung von Active Directory-Domänendiensten für die Anmeldung beim Skype for Business-Client. Da es sich bei Pflicht Profilen um schreibgeschützte Benutzerprofile handelt, können die für Skype for Business-Konferenzen erforderlichen PKI-Schlüssel (Public Key Infrastructure) nicht im Profil gespeichert werden. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Systemanforderungen für Skype for Business für Windows Phone
 
 
Microsoft Skype for Business für Windows phone bietet Instant Messaging (im), erweiterte Anwesenheitsinformationen und Telefonie für Benutzer in Ihrer Organisation, die über ein Smartphone oder ein Windows Professional-Mobilgerät eine Verbindung herstellen. Mit mobilen Geräten können Nutzer die Reichweite von Skype for Business verlängern. In diesem Thema werden Planungsüberlegungen für Skype for Business für Windows Phone beschrieben, die die Ermittlung von Voraussetzungen und technischen Anforderungen, erforderlichen Komponenten und Bereitstellungsanleitungen beinhalten.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Voraussetzungen für Skype for Business Windows Phone

Im folgenden finden Sie die Voraussetzungen für Skype for Business für Windows phone.
  
- Windows Phone 8.1 oder höher.
    
- Das Windows Phone-Gerät muss über die neuesten Updates verfügen, die von Microsoft bereitgestellt wurden. Ausführliche Informationen finden Sie im Abschnitt Windows Phone 8,1 unter [Windows Phone 8-Updateverlauf](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- Auf dem Gerät müssen 22 MB Speicherplatz verfügbar sein.
    
- Der Benutzer muss einen Sprach- und Datendienstvertrag bei einem Netzbetreiber abgeschlossen haben.


## <a name="see-also"></a>Siehe auch

[Planen von Besprechungs Clients (app für Web App und Besprechungen)](meetings-clients.md)
  
[Skype for Business für Mac-Clientanforderungen](mac-requirements.md)

[Herunterladen von Skype for Business auf allen ihren Geräten](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365-Systemanforderungen](https://products.office.com/en-us/office-system-requirements)
