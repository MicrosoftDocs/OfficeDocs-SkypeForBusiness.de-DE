---
title: Verwenden des Office-Anpassungstools (OCT) in Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Zusammenfassung: Informationen zum Office-Anpassungstool mit der Skype für Business-Client verwenden.'
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a>Verwenden des Office-Anpassungstools (OCT) in Skype for Business Server 2015
 
**Zusammenfassung:** Verwendung von Office-Anpassungstool mit der Skype für Business-Client.
  
Office-Anpassungstool (OAT) ist Teil des Setup-Programms und ist das empfohlene Tool für viele Anpassungen. Mithilfe des OAT Anpassen von Office und Ihre Anpassungen in einer MSP-Setupanpassungsdatei zu speichern. Platzieren Sie die Datei in den Ordner Updates im Netzwerkinstallationspfad. Bei der Installation von Office wird Setup für eine Setupanpassungsdatei im Ordner Updates sucht und wendet die Anpassungen. Der Ordner "Updates" kann nur für das Bereitstellen von Softwareupdates bei einer Erstinstallation von Office verwendet werden.
  
Office-Anpassungstool ist Teil der Installation, und es wird nur für Volumenlizenzversionen des Produkts verwendet. Führen Sie Office-Anpassungstool, indem Sie eingeben `setup.exe /admin` an der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspfads, die die Office-Quelldateien. Verwenden Sie beispielsweise folgenden Befehl:
  
 `\\server\share\Office15\setup.exe /admin`
  
Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei MSP-Datei und die folgenden Bereiche anpassen können:
  
- **Setup** Anzeigen Sie Ebene, frühere Versionen von Office entfernt, benutzerdefinierte Programme, die während der ausgeführt werden verwendet, um die Standard-Installationsspeicherort angeben, auf dem Client und Standardwerte in der Name der Organisation, zusätzliche netzwerkinstallationsquellen, Produktschlüssel, Endbenutzer-Lizenzvertrag, Installation, Sicherheitseinstellungen und Setup-Eigenschaften.
    
- **Features** So konfigurieren Sie benutzereinstellungen sowie zum Anpassen der Installation von Office-Features verwendet. Administratoren können mithilfe des OAT anfängliche Standardwerte für Office-Anwendungseinstellungen für Benutzer an. Benutzer können die meisten Einstellungen nach der Installation ändern.
    
- **Weitere Inhalte** Zum Hinzufügen oder Entfernen von Dateien, hinzufügen oder Entfernen von Registrierungseinträgen und Konfigurieren von Verknüpfungen verwendet.
    
- **Outlook** Zum Anpassen von Outlook-Standardprofils des Benutzers verwendet, Exchange-Einstellungen angeben, Konten hinzufügen, Entfernen von Konten und exporteinstellungen und Senden-Empfangen-Gruppen angeben.
    
Informationen zum OAT finden Sie unter [mithilfe des OAT zum Anpassen von Office 2013](https://technet.microsoft.com/library/cc179132.aspx). Beachten Sie, dass diese Informationen auch für Office 2016 gilt.
  

