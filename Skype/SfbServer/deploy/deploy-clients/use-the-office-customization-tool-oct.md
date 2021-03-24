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
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100451"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Verwenden des Office-Anpassungstools (OCT) in Skype for Business Server
 
**Zusammenfassung:** Verwenden des Office-Anpassungstools mit dem Skype for Business-Client.
  
Das Office Customization Tool (OCT) ist Teil des Setupprogramms und wird für viele Anpassungen empfohlen. Mithilfe des OCT passen Sie Office an und speichern Ihre Anpassungen in einer Setupanpassungs-MSP-Datei. Legen Sie die Datei am Netzwerkinstallationspfad im Ordner "Updates" ab. Bei der Installation von Office sucht Setup im Ordner Updates nach einer Setupanpassungsdatei und wendet die Anpassungen an. Der Ordner Updates kann nur zum Bereitstellen von Softwareupdates während einer Erstinstallation von Office verwendet werden.
  
Das OCT ist Teil des Setups und wird nur für Volumenlizenzversionen des Produkts verwendet. Sie führen das OCT aus, indem Sie an der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspunkts eingeben, der  `setup.exe /admin` die Office-Quelldateien enthält. Verwenden Sie beispielsweise folgenden Befehl:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Administratoren verwenden das OCT, um eine Setupanpassungs-MSP-Datei zu erstellen und können die folgenden Bereiche anpassen:
  
- **Setup** Wird verwendet, um den Standardinstallationsspeicherort auf dem Client- und Standardorganisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzerlizenzvertrag, Anzeigeebene, frühere zu entfernende Versionen von Office, benutzerdefinierte Programme, die während der Installation ausgeführt werden, Sicherheitseinstellungen und Setupeigenschaften anzugeben.
    
- **Features** Wird verwendet, um Benutzereinstellungen zu konfigurieren und die Installation von Office-Features anzupassen. Administratoren können das OCT verwenden, um die anfänglichen Standardwerte der Office-Anwendungseinstellungen für Benutzer anzugeben. Benutzer können die meisten Einstellungen nach der Installation ändern.
    
- **Zusätzliche Inhalte** Wird verwendet, um Dateien hinzuzufügen oder zu entfernen, Registrierungseinträge hinzuzufügen oder zu entfernen und Verknüpfungen zu konfigurieren.
    
- **Outlook** Wird verwendet, um das Standardmäßige Outlook-Profil eines Benutzers anzupassen, Exchange-Einstellungen anzugeben, Konten hinzuzufügen, Konten zu entfernen und Exporteinstellungen sowie Sende-\Empfangsgruppen anzugeben.
    
Weitere Informationen zum OCT finden Sie unter [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Beachten Sie, dass diese Informationen auch für spätere Versionen von Office gelten.
