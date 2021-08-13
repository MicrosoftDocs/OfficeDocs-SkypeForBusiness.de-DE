---
title: Verwenden von Config.xml zum Ausführen von Installationsaufgaben in Skype for Business Clients
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
description: 'Zusammenfassung: Verwenden der Config.xml datei zum Angeben zusätzlicher Installationsanweisungen.'
ms.openlocfilehash: b7c04a9c08f6a5dd51c21a189ce3a07d81a589cf694e5020a75cf6f646bd1cef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332047"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Verwenden von Config.xml zum Ausführen von Installationsaufgaben in Skype for Business Clients

**Zusammenfassung:** So verwenden Sie die Config.xml-Datei, um zusätzliche Installationsanweisungen anzugeben.

Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:

- Angeben des Netzwerkinstallationspfads

- Auswählen der zu installierenden Produkte

- Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates

- Angeben von Installationsoptionen, z. B. Benutzername

- Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office

- Hinzufügen oder Entfernen von Sprachen in der Installation

Es wird empfohlen, die Config.xml-Datei zu verwenden, um Skype for Business automatische Installation zu konfigurieren. 

Standardmäßig wird die Config.xml Datei, die im Hauptproduktordner gespeichert ist (z. B. \ _Produkt_. WW) leitet Setup an, dieses Produkt zu installieren. Beispielsweise wird die Config.xml-Datei im folgenden Ordner Skype for Business installiert:

- \\server\share\Skype15\Skype. WW-\Config.xml

Die Config.xml Elemente, die am häufigsten für Skype for Business Installation verwendet werden, sind in der folgenden Tabelle aufgeführt.

**Config.xml-Elemente**


| **Element**              | **Beschreibung**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfiguration  <br/>     | Element der obersten Ebene (erforderlich). Enthält das Product-Attribut, z. B.: Product=Lync (Dies funktioniert für Skype for Business Clients)  <br/>                                                                                                                                                          |
| Optionstate  <br/>       | Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden. Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, die freigegebene Komponenten enthält, die Outlook beeinträchtigen: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Anzeigen  <br/>           | Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Protokollierung  <br/>           | Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende: <br/>  Type ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:<br/>  Setting Id=" *name*" (der Name der Windows Installer-Eigenschaft)  <br/>  Value=" *value*" (der Wert, der der Eigenschaft zugewiesen werden soll)  <br/>                                                             |
| DistributionPoint  <br/> | Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:<br/>  Location=" *path*"  <br/>                                                                                                                                     |

Das folgende Beispiel zeigt eine Config.xml-Datei für eine typische automatische Installation des Skype for Business-Clients. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Ausführliche Informationen zur Verwendung der Config.xml-Datei zum Ausführen Office Installations- und Wartungsaufgaben finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) .

## <a name="to-customize-the-configxml-file"></a>So passen Sie die Datei "Config.xml" an

1. Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.

2. Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.

3. Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation. Stellen Sie sicher, dass Sie die Kommentartrennzeichen " " \<!--" and "--\> entfernen. Verwenden Sie z. B. die folgende Syntax:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Speichern Sie die Datei Config.xml.