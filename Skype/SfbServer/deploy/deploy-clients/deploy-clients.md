---
title: Bereitstellen von Clients für Skype für Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.'
ms.openlocfilehash: db5b1a4ed51aed5986cd954af9cdbecab208647d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893462"
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
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Konfigurieren der intelligenten Kontaktliste in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installieren von Gerät-clients

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Bereitstellen Sie herunterladbare Webclients in Skype für Business Server](deploy-web-downloadable-clients.md)
    
- [Anpassen der Mac-Clienterfahrung in Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen der Skype für Business-Client in Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
