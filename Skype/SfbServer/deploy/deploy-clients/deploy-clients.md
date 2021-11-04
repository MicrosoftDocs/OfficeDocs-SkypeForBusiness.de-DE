---
title: Bereitstellen von Clients für Skype for Business Server
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über die Installationsmethoden für Unternehmensclients für Skype for Business.'
ms.openlocfilehash: 60da950c4ef330f704d45944a900e579478c558c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778925"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Bereitstellen von Clients für Skype for Business Server
 
**Zusammenfassung:** Übersicht über die Installationsmethoden von Unternehmensclients für Skype for Business.
  
Wie Sie Skype for Business für Ihre Benutzer bereitstellen, hängt davon ab, ob Sie Skype for Business als Teil eines Microsoft 365 oder Office 365 Plans erworben oder eine volumenlizenzierte Version von Skype for Business erworben haben. 
  
- **Microsoft 365 oder Office 365** Wenn Sie über einen Microsoft 365 oder Office 365 Plan verfügen, der Skype for Business enthält, heißt die verwendete Installationstechnologie Klick-und-Los. Sie können Ihren Benutzern die Installation von Skype for Business für sich selbst über die Microsoft 365 Admin Center ermöglichen. Sie können auch Skype for Business für Ihre Benutzer bereitstellen, indem Sie die Software in Ihr lokales Netzwerk herunterladen und dann Ihre vorhandenen Softwarebereitstellungstools verwenden, z. B. mit Microsoft Endpoint Configuration Manager. Installationsinformationen zu Skype for Business, die in Microsoft 365 und Office 365 enthalten sind, finden Sie unter [Deploy the Skype for Business client in Microsoft 365 or Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)
    
- **Volumenlizenziert** Wenn Sie über eine Volumenlizenzversion des Skype for Business 2015- oder 2016-Clients verfügen, ist die verwendete Installationstechnologie Windows Installer (MSI). Ein Windows installationsbasierte Installationspaket besteht aus mehreren MSI-Dateien. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus. Der Skype for Business 2019-Client verwendet Klick-und-Los-Installationsprogramme.
    
In den Themen in diesem Abschnitt wird beschrieben, wie Sie den Windows Installer verwenden und anpassen, um den Skype for Business-Client für Ihre Benutzer über Ihre normalen Verfahren bereitzustellen.
  
> [!NOTE]
> Das Skype-Besprechung-Add-In für Microsoft Office, das die Besprechungsverwaltung innerhalb des Outlook Messaging- und Zusammenarbeitsclients unterstützt, wird automatisch mit Skype for Business Clients installiert. 
  
> [!NOTE]
> Die Setupprogramme Microsoft 365 und Office 365 deinstallieren keine früheren Versionen von Lync. Der Skype for Business-Client wird parallel zu anderen Lync-Clients installiert. 
  
## <a name="installing-windows-clients"></a>Installieren von Windows Clients

- [Anpassen Windows Clientinstallation in Skype for Business Server](customize-windows-client-installation.md)
    
- [Konfigurieren der Clientumgebung mit Skype for Business](configure-the-client-experience.md)
    
- [Konfigurieren einer intelligenten Kontaktliste in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installieren von Geräteclients

- [Installieren und Testen Skype for Business für Windows Phone](windows-phone.md)
    
- [Installieren und Testen von Skype for Business für iOS](ios.md)
    
    
- [Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Bereitstellen von herunterladbaren Webclients in Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Anpassen der Mac-Clientumgebung in Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Weitere Informationen

[Bereitstellen des Skype for Business-Clients in Microsoft 365 oder Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
