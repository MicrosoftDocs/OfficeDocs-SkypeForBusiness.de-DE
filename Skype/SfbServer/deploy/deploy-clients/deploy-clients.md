---
title: Bereitstellen von Clients für Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>Bereitstellen von Clients für Skype for Business Server 2015
 
**Zusammenfassung:** Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.
  
Wie Sie Skype für Unternehmen für die Benutzer bereitstellen, hängt gibt an, ob Sie Skype für Unternehmen im Rahmen eines Plans für Office 365 erworben haben, oder Sie eine Volume lizenzierte Version von Skype für Unternehmen erworben. 
  
- **Office 365** Wenn Sie einen Office 365-Plan haben, der Skype für Unternehmen enthält, wird die Installation-Technologie, die verwendet wird, Klick-und-Los aufgerufen. Mit Office 365 können Sie Ihre Benutzer Skype für Unternehmen für sich selbst über Office 365-Portal installieren lassen. Oder Sie können Skype für Unternehmen Herunterladen der Software in Ihr lokales Netzwerk und dann mit der vorhandenen Software von Tools wie Microsoft System Center Configuration Manager für die Benutzer bereitstellen. Installationsinformationen zu Skype für Unternehmen, die mit Office 365 enthalten ist, finden Sie unter [Bereitstellen der Skype für Business-Client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Volume lizenziert** Wenn Sie eine Volumenlizenz-Version von Skype für Unternehmen verfügen, ist die Installation-Technologie, die verwendet wird, wird Windows Installer (MSI). Ein Windows Installer-basierten Installationspaket umfasst mehrere MSI-Dateien. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus.
    
In den Themen in diesem Abschnitt wird beschrieben, wie verwenden und Anpassen von Windows Installer, um die Skype für Business-Client, die Benutzern in Ihrer normalen Verfahren bereitstellen.
  
> [!NOTE]
> Meeting-Add-in für Skype für Unternehmen, welche meeting Verwaltung von Besprechungen Outlook unterstützt Client für messaging und Zusammenarbeit, wird automatisch mit Skype für Unternehmen Online. 
  
> [!NOTE]
> Das Setupprogramm für Office 365 wird nicht mit frühere Versionen von Lync oder Office Communicator deinstalliert. Die Skype für Business-Client installiert Side-by-Side mit anderen Lync oder Office Communicator-Clients. 
  
## <a name="installing-windows-clients"></a>Installieren von Windows-clients

- [Anpassen von Windows-Client-Installation in Skype für Business Server 2015](customize-windows-client-installation.md)
    
- [Konfigurieren der Clientumgebung mit Skype für Unternehmen](configure-the-client-experience.md)
    
- [Konfigurieren von Smart Kontaktliste in Skype für Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installieren von Gerät-clients

- [Installieren und Testen von Skype für Business für Windows Phone](windows-phone.md)
    
- [Installieren und Testen von Skype für Unternehmen für iOS](ios.md)
    
- [Bereitstellen von Skype Raum System in Skype für Business Server](deploy-skype-room-system.md)
    
- [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)
    
- [Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server 2015](deploy-the-lync-vdi-plug-in.md)
    
- [Bereitstellen von herunterladbaren Webclients in Skype für Business Server 2015](deploy-web-downloadable-clients.md)
    
- [Anpassen der Mac-Clientumgebung in Skype für Unternehmen](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Siehe auch

#### 

[Bereitstellen der Skype für Business-Client für Ihre Organisation](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

