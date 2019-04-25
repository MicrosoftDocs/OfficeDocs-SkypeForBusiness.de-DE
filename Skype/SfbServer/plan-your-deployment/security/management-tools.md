---
title: Windows PowerShell und Skype für Business Server-Verwaltungstools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'In Skype für Business Server werden die Verwaltungstools von Windows PowerShell implementiert. Windows PowerShell enthält ein Command-Line-Umgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Die folgenden Skype für Business Server-Tools, die von Windows PowerShell implementiert werden:'
ms.openlocfilehash: 743823e5465d6fa18f46d0f8f38802098416d7e6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213592"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell und Skype für Business Server-Verwaltungstools
 
In Skype für Business Server werden die Verwaltungstools von Windows PowerShell implementiert. Windows PowerShell enthält ein Command-Line-Umgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Die folgenden Skype für Business Server-Tools, die von Windows PowerShell implementiert werden: 
  
- **Topologie-Generator**. Verwenden Sie Topology Builder erstellen, anpassen und veröffentlichen Ihre geplante Topologie, und prüft er Ihrer Topologie vor Beginn des Server-Installationen. Wenn Sie Skype für Business Server auf einzelnen Servern installieren, die Server Lesen der veröffentlichten Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server bereit, wie beschrieben in der Topologie. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Skype für Business Server-Verwaltungsshell**. Sie können Skype für Business Server-Verwaltungsshell für vollständigen Befehlszeilen Verwaltung Ihrer Bereitstellung verwenden.
    
- **Skype für Business Server-Systemsteuerung**. Die Skype Business Server-Systemsteuerung-Benutzeroberfläche können Sie am häufigsten ausgeführten Aufgaben in Ihrer Bereitstellung verwalten.
    
Diese Tools werden Windows PowerShell-Cmdlets zur Verwaltung Ihrer Bereitstellung, einschließlich erreicht bald 550 produktspezifische-Cmdlets verwenden. Die Sicherheit in enthaltenen Cmdlets für Skype für Business Server werden vorrangig zur Verwaltung von Authentifizierung und Benutzerrechte und-Berechtigungen verwendet. Zum Verwalten der Authentifizierung stehen vielfältige Cmdlets zur Verfügung, darunter Cmdlets für die Zertifikat- und PIN-Authentifizierung. Darüber hinaus kann eine Reihe von Cmdlets Sie das neue Feature für Role-Based Access Control (RBAC) zum Delegieren der administrativen Steuerung von Skype für Business Server verwenden. Ausführliche Informationen zu den Skype für Business Server-Cmdlets finden Sie unter [Skype für Business Server-Verwaltungsshell](../../manage/management-shell.md).
  
Das Skript Sicherheitsfeatures für Windows PowerShell sind speziell für einige der Sicherheitsprobleme scripting-bezogene ältere Technologien, einschließlich Microsoft Visual Basic Scripting Edition (VBScript) zu verhindern. Die Windows PowerShell-Sicherheitsfeatures sind für die direkte Verwendung zum Erstellen einer Umgebung, in der Benutzer auf einfache Weise können nicht, oder unwissentlich Skripts ausführen. Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert. Sie können den Status des Skripting kann diese Features sowie einer Reihe von Sicherheitsziele ändern. Dies ist nicht zu sagen, dass die Shell für Benutzer zum Ausführen von Skripts unmöglich macht. Vielmehr die Shell erschwert – standardmäßig – für Benutzer zum Ausführen von Skripts ohne zu bemerken sie sind auf diese Weise. Weitere Informationen hierzu finden Sie unter [Windows PowerShell-Skript-Sicherheit](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

