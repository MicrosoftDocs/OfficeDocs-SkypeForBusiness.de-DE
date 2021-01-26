---
title: Anforderungen und Softwareunterstützung für den Windows-Client
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Zusammenfassung: Überprüfen Sie die Supportanforderungen für den Windows-Client, während Sie Skype for Business Server planen.'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816065"
---
# <a name="windows-client-requirements-and-software-support"></a>Anforderungen und Softwareunterstützung für den Windows-Client
 
**Zusammenfassung:** Überprüfen Sie die Supportanforderungen für den Windows-Client, während Sie Skype for Business Server planen.
  
In diesem Abschnitt wird die erforderliche Software zur Unterstützung der Skype for Business -Windows-Clients zusammengefasst. Diese Clients werden bei der Installation von Microsoft 365 oder Office 365 installiert und sind auch auf allen Ihren Geräten unter ["Skype for Business herunterladen" verfügbar.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> Das Online-Besprechungs-Add-In für Skype for Business, das die Besprechungsverwaltung über den Messaging- und Zusammenarbeitsclient von Outlook unterstützt, wird automatisch mit Skype for Business installiert. 
  
**Erforderliche Software für den Skype for Business-Client und das Online-Besprechungs-Add-In**

|**Systemkomponente**|**Unterstützte Versionen**|
|:-----|:-----|
|Windows-Betriebssystem  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 oder höher mit dem neuesten Service Pack  <br/> **Hinweis:** Skype for Business und das Online-Besprechungs-Add-In für Skype for Business werden unter Windows Vista oder Windows XP (beliebige Version) nicht unterstützt. <br/> |
|Installation und Updates  <br/> |Administratorrechte und -berechtigungen  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11-Internetbrowser  <br/>  Internet Explorer 10 Internetbrowser <br/> Internet Explorer 9-Internetbrowser  <br/> Internet Explorer 8 Internetbrowser  <br/> Internet Explorer 7-Internetbrowser  <br/> Webbrowser Mozilla Firefox  <br/>  Google Chrome-Webbrowser  <br/>**Hinweis:** Wenn Sie Skype for Business mit Microsoft Exchange Online und Ihre Organisation einen authentifizierenden HTTP-Proxy bereitgestellt hat, Internet Explorer 8 oder höher erforderlich.           |
|Microsoft Office-Integration  <br/> | Outlook 2010 oder höher |
|Microsoft Exchange-Integration  <br/> | Microsoft Exchange Server 2010 oder höher  | 
   
## <a name="hardware"></a>Hardware

Lesen Sie die Microsoft 365- und Office [System-Anforderungen](https://products.office.com/office-system-requirements) für die Hardware, die zum Ausführen des Skype for Business-Clients erforderlich ist.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype-Besprechungs-App und Skype for Business Web App 

Die Skype-Besprechungs-App und Skype for Business Web App unterstützen bestimmte Kombinationen von Betriebssystemen und Browsern. Weitere Informationen finden Sie unter [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Verwenden von verbindlichen Profilen

Wenn Sie planen, die Skype for Business-Konferenzfunktionen zu verwenden, vermeiden Sie die Verwendung obligatorischer Active Directory Domain Services-Profile, um sich beim Skype for Business-Client zu anmelden. Da obligatorische Profile schreibgeschützte Benutzerprofile sind, können die für Skype for Business-Konferenzen erforderlichen Public Key Infrastructure (PKI)-Schlüssel nicht im Profil gespeichert werden. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Systemanforderungen für Skype for Business for Windows Phone
 
 
Microsoft Skype for Business for Windows Phone bietet Chat, erweiterte Anwesenheit und Telefonie für Benutzer in Ihrer Organisation, die über ein Smartphone oder ein mobiles Windows Professional-Gerät eine Verbindung herstellen. Mit mobilen Geräten können Benutzer die Reichweite von Skype for Business erweitern. In diesem Thema werden Planungsüberlegungen für Skype for Business for Windows Phone beschrieben, die das Identifizieren von Voraussetzungen und technischen Anforderungen, erforderliche Komponenten und Anleitungen zur Bereitstellung umfassen.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Voraussetzungen für Skype for Business Windows Phone A0

Nachfolgend finden Sie die Voraussetzungen für Skype for Business Windows Phone.
  
- Windows Phone 8.1 oder höher.
    
- Das Windows Phone muss über die neuesten Updates von Microsoft verfügen. Weitere Informationen finden Sie im Abschnitt Windows Phone 8.1 unter [Windows Phone 8 Updateverlauf.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- Das Gerät muss über 22 MB verfügbaren Speicherplatz verfügen.
    
- Der Benutzer muss einen Sprach- und Datendienstvertrag bei einem Netzbetreiber abgeschlossen haben.


## <a name="see-also"></a>Siehe auch

[Planen von Besprechungsclients (Web App und Besprechungs-App)](meetings-clients.md)
  
[Clientanforderungen für Skype for Business auf dem Mac](mac-requirements.md)

[Herunterladen von Skype for Business auf allen Geräten](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Systemanforderungen für Microsoft 365 und Office](https://products.office.com/office-system-requirements)
