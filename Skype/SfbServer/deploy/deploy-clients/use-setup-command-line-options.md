---
title: Verwenden von Setupbefehlszeilenoptionen mit Skype for Business-Clients
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
description: 'Zusammenfassung: Informationen zu Setup.exe Befehlszeilenvorgängen im Office-Setup.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837205"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Verwenden von Setupbefehlszeilenoptionen für Skype for Business-Clients
 
**Zusammenfassung:** Informationen zu Setup.exe Befehlszeilenvorgängen im Office-Setup.
  
Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Anstelle der Setupbefehlszeilenoptionen verwenden Sie in der Regel das Office-Anpassungstool und die Config.xml-Datei für die Produkteinrichtung und Featureanpassung.
  
Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.
  
**Optionen der Office Setup-Befehlszeile**

|**Option der Office Setup-Befehlszeile**|**Beschreibung**|
|:-----|:-----|
|/admin  <br/> |Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.  <br/> |
|/adminfile [Pfad]  <br/> |Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.  <br/> |
|/config [Pfad]  <br/> |Gibt die datei Config.xml, die Setup während der Installation verwendet. Verwenden Sie die Option "/config", um die Config.xml anzugeben, die Sie für Skype for Business-Installationen angepasst haben. Beispiel:  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Wird mit einer geänderten Config.xml-Datei verwendet, um das Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen. Sie können beispielsweise die Option "/modify" verwenden, um Skype for Business-Funktionen hinzuzufügen oder zu entfernen.  <br/> |
|/repair Skype  <br/> |Führt setup vom Computer des Benutzers aus, um Skype for Business zu reparieren.  <br/> |
|/uninstall Skype  <br/> |Führt Setup aus, um Skype for Business vom Computer des Benutzers zu entfernen.  <br/> |
   


