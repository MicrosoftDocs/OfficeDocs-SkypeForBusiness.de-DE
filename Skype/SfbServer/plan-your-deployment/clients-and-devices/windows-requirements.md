---
title: Windows Clientanforderungen und Softwareunterstützung
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Zusammenfassung: Überprüfen Sie die Supportanforderungen für Windows Clients bei der Planung Skype for Business Server.'
ms.openlocfilehash: 755f60030c905bfb5a5f488e2573c12b3396ab1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627947"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows Clientanforderungen und Softwareunterstützung
 
**Zusammenfassung:** Überprüfen Sie die Supportanforderungen für Windows Clients, während Sie Skype for Business Server planen.
  
In diesem Abschnitt wird die Software zusammengefasst, die zur Unterstützung der Skype for Business Windows-Clients erforderlich ist. Diese Clients werden installiert, wenn Microsoft 365 oder Office 365 installiert werden, und sind auch auf [allen Ihren Geräten](https://products.office.com/skype-for-business/download-app?tab=tabs-3)unter Download Skype for Business verfügbar.
  
> [!NOTE]
> Das Onlinebesprechungs-Add-In für Skype for Business, das die Besprechungsverwaltung innerhalb des Outlook Messaging- und Zusammenarbeitsclients unterstützt, wird automatisch mit Skype for Business installiert. 
  
**Erforderliche Software für Skype for Business-Client und das Onlinebesprechungs-Add-In**

|**Systemkomponente**|**Unterstützte Versionen**|
|:-----|:-----|
|Windows Betriebssystem  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 oder höher mit dem neuesten Service Pack  <br/> **Hinweis:** Skype for Business und das Onlinebesprechungs-Add-In für Skype for Business werden unter Windows Vista oder Windows XP (beliebige Version) nicht unterstützt. <br/> |
|Installation und Updates  <br/> |Administratorrechte und -berechtigungen  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11-Internetbrowser  <br/>  Internet Explorer 10 Internetbrowser <br/> Internet Explorer 9-Internetbrowser  <br/> Internet Explorer 8-Internetbrowser  <br/> Internet Explorer 7-Internetbrowser  <br/> Webbrowser Mozilla Firefox  <br/>  Google Chrome-Webbrowser  <br/>**Hinweis:** Wenn Sie Skype for Business mit Microsoft Exchange Online verwenden und Ihre Organisation einen Authentifizierungs-HTTP-Proxy bereitgestellt hat, ist Internet Explorer 8 oder höher erforderlich.           |
|Microsoft Office-Integration  <br/> | Outlook 2010 oder höher |
|Microsoft Exchange-Integration  <br/> | Microsoft Exchange Server 2010 oder höher  | 
   
## <a name="hardware"></a>Hardware

Lesen Sie die [Systemanforderungen](https://products.office.com/office-system-requirements) Microsoft 365 und Office für die Hardware, die zum Ausführen des Skype for Business-Clients erforderlich ist.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype Besprechungs-App und Skype for Business-Web-App 

Die Skype Besprechungs-App und Skype for Business-Web-App bestimmte Kombinationen von Betriebssystemen und Browsern unterstützen. Ausführliche Informationen finden Sie unter [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Verwenden von verbindlichen Profilen

Wenn Sie die Skype for Business Konferenzfunktionen verwenden möchten, vermeiden Sie die Verwendung von obligatorischen Active Directory Domain Services-Profilen, um sich beim Skype for Business-Client anzumelden. Da es sich bei obligatorischen Profilen um schreibgeschützte Benutzerprofile handelt, können die PKI-Schlüssel (Public Key Infrastructure), die für Skype for Business Konferenzen erforderlich sind, nicht im Profil gespeichert werden. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Systemanforderungen für Skype for Business für Windows Phone
 
 
Microsoft Skype for Business für Windows Phone bietet Chatnachrichten, erweiterte Anwesenheit und Telefonie für Benutzer in Ihrer Organisation, die sich über ein Smartphone oder ein Windows Professional mobile Gerät verbinden. Mit mobilen Geräten können Benutzer die Reichweite von Skype for Business erweitern. In diesem Thema werden Planungsüberlegungen für Skype for Business für Windows Phone beschrieben, die die Ermittlung von Voraussetzungen und technischen Anforderungen, erforderlichen Komponenten und Bereitstellungsanleitungen umfassen.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype for Business für Windows Phone Voraussetzungen

Nachfolgend sind die Skype for Business für Windows Phone Voraussetzungen beschrieben.
  
- Windows Phone 8.1 oder höher.
    
- Das Windows Phone Gerät muss über die neuesten Updates verfügen, die von Microsoft zur Verfügung stehen. Ausführliche Informationen finden Sie im Abschnitt Windows Phone 8.1 unter [Windows Phone 8 Updateverlauf.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- Das Gerät muss über 22 MB verfügbaren Speicherplatz verfügen.
    
- Der Benutzer muss einen Sprach- und Datendienstvertrag bei einem Netzbetreiber abgeschlossen haben.


## <a name="see-also"></a>Siehe auch

[Planen von Besprechungsclients (Web App und Besprechungs-App)](meetings-clients.md)
  
[Skype for Business für Mac-Clientanforderungen](mac-requirements.md)

[Herunterladen von Skype for Business auf allen Ihren Geräten](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 und Office Systemanforderungen](https://products.office.com/office-system-requirements)
