---
title: Verwenden Sie das Office-Anpassungstool (OAT) in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Zusammenfassung: Informationen zum Office-Anpassungstool mit der Skype für Business-Client verwenden.'
ms.openlocfilehash: 7f7f3f15be3591b9bfac19ae4a70d887b1ad0f83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893317"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Verwenden Sie das Office-Anpassungstool (OAT) in Skype für Business Server
 
**Zusammenfassung:** Verwendung von Office-Anpassungstool mit der Skype für Business-Client.
  
Office-Anpassungstool (OAT) ist Teil des Setup-Programms und ist das empfohlene Tool für viele Anpassungen. Mithilfe des OAT Anpassen von Office und Ihre Anpassungen in einer MSP-Setupanpassungsdatei zu speichern. Platzieren Sie die Datei in den Ordner Updates im Netzwerkinstallationspfad. Bei der Installation von Office wird Setup für eine Setupanpassungsdatei im Ordner Updates sucht und wendet die Anpassungen. Der Ordner "Updates" kann nur für das Bereitstellen von Softwareupdates bei einer Erstinstallation von Office verwendet werden.
  
Office-Anpassungstool ist Teil der Installation, und es wird nur für Volumenlizenzversionen des Produkts verwendet. Führen Sie Office-Anpassungstool, indem Sie eingeben `setup.exe /admin` an der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspfads, die die Office-Quelldateien. Verwenden Sie beispielsweise folgenden Befehl:
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei MSP-Datei und die folgenden Bereiche anpassen können:
  
- **Setup** Anzeigen Sie Ebene, frühere Versionen von Office entfernt, benutzerdefinierte Programme, die während der ausgeführt werden verwendet, um die Standard-Installationsspeicherort angeben, auf dem Client und Standardwerte in der Name der Organisation, zusätzliche netzwerkinstallationsquellen, Produktschlüssel, Endbenutzer-Lizenzvertrag, Installation, Sicherheitseinstellungen und Setup-Eigenschaften.
    
- **Features** So konfigurieren Sie benutzereinstellungen sowie zum Anpassen der Installation von Office-Features verwendet. Administratoren können mithilfe des OAT anfängliche Standardwerte für Office-Anwendungseinstellungen für Benutzer an. Benutzer können die meisten Einstellungen nach der Installation ändern.
    
- **Weitere Inhalte** Zum Hinzufügen oder Entfernen von Dateien, hinzufügen oder Entfernen von Registrierungseinträgen und Konfigurieren von Verknüpfungen verwendet.
    
- **Outlook** Zum Anpassen von Outlook-Standardprofils des Benutzers verwendet, Exchange-Einstellungen angeben, Konten hinzufügen, Entfernen von Konten und exporteinstellungen und Senden-Empfangen-Gruppen angeben.
    
Informationen zum OAT finden Sie unter [mithilfe des OAT zum Anpassen von Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Beachten Sie, dass diese Informationen auch für spätere Versionen von Office gilt.
  

