---
title: Mit "config.xml" zum Ausführen von Installationsaufgaben in Skype für Business-clients
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.'
ms.openlocfilehash: a6234424240dc0d7ebb70762598467bfcee997e2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371513"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Mit "config.xml" zum Ausführen von Installationsaufgaben in Skype für Business-clients

**Zusammenfassung:** Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.

Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:

- Angeben des Netzwerkinstallationspfads

- Auswählen der zu installierenden Produkte

- Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates

- Angeben von Installationsoptionen, z. B. Benutzername

- Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office

- Hinzufügen oder Entfernen von Sprachen in der Installation

Es wird empfohlen, dass Sie die Datei "config.xml" zum Konfigurieren von Skype für die automatische Installation von Business verwenden. 

Standardmäßig werden in der Datei Config.xml, die in der kernproduktordner gespeichert wird (beispielsweise \ _Produkt_. WW) weist das Installationsprogramm, um dieses Produkt zu installieren. Beispielsweise wird die Datei "config.xml" in den folgenden Ordner Skype für Unternehmen installiert:

- \\server\share\Skype15\Skype.ww \Config.xml

Die am häufigsten verwendeten für Skype für die Installation von Business Config.xml-Elemente sind in der folgenden Tabelle aufgeführt.

**Config.xml-Elemente**


| **Element**              | **Beschreibung**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfiguration  <br/>     | Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync (auch für Skype for Business-Clients geeignet)  <br/>                                                                                                                                                          |
| "OptionState"  <br/>       | Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden. Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, dass die freigegebene Komponenten umfasst, die Outlook beeinflussen: <br/>  ID = "LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Anzeige  <br/>           | Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende: <br/>  CompletionNotice = "Yes"                                                                                                                                                                                |
| Protokollierung  <br/>           | Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende: <br/>  Type = "Off"                                                                                                                                                                                       |
| Einstellung  <br/>           | Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:<br/>  Setting Id = " *Name*" (der Name der Windows Installer-Eigenschaft)  <br/>  Wert = " *Wert*" (der Wert der Eigenschaft zugewiesen)  <br/>                                                             |
| DistributionPoint  <br/> | Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:<br/>  Speicherort = " *Pfad*"  <br/>                                                                                                                                     |

Das folgende Beispiel zeigt eine Datei Config.xml für eine typische automatische Installation von der Skype für Business-Client. 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Ausführliche Informationen zur Verwendung der Datei "config.xml" zum Ausführen von Office-Installation und Wartung Aufgaben finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).

## <a name="to-customize-the-configxml-file"></a>So passen Sie die Datei "Config.xml" an

1. Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.

2. Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.

3. Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation. Stellen Sie sicher, dass Sie die Kommentartrennzeichen entfernen "\<!--" und "–\>". Verwenden Sie z. B. die folgende Syntax:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Speichern Sie die Datei Config.xml.


