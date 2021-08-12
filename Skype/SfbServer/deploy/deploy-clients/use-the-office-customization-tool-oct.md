---
title: Verwenden des tools zum anpassen von Office (OCT) in Skype for Business Server
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
ms.openlocfilehash: 383db7b623790153114740c4d245823c38ec63c5881842c281e6c10f7834a450
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294922"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Verwenden des tools zum anpassen von Office (OCT) in Skype for Business Server
 
**Zusammenfassung:** So verwenden Sie das Office-Anpassungstool mit dem Skype for Business-Client.
  
Das Office Customization Tool (OCT) ist Teil des Setupprogramms und das empfohlene Tool für viele Anpassungen. Mithilfe des OAT passen Sie Office an und speichern Ihre Anpassungen in einer MSP-Datei für die Setupanpassung. Legen Sie die Datei am Netzwerkinstallationspfad im Ordner "Updates" ab. Wenn Sie Office installieren, sucht Setup im Ordner "Updates" nach einer Setupanpassungsdatei und wendet die Anpassungen an. Der Ordner "Updates" kann nur verwendet werden, um Softwareupdates während einer Erstinstallation von Office bereitzustellen.
  
Das OAT ist Teil des Setups und wird nur für volumenlizenzierte Versionen des Produkts verwendet. Sie führen das OAT aus, indem Sie `setup.exe /admin` in der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspunkts eingeben, der die Office Quelldateien enthält. Verwenden Sie beispielsweise folgenden Befehl:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Administratoren verwenden das OAT, um eine MSP-Datei für die Setupanpassung zu erstellen, und können die folgenden Bereiche anpassen:
  
- **Setup** Wird verwendet, um den Standardinstallationsspeicherort auf dem Client und den Standardnamen der Organisation anzugeben, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzerlizenzvertrag, Anzeigeebene, frühere Versionen von zu entfernenden Office, benutzerdefinierte Programme, die während der Installation ausgeführt werden sollen, Sicherheitseinstellungen und Setupeigenschaften.
    
- **Features** Wird verwendet, um Benutzereinstellungen zu konfigurieren und anzupassen, wie Office Features installiert werden. Administratoren können das OAT verwenden, um die anfänglichen Standardwerte für Office Anwendungseinstellungen für Benutzer anzugeben. Benutzer können die meisten Einstellungen nach der Installation ändern.
    
- **Zusätzliche Inhalte** Wird verwendet, um Dateien hinzuzufügen oder zu entfernen, Registrierungseinträge hinzuzufügen oder zu entfernen und Verknüpfungen zu konfigurieren.
    
- **Outlook** Wird verwendet, um das Standardprofil eines Benutzers Outlook anzupassen, Exchange Einstellungen anzugeben, Konten hinzuzufügen, Konten zu entfernen und Einstellungen zu exportieren und "Senden\Empfangen"-Gruppen anzugeben.
    
Informationen zum OAT finden Sie unter ["Verwenden des OAT zum Anpassen Office 2013".](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) Beachten Sie, dass diese Informationen auch für spätere Versionen von Office gelten.
