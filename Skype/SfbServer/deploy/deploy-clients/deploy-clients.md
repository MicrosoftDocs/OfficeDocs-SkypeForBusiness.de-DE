---
title: Bereitstellen von Clients für Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über die Enterprise-Client-Installationsmethoden für Skype for Business.'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805695"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Bereitstellen von Clients für Skype for Business Server
 
**Zusammenfassung:** Übersicht über die Enterprise-Client-Installationsmethoden für Skype for Business.
  
Wie Sie Skype for Business für Ihre Benutzer bereitstellen, hängt davon ab, ob Sie Skype for Business als Teil eines Microsoft 365- oder Office 365-Plans oder eine Volumenlizenzversion von Skype for Business erworben haben. 
  
- **Microsoft 365 oder Office 365** Wenn Sie über einen Microsoft 365- oder Office 365-Plan verfügen, der Skype for Business umfasst, wird die verwendete Installationstechnologie als Klick-und-Klick bezeichnet. Sie können Ihren Benutzern die Installation von Skype for Business über das Microsoft 365 Admin Center ermöglichen. Oder Sie können Skype for Business für Ihre Benutzer bereitstellen, indem Sie die Software in Ihr lokales Netzwerk herunterladen und dann Ihre vorhandenen Softwarebereitstellungstools verwenden, z. B. mit Microsoft Endpoint Configuration Manager. Installationsinformationen zu Skype for Business, die in Microsoft 365 und Office 365 enthalten sind, finden Sie unter Bereitstellen des Skype for Business-Clients [in Microsoft 365 oder Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)
    
- **Volumenlizenz** Wenn Sie über eine Volumenlizenzversion des Skype for Business 2015- oder 2016-Clients verfügen, wird Windows Installer (MSI) als Installationstechnologie verwendet. Ein Windows Installer-basiertes Installationspaket besteht aus mehreren MSI-Dateien. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus. Der Skype for Business 2019-Client verwendet Klick-und-Ausführen-Installationsprogramme.
    
In den Themen in diesem Abschnitt wird beschrieben, wie Sie Windows Installer verwenden und anpassen, um den Skype for Business-Client über Ihre normalen Verfahren für Ihre Benutzer bereitstellen zu können.
  
> [!NOTE]
> Das Skype-Besprechungs-Add-In für Microsoft Office, das die Besprechungsverwaltung über den Messaging- und Zusammenarbeitsclient von Outlook unterstützt, wird automatisch mit Skype for Business-Clients installiert. 
  
> [!NOTE]
> Die Microsoft 365- und Office 365-Setupprogramme deinstallieren frühere Versionen von Lync nicht. Der Skype for Business-Client wird nebeneinander mit anderen Lync-Clients installiert. 
  
## <a name="installing-windows-clients"></a>Installieren von Windows-Clients

- [Anpassen der Windows-Client-Installation in Skype for Business Server](customize-windows-client-installation.md)
    
- [Konfigurieren der Clienterfahrung mit Skype for Business](configure-the-client-experience.md)
    
- [Konfigurieren der intelligenten Kontaktliste in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installieren von Geräteclients

- [Installieren und Testen von Skype for Business for Windows Phone](windows-phone.md)
    
- [Installieren und Testen von Skype for Business für iOS](ios.md)
    
    
- [Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Bereitstellen von herunterladbaren Webclients in Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Anpassen der Mac-Client-Erfahrung in Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen des Skype for Business-Clients in Microsoft 365 oder Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
