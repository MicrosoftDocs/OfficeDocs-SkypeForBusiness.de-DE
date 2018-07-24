---
title: Verwenden von Setup-Befehlszeilenoptionen mit Skype für Business-clients
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Zusammenfassung: Erfahren Sie mehr über Setup.exe Befehlszeile Vorgänge während des Setups von Office.'
ms.openlocfilehash: 13005f96b353b8648ed676ef68af54b76a99e48c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974452"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Verwenden von Setup-Befehlszeilenoptionen mit Skype für Business-clients
 
**Zusammenfassung:** Informationen Sie zu Setup.exe Befehlszeile Vorgänge während des Setups von Office.
  
Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Verwenden Sie die Setup-Befehlszeilenoptionen, sondern in der Regel verwenden Office-Anpassungstool und der Datei Config.xml für Produkt-Setup und Anpassung Sie.
  
Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.
  
**Optionen der Office Setup-Befehlszeile**

|**Option der Office Setup-Befehlszeile**|**Beschreibung**|
|:-----|:-----|
|/admin  <br/> |Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.  <br/> |
|/adminfile [Pfad]  <br/> |Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.  <br/> |
|/config [Pfad]  <br/> |Gibt die Datei Config.xml, die Setup während der Installation verwendet. Verwenden Sie die Option/config auf die Datei Config.xml angeben, die Sie für Skype für Business-Installationen, beispielsweise angepasst:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Wird mit einer geänderten config.xml-Datei verwendet, um Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen. Angenommen, Sie können die / modify Option zum Hinzufügen oder Entfernen von Skype für Business-Features.  <br/> |
|/repair Skype  <br/> |Führt Setup aus dem Computer des Benutzers, Skype für Unternehmen zu reparieren.  <br/> |
|/uninstall Skype  <br/> |Führt Setup aus, um Skype für Unternehmen aus dem Computer des Benutzers zu entfernen.  <br/> |
   


