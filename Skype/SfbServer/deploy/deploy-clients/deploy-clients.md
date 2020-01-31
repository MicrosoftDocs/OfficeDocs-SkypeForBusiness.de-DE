---
title: Bereitstellen von Clients für Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über Unternehmensclient-Installationsmethoden für Skype for Business.'
ms.openlocfilehash: b791a4f460eaeac86345eae8896046d90d88831b
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628291"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Bereitstellen von Clients für Skype for Business Server
 
**Zusammenfassung:** Übersicht über die Enterprise-Client-Installationsmethoden für Skype for Business.
  
Wie Sie Skype for Business für Ihre Benutzer bereitstellen, hängt davon ab, ob Sie Skype for Business im Rahmen eines Office 365-Plans erworben haben oder eine Volumenlizenzversion von Skype for Business erworben haben. 
  
- **Office 365** Wenn Sie über einen Office 365-Plan verfügen, der Skype for Business umfasst, wird die verwendete Installationstechnologie als Klick-und-Los bezeichnet. Mit Office 365 können Sie es Ihren Benutzern ermöglichen, Skype for Business für sich selbst aus dem Office 365-Portal zu installieren. Oder Sie können Skype for Business für Ihre Benutzer bereitstellen, indem Sie die Software in Ihr lokales Netzwerk herunterladen und dann Ihre vorhandenen Softwarebereitstellungstools verwenden, beispielsweise mit Microsoft Endpoint Configuration Manager. Installationsinformationen zu Skype for Business, die in Office 365 enthalten sind, finden Sie unter [Bereitstellen des Skype for Business-Clients in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Volumen lizenziert** Wenn Sie über eine Volumenlizenzversion des Skype for Business 2015-oder 2016-Clients verfügen, ist die verwendete Installationstechnologie Windows Installer (MSI). Ein Windows Installer-basiertes Installationspaket besteht aus mehreren MSI-Dateien. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus. Der Skype for Business 2019-Client verwendet Klick-und-Los-Installationsprogramme.
    
In den Themen in diesem Abschnitt wird beschrieben, wie Sie den Windows Installer verwenden und anpassen, um den Skype for Business-Client über Ihre normalen Verfahren für Ihre Benutzer bereitzustellen.
  
> [!NOTE]
> Das Skype-Besprechungs-Add-in für Microsoft Office, das die Besprechungsverwaltung innerhalb des Outlook-Messaging-und Zusammenarbeits-Clients unterstützt, wird automatisch mit Skype for Business-Clients installiert. 
  
> [!NOTE]
> Das Office 365-Setupprogramm deinstalliert frühere Versionen von lync nicht. Der Skype for Business-Client wird parallel zu anderen lync-Clients installiert. 
  
## <a name="installing-windows-clients"></a>Installieren von Windows-Clients

- [Anpassen der Windows-Clientinstallation in Skype for Business Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Konfigurieren der intelligenten Kontaktliste in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installieren von Geräteclients

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Bereitstellen von Webdownload-Clients in Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Anpassen der Mac-Clienterfahrung in Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen des Skype for Business-Clients in Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
