---
title: Windows-Clientanforderungen und Softwareunterstützung
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Überprüfen Sie die Anforderungen für den Windows-Client Support beim Planen Skype for Business Server.'
ms.openlocfilehash: 39f9efcd2008dacb653538b56f2aff3fcb8b7887
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928238"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows-Clientanforderungen und Softwareunterstützung
 
**Zusammenfassung:** Überprüfen Sie die Anforderungen für den Windows-Client Support beim Planen Skype for Business Server.
  
In diesem Abschnitt wird die Software zusammengefasst, die zur Unterstützung der Skype for Business Windows-Clients erforderlich ist.  Diese Clients werden installiert, wenn Office 365 installiert und auch unter [Download Skype for Business auf allen Geräten](https://products.office.com/skype-for-business/download-app?tab=tabs-3)verfügbar sind.
  
> [!NOTE]
> Das Online Besprechungs-Add-in für Skype for Business, das die Besprechungsverwaltung im Outlook-Client für Messaging und Zusammenarbeit unterstützt, wird automatisch mit Skype for Business installiert. 
  
**Für Skype for Business-Client und das Online-Besprechungs-Add-in erforderliche Software**

|**Systemkomponente**|**Unterstützte Versionen**|
|:-----|:-----|
|Windows-Betriebssystem  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 oder höher mit dem neuesten Service Pack  <br/> **Hinweis:** Skype for Business und das Online-Besprechungs-Add-in für Skype for Business werden auf Windows Vista oder Windows XP (jede Version) nicht unterstützt. <br/> |
|Installation und Updates  <br/> |Administratorrechte und -berechtigungen  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet Browser  <br/>  Internet Explorer 10 Internet Browser <br/> Internet Explorer 9 Internet Browser  <br/> Internet Explorer 8 Internet Browser  <br/> Internet Explorer 7-Internet Browser  <br/> Webbrowser Mozilla Firefox  <br/>  Google Chrome-Webbrowser  <br/>**Hinweis:** Wenn Sie Skype for Business mit Microsoft Exchange Online verwenden und Ihre Organisation einen authentifizierenden http-Proxy bereitgestellt hat, ist Internet Explorer 8 oder höher erforderlich.           |
|Microsoft Office-Integration  <br/> | Outlook 2010 oder höher |
|Microsoft Exchange-Integration  <br/> | Microsoft Exchange Server 2010 oder höher  | 
   
## <a name="hardware"></a>Hardware

Lesen Sie die Office 365 [System Anforderungen](https://products.office.com/office-system-requirements) für die Hardware, die zum Ausführen des Skype for Business-Clients erforderlich ist.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype-Besprechungs-APP und Skype for Business-Webanwendung 

Die Skype-Besprechungs-APP und die Skype for Business-Webanwendung unterstützen bestimmte Kombinationen aus Betriebssystemen und Browsern. Ausführliche Informationen finden Sie unter [Plan for Meetings Clients (app für Webanwendungen und Besprechungen)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Verwenden von verbindlichen Profilen

Wenn Sie die Skype for Business Konferenzfeatures verwenden möchten, vermeiden Sie die Verwendung Active Directory-Domänendienste obligatorischen Profilen, um sich beim Skype for Business-Client anzumelden. Da es sich bei obligatorischen Profilen um schreibgeschützte Benutzerprofile handelt, können die PKI-Schlüssel (Public Key Infrastructure), die für Skype for Business Konferenzen erforderlich sind, nicht im Profil gespeichert werden. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>System Anforderungen für Skype for Business für Windows Phone
 
 
Microsoft Skype for Business für Windows phone bietet Instant Messaging (Sofortnachrichten), erweiterte Anwesenheitsinformationen und Telefonie für Benutzer in Ihrer Organisation, die eine Verbindung von einem Smartphone oder einem mobilen Windows Professional-Gerät herstellen. Mobile Geräte ermöglichen Benutzern, die Reichweite von Skype for Business zu erweitern. In diesem Thema werden Planungsüberlegungen für Skype for Business für Windows Phone beschrieben, die die Ermittlung von Voraussetzungen und technischen Anforderungen, erforderlichen Komponenten und Bereitstellungsanleitungen umfassen.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype for Business für Windows Phone Voraussetzungen

Im folgenden finden Sie die Skype for Business für Windows Phone Voraussetzungen.
  
- Windows Phone 8,1 oder höher.
    
- Das Windows Phone Gerät muss über die neuesten Updates verfügen, die von Microsoft verfügbar sind. Ausführliche Informationen finden Sie im Abschnitt Windows Phone 8,1 unter [Windows Phone 8 Updateverlauf](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- Das Gerät muss 22 MB verfügbaren Speicherplatz aufweisen.
    
- Der Benutzer muss einen Sprach- und Datendienstvertrag bei einem Netzbetreiber abgeschlossen haben.


## <a name="see-also"></a>Siehe auch

[Planen von Besprechungs Clients (app für Webanwendungen und Besprechungen)](meetings-clients.md)
  
[Skype for Business auf Mac-Clientanforderungen](mac-requirements.md)

[Herunterladen von Skype for Business auf allen Geräten](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Systemanforderungen für Office 365](https://products.office.com/office-system-requirements)
