---
title: Verwenden des Office-Anpassungstools (OAT) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Zusammenfassung: Verwenden des Office-Anpassungstools mit dem Skype for Business-Client'
ms.openlocfilehash: d5b9e5363f56842675831c4b3c0fe3582fb6d02a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768448"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Verwenden des Office-Anpassungstools (OAT) in Skype for Business Server
 
**Zusammenfassung:** Verwenden des Office-Anpassungstools mit dem Skype for Business-Client
  
Das Office-Anpassungstool (OAT) ist Teil des Setup-Programms und wird als Tool für viele Anpassungen empfohlen. Wenn Sie das OAT verwenden, passen Sie Office an, und speichern Sie Ihre Anpassungen in einer MSP-Datei für die Setup Anpassung. Sie fügen die Datei im Ordner Updates auf dem Netzwerkinstallationspfad ein. Wenn Sie Office installieren, sucht Setup im Ordner Updates nach einer Setupanpassungsdatei und wendet die Anpassungen an. Der Ordner Updates kann nur zum Bereitstellen von Softwareupdates während einer anfänglichen Installation von Office verwendet werden.
  
Das OAT ist Teil des Setups und wird nur für volumenlizenzierte Versionen des Produkts verwendet. Sie führen das OAT durch Eingabe `setup.exe /admin` über die Befehlszeile aus dem Stammverzeichnis des Netzwerkinstallationspfads, der die Office-Quelldateien enthält. Verwenden Sie beispielsweise folgenden Befehl:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Administratoren verwenden das OAT zum Erstellen einer Setup Customization. msp-Datei und können die folgenden Bereiche anpassen:
  
- **Einrichtung** Dient zum Angeben des Standard Installationsspeicherorts auf dem Client und dem Standard Organisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Versionen von Office, benutzerdefinierte Programme, die während der Installation, Sicherheitseinstellungen und Setup Eigenschaften ausgeführt werden sollen.
    
- **Funktionen** Wird verwendet, um Benutzereinstellungen zu konfigurieren und die Installation von Office-Features anzupassen. Administratoren können das OAT verwenden, um anfängliche Standardwerte für die Office-Anwendungseinstellungen für Benutzer festzulegen. Benutzer können die meisten Einstellungen nach der Installation ändern.
    
- **Zusätzlicher Inhalt** Wird zum Hinzufügen oder Entfernen von Dateien, hinzufügen oder Entfernen von Registrierungseinträgen und Konfigurieren von Tastenkombinationen verwendet.
    
- **Outlook** Wird verwendet, um das standardmäßige Outlook-Profil eines Benutzers anzupassen, Exchange-Einstellungen anzugeben, Konten hinzuzufügen, Konten zu entfernen und Einstellungen zu exportieren sowie Übermittlungs-Gruppen anzugeben.
    
Informationen zum OAT finden Sie unter [Verwenden des OAT zum Anpassen von Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Beachten Sie, dass diese Informationen auch für spätere Versionen von Office gelten.
  

