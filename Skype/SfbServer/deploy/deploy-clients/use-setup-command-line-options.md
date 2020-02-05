---
title: Verwenden von Setup-Befehlszeilenoptionen für Skype for Business-Clients
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Zusammenfassung: erfahren Sie mehr über die Befehlszeilenfunktionen von Setup. exe in Office Setup.'
ms.openlocfilehash: 68add6e2744e9648db49508519c14e64b4e6aeef
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768628"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Verwenden von Setup-Befehlszeilenoptionen für Skype for Business-Clients
 
**Zusammenfassung:** Informieren Sie sich über die Befehlszeilenfunktionen von Setup. exe in Office-Setup.
  
Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Anstatt die Setup-Befehlszeilenoptionen zu verwenden, verwenden Sie in der Regel das Office-Anpassungs Tool und die Datei config. XML für die Produkteinrichtung und die Anpassung von Features.
  
Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.
  
**Optionen der Office Setup-Befehlszeile**

|**Option der Office Setup-Befehlszeile**|**Beschreibung**|
|:-----|:-----|
|/admin  <br/> |Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.  <br/> |
|/adminfile [Pfad]  <br/> |Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.  <br/> |
|/config [Pfad]  <br/> |Gibt die Datei config. XML an, die von Setup während der Installation verwendet wird. Verwenden Sie die Option/config, um die Datei config. XML anzugeben, die Sie für Skype for Business-Installationen angepasst haben, beispielsweise:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Wird mit einer geänderten config.xml-Datei verwendet, um Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen. So können Sie beispielsweise die Option/MODIFY verwenden, um Skype for Business-Features hinzuzufügen oder zu entfernen.  <br/> |
|/repair Skype  <br/> |Führt das Setup vom Computer des Benutzers aus, um Skype for Business zu reparieren.  <br/> |
|/uninstall Skype  <br/> |Führt das Setup aus, um Skype for Business vom Computer des Benutzers zu entfernen.  <br/> |
   


