---
title: Verwaltungstools für Windows PowerShell und Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'In Skype for Business Server werden Verwaltungstools mithilfe von Windows PowerShell implementiert. Windows PowerShell bietet eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Skype for Business Server tools that are implemented using Windows PowerShell include the following:'
ms.openlocfilehash: ff8cafa49f502c14bd9d6f67de35e0109b30e44b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595327"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Verwaltungstools für Windows PowerShell und Skype for Business Server
 
In Skype for Business Server werden Verwaltungstools mithilfe von Windows PowerShell implementiert. Windows PowerShell bietet eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Skype for Business Server tools that are implemented using Windows PowerShell include the following: 
  
- **Topologie-Generator**. Sie verwenden den Topologie-Generator zum Erstellen, Anpassen und Veröffentlichen der geplanten Topologie und überprüfen Ihre Topologie, bevor Sie mit der Serverinstallation beginnen. Wenn Sie Skype for Business Server auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server wie in der Topologie angewiesen bereit. Nach der Einrichtung werden Konfigurationsinformationen automatisch auf allen Servern repliziert. Komponenten können ihrer Bereitstellung nur mithilfe des Topologie-Generators hinzugefügt werden.
    
- **Skype for Business Server-Verwaltungsshell**. Sie können Skype for Business Server Verwaltungsshell für die vollständige Befehlszeilenverwaltung Ihrer Bereitstellung verwenden.
    
- **Skype for Business Server Systemsteuerung.** Sie können die Skype for Business Server Systemsteuerungs-Benutzeroberfläche verwenden, um die gängigsten Aufgaben in Ihrer Bereitstellung zu verwalten.
    
In diesen Tools werden Windows PowerShell-Cmdlets für die Verwaltung einer Bereitstellung verwendet, darunter fast 550 produktspezifische Cmdlets. Die in Skype for Business Server enthaltenen Sicherheits-Cmdlets werden in erster Linie zum Verwalten der Authentifizierung sowie von Benutzerrechten und -berechtigungen verwendet. Zum Verwalten der Authentifizierung stehen zahlreiche Cmdlets zur Verfügung, darunter Cmdlets für die Authentifizierung unter Verwendung von Zertifikaten oder einer persönlichen Identifikationsnummer (PIN). Darüber hinaus können Sie mit einer Reihe von Cmdlets das neue RBAC-Feature (Role-Based Access Control) verwenden, um die administrative Steuerung von Skype for Business Server zu delegieren. Ausführliche Informationen zu den cmdlets Skype for Business Server finden Sie unter [Skype for Business Server Verwaltungsshell.](../../manage/management-shell.md)
  
Die skriptbezogenen Sicherheitsfeatures für Windows PowerShell wurden speziell entwickelt, um einige der mit Skripts zusammenhängenden Sicherheitsprobleme in älteren Technologien zu vermeiden, z, B. in Microsoft Visual Basic Scripting Edition (VBScript). Die Windows PowerShell-Sicherheitsfeatures sollen Ihnen helfen, eine Umgebung aufzubauen, in der es den Benutzern nicht möglich ist, auf einfache Weise oder unwissentlich Skripts auszuführen. Standardmäßig sind Windows PowerShell-Sicherheitsfeatures aktiviert. Sie können den Status dieser Features ändern, um Ihren Anforderungen in Bezug auf Skripts und Ihren individuellen Sicherheitszielen Rechnung zu tragen. Das bedeutet nicht, dass Windows PowerShell den Benutzern die Ausführung von Skripts unmöglich macht. Vielmehr erschwert sie es den Benutzern, Skripts auszuführen, ohne dass Sie sich dessen bewusst sind. Ausführliche Informationen finden Sie unter [Windows PowerShell Script Security](/previous-versions/msdn10/gg261722(v=msdn.10)).
