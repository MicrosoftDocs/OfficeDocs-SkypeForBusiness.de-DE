---
title: Verwenden Config.xml zum Ausführen von Installationsaufgaben in Skype for Business-Clients
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Informationen zum Verwenden der Config.xml zum Angeben zusätzlicher Installationsanweisungen.'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825185"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Verwenden Config.xml zum Ausführen von Installationsaufgaben in Skype for Business-Clients

**Zusammenfassung:** So verwenden Sie die Config.xml, um zusätzliche Installationsanweisungen anzugeben.

Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:

- Angeben des Netzwerkinstallationspfads

- Auswählen der zu installierenden Produkte

- Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates

- Angeben von Installationsoptionen, z. B. Benutzername

- Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office

- Hinzufügen oder Entfernen von Sprachen in der Installation

Es wird empfohlen, dass Sie die Config.xml verwenden, um die automatische Installation von Skype for Business zu konfigurieren. 

Standardmäßig wird die Config.xml, die im Hauptproduktordner gespeichert ist (z. B. _\product_). WW) leitet Setup an, dieses Produkt zu installieren. Die Datei "Config.xml" im folgenden Ordner installiert beispielsweise Skype for Business:

- \\server\share\Skype15\Skype.WW \Config.xml

Die Config.xml elemente, die am häufigsten für die Skype for Business-Installation verwendet werden, sind in der folgenden Tabelle aufgeführt.

**Config.xml-Elemente**


| **Element**              | **Beschreibung**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfiguration  <br/>     | Element der obersten Ebene (erforderlich). Enthält das Product-Attribut, z. B.: Product=Lync (dies funktioniert für Skype for Business-Clients)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden. Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, die freigegebene Komponenten enthält, die Outlook stören: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Anzeigen  <br/>           | Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Protokollierung  <br/>           | Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende: <br/>  Type ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:<br/>  Setting Id=" *name*" (der Name der Windows Installer-Eigenschaft)  <br/>  Value=" *value*" (der Wert, der der Eigenschaft zugewiesen werden soll)  <br/>                                                             |
| DistributionPoint  <br/> | Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:<br/>  Location=" *path*"  <br/>                                                                                                                                     |

Das folgende Beispiel zeigt eine Config.xml für eine typische automatische Installation des Skype for Business-Clients. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Ausführliche Informationen zur Verwendung der Config.xml zum Ausführen von Installations- und Wartungsaufgaben für Office finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) .

## <a name="to-customize-the-configxml-file"></a>So passen Sie die Datei "Config.xml" an

1. Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.

2. Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.

3. Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation. Stellen Sie sicher, dass Sie die Kommentartrennzeichen " " \<!--" and "--\> entfernen. Verwenden Sie z. B. die folgende Syntax:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Speichern Sie die Datei Config.xml.


