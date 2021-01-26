---
title: Windows PowerShell und Skype for Business Server-Verwaltungstools
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'In Skype for Business Server werden Verwaltungstools mithilfe von Windows PowerShell. Windows PowerShell bietet eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Skype for Business Server-Tools, die mithilfe von Windows PowerShell implementiert werden, umfassen Folgendes:'
ms.openlocfilehash: 740a5e3d7998523970e1b0adc1e72aa85d0b09c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832155"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell und Skype for Business Server-Verwaltungstools
 
In Skype for Business Server werden Verwaltungstools mithilfe von Windows PowerShell. Windows PowerShell bietet eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Skype for Business Server-Tools, die mithilfe von Windows PowerShell implementiert werden, umfassen Folgendes: 
  
- **Topologie-Generator**. Sie verwenden den Topologie-Generator, um die geplante Topologie zu erstellen, anzupassen und zu veröffentlichen, und überprüft Ihre Topologie, bevor Sie mit serverinstallationen beginnen. Wenn Sie Skype for Business Server auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsprozesses, und das Installationsprogramm stellt den Server wie in der Topologie bereitgestellt. Nach dem Setup werden die Konfigurationsinformationen automatisch auf alle Server repliziert. Komponenten können ihrer Bereitstellung nur mithilfe des Topologie-Generators hinzugefügt werden.
    
- **Skype for Business Server Management Shell**. Sie können skype for Business Server Management Shell für die vollständige Befehlszeilenverwaltung Ihrer Bereitstellung verwenden.
    
- **Skype for Business Server Systemsteuerung**. Sie können die Benutzeroberfläche der Skype for Business Server-Systemsteuerung verwenden, um die gängigsten Aufgaben in Ihrer Bereitstellung zu verwalten.
    
In diesen Tools werden Windows PowerShell-Cmdlets für die Verwaltung einer Bereitstellung verwendet, darunter fast 550 produktspezifische Cmdlets. Die in Skype for Business Server enthaltenen Sicherheits-Cmdlets werden in erster Linie zum Verwalten der Authentifizierung sowie von Benutzerrechten und -berechtigungen verwendet. Zum Verwalten der Authentifizierung stehen zahlreiche Cmdlets zur Verfügung, darunter Cmdlets für die Authentifizierung unter Verwendung von Zertifikaten oder einer persönlichen Identifikationsnummer (PIN). Darüber hinaus können Sie mit einer Reihe von Cmdlets die neue funktion Role-Based Access Control (RBAC) verwenden, um die administrative Steuerung von Skype for Business Server zu delegieren. Details zu den Skype for Business Server-Cmdlets finden Sie unter [Skype for Business Server Management Shell](../../manage/management-shell.md).
  
Die skriptbezogenen Sicherheitsfeatures für Windows PowerShell wurden speziell entwickelt, um einige der mit Skripts zusammenhängenden Sicherheitsprobleme in älteren Technologien zu vermeiden, z, B. in Microsoft Visual Basic Scripting Edition (VBScript). Die Windows PowerShell-Sicherheitsfeatures sollen Ihnen helfen, eine Umgebung aufzubauen, in der es den Benutzern nicht möglich ist, auf einfache Weise oder unwissentlich Skripts auszuführen. Standardmäßig sind Windows PowerShell-Sicherheitsfeatures aktiviert. Sie können den Status dieser Features ändern, um Ihren Anforderungen in Bezug auf Skripts und Ihren individuellen Sicherheitszielen Rechnung zu tragen. Das bedeutet nicht, dass Windows PowerShell den Benutzern die Ausführung von Skripts unmöglich macht. Vielmehr erschwert sie es den Benutzern, Skripts auszuführen, ohne dass Sie sich dessen bewusst sind. Weitere Informationen finden Sie unter [Windows PowerShell Script Security](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

