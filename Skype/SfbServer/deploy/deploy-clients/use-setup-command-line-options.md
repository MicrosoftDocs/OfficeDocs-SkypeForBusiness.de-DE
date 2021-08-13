---
title: Verwenden von Setup-Befehlszeilenoptionen mit Skype for Business Clients
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Zusammenfassung: Erfahren Sie mehr über Setup.exe Befehlszeilenvorgänge in Office Setup.'
ms.openlocfilehash: 1eb0a6b1e2050eb7152ff0eb65c7c08af57e307f5253a8ec8502fd3e7718aa3a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300351"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Verwenden von Setup-Befehlszeilenoptionen mit Skype for Business Clients
 
**Zusammenfassung:** Erfahren Sie mehr über Setup.exe Befehlszeilenvorgänge in Office Setup.
  
Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Anstatt die Setup-Befehlszeilenoptionen zu verwenden, verwenden Sie in der Regel das Office-Anpassungstool und die Config.xml-Datei für die Produkteinrichtung und featureanpassung.
  
Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.
  
**Optionen der Office Setup-Befehlszeile**

|**Option der Office Setup-Befehlszeile**|**Beschreibung**|
|:-----|:-----|
|/admin  <br/> |Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.  <br/> |
|/adminfile [Pfad]  <br/> |Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.  <br/> |
|/config [Pfad]  <br/> |Gibt die Config.xml Datei an, die Setup während der Installation verwendet. Verwenden Sie die Option /config, um die Config.xml Datei anzugeben, die Sie für Skype for Business Installationen angepasst haben, z. B.:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Wird mit einer geänderten Config.xml-Datei verwendet, um das Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen. Sie können z. B. die Option /modify verwenden, um Skype for Business Features hinzuzufügen oder zu entfernen.  <br/> |
|/repair Skype  <br/> |Führt setup from the user's computer to repair Skype for Business.  <br/> |
|/uninstall Skype  <br/> |Führt Setup aus, um Skype for Business vom Computer des Benutzers zu entfernen.  <br/> |
   


