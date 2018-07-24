---
title: Bereitstellen von Clients für Skype für Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.'
ms.openlocfilehash: 31eb109f80379487ba50342817759f8d9b30acda
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985687"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Bereitstellen von Clients für Skype für Business Server
 
**Zusammenfassung:** Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.
  
Wie Sie Skype für Unternehmen für die Benutzer bereitstellen, hängt gibt an, ob Sie Skype für Unternehmen im Rahmen eines Plans für Office 365 erworben haben, oder Sie eine Volume lizenzierte Version von Skype für Unternehmen erworben. 
  
- **Office 365** Wenn Sie einen Office 365-Plan haben, der Skype für Unternehmen enthält, wird die Installation-Technologie, die verwendet wird, Klick-und-Los aufgerufen. Mit Office 365 können Sie Ihre Benutzer Skype für Unternehmen für sich selbst über Office 365-Portal installieren lassen. Oder Sie können Skype für Unternehmen Herunterladen der Software in Ihr lokales Netzwerk und dann mit der vorhandenen Software von Tools wie Microsoft System Center Configuration Manager für die Benutzer bereitstellen. Installationsinformationen zu Skype für Unternehmen, die mit Office 365 enthalten ist, finden Sie unter [Bereitstellen der Skype für Business-Client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Volume lizenziert** Wenn Sie eine Volume lizenzierte Version von der Skype für Business 2015 oder 2016 Client verfügen, ist die Installation-Technologie, die verwendet wird Windows Installer (MSI). Ein Windows Installer-basierten Installationspaket umfasst mehrere MSI-Dateien. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus. Die Skype für Business 2019 Client verwendet Klick-und-Los-Installer.
    
In den Themen in diesem Abschnitt wird beschrieben, wie verwenden und Anpassen von Windows Installer, um die Skype für Business-Client, die Benutzern in Ihrer normalen Verfahren bereitstellen.
  
> [!NOTE]
> Die Skype-Meeting-Add-in für Microsoft Office, das die besprechungsverwaltung aus dem Outlook-Client für messaging und Zusammenarbeit unterstützt, wird automatisch mit Skype für Business-Clients. 
  
> [!NOTE]
> Das Setupprogramm für Office 365 wird nicht mit frühere Versionen von Lync deinstalliert. Die Skype für Business-Client installiert Side-by-Side mit anderen Lync-Clients. 
  
## <a name="installing-windows-clients"></a>Installieren von Windows-clients

- [Anpassen von Windows-Client-Installation in Skype für Business Server](customize-windows-client-installation.md)
    
- [Konfigurieren der Clientumgebung mit Skype for Business](configure-the-client-experience.md)
    
- [Konfigurieren der intelligenten Kontaktliste in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installieren von Gerät-clients

- [Skype for Business Server 2015: Installieren und Testen von Skype for Business für Windows Phone](windows-phone.md)
    
- [Installieren und Testen von Skype for Business für iOS](ios.md)
    
- [Bereitstellen von Skype Room System in Skype for Business Server](deploy-skype-room-system.md)
    
- [Bereitstellen von Skype Room Systems v2](room-systems-v2.md)
    
- [Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Bereitstellen Sie herunterladbare Webclients in Skype für Business Server](deploy-web-downloadable-clients.md)
    
- [Anpassen der Mac-Clienterfahrung in Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen der Skype für Business-Client in Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)