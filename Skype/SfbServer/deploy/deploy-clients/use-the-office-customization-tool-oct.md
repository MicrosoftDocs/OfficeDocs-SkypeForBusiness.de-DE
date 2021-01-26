---
title: Verwenden des Office-Anpassungstools (OCT) in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Zusammenfassung: Verwenden des Office-Anpassungstools mit dem Skype for Business-Client.'
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812565"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Verwenden des Office-Anpassungstools (OCT) in Skype for Business Server
 
**Zusammenfassung:** Verwenden des Office-Anpassungstools mit dem Skype for Business-Client.
  
Das Office Customization Tool (OCT) ist Teil des Setupprogramms und wird für viele Anpassungen empfohlen. Mithilfe des OFFICE passen Sie Office an und speichern Die Anpassungen in einer Setupanpassungsdatei (MSP-Datei). Legen Sie die Datei am Netzwerkinstallationspfad im Ordner "Updates" ab. Bei der Installation von Office sucht Setup im Ordner "Updates" nach einer Setupanpassungsdatei und wendet die Anpassungen an. Der Ordner "Updates" kann nur zum Bereitstellen von Softwareupdates während einer Erstinstallation von Office verwendet werden.
  
Das OCT ist Teil des Setups und wird nur für Volumenlizenzversionen des Produkts verwendet. Sie führen das OFFICE aus, indem Sie an der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspunkts eingeben, der  `setup.exe /admin` die Office-Quelldateien enthält. Verwenden Sie beispielsweise folgenden Befehl:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Administratoren verwenden das OCT, um eine Setupanpassungsdatei (MSP) zu erstellen, und können die folgenden Bereiche anpassen:
  
- **Setup** Wird verwendet, um den Standardinstallationsspeicherort auf dem Client und den Standardorganisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Versionen von Office, während der Installation ausgeführte benutzerdefinierte Programme, Sicherheitseinstellungen und Setupeigenschaften anzugeben.
    
- **Features** Wird zum Konfigurieren von Benutzereinstellungen und zum Anpassen der Installation von Office-Features verwendet. Administratoren können mithilfe des OFFICE anfängliche Standardwerte der Einstellungen für die Office-Anwendung für Benutzer angeben. Benutzer können die meisten Einstellungen nach der Installation ändern.
    
- **Zusätzliche Inhalte** Wird verwendet, um Dateien hinzuzufügen oder zu entfernen, Registrierungseinträge hinzuzufügen oder zu entfernen und Verknüpfungen zu konfigurieren.
    
- **Outlook** Wird zum Anpassen des Standard-Outlook-Profils eines Benutzers, zum Angeben von Exchange-Einstellungen, zum Hinzufügen von Konten, zum Entfernen von Konten und zum Exportieren von Einstellungen sowie zum Angeben von Senden-Empfangen-Gruppen verwendet.
    
Weitere Informationen zum Office 2013 finden Sie unter Verwenden [des Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))-Anpassungs-OCT. Beachten Sie, dass diese Informationen auch für spätere Versionen von Office gelten.
  

