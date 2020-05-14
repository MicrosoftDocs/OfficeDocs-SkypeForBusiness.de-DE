---
title: Bereitstellen von Clients für Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über die Installationsmethoden von Enterprise-Clients für Skype for Business.'
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220645"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Bereitstellen von Clients für Skype for Business Server
 
**Zusammenfassung:** Übersicht über die Installationsmethoden von Enterprise-Clients für Skype for Business.
  
Wie Sie Skype for Business für Ihre Benutzer bereitstellen, hängt davon ab, ob Sie Skype for Business als Teil eines Microsoft 365-oder Office 365-Plans erworben haben oder eine Volumenlizenzversion von Skype for Business erworben haben. 
  
- **Microsoft 365 oder Office 365** Wenn Sie über einen Microsoft 365-oder Office 365-Plan verfügen, der Skype for Business enthält, wird die verwendete Installationstechnologie als Klick-und-Los bezeichnet. Sie können Benutzern das Installieren von Skype for Business aus dem Microsoft 365 Admin Center ermöglichen. Oder Sie können Skype for Business für Ihre Benutzer bereitstellen, indem Sie die Software in Ihr lokales Netzwerk herunterladen und dann Ihre vorhandenen Softwarebereitstellungstools verwenden, beispielsweise mit dem Microsoft Endpoint Configuration Manager. Installationsinformationen zu Skype for Business, die mit Microsoft 365 und Office 365 geliefert werden, finden Sie unter [deploy the Skype for Business Client in Microsoft 365 oder Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Volumen lizenziert** Wenn Sie über eine Volumenlizenzversion des Skype for Business 2015-oder 2016-Clients verfügen, wird die verwendete Installationstechnologie als Windows Installer (MSI) verwendet. Ein Windows Installer-basiertes Installationspaket besteht aus mehreren MSI-Dateien. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus. Der Skype for Business 2019-Client verwendet Klick-und-Los-Installationsprogramme.
    
In den Themen in diesem Abschnitt wird beschrieben, wie Sie den Windows Installer verwenden und anpassen, um den Skype for Business-Client über die normalen Verfahren für Ihre Benutzer bereitzustellen.
  
> [!NOTE]
> Das Skype-Besprechungs-Add-in für Microsoft Office, das die Besprechungsverwaltung über den Outlook-Client für Messaging und Zusammenarbeit unterstützt, wird automatisch mit Skype for Business-Clients installiert. 
  
> [!NOTE]
> Mit den Setupprogrammen von Microsoft 365 und Office 365 werden frühere Versionen von lync nicht deinstalliert. Der Skype for Business Client wird nebeneinander mit anderen lync-Clients installiert. 
  
## <a name="installing-windows-clients"></a>Installieren von Windows-Clients

- [Anpassen der Windows-Clientinstallation in Skype for Business Server](customize-windows-client-installation.md)
    
- [Konfigurieren der Clientumgebung mit Skype for Business](configure-the-client-experience.md)
    
- [Konfigurieren der intelligenten Kontaktliste in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installieren von Geräteclients

- [Installieren und Testen von Skype for Business für Windows Phone](windows-phone.md)
    
- [Installieren und Testen von Skype for Business für IOS](ios.md)
    
    
- [Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Bereitstellen von Webdownload-Clients in Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Anpassen der Mac-Clientumgebung in Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen des Skype for Business-Clients in Microsoft 365 oder Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
